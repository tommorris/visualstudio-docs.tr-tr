---
title: Basit veri bağlamayı destekleyen bir kullanıcı denetimi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom controls [Visual Studio], Data Sources Window
- Data Sources Window, controls
ms.assetid: b1488366-6dfb-454e-9751-f42fd3f3ddfb
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: edfa94a6ca1bdc4fc8a5e9353505da4354b126ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-windows-forms-user-control-that-supports-simple-data-binding"></a>Basit veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma
Windows uygulamaları formlarda verileri görüntüleme, var olan denetimleri seçebilirsiniz **araç**, veya uygulamanızın standart denetimlerinde kullanılamıyor işlevsellik gerektiriyorsa özel denetimler yazabilirsiniz. Bu kılavuzda uygulayan bir denetimin nasıl oluşturulacağını gösterir <xref:System.ComponentModel.DefaultBindingPropertyAttribute>. Denetimleri uygulayan <xref:System.ComponentModel.DefaultBindingPropertyAttribute> veriye bağlı bir özellik içerebilir. Bu tür denetimler benzer bir <xref:System.Windows.Forms.TextBox> veya <xref:System.Windows.Forms.CheckBox>.  
  
 Denetim yazma hakkında daha fazla bilgi için bkz: [tasarım zamanında Windows Forms denetimleri geliştirme](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time).  
  
 Veri bağlama senaryolarda kullanım için denetimleri yazarken aşağıdaki veri bağlama özniteliklerden birini uygulamanız gerekir:  
  
|Veri bağlama öznitelik kullanımı|  
|-----------------------------------|  
|Uygulama <xref:System.ComponentModel.DefaultBindingPropertyAttribute> basit denetimlerinde gibi bir <xref:System.Windows.Forms.TextBox>, tek bir sütun (veya özelliği) veri görüntüleme. (Bu işlem bu izlenecek yol sayfasında açıklanan.)|  
|Uygulama <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> , denetimlerinde gibi bir <xref:System.Windows.Forms.DataGridView>, veri listeleri (veya tablo) görüntüler. Daha fazla bilgi için bkz: [karmaşık veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).|  
|Uygulama <xref:System.ComponentModel.LookupBindingPropertiesAttribute> , denetimlerinde gibi bir <xref:System.Windows.Forms.ComboBox>, veri listeleri (veya tablo) görüntüleme ancak tek bir sütun veya özelliği sunmak de gerekir. Daha fazla bilgi için bkz: [arama veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).|  
  
 Bu kılavuz, bir tablodaki tek bir sütun verileri görüntüleyen basit bir denetim oluşturur. Bu örnekte `Phone` sütunu `Customers` Northwind örnek veritabanı tablosundan. Basit kullanıcı denetiminin müşterilerin telefon numaralarını standart bir telefon numarası biçimi kullanarak görüntüleneceği bir <xref:System.Windows.Forms.MaskedTextBox> ve maskesini ayarlarken bir telefon numarası.  
  
 Bu gözden geçirme sırasında öğreneceksiniz nasıl yapılır:  
  
-   Yeni bir **Windows Forms uygulaması**.  
  
-   Yeni bir ekleme **kullanıcı denetimi** projenize.  
  
-   Görsel olarak kullanıcı denetimi tasarlayın.  
  
-   Uygulama `DefaultBindingProperty` özniteliği.  
  
-   İle bir veri kümesi oluşturma **veri kaynağı yapılandırması** Sihirbazı.  
  
-   Ayarlama **telefon** sütununda **veri kaynakları** yeni denetimi kullanmak için penceresi.  
  
-   Yeni denetiminde verileri görüntülemek için bir form oluşturun.  
  
## <a name="prerequisites"></a>Önkoşullar  
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.  
  
1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.  
  
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

4. Proje adı **SimpleControlWalkthrough**ve ardından **Tamam**. 
  
     **SimpleControlWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="add-a-user-control-to-the-project"></a>Projeye bir kullanıcı denetimi Ekle  
 Bu kılavuzda basit veri bağlanabilir denetimden oluşturur bir **kullanıcı denetimi**, bu nedenle ekleyin bir **kullanıcı denetimi** öğesinin **SimpleControlWalkthrough** projesi.  
  
#### <a name="to-add-a-user-control-to-the-project"></a>Bir kullanıcı denetimi projeye eklemek için  
  
1.  Gelen **proje** menüsünde seçin **kullanıcı denetimi Ekle**.  
  
2.  Tür `PhoneNumberBox` ad alanında hem tıklatın **Ekle**.  
  
     **PhoneNumberBox** denetim eklenen **Çözüm Gezgini**ve Tasarımcısı'nda açılır.  
  
## <a name="design-the-phonenumberbox-control"></a>Tasarım PhoneNumberBox denetimi  
 Bu kılavuz mevcut bağlı genişletir <xref:System.Windows.Forms.MaskedTextBox> oluşturmak için `PhoneNumberBox` denetim.  
  
#### <a name="to-design-the-phonenumberbox-control"></a>Tasarım PhoneNumberBox denetimi  
  
1.  Sürükleme bir <xref:System.Windows.Forms.MaskedTextBox> gelen **araç** kullanıcı denetiminin tasarım yüzeyine.  
  
2.  Akıllı etiket seçin <xref:System.Windows.Forms.MaskedTextBox> yalnızca sürüklenen ve seçin **ayarlamak maskesi**.  
  
3.  Seçin **telefon numarası** içinde **giriş maskesi** iletişim kutusu ve tıklatın **Tamam** maskesi ayarlamak için.  
  
## <a name="add-the-required-data-binding-attribute"></a>Gerekli veri bağlama öznitelik Ekle  
 Bu destek databinding basit denetimleri için uygulama <xref:System.ComponentModel.DefaultBindingPropertyAttribute>.  
  
#### <a name="to-implement-the-defaultbindingproperty-attribute"></a>DefaultBindingProperty özniteliği uygulamak için  
  
1.  Anahtar `PhoneNumberBox` denetim kodu görüntülemek için. (Üzerinde **Görünüm** menüsünde seçin **kod**.)  
  
2.  Kodla `PhoneNumberBox` aşağıdaki:  
  
     [!code-csharp[VbRaddataDisplaying#3](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.cs)]
     [!code-vb[VbRaddataDisplaying#3](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-simple-data-binding_1.vb)]  
  
3.  Gelen **yapı** menüsünde seçin **yapı çözümü**.  
  
## <a name="create-a-data-source-from-your-database"></a>Veritabanından bir veri kaynağı oluşturun  
 Bu adımı kullanan **veri kaynağı yapılandırması**bir veri kaynağı oluşturmak için Sihirbazı'nı temel alarak `Customers` Northwind örnek veritabanı tablosunda. Northwind örnek veritabanı bağlantısı oluşturmak için erişimi olmalıdır. Northwind örnek veritabanı ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: örnek veritabanları yükleme](../data-tools/installing-database-systems-tools-and-samples.md).  
  
#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.  
  
2.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı yapılandırması** Sihirbazı.  
  
3.  Üzerinde **bir veri kaynağı türü seç** sayfasında, **veritabanı**ve ardından **sonraki**.  
  
4.  Üzerinde **veri bağlantınızı seçin** sayfasında, aşağıdakilerden birini yapın:  
  
    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.  
  
    -   Seçin **yeni bağlantı** başlatmak için **Ekle/Değiştir bağlantı** iletişim kutusu.  
  
5.  Veritabanınız bir parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.  
  
6.  Üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfasında, **sonraki**.  
  
7.  Üzerinde **veritabanı nesnelerini seçin** sayfasında **tabloları** düğümü.  
  
8.  Seçin `Customers` tablo ve ardından **son**.  
  
     **NorthwindDataSet** projenize, eklenen ve `Customers` tablo görünür **veri kaynakları** penceresi.  
  
## <a name="set-the-phone-column-to-use-the-phonenumberbox-control"></a>PhoneNumberBox denetimi kullanmak için telefon sütun kümesi  
 İçinde **veri kaynakları** penceresinde formunuza öğeleri sürükleme önce oluşturulacak denetim ayarlayabilirsiniz.  
  
#### <a name="to-set-the-phone-column-to-bind-to-the-phonenumberbox-control"></a>PhoneNumberBox denetimi bağlamak için Telefon sütunu ayarlamak için  
  
1.  Açık **Form1** Tasarımcısı'nda.  
  
2.  Genişletme **müşteriler** düğümünde **veri kaynakları** penceresi.  
  
3.  Aşağı açılan oku tıklatın **müşteriler** düğümü ve seçin **ayrıntıları** denetim listesinde.  
  
4.  Aşağı açılan oku tıklatın **telefon** sütun ve **Özelleştir**.  
  
5.  Seçin **PhoneNumberBox** listesinden **ilişkili denetimleri** içinde **veri UI özelleştirme seçenekleri** iletişim kutusu.  
  
6.  Aşağı açılan oku tıklatın **telefon** sütun ve **PhoneNumberBox**.  
  
## <a name="add-controls-to-the-form"></a>Forma denetimler ekleme  
 Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturabileceğiniz **veri kaynakları** forma penceresi.  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>Form üzerinde veri bağlama denetimleri oluşturmak için  
  
-   Ana sürükleyin **müşteriler** düğümden **veri kaynakları** form üzerine penceresi doğrulayın `PhoneNumberBox` denetimi verileri görüntülemek için kullanılır `Phone` sütun.  
  
     Verilere bağlı denetimler tanımlayıcı etiketlerle görünür formdaki bir aracı Şerit birlikte (<xref:System.Windows.Forms.BindingNavigator>) kayıtları gezinme. A [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), TableAdapter, <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür.  
  
## <a name="run-the-application"></a>Uygulamayı çalıştırın  
  
#### <a name="to-run-the-application"></a>Uygulamayı çalıştırmak için  
  
-   Uygulamayı çalıştırmak için F5 tuşuna basın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Uygulama gereksinimlerinize bağlı olarak, veri bağlamayı destekleyen bir denetim oluşturma sonra gerçekleştirmek istediğinizi düşünelim birkaç adım vardır. Bazı tipik sonraki adımlar şunlardır:  
  
-   Diğer uygulamalarda yeniden kullanabileceğiniz şekilde bir Denetim Kitaplığı'nda özel denetimler yerleştirme.  
  
-   Daha karmaşık veri bağlama senaryoları desteklemek denetimler oluşturma. Daha fazla bilgi için bkz: [karmaşık veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md) ve [arama veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Deneti veri kaynakları penceresinden sürüklendiğinde oluşturulacak şekilde ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)
