---
title: "Arama tabloları veri bağlama - Windows Forms denetimleri kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding, user controls
- LookupBindingPropertiesAttribute class, examples
- user controls [Visual Basic], creating
ms.assetid: c48b4d75-ccfc-4950-8b14-ff8adbfe4208
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c3ecb38b4f208eac3a49cc2f0e21fb98ef81ea68
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="create-a-windows-forms-user-control-that-supports-lookup-data-binding"></a>Arama veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma
Windows Forms'ta veri görüntüleme, var olan denetimleri seçebilirsiniz **araç**, veya uygulamanızın standart denetimlerinde kullanılamaz işlevsellik gerektiriyorsa özel denetimler yazabilirsiniz. Bu kılavuzda uygulayan bir denetimin nasıl oluşturulacağını gösterir <xref:System.ComponentModel.LookupBindingPropertiesAttribute>. Denetimleri uygulayan <xref:System.ComponentModel.LookupBindingPropertiesAttribute> veriye bağlı üç özellikler içerebilir. Bu tür denetimler benzer bir <xref:System.Windows.Forms.ComboBox>.  
  
 Denetim yazma hakkında daha fazla bilgi için bkz: [tasarım zamanında Windows Forms denetimleri geliştirme](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time).  
  
 Veri bağlama senaryolarda kullanım için denetimleri yazarken aşağıdaki veri bağlama özniteliklerden birini yapması gerekir:  
  
|Veri bağlama öznitelik kullanımı|  
|-----------------------------------|  
|Uygulama <xref:System.ComponentModel.DefaultBindingPropertyAttribute> basit denetimlerinde gibi bir <xref:System.Windows.Forms.TextBox>, tek bir sütun (veya özelliği) veri görüntüleme. Daha fazla bilgi için bkz: [basit veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).|  
|Uygulama <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> , denetimlerinde gibi bir <xref:System.Windows.Forms.DataGridView>, veri listeleri (veya tablo) görüntüler. Daha fazla bilgi için bkz: [karmaşık veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).|  
|Uygulama <xref:System.ComponentModel.LookupBindingPropertiesAttribute> , denetimlerinde gibi bir <xref:System.Windows.Forms.ComboBox>, bu veri listeleri (veya tablo) görüntülenir, ancak tek bir sütun veya özelliği sunmak de gerekir. (Bu işlem bu izlenecek yol sayfasında açıklanan.)|  
  
 Bu kılavuzda iki tablodan veri bağlar bir arama denetimi oluşturur. Bu örnekte `Customers` ve `Orders` Northwind örnek veritabanı tablolarından. Arama denetimi bağlanacağı `CustomerID` alanının `Orders` tablo. Aramak için bu değeri kullanır `CompanyName` gelen `Customers` tablo.  
  
 Bu gözden geçirme sırasında öğreneceksiniz nasıl yapılır:  
  
-   Yeni bir **Windows Forms uygulaması**.  
  
-   Yeni bir ekleme **kullanıcı denetimi** projenize.  
  
-   Görsel olarak kullanıcı denetimi tasarlayın.  
  
-   Uygulama `LookupBindingProperty` özniteliği.  
  
-   İle bir veri kümesi oluşturma **veri kaynağı yapılandırması** Sihirbazı.  
  
-   Ayarlama **CustomerID** sütunu **siparişleri** tablo, buna **veri kaynakları** penceresinde, yeni denetimi kullanmak için.  
  
-   Yeni denetiminde verileri görüntülemek için bir form oluşturun.  
  
## <a name="prerequisites"></a>Önkoşullar  
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.  
  
1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server sürümleri indirme sayfasına](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.  
  
2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:  

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .  

       Sorgu Düzenleyicisi penceresini açar.  

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.  

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.  

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.  
  
## <a name="create-a-windows-forms-application"></a>Bir Windows Forms uygulaması oluşturma  
 İlk adım oluşturmaktır bir **Windows Forms uygulaması**.  
  
#### <a name="to-create-the-new-windows-project"></a>Yeni Windows projesi oluşturmak için  
  
1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **LookupControlWalkthrough**ve ardından **Tamam**. 
  
     **LookupControlWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="add-a-user-control-to-the-project"></a>Projeye bir kullanıcı denetimi Ekle  
 Bu kılavuz bir arama denetiminden oluşturur bir **kullanıcı denetimi**, bu nedenle ekleyin bir **kullanıcı denetimi** öğesinin **LookupControlWalkthrough** projesi.  
  
#### <a name="to-add-a-user-control-to-the-project"></a>Bir kullanıcı denetimi projeye eklemek için  
  
1.  Gelen **proje** menüsünde, select **kullanıcı denetimi Ekle**.  
  
2.  Tür `LookupBox` içinde **adı** alan ve ardından **Ekle**.  
  
     **LookupBox** denetim eklenen **Çözüm Gezgini**ve Tasarımcısı'nda açılır.  
  
## <a name="design-the-lookupbox-control"></a>Tasarım LookupBox denetimi  
  
#### <a name="to-design-the-lookupbox-control"></a>Tasarım LookupBox denetimi  
  
-   Sürükleme bir <xref:System.Windows.Forms.ComboBox> gelen **araç** kullanıcı denetiminin tasarım yüzeyine.  
  
## <a name="add-the-required-data-binding-attribute"></a>Gerekli veri bağlama öznitelik Ekle  
 Arama bu destek veri bağlama denetimleri için uygulayabileceğiniz <xref:System.ComponentModel.LookupBindingPropertiesAttribute>.  
  
#### <a name="to-implement-the-lookupbindingproperties-attribute"></a>LookupBindingProperties özniteliği uygulamak için  
  
1.  Anahtar **LookupBox** denetim kodu görüntülemek için. (Üzerinde **Görünüm** menüsünde seçin **kod**.)  
  
2.  Kodla `LookupBox` aşağıdaki:  
  
     [!code-vb[VbRaddataDisplaying#5](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-lookup-data-binding_1.vb)]
     [!code-csharp[VbRaddataDisplaying#5](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-lookup-data-binding_1.cs)]  
  
3.  Gelen **yapı** menüsünde seçin **yapı çözümü**.  
  
## <a name="create-a-data-source-from-your-database"></a>Veritabanından bir veri kaynağı oluşturun  
Bu adımı kullanarak bir veri kaynağı oluşturur **veri kaynağı yapılandırması**göre Sihirbazı'nı `Customers` ve `Orders` Northwind örnek veritabanı tablolarında.  
  
#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.  
  
2.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı yapılandırması** Sihirbazı.  
  
3.  Seçin **veritabanı** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.  
  
4.  Üzerinde **veri bağlantınızı seçin** sayfasında aşağıdakilerden birini yapın:  
  
    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.  
  
    -   Seçin **yeni bağlantı** başlatmak için **Ekle/Değiştir bağlantı** iletişim kutusu.  
  
5.  Veritabanınız bir parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.  
  
6.  Üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfasında, **sonraki**.  
  
7.  Üzerinde **veritabanı nesnelerini seçin** sayfasında **tabloları** düğümü.  
  
8.  Seçin `Customers` ve `Orders` tablolar ve ardından **son**.  
  
     **NorthwindDataSet** projenize, eklenen ve `Customers` ve `Orders` tabloları görünür **veri kaynakları** penceresi.  
  
## <a name="set-the-customerid-column-of-the-orders-table-to-use-the-lookupbox-control"></a>LookupBox denetimi kullanmak için Siparişler tablosunun CustomerID sütun kümesi  
 İçinde **veri kaynakları** penceresinde formunuza öğeleri sürükleme önce oluşturulacak denetim ayarlayabilirsiniz.  
  
#### <a name="to-set-the-customerid-column-to-bind-to-the-lookupbox-control"></a>LookupBox denetimi bağlamak için CustomerID sütun ayarlamak için  
  
1.  Açık **Form1** Tasarımcısı'nda.  
  
2.  Genişletme **müşteriler** düğümünde **veri kaynakları** penceresi.  
  
3.  Genişletme **siparişleri** düğümü (bir **müşteriler** düğümü aşağıdaki **faks** sütun).  
  
4.  Aşağı açılan oku tıklatın **siparişleri** düğümü ve seçin **ayrıntıları** denetim listesinde.  
  
5.  Aşağı açılan oku tıklatın **CustomerID** sütun (içinde **siparişleri** düğüm) ve seçin **Özelleştir**.  
  
6.  Seçin **LookupBox** listesinden **ilişkili denetimleri** içinde **veri UI özelleştirme seçenekleri** iletişim kutusu.  
  
7.  **Tamam**'ı tıklatın.  
  
8.  Aşağı açılan oku tıklatın **CustomerID** sütun ve **LookupBox**.  
  
## <a name="add-controls-to-the-form"></a>Forma denetimler ekleme  
 Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturabileceğiniz **veri kaynakları** penceresi üzerine **Form1**.  
  
#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Windows formunda veri bağlama denetimleri oluşturmak için  
  
-   Sürükleme **siparişleri** düğümden **veri kaynakları** Windows Form üzerine penceresi doğrulayın **LookupBox** denetimi verileri görüntülemek için kullanılır `CustomerID` sütun.  
  
## <a name="bind-the-control-to-look-up-companyname-from-the-customers-table"></a>Müşteriler tablosundan ŞirketAdı aramak için denetimini bağlama  
  
#### <a name="to-setup-the-lookup-bindings"></a>Arama bağlantıları kurmak için  
  
-   Ana seçin **müşteriler** düğümünde **veri kaynakları** penceresi ve sürüklediğinizde birleşik giriş kutusu sürükleyin **CustomerIDLookupBox** üzerinde **Form1** .  
  
     Görüntülenecek veri bağlamanın ayarlar bu `CompanyName` gelen `Customers` koruyarak tablo `CustomerID` değeri `Orders` tablo.  
  
## <a name="running-the-application"></a>Uygulamayı çalıştırma  
  
#### <a name="to-run-the-application"></a>Uygulamayı çalıştırmak için  
  
-   Uygulamayı çalıştırmak için F5 tuşuna basın.  
  
-   Bazı kayıtlarda gidin ve doğrulayın `CompanyName` görünür `LookupBox` denetim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
