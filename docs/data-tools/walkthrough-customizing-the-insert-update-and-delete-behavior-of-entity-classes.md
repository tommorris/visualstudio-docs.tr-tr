---
title: 'İzlenecek yol: Ekle özelleştirme, güncelleştirme ve Varlık davranışını silme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 03ff1146-706e-4780-91cb-56a83df63eea
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 38dc02e4c1cd7a0d6bead05a585b878f242209ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes"></a>İzlenecek yol: Ekle özelleştirme, güncelleştirme ve Varlık davranışını silme

[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md) oluşturmak ve düzenlemek için bir görsel tasarım yüzeyi sağlar [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] bir veritabanındaki nesnelerde temel sınıfları (varlık sınıfları). Kullanarak [LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index), access SQL veritabanları için LINQ teknolojisi kullanabilirsiniz. Daha fazla bilgi için bkz: [LINQ (dil ile tümleşik sorgu)](/dotnet/csharp/linq/).  
  
Varsayılan olarak, güncelleştirmeleri gerçekleştirmek için mantığı tarafından sağlanan [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] çalışma zamanı. Çalışma zamanı (sütun tanımları ve birincil anahtar bilgilerini) tablo şemasını temel alan INSERT, Update ve Delete deyimleri varsayılan oluşturur. Varsayılan davranışı kullanmak istiyor musunuz, güncelleştirme davranışını yapılandırmak ve gerekli ekler, güncelleştirmeleri gerçekleştirmek için özel saklı yordamları belirlemek ve siler veritabanındaki verilerle çalışmak için gerekli. Varlık sınıflarınızı görünümlerine eşlediğinizde varsayılan davranışı, örneğin, değil oluşturulduğunda de bunu yapabilirsiniz. Ayrıca, veritabanı saklı yordamları aracılığıyla tablo erişim gerektirdiğinde varsayılan güncelleştirme davranışı geçersiz kılabilirsiniz. Daha fazla bilgi için bkz: [özelleştirme işlemleri tarafından kullanarak saklı yordamlar](/dotnet/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures).  
  
> [!NOTE]
> Bu kılavuzda kullanılabilirliğini gerektirir **InsertCustomer**, **UpdateCustomer**, ve **DeleteCustomer** saklı yordamlar Northwind veritabanı için.  
  
Bu kılavuz, varsayılan LINQ saklı yordamları kullanarak verileri bir veritabanına kaydetme SQL çalışma zamanı davranışını geçersiz kılmak için izlemeniz gereken adımları sağlar.  
  
Bu gözden geçirme sırasında aşağıdaki görevleri gerçekleştirmek öğreneceksiniz:  
  
-   Yeni bir Windows Forms uygulaması oluşturma ve ekleme bir [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] ona dosya.  
  
-   Northwind müşterileri tabloya eşlenen bir varlık sınıfı oluşturun.  
  
-   LINQ-SQL müşteri sınıf başvuruda bulunan bir nesnenin veri kaynağı oluşturun.  
  
-   İçeren bir Windows formu oluşturma bir <xref:System.Windows.Forms.DataGridView> müşteri sınıfa bağlı.  
  
-   Uygulama işlevselliği form için kaydedin.  
  
-   Oluşturma <xref:System.Data.Linq.DataContext> ekleyerek yöntemleri saklı yordamlar için [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
-   Saklı yordamlar ekler, güncelleştirmeleri ve silme işlemini gerçekleştirmek için kullanılacak müşteri sınıf yapılandırın.  
  
## <a name="prerequisites"></a>Önkoşullar

Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.  
  
1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.  
  
2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:  

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .  

       Sorgu Düzenleyicisi penceresini açar.  

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.  

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.  

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.  
  
## <a name="creating-an-application-and-adding-linq-to-sql-classes"></a>Uygulama oluşturma ve LINQ SQL sınıflara ekleme

İle çalışacaksınız çünkü [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] sınıflar ve bir Windows formunda veri görüntüleme yeni bir Windows Forms uygulaması oluşturma ve bir LINQ SQL sınıfları dosyasına ekleyin.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-new-windows-forms-application-project-that-contains-linq-to-sql-classes"></a>SQL'e sınıflarını LINQ içeren yeni bir Windows Forms uygulaması projesi oluşturmak için
  
1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **UpdatingWithSProcsWalkthrough**ve ardından **Tamam**. 
  
     **UpdatingWithSProcsWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
4.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
5.  Tıklatın **LINQ'ten SQL'e sınıflarını** şablonu ve türü **Northwind.dbml** içinde **adı** kutusu.  
  
6.  **Ekle**'yi tıklatın.  
  
     Boş bir LINQ to SQL sınıfları dosya (Northwind.dbml) projeye eklenir ve [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] açar.  
  
## <a name="creating-the-customer-entity-class-and-object-data-source"></a>Müşteri varlık sınıfı ve nesne veri kaynağı oluşturma

Oluşturma [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] veritabanı tablolarında tablolardan sürükleyerek eşlenmiş sınıfları **Sunucu Gezgini**/**Database Explorer** üzerine [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. LINQ veritabanındaki tabloların Eşle SQL varlık sınıflarına sonucudur. Varlık sınıfı oluşturduktan sonra nesne veri kaynakları gibi ortak özelliklere sahip diğer sınıflar olarak kullanılabilir.  
  
### <a name="to-create-a-customer-entity-class-and-configure-a-data-source-with-it"></a>Bir müşteri varlık sınıfı oluşturmak ve bir veri kaynağı ile yapılandırmak için
  
1.  İçinde **Sunucu Gezgini**/**Database Explorer**, Northwind örnek veritabanı SQL Server sürümünde Müşteri tablosunu bulun. 
  
2.  Sürükleme **müşteriler** düğümden **Sunucu Gezgini**/**Database Explorer** üzerine [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] yüzeyini.  
  
     Adlı bir varlık sınıfı **müşteri** oluşturulur. Müşteriler tablosundaki sütunlara karşılık gelen özellikler vardır. Varlık sınıfı adlı **müşteri** (değil **müşteriler**) çünkü tek bir müşteri Müşteriler tablosundan temsil eder.  
  
    > [!NOTE]
    >  Yeniden adlandırma bu davranışı adlı *çoğullaştırma*. Bunu açmak veya kapatmak açılabilir [Seçenekler iletişim kutusu](../ide/reference/options-dialog-box-visual-studio.md). Daha fazla bilgi için bkz: [nasıl yapılır: çoğullaştırma üzerinde ve devre dışı bırak (O/R Tasarımcısı)](../data-tools/how-to-turn-pluralization-on-and-off-o-r-designer.md).  
  
3.  Üzerinde **yapı** menüsünde tıklatın **yapı UpdatingwithSProcsWalkthrough** Projeyi derlemek için.  
  
4.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.  
  
5.  İçinde **veri kaynakları** penceresinde tıklatın **yeni veri kaynağı Ekle**.  
  
6.  Tıklatın **nesne** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.  
  
7.  Genişletme **UpdatingwithSProcsWalkthrough** düğümü bulun ve seçin **müşteri** sınıfı.  
  
    > [!NOTE]
    >  Varsa **müşteri** sınıfı kullanılabilir değil, Sihirbazı iptal, projeyi oluşturun ve sihirbazı yeniden çalıştırın.  
8.  Tıklatın **son** veri kaynağı oluşturun ve eklemek için **müşteri** varlık sınıfı için **veri kaynakları** penceresi.  
  
## <a name="creating-a-datagridview-to-display-the-customer-data-on-a-windows-form"></a>Bir Windows formunda müşteri verilerini görüntülemek için bir DataGridView oluşturma

Varlık sınıflarına sürükleyerek ilişkili denetimleri oluşturma [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] veri kaynağı öğelerinden **veri kaynakları** Windows forma penceresi.  
  
### <a name="to-add-controls-that-are-bound-to-the-entity-classes"></a>Varlık sınıfları ilişkili denetimleri eklemek için
  
1.  Form1 Tasarım görünümünde açın.  
  
2.  Gelen **veri kaynakları** penceresinde, sürükle **müşteri** Form1 düğüme.  
  
    > [!NOTE]
    > Görüntülemek için **veri kaynakları** penceresinde tıklatın **veri kaynaklarını Göster** üzerinde **veri** menüsü.  
  
3.  Form1 kod düzenleyicisinde açın.  
  
4.  Form, formun, herhangi bir belirli yöntemi dışında ancak Form1 sınıfı içinde genel aşağıdaki kodu ekleyin:  
  
    ```vb  
    Private NorthwindDataContext1 As New NorthwindDataContext  
    ```  
  
    ```csharp  
    private NorthwindDataContext northwindDataContext1  
        = new NorthwindDataContext();    
    ```  
  
5.  İçin bir olay işleyicisi oluşturun `Form_Load` olay işleyicisine ve aşağıdaki kodu ekleyin:  
  
    ```vb  
    CustomerBindingSource.DataSource = NorthwindDataContext1.Customers  
    ```  
  
    ```csharp  
    customerBindingSource.DataSource  
        = northwindDataContext1.Customers;    
    ```  
  
## <a name="implementing-save-functionality"></a>İşlevlerini uygulama

Varsayılan olarak Kaydet düğmesi etkin değildir ve kaydetme işlevinin uygulanmadı. Ayrıca, kodu verilere bağlı denetimler nesne veri kaynakları için oluşturulduğunda değiştirilen verileri veritabanına kaydetmek için otomatik olarak eklenmez. Bu bölümde, kaydetme etkinleştirmek açıklanmaktadır düğmesine tıklayın ve işlevselliği için Kaydet uygulamak [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] nesneleri.  
  
### <a name="to-implement-save-functionality"></a>Kaydetme işlevinin uygulamak için
  
1.  Form1 Tasarım görünümünde açın.  
  
2.  Kaydet'i seçin düğmesini **CustomerBindingNavigator** (disket simgesiyle düğme).  
  
3.  İçinde **özellikleri** penceresindeki ayarlayın **etkin** özelliğine **doğru**.  
  
4.  Kaydet düğmesi olay işleyicisi oluşturun ve kod düzenleyicisine geçiş yapmak için çift tıklatın.  
  
5.  Kaydet aşağıdaki kodu ekleyin düğmesi olay işleyicisi:  
  
    ```vb  
    NorthwindDataContext1.SubmitChanges()  
    ```  
  
    ```csharp  
    northwindDataContext1.SubmitChanges();  
    ```  
  
## <a name="overriding-the-default-behavior-for-performing-updates-inserts-updates-and-deletes"></a>Güncelleştirmeler (ekler, güncelleştirmeleri ve silme) gerçekleştirmek için varsayılan davranışı geçersiz kılma
  
### <a name="to-override-the-default-update-behavior"></a>Varsayılan güncelleştirme davranışını geçersiz kılmak için
  
1.  LINQ-SQL dosyasında açmak [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. (Çift **Northwind.dbml** dosyasını **Çözüm Gezgini**.)  
  
2.  İçinde **Sunucu Gezgini**/**Database Explorer**, Northwind veritabanları'nı genişletin **saklı yordamlar** düğümü ve bulun  **InsertCustomers**, **UpdateCustomers**, ve **DeleteCustomers** saklı yordamlar.  
  
3.  Tüm üç saklı yordamlar üzerine sürükleyin [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
     Saklı yordamlar yöntemleri bölmesine eklenir <xref:System.Data.Linq.DataContext> yöntemleri. Daha fazla bilgi için bkz: [DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md).  
  
4.  Seçin **müşteri** varlık sınıfında [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
5.  İçinde **özellikleri** penceresinde, seçin **Ekle** özelliği.  
  
6.  Yanındaki üç nokta işaretine (...) **kullanım çalışma zamanı** açmak için **yapılandırma davranışı** iletişim kutusu.  
  
7.  Seçin **özelleştirme**.  
  
8.  Seçin **InsertCustomers** yönteminde **Özelleştir** listesi.  
  
9. Tıklatın **Uygula** seçili sınıfı ve davranışı yapılandırmayı kaydetmek için.  
  
    > [!NOTE]
    >  Tıklattığınız sürece her sınıf/davranışı birleşimi için davranış yapılandırmaya devam edebilirsiniz **Uygula** her değişikliği yaptıktan sonra. Tıklatmadan önce sınıf veya davranışı değiştirirseniz **Uygula**, değişiklikleri uygulamak için bir fırsat görünür sağlayan bir uyarı iletişim kutusu.  
  
10. Seçin **güncelleştirme** içinde **davranışı** listesi.  
  
11. Seçin **özelleştirme**.  
  
12. Seçin **UpdateCustomers** yönteminde **Özelleştir** listesi.  
  
     Listesini inceleyin **yöntem bağımsız değişkenleri** ve **sınıf özelliklerini** ve iki olduğuna dikkat edin **yöntem bağımsız değişkenleri** ve iki **sınıf özelliklerini**tablosundaki bazı sütunları için. Bu değişiklikleri izlemek ve eşzamanlılık ihlali denetleyin deyimleri oluşturmak kolaylaştırır.  
  
13. Harita **Original_CustomerID** yöntem bağımsız değişkeni **CustomerID (özgün)** sınıf özelliği.  
  
    > [!NOTE]
    >  Adları eşleştiğinde varsayılan olarak, yöntem bağımsız değişkenleri sınıfın özelliklerine eşlenir. Özellik adlarının değişmesi ve artık tablo ve varlık sınıfı arasında eşleşmeyen, O/R Tasarımcısı doğru Eşleme belirleyemiyorsa eşlemek için eşdeğer sınıfı özelliği seçin gerekebilir. Ayrıca, yöntem bağımsız değişkenleri eşlemek için geçerli sınıf özelliklerini yoksa ayarlayabileceğiniz **sınıf özelliklerini** değeri **(hiçbiri)**.  
  
14. Tıklatın **Uygula** seçili sınıfı ve davranışı yapılandırmayı kaydetmek için.  
  
15. Seçin **silmek** içinde **davranışı** listesi.  
  
16. Seçin **özelleştirme**.  
  
17. Seçin **DeleteCustomers** yönteminde **Özelleştir** listesi.  
  
18. Harita **Original_CustomerID** yöntem bağımsız değişkeni **CustomerID (özgün)** sınıf özelliği.  
  
19. **Tamam**'ı tıklatın.  
  
> [!NOTE]
> Bu belirli yönlendirme için bir sorun olmasa da, belirtmeye değer olan [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] eklemeleri sırasında veritabanı tarafından üretilen değerler kimlik (otomatik artım), rowguıdcol (veritabanında oluşturulan GUID) ve zaman damgası sütunları için otomatik olarak işleme ve güncelleştirmeler. Diğer sütun türleri veritabanında oluşturulan değerlerde beklenmedik bir null değer neden olur. Veritabanında oluşturulan değer döndürmek için el ile ayarlamanız gerekir <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> için `true` ve <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> aşağıdakilerden birine: <xref:System.Data.Linq.Mapping.AutoSync>, <xref:System.Data.Linq.Mapping.AutoSync>, veya <xref:System.Data.Linq.Mapping.AutoSync>.  
  
## <a name="testing-the-application"></a>Uygulamayı test etme

Yeniden doğrulamak için uygulamayı çalıştırma **UpdateCustomers** saklı yordam doğru veritabanında müşteri kaydı güncelleştirir.

### <a name="to-test-the-application"></a>Uygulamayı test etmek için

1.  F5 tuşuna basın.  
  
2.  Güncelleştirme davranışı test etmek için kılavuz kaydında değiştirin.  
  
3.  INSERT davranışı test etmek için yeni bir kaydı ekleyin.  
  
4.  Değişiklikleri veritabanına kaydetmek için Kaydet düğmesine tıklayın.  
  
5.  Formu kapatın.  
  
6.  F5 tuşuna basın ve güncelleştirilmiş kayıt ve yeni eklenen kayıt kalıcı olduğunu doğrulayın.  
  
7.  İçinde oluşturulan yeni kayıt silme adım silme davranışı test etmek için 3.  
  
8.  Kaydet'i tıklatın değişiklikleri gönderir ve Silinen kaydı veritabanından kaldırmak için düğmesi  
  
9. Formu kapatın.  
  
10. F5 tuşuna basın ve Silinen kaydı veritabanından kaldırıldığını doğrulayın.  
  
    > [!NOTE]
    > Uygulamanızı değeri bağlı olarak SQL Server Express Edition kullanıp kullanmadığını **çıktı dizinine Kopyala** özelliği veritabanı dosyasının değişiklikleri 10 adımda F5 tuşuna bastığınızda görüntülenmeyebilir.

## <a name="next-steps"></a>Sonraki adımlar

Uygulama gereksinimlerinize bağlı olarak, oluşturduğunuz sonra gerçekleştirmek istediğinizi düşünelim birkaç adım vardır [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] sınıflar. Bu uygulamaya yapabilir bazı geliştirmeler şunları içerir:

- Eşzamanlılık güncelleştirmeleri sırasında denetimi uygular. Bilgi için bkz: [iyimser eşzamanlılık: genel bakış](/dotnet/framework/data/adonet/sql/linq/optimistic-concurrency-overview).

- LINQ sorgularını verilere filtre uygulamak için ekleyin. Bilgi için bkz: [LINQ sorgularını (C#) giriş](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).

## <a name="see-also"></a>Ayrıca bkz.

[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)  
[DataContext metotları](../data-tools/datacontext-methods-o-r-designer.md)  
[Nasıl yapılır: güncelleştirme, ekleme ve silme gerçekleştirmek için saklı yordamlar atayın](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)  
[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)  
[LINQ to SQL sorguları](/dotnet/framework/data/adonet/sql/linq/linq-to-sql-queries)