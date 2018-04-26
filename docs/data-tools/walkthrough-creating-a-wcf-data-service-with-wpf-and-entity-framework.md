---
title: 'İzlenecek yol: bir WCF veri hizmetine WPF ve Entity Framework ile oluşturma'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data services in Visual Studio
- WCF Data Services, Visual Studio
- ADO.NET Data Services, Visual Studio
- WCF data services in Visual Studio
ms.assetid: da66ad1b-a25d-485c-af13-2d18f0422e3d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d4ee4d9a1c64d39e6ef05f9c01b26686f13c6dea
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework"></a>İzlenecek yol: bir WCF veri hizmetine WPF ve Entity Framework ile oluşturma
Bu kılavuzda nasıl basit bir oluşturulduğunu gösteren [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] içinde barındırılan bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması ve bir Windows Forms uygulamasında erişebilir.

Bu izlenecek yolda yapacaklarınız:

-   Ana bilgisayar için bir Web uygulaması oluşturduğunuzda bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

-   Oluşturma bir [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] , Northwind veritabanı Müşteriler tablosunda temsil eder.

-   Oluşturma bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

-   İstemci uygulaması oluşturma ve bir başvuru ekleyin [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)].

-   Hizmete veri bağlamayı etkinleştirin ve kullanıcı arabirimini oluşturun.

-   İsteğe bağlı olarak, uygulamaya filtreleme yetenekleri ekleyin.

## <a name="prerequisites"></a>Önkoşullar
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.

1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server Express indirme sayfası](https://www.microsoft.com/sql-server/sql-server-editions-express), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.

2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .

       Sorgu Düzenleyicisi penceresini açar.

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.

## <a name="creating-the-service"></a>Hizmeti Oluşturma
Oluşturmak için bir [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)], bir Web projesi eklemek, oluşturma bir [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]ve ardından hizmet modeli oluşturun.

İlk adımda hizmeti barındırmak için bir Web projesi ekleyeceksiniz.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-create-the-web-project"></a>Web projesini oluşturmak için

1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.

2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual Basic** veya **Visual C#** ve **Web** düğümleri ve ardından **ASP. NET Web uygulaması** şablonu.

3.  İçinde **adı** metin kutusuna **NorthwindWeb**ve ardından **Tamam** düğmesi.

4.  İçinde **yeni ASP.NET projesi** iletişim kutusunda **bir şablon seçin** listesinde, seçin **boş**ve ardından **Tamam** düğmesi.

Sonraki adımda oluşturacağınız bir [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] , Northwind veritabanı Müşteriler tablosunda temsil eder.

#### <a name="to-create-the-entity-data-model"></a>Varlık Veri Modeli'ni oluşturmak için

1.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.

2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **veri** düğümünü ve ardından **ADO.NET varlık veri modeli** öğesi.

3.  İçinde **adı** metin kutusuna `NorthwindModel`ve ardından **Ekle** düğmesi.

     Varlık Veri Modeli Sihirbazı görüntülenir.

4.  Varlık veri modeli Sihirbazı'nda üzerinde **Model içeriği seçin** sayfasında, **veritabanından EF Designer** öğesini ve ardından **sonraki** düğmesi.

5.  Üzerinde **veri bağlantınızı** sayfasında, aşağıdaki adımlardan birini gerçekleştirin:

    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.

         -veya-

    -   Seçin **yeni bağlantı** yeni bir veri bağlantısı yapılandırmak için düğmesini. Daha fazla bilgi için bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).

6.  Veritabanı parola gerektiriyorsa, seçin **Evet, hassas verileri bağlantı dizesine eklemek** seçenek düğmesine ve ardından **sonraki** düğmesi.

    > [!NOTE]
    >  Bir iletişim kutusu görüntülenirse, seçin **Evet** dosyayı projenize kaydetmek için.

7.  Üzerinde **sürümünüzü seçin** sayfasında, **Entity Framework 5.0** seçenek düğmesine ve ardından **sonraki** düğmesi.

    > [!NOTE]
    >  WCF hizmetleri ile Entity Framework 6'ın en son sürümü kullanmak için WCF Veri Hizmetleri Entity Framework sağlayıcısı NuGet paketini yüklemeniz gerekir. Bkz: [kullanarak WCF Veri Hizmetleri Entity Framework 6 + 5.6.0](http://blogs.msdn.com/b/odatateam/archive/2013/10/02/using-wcf-data-services-5-6-0-with-entity-framework-6.aspx).

8.  Üzerinde **veritabanı nesnelerinizi** sayfasında **tabloları** düğümü, select **müşteriler** onay kutusunu işaretleyin ve ardından **son** düğme.

     Varlık modeli diyagramı görüntülenir ve projenize bir NorthwindModel.edmx dosyası eklenir.

Sonraki adımda oluşturun ve veri hizmeti sınayın.

#### <a name="to-create-the-data-service"></a>Veri hizmetini oluşturmak için

1.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.

2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **Web** düğümünü ve ardından **WCF veri hizmeti 5.6** öğesi.

3.  İçinde **adı** metin kutusuna `NorthwindCustomers`ve ardından **Ekle** düğmesi.

     NorthwindCustomers.svc dosya görünür **Kod düzenleyicisinde**.

4.  İçinde **Kod düzenleyicisinde**, ilk bulun `TODO:` açıklama ve kodu aşağıdakilerle değiştirin:

     [!code-vb[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_1.cs)]

5.  Açıklamaları değiştirin `InitializeService` aşağıdaki kod ile olay işleyicisi:

     [!code-vb[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.vb)]
     [!code-csharp[WCFDataServiceWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework_2.cs)]

6.  Menü çubuğunda seçin **hata ayıklama**, **hata ayıklama olmadan Başlat** hizmetini çalıştırmak için. Bir tarayıcı penceresi açılır ve hizmet için XML şeması görüntülenir.

7.  İçinde **adresi** çubuğu, girin `Customers` NorthwindCustomers.svc, URL'sini sonunda ve ardından **ENTER** anahtarı.

     Müşteriler tablosundaki verilerin bir XML gösterimi görüntülenir.

    > [!NOTE]
    >  Bazı durumlarda, Internet Explorer verileri yanlışlıkla RSS akışı olarak yorumlar. RSS akışlarını görüntüleme seçeneğinin devre dışı bırakıldığından emin olmalısınız. Daha fazla bilgi için bkz: [sorun giderme hizmeti başvuruları](../data-tools/troubleshooting-service-references.md).

8.  Tarayıcı penceresini kapatın.

Sonraki adımlarda, hizmeti kullanmak üzere bir Windows Forms istemci uygulaması oluşturacaksınız.

## <a name="creating-the-client-application"></a>İstemci Uygulamasını Oluşturma
 İstemci uygulamasını oluşturmak için ikinci bir proje ekleyecek, projeye bir hizmet başvurusu ekleyecek, bir veri kaynağı yapılandıracak ve hizmetten alınan verileri görüntülemek üzere bir kullanıcı arabirimi oluşturacaksınız.

 İlk adımda, çözüme bir Windows Forms projesi ekleyecek ve bunu başlangıç projesi olarak ayarlayacaksınız.

#### <a name="to-create-the-client-application"></a>İstemci uygulamasını oluşturmak için

1.  Menü çubuğunda, dosya **Ekle**, **yeni proje**.

2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual Basic** veya **Visual C#** düğümü ve seçin **Windows** düğümü ve ardından seçin **Windows Forms uygulamasına**.

3.  İçinde **adı** metin kutusuna `NorthwindClient`ve ardından **Tamam** düğmesi.

4.  İçinde **Çözüm Gezgini**, seçin **NorthwindClient** proje düğümüne.

5.  Menü çubuğunda seçin **proje**, **başlangıç projesi olarak ayarla**.

Sonraki adımda, bir hizmet başvurusu ekleyecek [!INCLUDE[ss_data_service](../data-tools/includes/ss_data_service_md.md)] Web projesinde.

#### <a name="to-add-a-service-reference"></a>Hizmet başvurusu eklemek için

1.  Menü çubuğunda seçin **proje**, **hizmet Başvurusu Ekle**.

2.  İçinde **hizmet Başvurusu Ekle** iletişim kutusunda, seçin **bulma** düğmesi.

     NorthwindCustomers hizmeti için URL görünür **adresi** alan.

3.  Seçin **Tamam** hizmet Başvurusu Ekle düğmesi.

Sonraki adımda, veri bağlama hizmetine etkinleştirmek için bir veri kaynağı yapılandırır.

#### <a name="to-enable-data-binding-to-the-service"></a>Hizmete veri bağlamayı etkinleştirmek için

1.  Menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **veri kaynakları**.

2.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** düğmesi.

3.  Üzerinde **bir veri kaynağı türü seç** sayfasında **veri kaynağı Yapılandırma Sihirbazı**, seçin **nesne**ve ardından **sonraki** düğmesi .

4.  Üzerinde **veri nesneleri seçin** sayfasında **NorthwindClient** düğümünü genişletin ve ardından **NorthwindClient.ServiceReference1** düğümü.

5.  Seçin **müşteri** onay kutusunu işaretleyin ve ardından **son** düğmesi.

Sonraki adımda hizmetinden veri görüntüleyecek kullanıcı arabirimi oluşturacaksınız.

#### <a name="to-create-the-user-interface"></a>Kullanıcı arabirimini oluşturmak için

1.  İçinde **veri kaynakları** penceresinde kısayol menüsünü açın **müşteriler** düğümü seçin **kopyalama**.

2.  İçinde **Form1.vb** veya **Form1.cs** form tasarımcısı, kısayol menüsünü açın ve seçin **Yapıştır**.

     A <xref:System.Windows.Forms.DataGridView> denetimi, bir <xref:System.Windows.Forms.BindingSource> bileşeni ve bir <xref:System.Windows.Forms.BindingNavigator> bileşen forma eklenir.

3.  Seçin **CustomersDataGridView** denetim ve ardından **özellikleri** penceresi kümesi **yerleştirme** özelliğine **doldurun**.

4.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **Form1** düğümü seçin **görünümü kodu** kod düzenleyicisini açın ve aşağıdaki içeri aktarmaları veya ifadesine kullanarak eklemek için dosyanın üst kısmına:

    ```vb
    Imports NorthwindClient.ServiceReference1
    ```

    ```csharp
    using NorthwindClient.ServiceReference1;
    ```

5.  Aşağıdaki kodu ekleyin `Form1_Load` olay işleyicisi:

    ```vb
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
            Dim proxy As New NorthwindEntities _
    (New Uri("http://localhost:53161/NorthwindCustomers.svc/"))
            Me.CustomersBindingSource.DataSource = proxy.Customers
        End Sub
    ```

    ```csharp
    private void Form1_Load(object sender, EventArgs e)
    {
    NorthwindEntities proxy = new NorthwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc/"));
    this.CustomersBindingSource.DataSource = proxy.Customers;
    }

    ```

6.  İçinde **Çözüm Gezgini**, NorthwindCustomers.svc dosya için kısayol menüsünü açın ve seçin **tarayıcıda görüntüle**. Internet Explorer açılır ve hizmet için XML şeması görüntülenir.

7.  Internet Explorer adres çubuğundan URL'yi kopyalayın.

8.  4. adımda eklediğiniz kodda seçin `http://localhost:53161/NorthwindCustomers.svc/` ve kopyaladığınız URL'niz ile değiştirin.

9. Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat** uygulamayı çalıştırın. Müşteri bilgileri görüntülenir.

 Artık, NorthwindCustomers hizmetinden müşterilerin listesini görüntüleyen çalışır bir uygulamanız var. Ek veri hizmeti aracılığıyla kullanıma sunmak isterseniz değiştirebileceğiniz [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] Northwind veritabanı ek tablodan eklenecek.

Bir sonraki isteğe bağlı adımda hizmetin döndürdüğü verileri filtrelemeyi öğreneceksiniz.

## <a name="adding-filtering-capabilities"></a>Filtreleme Yetenekleri Ekleme
 Bu adımda uygulamayı, müşterinin şehir bilgisine göre verileri filtreleyecek şekilde özelleştireceksiniz.

#### <a name="to-add-filtering-by-city"></a>Şehir bilgisine göre filtreleme eklemek için

1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **Form1.vb** veya **Form1.cs** düğümü seçin **açmak**.

2.  Ekleme bir <xref:System.Windows.Forms.TextBox> denetim ve <xref:System.Windows.Forms.Button> gelen denetim **araç** forma.

3.  Kısayol menüsünü açın <xref:System.Windows.Forms.Button> denetlemek ve seçin **görünümü kodu**ve ardından aşağıdaki kodu ekleyin `Button1_Click` olay işleyicisi:

    ```vb
    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
            Dim proxy As New northwindEntities _
    (New Uri("http://localhost:53161/NorthwindCustomers.svc"))
            Dim city As String = TextBox1.Text

            If city <> "" Then
                Me.CustomersBindingSource.DataSource = From c In _
             proxy.Customers Where c.City = city
            End If

        End Sub
    ```

    ```csharp
    private void Button1_Click(object sender, EventArgs e)
    {
    ServiceReference1.northwindModel.northwindEntities proxy = new northwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc"));
    string city = TextBox1.Text;

    if (!string.IsNullOrEmpty(city)) {
    this.CustomersBindingSource.DataSource = from c in proxy.Customers where c.City == city;
    }

    }
    ```

4.  Önceki kodla `http://localhost:53161/NorthwindCustomers.svc` URL'den ile `Form1_Load` olay işleyicisi.

5.  Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat** uygulamayı çalıştırın.

6.  Metin kutusuna girin **Londra**ve ardından düğmesini seçin. Yalnızca Londralı müşteriler görüntülenir.

## <a name="see-also"></a>Ayrıca bkz.

- [Windows Communication Foundation Hizmetleri ve Visual Studio'da WCF Veri Hizmetleri](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
- [Nasıl yapılır: ekleme, güncelleştirme veya bir WCF veri hizmeti başvurusunu kaldırma](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)