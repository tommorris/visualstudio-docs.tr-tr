---
title: "İzlenecek yol: N katmanlı veri uygulaması oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 09/08/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, creating
- n-tier applications, walkthroughs
ms.assetid: d15e4d31-2839-48d9-9e0e-2e73404d82a2
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 7cc4d8420cd823964aeed790a412e462b14634c0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-n-tier-data-application"></a>İzlenecek Yol: N Katmanlı Bir Veri Uygulaması Oluşturma
*N katmanlı* veri uygulamalardır verilere erişebilir ve birden çok mantıksal katmanlara ayrılır uygulamalar veya *katmanları*. Uygulama bileşenlerini farklı katmanlara ayırmak uygulamanızın yönetilebilirliğini ve ölçeklenebilirliğini artırır. Bunu, tüm çözümü yeniden tasarlamanıza gerek kalmadan tek bir katmana uygulanabilen yeni teknolojilerin daha kolay benimsenmesini sağlayarak yapar. N katmanlı mimaride bir sunu katmanı, bir orta katman ve bir veri katmanı bulunur. Orta katmanda genellikle bir veri erişim katmanı, iş mantığı katmanı ve kimlik doğrulaması ve doğrulama gibi paylaşılan bileşenler bulunur. Veri katmanında ilişkisel bir veritabanı vardır. N katmanlı uygulamalar hassas bilgileri orta katmanın veri erişimi katmanında depolayarak sunu katmanına erişimi olan son kullanıcılardan uzakta tutulmasını sağlar. Daha fazla bilgi için bkz: [N katmanlı veri uygulamalarına genel bakış](../data-tools/n-tier-data-applications-overview.md).  
  
N katmanlı uygulamada çeşitli katmanları ayırma yollarından biri, uygulamanıza eklemek istediğiniz her katman için ayrı projeler oluşturmaktır. Türü belirtilmiş veri kümelerinde, üretilen veri kümesinin ve `DataSet Project` kodunun gitmesi gereken projeleri belirleyen bir `TableAdapter` özelliği bulunur.  
  
Bu kılavuzda, veri kümesi ayırmak gösterilmiştir ve `TableAdapter` kullanarak ayrık Sınıf Kitaplığı projelerinde koda **veri kümesi Tasarımcısı**. Veri kümesi ve TableAdapter kodu ayrı sonra oluşturacak bir [Windows Communication Foundation Hizmetleri ve Visual Studio'da WCF Veri Hizmetleri](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) veri erişim katmanı çağrılacak hizmet. Son olarak, sunu katmanı olarak bir Windows Forms uygulaması oluşturacaksınız. Bu katman veri hizmetindeki verilere erişir.  
  
Bu kılavuzda aşağıdaki adımları gerçekleştireceksiniz:  
  
-   Birden fazla proje içeren yeni bir n katmanlı çözüm oluşturma.  
  
-   N katmanlı çözüme iki sınıf kitaplığı ekleme.  
  
-   Türü belirtilmiş veri kümesi kullanarak oluşturma **veri kaynağı Yapılandırma Sihirbazı**.  
  
-   Oluşturulan ayrı [TableAdapters](create-and-configure-tableadapters.md) ve ayrık projelerine dataset kodu.  
  
-   Veri erişim katmanına çağrı göndermek için bir Windows Communication Foundation (WCF) hizmeti oluşturma.  
  
-   Veri erişim katmanından veri almak için hizmet içinde işlevler oluşturma.  
  
-   Sunu katmanı olarak hizmet verecek bir Windows Forms uygulaması oluşturma.  
  
-   Veri kaynağına bağlanan Windows Forms denetimleri oluşturma.  
  
-   Veri tablolarını doldurmak için kod yazma.  
  
![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") bu konuda video sürümü için bkz: [Video nasıl yapılır: N katmanlı veri uygulaması oluşturma](http://go.microsoft.com/fwlink/?LinkId=115188).  
  
## <a name="prerequisites"></a>Önkoşullar  
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.  
  
1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server sürümleri indirme sayfasına](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **.NET masaüstü geliştirme** iş yükü veya tek bir bileşen olarak.  
  
2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:  

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .  

       Sorgu Düzenleyicisi penceresini açar.  

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.  

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.  

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.  
  
## <a name="creating-the-n-tier-solution-and-class-library-to-hold-the-dataset-dataentitytier"></a>Veri Kümesini Tutacak N Katmanlı Çözüm ve Sınıf Kitaplığı Oluşturma (DataEntityTier)  
 Bu kılavuzun ilk adımı bir çözüm ve iki sınıf kitaplığı projesi oluşturmaktır. Birinci sınıf kitaplığı veri kümesini tutacaktır (uygulama verilerini tutacak, üretilen türü belirtilmiş DataSet sınıfı ve DataTable tabloları). Bu proje uygulamanın veri varlık katmanı olarak kullanılır ve genellikle orta katmanda bulunur. İlk veri kümesi oluşturmak ve kod iki sınıf kitaplıkları otomatik olarak ayırmak için kullanılan zaman.  
  
> [!NOTE]
>  Tıklatmadan önce proje ve çözüm doğru adı özen **Tamam**. Böylece bu kılavuzu tamamlamanız kolaylaşır.  
  
#### <a name="to-create-the-n-tier-solution-and-dataentitytier-class-library"></a>N katmanlı çözüm ve DataEntityTier sınıf kitaplığı oluşturmak için  

1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **sınıf kitaplığı** proje türü.  
  
4. Proje adı **DataEntityTier**.  
  
5. Çözüm adı **NTierWalkthrough**ve ardından **Tamam**.  
  
     DataEntityTier projeyi içeren NTierWalkthrough çözümünü oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="creating-the-class-library-to-hold-the-tableadapters-dataaccesstier"></a>TableAdapter Bağdaştırıcılarını Tutacak Sınıf Kitaplığı Oluşturma (DataAccessTier)  
 DataEntityTier projesini oluşturduktan sonraki adım başka bir sınıf kitaplığı projesi oluşturmaktır. Bu proje oluşturulan tutacak `TableAdapter`s ve çağrılır *veri erişim katmanı* uygulamanın. Veri erişim katmanında, veritabanına bağlanmak için gereken bilgiler bulunur ve genelde orta katmanda yer alır.  
  
#### <a name="to-create-a-separate-class-library-for-the-tableadapters"></a>TableAdapters için ayrı sınıf kitaplığı oluşturmak için  
  
1.  Çözüm Gezgini'ndeki çözüme sağ tıklayın ve seçin **Ekle**, **yeni proje...** .  
  
2.  İçinde **yeni proje** Orta bölmede, Seç iletişim kutusu **sınıf kitaplığı**.  
  
3.  Proje adı **DataAccessTier** ve **Tamam**.  
  
     DataAccessTier projesi oluşturulur ve NTierWalkthrough çözümüne eklenir.  
  
## <a name="creating-the-dataset"></a>Veri Kümesi Oluşturma  
 Sonraki adım türü belirtilmiş bir veri kümesi oluşturmaktır. Türü belirtilmiş veri kümeleri, her iki veri kümesi sınıfıyla (DataTable sınıfları dahil) ve `TableAdapter` sınıflarıyla tek bir projede oluşturulur. (Tüm sınıflar tek dosyada oluşturulur.) Veri kümesini ve `TableAdapter` bağdaştırıcılarını farklı projelere ayırdığınızda veri kümesi sınıfı diğer projeye taşınır, `TableAdapter` sınıfları özgün projede kalır. Bu nedenle, veri kümesini sonuçta `TableAdapter` bağdaştırıcılarını içerecek projede oluşturun (DataAccessTier projesi). Kullanarak veri kümesi oluşturacaksınız **veri kaynağı Yapılandırma Sihirbazı**.  
  
> [!NOTE]
>  Northwind örnek veritabanı bağlantısı oluşturmak için erişimi olmalıdır. Northwind örnek veritabanı ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: örnek veritabanları yükleme](../data-tools/installing-database-systems-tools-and-samples.md).  
  
#### <a name="to-create-the-dataset"></a>Veri kümesi oluşturma  
  
1.  İçinde DataAccessTier seçin **Çözüm Gezgini**.  
  
2.  Üzerinde **veri** menüsünde, select **veri kaynaklarını Göster**.  
  
3.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı Yapılandırma Sihirbazı**.  
  
4.  Üzerinde **bir veri kaynağı türü seç** sayfasında, **veritabanı** ve ardından **sonraki**.  
  
5.  Üzerinde **veri bağlantınızı** sayfasında, aşağıdaki eylemlerden birini gerçekleştirin:  
  
     Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.  
  
     veya  
  
     Seçin **yeni bağlantı** açmak için **Bağlantı Ekle** iletişim kutusu.  
  
6.  Veritabanı parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.  
  
    > [!NOTE]
    >  Bir yerel veritabanı dosyası (SQL Server'a bağlanmak yerine) seçtiyseniz projeye dosya eklemek isteyip istemediğiniz sorulabilir. Seçin **Evet** veritabanı dosyası projeye eklemek için.  
  
7.  Seçin **sonraki** üzerinde **bağlantı dizesini uygulama yapılandırma dosyasını Kaydet** sayfası.  
  
8.  Genişletme **tabloları** düğümde **veritabanı nesnelerinizi** sayfası.  
  
9.  Onay kutularını işaretleyin **müşteriler** ve **siparişleri** tabloları ve ardından **son**.  
  
     NorthwindDataSet DataAccessTier projeye eklendi ve görünür **veri kaynakları** penceresi.  
  
## <a name="separating-the-tableadapters-from-the-dataset"></a>TableAdapter Bağdaştırıcılarını Veri Kümesinden Ayırma  
 Veri kümesi oluşturduktan sonra, üretilen veri kümesi sınıfını TableAdapter bağdaştırıcılarından ayırın. Ayarlayarak bunu **DataSet projesi** dataset sınıfı ayrılmış depolanacağı projesinin adı özelliği.  
  
#### <a name="to-separate-the-tableadapters-from-the-dataset"></a>TableAdapter Bağdaştırıcılarını Veri Kümesinden ayırmak için  
  
1.  Çift **NorthwindDataSet.xsd** içinde **Çözüm Gezgini** kümesinde açmak için **veri kümesi Tasarımcısı**.  
  
2.  Tasarımcı üzerinde boş bir alan seçin.  
  
3.  Bulun **DataSet projesi** düğümünde **özellikleri** penceresi.  
  
4.  İçinde **DataSet projesi** listesinde **DataEntityTier**.  
  
5.  Üzerinde **yapı** menüsünde, select **yapı çözümü**.  
  
 Veri kümesi ve TableAdapter bağdaştırıcıları iki sınıf kitaplığı projesine ayrılır. Başlangıçta tüm veri kümesini (DataAccessTier) içeren projede şimdi yalnızca TableAdapter bağdaştırıcıları bulunur. Proje belirtilen **DataSet projesi** özelliği (DataEntityTier) türü belirtilmiş veri kümesi içerir: NorthwindDataSet.Dataset.Designer.vb (veya NorthwindDataSet.Dataset.Designer.cs).  
  
> [!NOTE]
>  Ne zaman, ayrı veri kümeleri ve TableAdapters öğelerini (ayarlayarak **DataSet projesi** özelliği), projedeki mevcut kısmi veri kümesi sınıflarını değil taşınabilir otomatik olarak. Mevcut veri kümesi kısmi sınıflarının veri kümesi projesine el ile taşınması gerekir.  
  
## <a name="creating-a-new-service-application"></a>Yeni Hizmet Uygulaması Oluşturma  
Bu kılavuz, bir WCF hizmeti kullanarak veri erişim katmanı erişmek için yeni bir WCF hizmeti uygulaması oluşturalım şekilde gösterilmiştir.  
  
#### <a name="to-create-a-new-wcf-service-application"></a>Yeni bir WCF Hizmeti uygulaması oluşturmak için  
  
1.  Çözüm Gezgini'ndeki çözüme sağ tıklayın ve seçin **Ekle**, **yeni proje...** .  
  
2.  İçinde **yeni proje** iletişim kutusunda, sol bölmesinde, **WCF**.  Orta bölmede seçin **WCF Hizmeti Kitaplığı**.  
  
3.  Proje adı **DataService** seçip **Tamam**.  
  
     DataService projesi oluşturulur ve NTierWalkthrough çözümüne eklenir.  
  
## <a name="creating-methods-in-the-data-access-tier-to-return-the-customers-and-orders-data"></a>Müşteri ve Sipariş Verilerini Döndürmek İçin Veri Erişim Katmanında Yöntemler Oluşturma  
 Veri hizmetinin veri erişim katmanında iki yöntem çağırması gerekir: GetCustomers ve GetOrders. Bu yöntemler Northwind Customers ve Orders tablolarını döndürür. DataAccessTier projesinde GetCustomers ve GetOrders yöntemlerini oluşturun.  
  
#### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-customers-table"></a>Veri erişim katmanında Customers tablosunu döndüren bir yöntem oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, NorthwindDataset.xsd dataset açmak için çift tıklayın.
  
2.  TableAdapter sağ tıklatın ve **Sorgu Ekle**.  
  
3.  Üzerinde **komut türü seçin** sayfasında, varsayılan değerini bırakın **kullanım SQL deyimlerini** tıklatıp **sonraki**.  
  
4.  Üzerinde **sorgu türü seç** sayfasında, varsayılan değerini bırakın **satırlar döndüren seçin** tıklatıp **sonraki**.  
  
5.  Üzerinde **SQL SELECT deyimine belirtin** sayfasında, varsayılan sorgu bırakın ve tıklayın **sonraki**.  
  
6.  Üzerinde **oluşturma yöntemlerini seçin** sayfasında, **GetCustomers** için **yöntem adı** içinde **DataTable dönmek** bölümü.  
  
7.  **Son**'a tıklayın.  
  
#### <a name="to-create-a-method-in-the-data-access-tier-that-returns-the-orders-table"></a>Veri erişim katmanında Orders tablosunu döndüren bir yöntem oluşturmak için  
  
1.  OrdersTableAdapter sağ tıklatın ve **Sorgu Ekle**.  
  
2.  Üzerinde **komut türü seçin** sayfasında, varsayılan değerini bırakın **kullanım SQL deyimlerini** tıklatıp **sonraki**.  
  
3.  Üzerinde **sorgu türü seç** sayfasında, varsayılan değerini bırakın **satırlar döndüren seçin** tıklatıp **sonraki**.  
  
4.  Üzerinde **SQL SELECT deyimine belirtin** sayfasında, varsayılan sorgu bırakın ve tıklayın **sonraki**.  
  
5.  Üzerinde **oluşturma yöntemlerini seçin** sayfasında, **GetOrders** için **yöntem adı** içinde **DataTable dönmek** bölümü.  
  
6.  **Son**'a tıklayın.  
  
7.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
## <a name="adding-a-reference-to-the-data-entity-and-data-access-tiers-to-the-data-service"></a>Veri Hizmetinin Veri Varlığı ve Veri Erişimi Katmanlarına Başvuru Ekleme  
 Veri hizmetinin veri kümesinden ve TableAdapter bağdaştırıcılarından bilgi alması gerektiğinden DataEntityTier ve DataAccessTier projelerine başvurular ekleyin.  
  
#### <a name="to-add-references-to-the-data-service"></a>Veri hizmetine başvuru eklemek için  
  
1.  DataService, sağ **Çözüm Gezgini** tıklatıp **Başvuru Ekle**.  
  
2.  Tıklatın **projeleri** sekmesinde **Başvuru Ekle** iletişim kutusu.  
  
3.  Her ikisini de seçin **DataAccessTier** ve **DataEntityTier** projeleri.  
  
4.  **Tamam**'ı tıklatın.  
  
## <a name="adding-functions-to-the-service-to-call-the-getcustomers-and-getorders-methods-in-the-data-access-tier"></a>Veri Erişim Katmanındaki GetCustomers ve GetOrder Yöntemlerini Çağırmak İçin Hizmete İşlev Ekleme  
 Şimdi veri erişim katmanında veri döndürme yöntemleri bulunduğuna göre, veri erişim katmanındaki yöntemleri çağırmak için veri hizmetinde yöntemler oluşturun.  
  
> [!NOTE]
>  C# projelerinde aşağıdaki kodu derlemek için `System.Data.DataSetExtensions` derlemesine bir başvuru eklemeniz gerekir.  
  
#### <a name="to-create-the-getcustomers-and-getorders-functions-in-the-data-service"></a>Veri hizmetinde GetCustomers ve GetOrders işlevlerini oluşturmak için  
  
1.  İçinde **DataService** projesi, IService1.vb veya IService1.cs çift tıklayın.  
  
2.  Altında aşağıdaki kodu ekleyin **ekleme, hizmet işlemlerinin** Açıklama:  
  
    ```vb  
    <OperationContract()> _  
    Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable  
  
    <OperationContract()> _  
    Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable  
    ```  
  
    ```csharp  
    [OperationContract]  
    DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers();  
  
    [OperationContract]  
    DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders();  
    ```  
  
3.  DataService projesinde Service1.vb (veya Service1.cs) öğesine çift tıklayın.  
  
4.  Aşağıdaki kodu Service1 sınıfına ekleyin:  
  
    ```vb  
    Public Function GetCustomers() As DataEntityTier.NorthwindDataSet.CustomersDataTable Implements IService1.GetCustomers  
        Dim CustomersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter  
        Return CustomersTableAdapter1.GetCustomers()  
    End Function  
  
    Public Function GetOrders() As DataEntityTier.NorthwindDataSet.OrdersDataTable Implements IService1.GetOrders  
        Dim OrdersTableAdapter1 As New DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter  
        Return OrdersTableAdapter1.GetOrders()  
    End Function  
    ```  
  
    ```csharp  
    public DataEntityTier.NorthwindDataSet.CustomersDataTable GetCustomers()  
    {  
        DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter  
             CustomersTableAdapter1  
            = new DataAccessTier.NorthwindDataSetTableAdapters.CustomersTableAdapter();  
        return CustomersTableAdapter1.GetCustomers();  
    }  
    public DataEntityTier.NorthwindDataSet.OrdersDataTable GetOrders()  
    {  
        DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter  
             OrdersTableAdapter1  
            = new DataAccessTier.NorthwindDataSetTableAdapters.OrdersTableAdapter();  
        return OrdersTableAdapter1.GetOrders();  
    }  
    ```  
  
5.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
## <a name="creating-a-presentation-tier-to-display-data-from-the-data-service"></a>Veri Hizmetinden Verileri Görüntülemek İçin Bir Sunu Katmanı Oluşturma  
 Şimdi çözümde veri erişim katmanına çağrı gönderen yöntemler bulunduğuna göre, veri hizmetine çağrı gönderecek ve verileri kullanıcılara sunacak başka bir proje oluşturun. Bu kılavuz için bir Windows Forms uygulaması oluşturun; bu n katmanlı uygulamanın sunu katmanıdır.  
  
#### <a name="to-create-the-presentation-tier-project"></a>Sunu katmanı projesi oluşturmak için  
  
1.  Çözüm Gezgini'ndeki çözüme sağ tıklayın ve seçin **Ekle**, **yeni proje...** .  
  
2.  İçinde **yeni proje** iletişim kutusunda, sol bölmesinde, **Windows Klasik Masaüstü**. Orta bölmede seçin **Windows Forms uygulaması**.  
  
3.  Proje adı **PresentationTier** tıklatıp **Tamam**.  
  
    PresentationTier projesi oluşturulur ve NTierWalkthrough çözümüne eklenir.  
  
## <a name="setting-the-presentationtier-project-as-the-startup-project"></a>PresentationTier Projesini Başlangıç Projesi Olarak Ayarlama  
Sunmak ve veri ile etkileşim kurmak için kullanılan gerçek istemci uygulaması olduğundan PresentationTier projesini başlangıç projesi çözüm için olacak şekilde yaparız.  
  
#### <a name="to-set-the-new-presentation-tier-project-as-the-startup-project"></a>Yeni sunu katmanı projesini Başlangıç projesi olarak ayarlamak için  
  
-   İçinde **Çözüm Gezgini**, sağ **PresentationTier** tıklatıp **başlangıç projesi olarak ayarla**.  
  
## <a name="adding-references-to-the-presentation-tier"></a>Sunu Katmanına Başvuru Ekleme  
 PresentationTier istemci uygulaması, hizmetteki yöntemlere erişmek için veri hizmetine yönelik bir hizmet başvurusu gerektirir. Buna ek olarak, WCF hizmeti tür paylaşımını etkinleştirmek için veri kümesine bir başvuru gerektirir. Veri hizmeti aracılığıyla tür paylaşımı etkinleştirilinceye kadar kısmi veri kümesi sınıfına eklenen kod sunu katmanı tarafından kullanılamaz. Genelde veri tablosundaki satır ve sütun değişikliği olaylarını doğrulama gibi bir kod ekleyeceğiniz için büyük olasılıkla bu koda istemcisinden erişmek isteyeceksiniz.  
  
#### <a name="to-add-a-reference-to-the-presentation-tier"></a>Sunu katmanına bir başvuru eklemek için  
  
1.  İçinde **Çözüm Gezgini**PresentationTier sağ tıklatın ve seçin **Başvuru Ekle**.  
  
2.  İçinde **Başvuru Ekle** iletişim kutusunda **projeleri** sekmesi.  
  
3.  Seçin **DataEntityTier** ve **Tamam**.  
  
#### <a name="to-add-a-service-reference-to-the-presentation-tier"></a>Sunu katmanına bir hizmet başvurusu eklemek için  
  
1.  İçinde **Çözüm Gezgini**PresentationTier sağ tıklatın ve seçin **hizmet Başvurusu Ekle**.  
  
2.  İçinde **hizmet Başvurusu Ekle** iletişim kutusunda **bulma**.  
  
3.  Seçin **Service1** ve **Tamam**.  
  
    > [!NOTE]
    >  Geçerli bilgisayarda birden çok hizmetiniz varsa, bu kılavuzda önceden oluşturduğunuz hizmeti seçin (GetCustomers ve GetOrders yöntemlerini içeren hizmet).  
  
## <a name="adding-datagridviews-to-the-form-to-display-the-data-returned-by-the-data-service"></a>Veri Hizmetinin Döndürdüğü Verileri Görüntülemek İçin Forma DataGridView Görünümleri Ekleme  
 Veri hizmetine hizmet başvurusu ekledikten sonra **veri kaynakları** penceresi hizmet tarafından döndürülen veriler ile otomatik olarak doldurulur.  
  
#### <a name="to-add-two-data-bound-datagridviews-to-the-form"></a>Forma iki DataGridView veri bağlama öğesi eklemek için  
  
1.  İçinde **Çözüm Gezgini**, PresentationTier projesini seçin.  
  
2.  İçinde **veri kaynakları** penceresinde genişletin **NorthwindDataSet** ve bulun **müşteriler** düğümü.  
  
3.  Sürükleme **müşteriler** Form1 düğüme.  
  
4.  İçinde **veri kaynakları** penceresinde genişletin **müşteriler** düğümü ve ilgili bulun **siparişleri** düğümü ( **siparişleri** düğümü içiçegeçmiş **Müşteriler** düğüm).  
  
5.  İlgili sürükleyin **siparişleri** Form1 düğüme.  
  
6.  Formda boş bir alanı çift tıklayarak bir `Form1_Load` olay işleyicisi oluşturun.  
  
7.  Aşağıdaki kodu ekleyin `Form1_Load` olay işleyicisi.  
  
    ```vb  
    Dim DataSvc As New ServiceReference1.Service1Client  
    NorthwindDataSet.Customers.Merge(DataSvc.GetCustomers)  
    NorthwindDataSet.Orders.Merge(DataSvc.GetOrders)  
    ```  
  
    ```csharp  
    ServiceReference1.Service1Client DataSvc =   
        new ServiceReference1.Service1Client();  
    northwindDataSet.Customers.Merge(DataSvc.GetCustomers());  
    northwindDataSet.Orders.Merge(DataSvc.GetOrders());  
    ```  
  
## <a name="increasing-the-maximum-message-size-allowed-by-the-service"></a>Hizmet Tarafından İzin Verilen En Büyük İleti Boyutunu Artırma  
MaxReceivedMessageSize için varsayılan değer müşteriler ve siparişler tablolardan alınan verileri tutmak için yeterince büyük değil. Aşağıdaki adımlarda 6553600 değerine artırırsınız. Hizmet başvurusu otomatik olarak güncelleştirir istemcide değerini değiştirir.  
  
> [!NOTE]
>  Varsayılan alt sınır boyutu hizmet reddi (DoS) saldırılarına maruz kalmayı sınırlamak içindir. Daha fazla bilgi için bkz. <xref:System.ServiceModel.WSHttpBindingBase.MaxReceivedMessageSize%2A>.  
  
#### <a name="to-increase-the-maxreceivedmessagesize-value"></a>MaxReceivedMessageSize değerini artırmak için  
  
1.  İçinde **Çözüm Gezgini**, PresentationTier projesinde app.config dosyasına çift tıklayın.  
  
2.  Bulun **maxReceivedMessage** boyut özniteliği ve değerini değiştirin `6553600`.  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
Tuşlarına basarak uygulamayı çalıştırın **F5**. Customers ve Orders tablolarındaki veriler veri hizmetinden alınır ve formda görüntülenir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Uygulama gereksinimlerinize bağlı olarak, Windows tabanlı bir uygulama içinde ilgili verileri kaydettikten sonra gerçekleştirmek isteyebileceğiniz birkaç adım vardır. Örneğin, bu uygulamada aşağıdaki geliştirmeleri yapabilirsiniz:  
  
-   Veri kümesine doğrulama ekleme. 
  
-   Verileri tekrar veritabanında güncelleştirmek için hizmete ek yöntemler ekleme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [N katmanlı uygulamalarda veri kümeleriyle çalışma](../data-tools/work-with-datasets-in-n-tier-applications.md)   
 [Hiyerarşik güncelleştirme](../data-tools/hierarchical-update.md)   
 [Visual Studio'da verilere erişime](../data-tools/accessing-data-in-visual-studio.md)