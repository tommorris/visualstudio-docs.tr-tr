---
title: 'İzlenecek yol: bir Silverlight Web parçası oluşturma SharePoint için OData görüntüleyen | Microsoft Docs'
ms.custom: ''
ms.date: 02/22/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.SPE.SilverlightWebPart
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 019c1d4b20f1d7a53fc68ef561d45989e93eee28
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint"></a>İzlenecek yol: SharePoint için OData Görüntüleyen bir Silverlight Web Parçası Oluşturma
  SharePoint 2010 listesi verilerini OData yoluyla kullanıma sunar. SharePoint'te OData hizmeti ListData.svc RESTful hizmeti tarafından uygulanır. Bu kılavuzda Silverlight uygulamasını barındıran bir SharePoint web bölümü oluşturulacağını gösterir. Silverlight uygulaması ListData.svc kullanarak SharePoint duyuru listesi bilgilerini görüntüler. Daha fazla bilgi için bkz: [SharePoint Foundation REST arabirimini](http://go.microsoft.com/fwlink/?LinkId=225999) ve [açık veri Protokolü](http://go.microsoft.com/fwlink/?LinkId=226000).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Microsoft Windows ve SharePoint sürümleri desteklenir. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
##  <a name="creating-a-silverlight-application-and-silverlight-web-part"></a>Silverlight uygulaması ve Silverlight Web parçası oluşturma  
 İlk olarak, Visual Studio'da bir Silverlight uygulaması oluşturun. Silverlight uygulaması ListData.svc hizmetini kullanarak SharePoint duyuruları listeden verileri alır.  
  
> [!NOTE]  
>  Silverlight 4.0 önce hiçbir sürümü, SharePoint listesi verileri başvurmak için gerekli arabirimleri destekler.  
  
#### <a name="to-create-a-silverlight-application-and-silverlight-web-part"></a>Silverlight uygulaması ile Silverlight web bölümü oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje** görüntülemek için **yeni proje** iletişim kutusu.  
  
2.  Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010** düğümü.  
  
3.  Şablonlar bölmesinde seçin **SharePoint 2010 Silverlight Web Bölümü** şablonu.  
  
4.  İçinde **adı** kutusuna **SLWebPartTest** ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** iletişim kutusu görüntülenir.  
  
5.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, istediğiniz site tanımı hata ayıklamak için SharePoint server site için URL'yi girin veya varsayılan konumu kullanın (http://*sistem adı*/) .  
  
6.  İçinde **bu SharePoint çözüm için güven düzeyini nedir?** bölümünde, seçin **Grup çözümü olarak dağıtma** seçenek düğmesi.  
  
     Bu örnek bir Grup çözümü kullansa da, Silverlight web parçası projeleri grubu ya da korumalı çözümler olarak dağıtılabilir. Korumalı çözümler ve Grup çözümleri hakkında daha fazla bilgi için bkz: [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  İçinde **nasıl Silverlight Web Bölümü ilişkilendirmek istediğiniz** bölümünü **Silverlight yapılandırma bilgilerini belirtmek** sayfasında, **yeni bir Silverlight projesi oluşturun ve web bölümüyle ilişkilendirmek** seçenek düğmesi.  
  
8.  Değişiklik **adı** için **SLApplication**ayarlayın **dil** ya da **Visual Basic** veya **Visual C#**, ve ardından **Silverlight sürümü** için **Silverlight 4.0**.  
  
9. Seçin **son** düğmesi. Projeleri görünür **Çözüm Gezgini**.  
  
     Çözüm iki proje içerir: Silverlight uygulaması ile bir Silverlight web bölümü. Silverlight uygulaması alır ve SharePoint listesi verileri görüntüler ve Silverlight web bölümü, SharePoint'te görüntülemek etkinleştirme Silverlight uygulaması barındırır.  
  
##  <a name="customizing-the-silverlight-application"></a>Silverlight uygulaması özelleştirme  
 Kod ve tasarım öğeleri için Silverlight uygulaması ekleyebilirsiniz.  
  
#### <a name="to-customize-the-silverlight-application"></a>Silverlight uygulaması özelleştirmek için  
  
1.  Bir derleme başvurusu System.Windows.Data için Silverlight uygulaması ekleyin. Daha fazla bilgi için bkz: [nasıl yapılır: başvuru ekleme veya kaldırma Başvurusu Ekle iletişim kutusunu kullanarak](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).  
  
2.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **başvuruları**ve ardından **hizmet Başvurusu Ekle**.  
  
    > [!NOTE]  
    >  Visual Basic kullanıyorsanız, seçmelisiniz **tüm dosyaları göster** en üstündeki simgesi **Çözüm Gezgini** görüntülemek için **başvuruları** düğümü.  
  
3.  Adresi kutusunda **hizmet Başvurusu Ekle** iletişim kutusunda, SharePoint sitenizi URL'sini girin **http://MySPSite**ve ardından **Git** düğmesi.  
  
     Silverlight SharePoint OData hizmeti ListData.svc bulduğunda, tam hizmet URL'si ile adresini değiştirir. Bu örnek için http://myserver hale http://myserver/_vti_bin/ListData.svc.  
  
4.  Seçin **Tamam** projesine hizmet Başvurusu Ekle düğmesi ve varsayılan hizmet adı, ServiceReference1 kullanın.  
  
5.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
6.  Projenin SharePoint hizmetini temel alan yeni bir veri kaynağı ekleyin. Bu, menü çubuğunda, tercih **Görünüm**, **diğer pencereler**, **veri kaynakları**.  
  
     **Veri kaynakları** penceresi tüm görevler, bildirimler ve takvim gibi kullanılabilir SharePoint listesi verileri gösterir.  
  
7.  Duyurular listesi verileri Silverlight uygulamaya ekleyin. ' Ndan "Duyuruları" sürükleyebilirsiniz **veri kaynakları** Silverlight tasarımcıya penceresi.  
  
     Bu SharePoint sitesinin duyuruları listeye bağlı bir kılavuz denetimi oluşturur.  
  
8.  Kılavuz denetim Silverlight sayfaya sığacak şekilde yeniden boyutlandırın.  
  
9. MainPage.xaml kod dosyasında (MainPage.xaml.cs Visual C# için) veya Visual Basic MainPage.xaml.vb, şu ad alanı başvurularını ekleyin.  
  
    ```vb  
    ' Add the following three Imports statements.  
    Imports SLApplication.ServiceReference1  
    Imports System.Windows.Data  
    Imports System.Data.Services.Client  
    ```  
  
    ```csharp  
    // Add the following three using statements.  
    using SLApplication.ServiceReference1;  
    using System.Windows.Data;  
    using System.Data.Services.Client;  
    ```  
  
10. Aşağıdaki değişken bildirimlerini sınıfı üstünde ekleyin.  
  
    ```vb  
    Private context As TeamSiteDataContext  
    Private myCollectionViewSource As CollectionViewSource  
    Private announcements As New DataServiceCollection(Of AnnouncementsItem)()  
    ```  
  
    ```csharp  
    private TeamSiteDataContext context;  
    private CollectionViewSource myCollectionViewSource;  
    DataServiceCollection<AnnouncementsItem> announcements = new DataServiceCollection<AnnouncementsItem>();  
    ```  
   
11. Değiştir `UserControl_Loaded` aşağıdaki yordama.  
  
    ```vb  
    Private Sub UserControl_Loaded_1(sender As Object, e As RoutedEventArgs)  
        ' The URL for the OData service.  
        ' Replace <server name> in the next line with the name of your SharePoint server.  
        context = New TeamSiteDataContext(New Uri("http://<server name>/_vti_bin/ListData.svc"))  
  
        ' Do not load your data at design time.  
        If Not System.ComponentModel.DesignerProperties.GetIsInDesignMode(Me) Then  
            'Load your data here and assign the results to the CollectionViewSource.  
            myCollectionViewSource =   DirectCast(Me.Resources("announcementsViewSource"), System.Windows.Data.CollectionViewSource)  
            announcements.LoadCompleted += New EventHandler(Of LoadCompletedEventArgs)(AddressOf announcements_LoadCompleted)  
            announcements.LoadAsync(context.Announcements)  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void UserControl_Loaded_1(object sender, RoutedEventArgs e)  
    {  
        // The URL for the OData service.  
        // Replace <server name> in the next line with the name of your   
        // SharePoint server.  
        context = new TeamSiteDataContext(new Uri("http://ServerName>/_vti_bin/ListData.svc"));  
  
        // Do not load your data at design time.  
        if (!System.ComponentModel.DesignerProperties.GetIsInDesignMode(this))  
        {  
            //Load your data here and assign the results to the CollectionViewSource.  
            myCollectionViewSource = (System.Windows.Data.CollectionViewSource)this.Resources["announcementsViewSource"];  
            announcements.LoadCompleted += new EventHandler<LoadCompletedEventArgs>(announcements_LoadCompleted);  
            announcements.LoadAsync(context.Announcements);  
        }  
    }  
    ```  
     Değiştirdiğinizden emin olun *ServerName* yer tutucu SharePoint çalıştıran sunucunuzun adını içeren.  
  
12. Hata işleme yordamını ekleyin.  
  
    ```vb  
    Private Sub announcements_LoadCompleted(sender As Object, e As LoadCompletedEventArgs)  
        ' Handle any errors.  
        If e.[Error] Is Nothing Then  
            myCollectionViewSource.Source = announcements  
        Else  
            MessageBox.Show(String.Format("ERROR: {0}", e.[Error].Message))  
        End If  
    End Sub  
  
    ```  
  
    ```csharp  
    void announcements_LoadCompleted(object sender, LoadCompletedEventArgs e)  
    {  
        // Handle any errors.  
        if (e.Error == null)  
        {  
            myCollectionViewSource.Source = announcements;  
        }  
        else  
        {  
            MessageBox.Show(string.Format("ERROR: {0}", e.Error.Message));  
        }  
    }  
    ```  
       
## <a name="modifying-the-silverlight-web-part"></a>Silverlight Web bölümünü değiştirme  
 Silverlight hata ayıklamayı etkinleştirmek için Silverlight web parçası projesinde özelliğini değiştirin.  
  
#### <a name="to-modify-the-silverlight-web-part"></a>Silverlight web bölümünü değiştirmek için  
  
1.  Silverlight web parçası projesinin kısayol menüsünü açın (**SLWebPartTest**) ve ardından **özellikleri**.  
  
2.  İçinde **özellikleri** penceresinde, seçin **SharePoint** sekmesi.  
  
3.  Henüz seçili değilse seçin **(komut dosyası hata ayıklaması yerine) etkinleştirmek Silverlight'ta hata ayıklama** onay kutusu.  
  
4.  Projeyi kaydedin.  
  
##  <a name="testing-the-silverlight-web-part"></a>Silverlight Web parçası test etme  
 Yeni bir Silverlight web bölümü SharePoint, SharePoint listesi verileri düzgün görüntülediğinden emin olmak için test edin.  
  
#### <a name="to-test-the-silverlight-web-part"></a>Silverlight web bölümü test etmek için  
  
1.  Derleme ve SharePoint çözüm çalıştırmak için F5 tuşuna seçin.  
  
2.  SharePoint, üzerinde **Site eylemleri** menüsünde seçin **yeni sayfa**.  
  
3.  İçinde **yeni sayfa** iletişim kutusunda, bir başlık girin **SL Web Bölümü Test**ve ardından **oluşturma** düğmesi.  
  
4.  Sayfa Tasarımcısı'nda üzerinde **düzenleme araçları** sekmesinde, seçin **Ekle**.  
  
5.  Sekme şeridinde seçin **Web Bölümü**.  
  
6.  İçinde **kategorileri** kutusunda, seçin **özel** klasör.  
  
7.  İçinde **Web Bölümleri** listesinde, Silverlight web bölümü seçin ve ardından **Ekle** Designer'a web bölümü eklemek için düğmesi.  
  
8.  Tüm eklemeleri web sayfası yaptıktan sonra Seç **sayfa** sekmesini ve ardından **Kaydet ve Kapat** araç çubuğu düğmesini.  
  
     Silverlight web bölümü artık SharePoint sitesinden duyuru verileri görüntüleme. Varsayılan olarak, sayfa SharePoint sitesi sayfalarını listesinde depolanır.  
  
    > [!NOTE]  
    >  Etki alanları arasında Silverlight'ta verilere erişirken, Silverlight web uygulamaları yararlanmak için kullanılan güvenlik güvenlik açıklarına karşı korur. Silverlight'ın uzak verilere erişirken sorun yaşarsanız bkz [bir hizmet kullanılabilir etki alanı sınırlar boyunca yapma](http://go.microsoft.com/fwlink/?LinkId=223276).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint için Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [SharePoint Çözüm Paketlerini Dağıtma, Yayımlama ve Yükseltme](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md)  
  
  
