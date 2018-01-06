---
title: "Nasıl yapılır: özel yerel ayara sahip olan bir projeyi yayımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, localized projects
- locales, publishing for
- deploying applications [ClickOnce], localized projects
- locales, deploying for
- publishing localized projects
- macros, deploying with
- macros, publishing with
ms.assetid: 7c4cd83a-f985-4c85-9022-fadb5dbd2b39
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: b2560275ae08a9a860d62f11e0fb011e5e7a5b31
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-publish-a-project-that-has-a-specific-locale"></a>Nasıl yapılır: Özel Yerel Ayara Sahip Olan Bir Projeyi Yayımlama
Bir uygulamanın farklı yerel ayarlara sahip bileşenleri içeren için seyrek değil. Bu senaryoda, birkaç projesi olan bir çözümü oluşturun ve sonra her yerel ayar için ayrı projeleri yayımlamak. Bu yordam bir makrosu 'tr' yerel ayarını kullanarak bir çözümde ilk projeyi yayımlamak için nasıl kullanılacağını gösterir. 'Tr' dışındaki yerel ayar ile bu yordamı denemek istiyorsanız, ayarladığınızdan emin olun `localeString` (örneğin, 'de' veya 'de-DE') kullanarak yerel eşleşecek şekilde makrosu içinde.  
  
> [!NOTE]
>  Bu makrosu kullandığınızda, yayımlama konumu geçerli bir URL veya Evrensel Adlandırma Kuralı (UNC) paylaşım olmalıdır. Ayrıca, Internet Information Services (IIS) bilgisayarınızda yüklü gerekir. IIS, yüklemek için **Başlat** menüsünde tıklatın **Denetim Masası**. Çift **Program Ekle veya Kaldır**. İçinde **Program Ekle veya Kaldır**, tıklatın **Windows Bileşenlerini Ekle/Kaldır**. İçinde **Windows Bileşenleri Sihirbazı'nı**seçin **Internet Information Services (IIS)** onay kutusuna **bileşenleri** listesi. Ardından **son** sihirbazı kapatın.  
  
### <a name="to-create-the-publishing-macro"></a>Yayımlama makrosu oluşturmak için  
  
1.  Makro Gezgini'ni açmak için **Araçları** menüsündeki **makroları**ve ardından **makrosu Explorer**.  
  
2.  Yeni bir makro modülü oluşturun. Makro Gezgininde seçin **MyMacros**. Üzerinde **Araçları** menüsündeki **makroları**ve ardından **yeni makro modülü**. Modül adı **PublishSpecificCulture olarak**.  
  
3.  Makro Gezgininde genişletin **MyMacros** düğümünü ve ardından açın **PublishAllProjects** çift tıklatarak Modülü (veya **Araçları** menüsündeki **Makroları**ve ardından **makroları IDE**).  
  
4.  Makrolar IDE'de aşağıdaki kodu modüle ekleyin `Import` deyimleri:  
  
    ```vb  
    Module PublishSpecificCulture  
        Sub PublishProjectFirstProjectWithEnLocale()  
            ' Note: You should publish projects by using the IDE at least once  
            ' before you use this macro. Items such as the certficate and the   
            ' security zone must be set.  
            Dim localeString As String = "en"  
  
            ' Get first project.  
            Dim proj As Project = DTE.Solution.Projects.Item(1)  
            Dim publishProperties As Object = proj.Properties.Item("Publish").Value  
  
            ' GenerateManifests and SignManifests must always be set to  
            ' True for publishing to work.   
            proj.Properties.Item("GenerateManifests").Value = True  
            proj.Properties.Item("SignManifests").Value = True  
  
            'Set the publish language.  
            'This will set the deployment language and pick up all   
            ' en resource dlls:  
            Dim originalTargetCulture As String = _  
                publishProperties.Item("TargetCulture").Value  
            publishProperties.Item("TargetCulture").Value = localeString  
  
            'Append 'en' to end of publish, install, and update URLs if needed:  
            Dim originalPublishUrl As String = _  
                publishProperties.Item("PublishUrl").Value  
            Dim originalInstallUrl As String = _  
                publishProperties.Item("InstallUrl").Value  
            Dim originalUpdateUrl As String = _  
                publishProperties.Item("UpdateUrl").Value  
            publishProperties.Item("PublishUrl").Value = _  
                AppendStringToUrl(localeString, New Uri(originalPublishUrl))  
            If originalInstallUrl <> String.Empty Then  
                publishProperties.Item("InstallUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalInstallUrl))  
            End If  
            If originalUpdateUrl <> String.Empty Then  
                publishProperties.Item("UpdateUrl").Value = _  
                    AppendStringToUrl(localeString, New Uri(originalUpdateUrl))  
            End If  
            proj.Save()  
  
            Dim slnbld2 As SolutionBuild2 = _  
                CType(DTE.Solution.SolutionBuild, SolutionBuild2)  
            slnbld2.Clean(True)  
  
            slnbld2.BuildProject( _  
            proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
            proj.UniqueName, True)  
  
            ' Only publish if build is successful.  
            If slnbld2.LastBuildInfo <> 0 Then  
                MsgBox("Build failed for " & proj.UniqueName)  
            Else  
                slnbld2.PublishProject( _  
                proj.ConfigurationManager.ActiveConfiguration.ConfigurationName, _  
                proj.UniqueName, True)  
                If slnbld2.LastPublishInfo = 0 Then  
                    MsgBox("Publish succeeded for " & proj.UniqueName _  
                    & vbCrLf & "." _  
                    & " Publish Language was '" & localeString & "'.")  
                Else  
                    MsgBox("Publish failed for " & proj.UniqueName)  
                End If  
            End If  
  
            ' Return URLs and target culture to their previous state.  
            publishProperties.Item("PublishUrl").Value = originalPublishUrl  
            publishProperties.Item("InstallUrl").Value = originalInstallUrl  
            publishProperties.Item("UpdateUrl").Value = originalUpdateUrl  
            publishProperties.Item("TargetCulture").Value = originalTargetCulture  
            proj.Save()  
        End Sub  
  
        Private Function AppendStringToUrl(ByVal str As String, _  
        ByVal baseUri As Uri) As String  
            Dim returnValue As String = baseUri.OriginalString  
            If baseUri.IsFile OrElse baseUri.IsUnc Then  
                returnValue = IO.Path.Combine(baseUri.OriginalString, str)  
            Else  
                If Not baseUri.ToString.EndsWith("/") Then  
                    returnValue = baseUri.OriginalString & "/" & str  
                Else  
                    returnValue = baseUri.OriginalString & str  
                End If  
            End If  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
5.  Makrolar IDE'yi kapatın. Odağı Visual Studio'ya döndürür.  
  
### <a name="to-publish-a-project-for-a-specific-locale"></a>Belirli bir yerel ayar için bir proje yayımlamak için  
  
1.  Visual Basic Windows uygulama projesi oluşturmak için **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **Windows uygulaması** gelen **Visual Basic** düğümü. Proje adı **PublishLocales'i**.  
  
3.  Form1'ı tıklatın. İçinde **özellikleri** penceresi altında **tasarım**, değiştirme **dil** özelliğinden **(varsayılan)** için **İngilizce**. Değişiklik **metin** forma özelliğinin **MyForm**.  
  
     Gerekene kadar yerelleştirilmiş kaynak dll oluşturulmaz unutmayın. Örneğin, yeni yerel belirttikten sonra form veya denetimlerinden birinin metnini değiştirdiğinizde oluşturulur.  
  
4.  Visual Studio IDE kullanarak PublishLocales'i yayımlayın.  
  
     İçinde **Çözüm Gezgini**, PublishLocales'i seçin. Üzerinde **proje** menüsünde, select **özellikleri**. Proje Tasarımcısı'nda üzerinde **Yayımla** sayfasında, bir yayımlama konumu belirtin **http://localhost/PublishLocales**ve ardından **Şimdi Yayımla**.  
  
     Yayımla Web sayfası göründüğünde, kapatın. (Bu adım için projeyi yayımlamak yeterlidir; yüklemeniz gerekmez.)  
  
5.  Visual Studio komut istemi penceresinde makrosu çağırarak PublishLocales'i yeniden yayımlayın. Komut İstemi penceresini görüntülemek için **Görünüm** menüsündeki **diğer pencereler** ve ardından **komut penceresi**, veya CTRL + ALT + A basın. Komut İstemi penceresinde yazın `macros`; otomatik tamamlama kullanılabilir makrolar listesini sağlar. Aşağıdaki makro seçin ve ENTER tuşuna basın:  
  
     `Macros.MyMacros.PublishSpecificCulture.PublishProjectFirstProjectWithEnLocale`  
  
6.  Yayımlama işlemi başarılı olduğunda, "Yayımla PublishLocales\PublishLocales.vbproj için başarılı oldu. belirten bir ileti oluşturur Yayımlama dili 'tr' idi. " Tıklatın **Tamam** ileti kutusunda. Yayımla Web sayfası görüntülendiğinde **yükleme**.  
  
7.  C:\Inetpub\wwwroot\PublishLocales\en içine bakın. Bildirimler, setup.exe ve Yayımla Web sayfası dosyası yerelleştirilmiş kaynak DLL'si yanı sıra gibi yüklü dosyaların görmelisiniz. (Varsayılan olarak ClickOnce exe ve DLL'ler .deploy uzantısı ekler; dağıtımdan sonra bu uzantıyı kaldırabilirsiniz.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Makrolar geliştirme ortamı](http://msdn.microsoft.com/en-us/d23105d8-34fe-4ad9-8278-fae2c660aeac)   
 [Makro Gezgini penceresi](http://msdn.microsoft.com/en-us/762169e6-f83f-44b4-bffa-d0f107cae9a3)   
 [Nasıl yapılır: Düzenle ve makrolar program aracılığıyla oluşturma](http://msdn.microsoft.com/en-us/6716f820-1feb-48ad-a718-27eb6b473c5a)