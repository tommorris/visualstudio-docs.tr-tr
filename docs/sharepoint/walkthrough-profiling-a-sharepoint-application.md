---
title: "İzlenecek yol: bir SharePoint uygulama profili oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, profiling
- performance testing [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, performance testing
- profiling [SharePoint development in Visual Studio]
ms.assetid: 0b19d4b7-5fcc-42a2-b411-96eccd00137f
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0b2785e69bbfd6dff17f73b9840b88ad48454e0b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-profiling-a-sharepoint-application"></a>İzlenecek Yol: SharePoint Uygulaması için Profil Oluşturma
  Bu kılavuz, profil oluşturma araçları Visual Studio'da SharePoint uygulaması performansını iyileştirmek için nasıl kullanılacağını gösterir. Örnek Uygulama özellik olay alıcısı performansını düşürür bir boşta döngü içeren bir SharePoint özelliğini olay alıcıdır. Visual Studio profil oluşturucu bulun ve proje en pahalı (yavaş gerçekleştirerek) parçası olarak da bilinen ortadan kaldırmanıza olanak tanır *etkin yolunuzda*.  
  
 Bu kılavuz aşağıdaki görevler gösterilmiştir:  
  
-   [Bir özellik ve özellik olay alıcısı ekleme](#BKMK_AddFtrandFtrEvntReceiver).  
  
-   [Yapılandırma ve SharePoint uygulaması dağıtma](#BKMK_ConfigSharePointApp).  
  
-   [SharePoint uygulaması çalıştıran](#BKMK_RunSPApp).  
  
-   [Görüntüleme ve profil oluşturma sonuçları yorumlayarak](#BKMK_ViewResults).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   Microsoft Windows ve SharePoint sürümleri desteklenir. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
## <a name="creating-a-sharepoint-project"></a>SharePoint Projesi Oluşturma  
 İlk olarak, bir SharePoint projesi oluşturun.  
  
#### <a name="to-create-a-sharepoint-project"></a>Bir SharePoint projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje** görüntülemek için **yeni proje** iletişim kutusu.  
  
2.  Genişletme **SharePoint** ya da düğümünde **Visual C#** veya **Visual Basic**ve ardından **2010** düğümü.  
  
3.  Şablonlar bölmesinde seçin **SharePoint 2010 proje** şablonu.  
  
4.  İçinde **adı** kutusuna **ProfileTest**ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
5.  Üzerinde **hata ayıklama için site ve güvenlik düzeyini belirtmek** sayfasında, istediğiniz site tanımı hata ayıklamak için SharePoint server site için URL'yi girin veya varsayılan konumu kullanın (http://*sistem adı*/) .  
  
6.  İçinde **bu SharePoint çözüm için güven düzeyini nedir?** bölümünde, seçin **Grup çözümü olarak dağıtma** seçenek düğmesi.  
  
     Şu anda, yalnızca profili küme çözümleri kullanabilirsiniz. Küme çözümleri karşı korumalı çözümler hakkında daha fazla bilgi için bkz: [Korumalı çözüm değerlendirmeleri](../sharepoint/sandboxed-solution-considerations.md).  
  
7.  Seçin **son** düğmesi. Proje görünür **Çözüm Gezgini**.  
  
##  <a name="BKMK_AddFtrandFtrEvntReceiver"></a>Bir özellik ve özellik olay alıcısı ekleme  
 Ardından, bir özellik proje özelliği için olay alıcı birlikte ekleyin. Bu olay alıcısı profili için kodu içerir.  
  
#### <a name="to-add-a-feature-and-feature-event-receiver"></a>Bir özellik ve özellik olay alıcısı eklemek için  
  
1.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **özellikleri** düğümü seçin **Özellik Ekle**ve adı varsayılan değerinde bırakın **Feature1**.  
  
2.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **Feature1**ve ardından **olay alıcısı Ekle**.  
  
     Bu özellik ile çeşitli kılınan olay işleyicileri için bir kod dosyası ekler ve dosyayı düzenlemek için açar.  
  
3.  Olay alıcı sınıfında aşağıdaki değişken bildirimlerini ekleyin.  
  
    ```vb  
    ' SharePoint site/subsite.  
    Private siteUrl As String = "http://localhost"  
    Private webUrl As String = "/"  
    ```  
  
    ```csharp  
    // SharePoint site/subsite.  
    private string siteUrl = "http://localhost";  
    private string webUrl = "/";  
    ```  
  
4.  Değiştir `FeatureActivated` aşağıdaki kodla yordamı.  
  
    ```vb  
    Public Overrides Sub FeatureActivated(properties As SPFeatureReceiverProperties)  
        Try  
            Using site As New SPSite(siteUrl)  
                Using web As SPWeb = site.OpenWeb(webUrl)  
                    ' Reference the lists.  
                    Dim announcementsList As SPList = web.Lists("Announcements")  
  
                    ' Add a new announcement to the Announcements list.  
                    Dim listItem As SPListItem = announcementsList.Items.Add()  
                    listItem("Title") = "Activated Feature: " & Convert.ToString(properties.Definition.DisplayName)  
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was activated on: " & DateTime.Now.ToString()  
                    ' Waste some time.  
                    TimeCounter()  
                    ' Update the list.  
                    listItem.Update()  
                End Using  
            End Using  
  
        Catch e As Exception  
            Console.WriteLine("Error: " & e.ToString())  
        End Try  
    End Sub  
    ```  
  
    ```csharp  
    public override void FeatureActivated(SPFeatureReceiverProperties properties)  
    {  
        try  
        {  
            using (SPSite site = new SPSite(siteUrl))  
            {  
                using (SPWeb web = site.OpenWeb(webUrl))  
                {  
                    // Reference the lists.  
                    SPList announcementsList = web.Lists["Announcements"];  
  
                    // Add a new announcement to the Announcements list.  
                    SPListItem listItem = announcementsList.Items.Add();  
                    listItem["Title"] = "Activated Feature: " + properties.Definition.DisplayName;  
                    listItem["Body"] = properties.Definition.DisplayName + " was activated on: " +   
    DateTime.Now.ToString();  
                    // Waste some time.  
                    TimeCounter();  
                    // Update the list.  
                    listItem.Update();                          
                }  
            }  
        }  
  
        catch (Exception e)  
        {  
            Console.WriteLine("Error: " + e.ToString());  
        }  
    }  
    ```  
  
5.  Aşağıdaki yordamı ekleyin `FeatureActivated`yordamı.  
  
    ```vb  
  
    Public Sub TimeCounter()  
        Dim result As Integer  
        For i As Integer = 0 To 99999  
            For j As Integer = 0 To 9999  
                result = i * j  
            Next j  
        Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void TimeCounter()  
    {  
        for (int i = 0; i < 100000; i++)  
        {  
            for (int j = 0; j < 10000; j++)  
            {  
                int result = i * j;  
            }  
        }  
    }  
    ```  
  
6.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın (**ProfileTest**) ve ardından **özellikleri**.  
  
7.  İçinde **özellikleri** iletişim kutusunda, seçin **SharePoint** sekmesi.  
  
8.  İçinde **etkin Dağıtım Yapılandırması** listesinde, seçin **Hayır etkinleştirme**.  
  
     Bu dağıtım yapılandırması seçerek SharePoint özelliğinde daha sonra el ile etkinleştirebilir sağlar.  
  
9. Projeyi kaydedin.  
  
##  <a name="BKMK_ConfigSharePointApp"></a>Yapılandırma ve SharePoint uygulaması dağıtma  
 SharePoint Proje hazırdır, yapılandırın ve SharePoint sunucusuna dağıtın.  
  
#### <a name="to-configure-and-deploy-the-sharepoint-application"></a>Yapılandırma ve SharePoint uygulaması dağıtma  
  
1.  Üzerinde **Çözümle** menüsünde seçin **başlatma performans Sihirbazı**.  
  
2.  ' Nın sayfasında **performans Sihirbazı**, olarak profil oluşturma yöntemi bırakın **CPU örnekleme** ve **sonraki** düğmesi.  
  
     Bir profil oluşturma yöntemlerini durumlarda profil daha gelişmiş kullanılabilir. Daha fazla bilgi için bkz: [anlama performans koleksiyon yöntemleri](/visualstudio/profiling/understanding-performance-collection-methods).  
  
3.  Sayfasında iki **performans Sihirbazı**, profil hedefi olarak bırakın **ProfileTest** ve **sonraki** düğmesi.  
  
     Birden çok proje bir çözüm varsa, bunlar bu listede görüntülenir.  
  
4.  Sayfasında üç **performans Sihirbazı**, Temizle **etkinleştirmek katman etkileşim profil** onay kutusunu işaretleyin ve ardından **sonraki** düğmesi.  
  
     Katman etkileşim profil oluşturma (TIP) özelliği, bu sorgu veritabanları uygulamaların performansını ölçmek için yararlıdır ve kaç kez göstermek için bir web sayfası istendi. Bu veriler bu örnek için gerekli olmadığından, biz bu özellik izin vermez.  
  
5.  Sayfasında dört **performans Sihirbazı**, bırakın **Sihirbaz tamamlandıktan sonra profil oluşturmayı Başlat** seçili kutuyu işaretleyin ve ardından **son** düğmesi.  
  
     Sihirbazın sunucu uygulama profilini sağlar, görüntüler **performans Gezgini** penceresi ve ardından derlemeleri dağıtır ve SharePoint uygulaması çalıştırır.  
  
##  <a name="BKMK_RunSPApp"></a>SharePoint uygulaması çalıştırma  
 SharePoint'teki özelliği etkinleştir tetikleme `FeatureActivation` çalıştırmak için olay kod.  
  
#### <a name="to-run-the-sharepoint-application"></a>SharePoint uygulamayı çalıştırmak için  
  
1.  SharePoint'te açmak **Site eylemleri** menüsünde ve ardından **Site Ayarları**.  
  
2.  İçinde **Site eylemleri** listesinde, seçin **site özelliklerini Yönet** bağlantı.  
  
3.  İçinde **özellikleri** listesinde, seçin **etkinleştirme** düğmesine **ProfileTest Feature1**.  
  
     Yapıldığında bir duraklama adlı boşta döngü nedeniyle bunu `FeatureActivated` işlevi.  
  
4.  Üzerinde **hızlı başlatma** çubuğu, seçin **listeler** ve ardından **listeler** listesinde, seçin **duyuruları**.  
  
     Yeni bir duyuru özelliği etkinleştirildi belirten listesine eklendiğini dikkat edin.  
  
5.  SharePoint sitesi kapatın.  
  
     SharePoint kapattıktan sonra Profil Oluşturucu oluşturur ve bir örnek profil oluşturma raporu görüntüler ve .vsp dosyası olarak kaydeder **ProfileTest** projenin klasör.  
  
##  <a name="BKMK_ViewResults"></a>Görüntüleme ve profil oluşturma sonuçları yorumlama  
 Çalıştırın ve SharePoint uygulama profili, test sonuçlarını görüntüleyin.  
  
#### <a name="to-view-and-interpret-the-profiling-results"></a>Görüntülemek ve profil oluşturma sonuçları yorumlamak için  
  
1.  İçinde **en tek tek iş yapan işlevlerin** bölüm örnek profil oluşturma raporu dikkat `TimeCounter` listesinin en üstüne olan.  
  
     Bu konumu belirten `TimeCounter` uygulamada büyük performans sorunları biri anlamı örnekleri, en yüksek sayıda işlevleriyle biri. Bu durum değil tanıtım amacıyla bu şekilde tasarlanmış bilerek olduğundan, ancak önler.  
  
2.  İçinde **en tek tek iş yapan işlevlerin** bölümünde, seçin `ProcessRequest` Maliyet dağıtımı görüntülemek için bağlantıyı `ProcessRequest` işlevi.  
  
     İçinde **işlevleri adlı** bölümü `ProcessRequest`, dikkat **FeatureActiviated** işlevi listelenmiş olarak en ucuz işlevini çağırdı.  
  
3.  İçinde **işlevleri adlı** bölümünde, seçin **FeatureActivated** düğmesi.  
  
     İçinde **işlevleri adlı** bölümü **FeatureActivated**, `TimeCounter` işlevi listelenmiş olarak en ucuz işlevini çağırdı. İçinde **işlevi kod görünümü** bölmesi, vurgulanmış kodu (`TimeCounter`) etkin olduğunu ve burada düzeltilmesi gereken gösterir.  
  
4.  Profil oluşturma raporu örnek kapatın.  
  
     Herhangi bir zamanda yeniden raporu görüntülemek için .vsp dosyasında açma **performans Gezgini** penceresi.  
  
## <a name="fixing-the-code-and-reprofiling-the-application"></a>Kod çözme ve uygulama Reprofiling  
 SharePoint uygulama etkin nokta işlevinde belirlenmiştir, bunu düzeltin.  
  
#### <a name="to-fix-the-code-and-reprofile-the-application"></a>Kod onarın ve uygulama reprofile  
  
1.  Özellik olay alıcı kod çıkışı açıklama `TimeCounter` yöntem çağrısı `FeatureActivated` adlı öğesinden önlemek için.  
  
2.  Projeyi kaydedin.  
  
3.  İçinde **performans Gezgini**hedefler klasörünü açın ve ardından **ProfileTest** düğümü.  
  
4.  Üzerinde **performans Gezgini** araç, **Eylemler** sekmesinde, seçin **Başlat profil** düğmesi.  
  
     Uygulama reprofiling önce profil özelliklerinden herhangi birini değiştirmek isterseniz seçin **performans Sihirbazı başlatın** yerine düğmesine tıklayın.  
  
5.  ' Ndaki yönergeleri izleyin **SharePoint uygulaması çalıştıran** bölümü, daha önce bu konuda.  
  
     Boşta döngü çağrısı ortadan göre özelliği çok daha hızlı etkinleştirmelisiniz. Profil oluşturma örnek raporu bu yansıtmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans Gezgini](/visualstudio/profiling/performance-explorer)   
 [Performans oturumuna genel bakış](/visualstudio/profiling/performance-session-overview)   
 [Performans profili oluşturma Başlangıç Kılavuzu](/visualstudio/profiling/beginners-guide-to-performance-profiling)   
 [Visual Studio Profil Oluşturucu ile uygulama engelleri bulun](http://go.microsoft.com/fwlink/?LinkID=137266)  
  
  