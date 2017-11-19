---
title: "Visual Studio'da SharePoint araçları için hata ayıklama uzantıları | Microsoft Docs"
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
helpviewer_keywords: SharePoint development in Visual Studio, debugging extensions
ms.assetid: 7cee8ce0-d07b-41f6-8ce1-b18e4be3b50c
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 98bb43322d4a222d63bafac22d78e433a3000530
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-extensions-for-the-sharepoint-tools-in-visual-studio"></a>Visual Studio'da SharePoint Araçları için Hata Ayıklama Uzantıları
  SharePoint araç uzantıları deneysel örneği ya da Visual Studio normal örneğini ayıklayabilirsiniz. Uzantı davranışını gidermek gerekiyorsa, ek hata bilgileri görüntülemek için ve Visual Studio SharePoint komutları nasıl yürütür yapılandırmak için kayıt defteri değerlerini de değiştirebilirsiniz.  
  
## <a name="debugging-extensions-in-the-experimental-instance-of-visual-studio"></a>Visual Studio Deneysel örneğindeki hata ayıklama uzantıları  
 Visual Studio geliştirme ortamınızı yanlışlıkla bozulmaya sınanmamış uzantıları tarafından korunması için Visual Studio SDK'sı olarak adlandırılan bir alternatif Visual Studio örneği sağlar *deneysel örneği*, kullanabileceğiniz Yükleme ve uzantılarını test etmek için. Visual Studio normal örneğini kullanarak yeni uzantılar geliştirmek, ancak hata ayıklama ve deneysel örneğinde çalıştırın. Daha fazla bilgi için bkz: [deneysel örneği](/visualstudio/extensibility/the-experimental-instance).  
  
 Uzantınızı dağıtmak için VSIX proje kullanın ve başlangıç projesi çözümünüzdeki VSIX proje ise, Visual Studio, otomatik olarak yükler ve çözümünüzü hata ayıklarken uzantısı deneysel örneğinde çalışır. Başlangıç projesi olarak birden çok proje içeren bir çözüm ayıklarken başlayan projesidir. Uzantınızı dağıtmak üzere bir VSIX proje kullanma hakkında daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  

 Visual Studio'nun deneysel örneği uzantılarında çeşitli türlerde hata ayıklamak nasıl gösteren örnekler için aşağıdaki izlenecek bakın:  
  
-   [İzlenecek yol: bir SharePoint proje öğesi türünü genişletme](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
-   [İzlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)  
  
-   [İzlenecek yol: SharePoint projeleri için özel bir dağıtım adımı oluşturma](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)  
  
-   [İzlenecek yol: Web bölümlerini görüntülemek için Sunucu Gezgini genişletme](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
-   [İzlenecek yol: bir sunucu Gezgini uzantısında SharePoint istemcisi nesne modelini çağırma](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)  
  
## <a name="debugging-extensions-in-the-regular-instance-of-visual-studio"></a>Visual Studio normal örneğindeki hata ayıklama uzantıları  
 Uzantı projeniz Visual Studio normal örneğindeki hata ayıklamak istediğiniz ilk uzantısı normal örneğinde yükleyin. Ardından, hata ayıklayıcı ikinci bir Visual Studio işlemini ekleyin. İşlemi tamamladığınızda, böylece artık geliştirme bilgisayarınızda yükler uzantısı kaldırabilirsiniz.  
  
#### <a name="to-install-the-extension"></a>Uzantıyı yüklemek için  
  
1.  Visual Studio tüm örneklerini kapatın.  
  
2.  Uzantı projesi için yapı çıktı klasörüne .vsix dosyasını çift tıklatarak veya kısayol menüsünü açarak ve ardından açmak **açmak**:  
  
3.  İçinde **Visual Studio Uzantı Yükleyicisi** iletişim kutusunda, Visual Studio uzantısını yükleyin ve ardından istediğiniz sürümü seçin **yükleme** düğmesi.  
  
     Visual Studio için %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0\Extensions uzantısı dosyalarını yükler\\*yazar adı*\\*uzantı adı* \\ *sürüm*. Bu yolun son üç klasörlerde gelen oluşturulan `Author`, `Name`, ve `Version` uzantısı extension.vsixmanifest dosyasındaki öğeleri.  
  
4.  Visual Studio uzantı yüklemelerinden sonra seçin **Kapat** düğmesi.  
  
#### <a name="to-debug-the-extension"></a>Dahili hata ayıklamak için  
  
1.  Yönetici ayrıcalıklarıyla Visual Studio'yu başlatın ve uzantı projesini açın. Bu örneği Visual Studio aşağıdaki adımları başvurmak *ilk örneği*.  
  
2.  Başka bir örnek Visual Studio'nun yönetici ayrıcalıklarıyla başlatın. Bu örneği Visual Studio aşağıdaki adımları başvurmak *ikinci örneği*.  
  
3.  Visual Studio ilk örneğine geçin.  
  
4.  Menü çubuğunda seçin **hata ayıklama**, **ekleme işlemi için**.  
  
5.  İçinde **kullanılabilir işlemler** listesinde, devenv.exe seçin. Bu giriş, Visual Studio ikinci örneğine başvurur; Bu proje uzantısı'nda hata ayıklamak istediğiniz örneğidir.  
  
6.  Seçin **Attach** düğmesi.  
  
     Visual Studio uzantı projesi hata ayıklama modunda çalışır.  
  
7.  Visual Studio ikinci örneğe geçin.  
  
8.  Uzantınızı yükler yeni bir SharePoint projesi oluşturun. Örneğin, bir uzantı listesi tanımı proje öğeleri için hata ayıklama, oluşturma bir **listesi tanımını** projesi.  
  
9. Hangi adımları uzantısı kodunuzu test etmek için gerekli olan gerçekleştirin.  
  
10. Hata ayıklama uzantısı işiniz bittiğinde, Visual Studio ikinci bir örneğini kapatın.  
  
#### <a name="to-remove-the-extension"></a>Uzantıyı kaldırmak için  
  
1.  Menü çubuğunda, Visual Studio'da seçin **Araçları**, **Uzantılar ve güncelleştirmeler**.  
  
     **Uzantılar ve güncelleştirmeler** iletişim kutusu açılır.  
  
2.  Uzantılar listesinde uzantısının adını seçin ve ardından **kaldırma** düğmesi.  
  
3.  Görüntülenen iletişim kutusunda seçin **Evet** düğmesi uzantıyı kaldırmak istediğinizi onaylayın.  
  
4.  Seçin **şimdi yeniden Başlat** kaldırma işleminin tamamlanması için düğmesi.  
  
## <a name="debugging-sharepoint-commands"></a>SharePoint komutları hata ayıklama  
 Bir SharePoint araçları uzantısı parçası olan bir SharePoint komutu hata ayıklama istiyorsanız, hata ayıklayıcı vssphost4.exe işleme iliştirilemiyor gerekir. SharePoint komutları yürütür 64-bit ana bilgisayar işlemi budur. SharePoint komutları ve vssphost4.exe hakkında daha fazla bilgi için bkz: [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
#### <a name="to-attach-the-debugger-to-the-vssphost4exe-process"></a>Hata ayıklayıcı vssphost4.exe işleme iliştirilemiyor  
  
1.  Yukarıdaki yönergeleri izleyerek Visual Studio'nun deneysel örneği veya Visual Studio normal örneği uzantı hata ayıklamayı Başlat.  
  
2.  Visual Studio içinde çalışırken hata ayıklayıcı menü çubuğunda örneğinde seçin **hata ayıklama**, **ekleme işlemi için**.  
  
3.  İçinde **kullanılabilir işlemler** listesinde, vssphost.exe seçin.  
  
    > [!NOTE]  
    >  Vssphost.exe listede görünmüyorsa, Visual Studio uzantısı çalıştırdığınız örneğinde vssphost4.exe işlem başlatmanız gerekir. Genellikle, geliştirme bilgisayarındaki SharePoint sitesine bağlanmak Visual Studio neden olan bir eylem uygulayarak yaparsınız. Örneğin, Visual Studio vssphost4.exe başlatır altında bir site bağlantısı düğümünü (bir site URL'si görüntüler düğüm) genişlettiğinizde **SharePoint bağlantıları** düğümünde **Sunucu Gezgini** penceresinde veya ne zaman, belirli bir SharePoint Proje öğeleri gibi ekleme **listesi örneği** veya **olay alıcı** bir SharePoint Proje öğeleri.  
  
4.  Seçin **Attach** düğmesi.  
  
5.  Ayıklanacak Visual Studio örneğinde komutu yürütmek için gerekli adımları uygulayın.  
  
## <a name="modifying-registry-values-to-help-debug-sharepoint-tools-extensions"></a>Hata ayıklama SharePoint yardımcı olmak için kayıt defteri değerlerini değiştirme uzantıları araçları  
 Visual Studio'da SharePoint araçları uzantısı hata ayıklarken uzantısı gidermenize yardımcı olması için kayıt defteri değerlerini değiştirebilirsiniz. Değerleri HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\11.0\SharePointTools anahtarında bulunur. Bu değerler varsayılan olarak yok.  
  
 Uzantıyı SharePoint Araçları'nın gidermenize yardımcı olması için oluşturabilir ve EnableDiagnostics değerini ayarlayın. Aşağıdaki tabloda, bu değer açıklanmaktadır.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|EnableDiagnostics|Tanılama iletileri içinde görüntülenip görüntülenmeyeceğini belirtir REG_DWORD **çıkış** penceresi.<br /><br /> Tanılama iletileri görüntülemek için bu değer 1 olarak ayarlayın. İletilerin görüntüleme durdurmak için bu değeri 0 olarak ayarlayın veya bu değeri silin.<br /><br /> İletileri yazmak için **çıkış** bir SharePoint penceresinden araçları uzantısı, SharePoint Proje hizmeti kullanın. Daha fazla bilgi için bkz: [SharePoint Proje hizmetini kullanma](../sharepoint/using-the-sharepoint-project-service.md).|  
  
 Dahili bir SharePoint komutu içeriyorsa, oluşturun ve komut gidermenize yardımcı olması için ek değerleri ayarlayın. Aşağıdaki tabloda, bu değerleri açıklanmaktadır.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|AttachDebuggerToHostProcess|REG_DWORD başlatıldıktan hemen sonra vssphost4.exe için hata ayıklayıcıyı Ekle olanak tanıyan bir iletişim kutusu görüntülenip görüntülenmeyeceğini belirtir. Bu işlem başlatıldıktan hemen sonra tarafından vssphost.exe hata ayıklamak istediğiniz komut yürütülürse faydalı olur ve hata ayıklayıcı komut yürütülmeden önce el ile eklemek için yeterli bir süre değil. İletişim kutusu, vssphost4.exe çağrıları görüntülenecek <xref:System.Diagnostics.Debugger.Break%2A> başlatıldığında yöntemi.<br /><br /> Bu davranışı etkinleştirmek için bu değer 1 olarak ayarlayın. Bu davranışı devre dışı bırakmak için bu değeri 0 olarak ayarlayın veya bu değeri silin.<br /><br /> Bu değer 1 olarak ayarlarsanız, kendiniz Visual Studio vssphost4.exe başarıyla başlatıldı sinyal bekliyor önce hata ayıklayıcısı eklemek için yeterli süre sağlamak için HostProcessStartupTimeout değerini artırmak isteyebilirsiniz.|  
|ChannelOperationTimeout|Visual Studio bir SharePoint komutu yürütmek bekleyeceği saniye cinsinden süreyi belirten REG_DWORD. Komutu, zaman içindeki yürütün değil, bir <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException> oluşturulur.<br /><br /> Varsayılan değer 120 saniyedir.|  
|HostProcessStartupTimeout|Sinyal vssphost4.exe için Visual Studio bekler saniye cinsinden süreyi belirten REG_DWORD başarıyla başlatıldı. Vssphost4.exe başarılı bir başlangıç, zaman içindeki işaret etmiyor varsa bir <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException> oluşturulur.<br /><br /> Varsayılan değer 60 saniyedir.|  
|MaxReceivedMessageSize|REG_DWORD Visual Studio ve vssphost4.exe arasında geçirilen WCF iletilerinin bayt cinsinden en büyük izin verilen boyutu belirtir.<br /><br /> 1.048.576 bayt (1 MB) varsayılandır.|  
|MaxStringContentLength|REG_DWORD Visual Studio ve vssphost4.exe arasında geçirilen dizeleri bayt cinsinden en büyük izin verilen boyutu belirtir.<br /><br /> 1.048.576 bayt (1 MB) varsayılandır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da SharePoint araçları genişletme](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Visual Studio'da SharePoint araçları için hata ayıklama uzantıları](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  