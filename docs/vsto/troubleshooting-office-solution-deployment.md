---
title: "Office çözümü dağıtımında sorunu giderme | Microsoft Docs"
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
- ClickOnce deployment [Office development in Visual Studio], troubleshooting
- Office development in Visual Studio, troubleshooting
- deploying applications [Office development in Visual Studio], troubleshooting
ms.assetid: 2206aeb6-44b3-4786-ba99-9c7dad5cce7c
caps.latest.revision: "74"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: a778aa9e257773ca186bba8b99d5e426f8f26aed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-office-solution-deployment"></a>Office Çözümü Dağıtımında Sorunu Giderme
  Bu konu, Office çözümlerini dağıtırken karşılaşabileceğiniz yaygın sorunların nasıl çözüleceği hakkında bilgi içerir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="troubleshooting-office-solutions-by-using-the-event-viewer"></a>Olay Görüntüleyicisi'ni kullanarak Office çözümlerinde sorun giderme  
 Tarafından kaydedilen hata iletilerini görmek için Windows Olay Görüntüleyicisi'ni kullanabilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yüklediğinizde veya Office çözümleri kaldırın. Bu olay günlükçüsü iletilerden yükleme ve dağıtım sorunlarını gidermek için kullanabilirsiniz. Daha fazla bilgi için bkz: [Office çözümleri için olay günlüğü](../vsto/event-logging-for-office-solutions.md).  
  
## <a name="changing-the-assembly-name-causes-conflicts"></a>Derleme adını değiştirmenin çakışmalarına neden olur  
 Değiştirirseniz **derleme adı** değeri **uygulama** sayfasında **Proje Tasarımcısı** zaten bir çözüm dağıttıktan sonra yayımlama araçları değiştirir Bir Setup.exe dosyasını ve iki dağıtım bildirimleri için Kurulum paketini. İki bildirim dosyası dağıtırsanız, aşağıdaki durumlardan ortaya çıkabilir:  
  
-   Son kullanıcı her iki sürümü de yüklerse, uygulama hem VSTO eklentileri yükler.  
  
-   VSTO eklenti derleme adı değiştirilmeden önce yüklenmişse, son kullanıcı hiçbir zaman güncelleştirmeleri almazlar.  
  
 Bu durumlardan kaçınmak için çözümün değişmez **derleme adı** çözümü dağıttıktan sonra değer.  
  
## <a name="checking-for-updates-takes-a-long-time"></a>Güncelleştirmeleri denetleme uzun sürüyor  
 Office çalışma zamanı için Visual Studio 2010 Araçları Yöneticiler bildirimlerinde ve çözümü indirme zaman aşımı değerini ayarlamak için kullanabileceğiniz bir kayıt defteri girişi sağlar.  
  
#### <a name="to-set-the-time-out-value"></a>Zaman aşımı değerini ayarlamak için  
  
1.  Kayıt defterinde aşağıdaki anahtarına gidin:  
  
     HKEY_CURRENT_USER\Software\Microsoft\VSTA  
  
2.  İçinde **AddInTimeout** alt anahtar, zaman aşımı değerini milisaniye olarak ayarlayın.  
  
     Varsa **AddInTimeout** alt değil, mevcut bir DWORD olarak oluşturun.  
  
## <a name="cant-update-or-publish-to-a-network-file-share"></a>Güncelleştirilemiyor veya bir ağ dosya paylaşımına Yayımla  
 Çözümün Setup.exe dosyasını güncelleştirme yayımlanırken bir işlemde kilitliyse bir ağ dosya paylaşımında bulunan office çözümleri güncelleştirmeleri sırasında yanıltıcı iletisi görüntülenebilir. Aşağıdaki ileti diyebilirsiniz: "'setup.exe' Web'e eklenemiyor. "Setup.exe' dosyası zaten bu Web'de var."  
  
 Dosya kilitleme önlemeye yardımcı olmak için paylaşımın salt okunur son kullanıcılara yapabilirsiniz. Belgeleri paylaşımında varsa, Bununla birlikte, bunlar Ayrıca son kullanıcılara salt okunur olur.  
  
## <a name="prerequisites-for-microsoft-office-arent-installed"></a>Microsoft Office için Önkoşullar yüklü değil  
 .NET Framework ekleyebilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]ve Office birincil birlikte çalışma derlemeleri Kurulum paketinize Office çözümünüzle birlikte dağıtılan bir önkoşul olarak. Birincil birlikte çalışma derlemelerini yükleme hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md) ve [nasıl yapılır: yükleme Office birincil birlikte çalışma derlemeleri](../vsto/how-to-install-office-primary-interop-assemblies.md).  
  
## <a name="publishing-using-localhost-can-cause-installation-problems"></a>'Localhost' kullanarak yayımlamanın yükleme sorunlarına neden olabilir  
 Belge düzeyi çözümlerde yayımlama ya da yükleme konumu olarak "http://localhost" kullandığınızda **Yayımlama Sihirbazı** dize gerçek bilgisayar adına dönüştürmez. Bu durumda, çözüm geliştirme bilgisayarına yüklenmesi gerekir. Dağıtılan çözümleri geliştirme bilgisayarınızda IIS kullanan yapmak için localhost yerine tüm HTTP/HTTPS/FTP konumları için tam ad kullanın.  
  
## <a name="cached-assemblies-are-loaded-instead-of-updated-assemblies"></a>Önbelleğe alınan derlemelerin yerine güncelleştirilen derlemelerin yüklü olduğundan  
 Fusion, .NET Framework derleme yükleyicisi proje çıktı yolu bir ağ dosya paylaşımında olduğunda, derleme tanımlayıcı bir ad ile imzalanır ve özelleştirme derleme sürümü değişmez derlemeleri önbelleğe alınmış bir kopyasını yükler. Bu koşullara uyan bir derlemeyi güncelleştirirseniz, güncelleştirme önbelleğe alınan kopya yüklendiği proje sonraki çalıştırmanızda görünmez.  
  
 Visual Studio Fusion projenin her çalıştırılışında derlemeleri yükleyecek şekilde yapılandırabilirsiniz.  
  
#### <a name="to-download-assemblies-instead-of-loading-cached-copies"></a>Önbelleğe alınan kopyaları yüklenirken yerine derlemeleri indirmek için  
  
1.  Menü çubuğunda seçin **proje**, *ProjectName***özellikleri**.  
  
2.  Üzerinde **uygulama** sayfasında, **derleme bilgilerini**.  
  
3.  İlk **derleme sürümü** kutusunda, bir yıldız işareti girin (\*) ve ardından **Tamam** düğmesi.  
  
 Derleme sürümünü değiştirdikten sonra derlemeyi tanımlayıcı adla imzalamak devam edebilirsiniz ve Fusion özelleştirmenin en son sürümünü yükler.  
  
## <a name="installation-fails-when-the-uri-has-characters-that-aret-us-ascii"></a>URI bu Are't US-ASCII karakter olduğunda yükleme başarısız olur.  
 Bir HTTP/HTTPS/FTP konumuna Office çözümü yayımladığınızda, yolun US-ASCII olmayan herhangi bir Unicode karakteri bulunamaz. Bu tür karakterler Kurulum programında tutarsız davranışa neden olabilir. US-ASCII karakter yükleme yolu için kullanın.  
  
## <a name="prompt-to-manually-uninstall-appears-when-you-publish-and-install-a-solution-on-the-development-computer"></a>Yayımlama ve bir çözüm geliştirme bilgisayarınızda yüklediğinizde el ile kaldırmak için istemi belirir.  
 Office çözümünü derlerken, derleme sürümü otomatik olarak kaydedilir. Önceden yayımlanan ve aynı çözüm geliştirme bilgisayarınızda yüklü değilse [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yükleme yolu çözümü sonraki oluşturulduktan sonra yayımlanan sürümü ve yerleşik sürümü farklı için yeniden veya yayımlanan olduğunu algılar. "Başka bir sürümü yüklü olan ve bu konumdan yükseltilemez özelleştirme yüklenemez." hata iletisi diyor. Bir çözümü yeniden her kayıt defteri anahtarlarını güncelleştirilir. Bu nedenle, yayımlama, hata ayıklama veya yeni sürümü çalıştırmadan önce önceki sürümü kaldırmanız gerekir.  
  
 İletinin görünmesini engellemek üzere, dağıtımınızı test etmek için geliştirme bilgisayarınızda başka bir kullanıcı hesabı oluşturun. Alternatif olarak, sonraki yayımlama, hata ayıklama veya çözümü yeniden derleyin önce bilgisayarda yüklü programlar listesinde sürümünü kaldırın.  
  
## <a name="uncaught-exception-or-method-not-found-error-when-you-install-a-solution"></a>Bir çözüm yüklediğinizde Yakalanmayan Özel durum veya yöntemi bulunamadı hatası  
 Office çözümleri (.vsto dosyası) dağıtım bildirimini açarak yüklediğinizde, aşağıdaki koşullar Office uygulama, belge veya çalışma kitabı, hata iletileri görünebilir:  
  
-   Yöntem bulunamadı.  
  
-   MissingMethodException.  
  
-   Yakalanmayan Özel durum.  
  
 Bu hata iletilerini önlemek için Kurulum programını çalıştırarak çözümü yükleyin.  
  
 Kurulum programı çalıştırmadan çözümü yüklediğinizde, yükleyici için denetleyin değil veya önkoşulları yükleyin. Kurulum programı önkoşulları doğru sürümünü denetler ve bunları gerektiği şekilde yükler.  
  
## <a name="manifest-registry-keys-for-add-ins-change-after-an-installshield-limited-edition-project-is-built"></a>InstallShield Limited Edition Proje oluşturulduktan sonra kayıt defteri anahtarları için eklentiler değişikliği bildirimi  
 VSTO eklenti Kurulum parçasıdır bildirim kayıt defteri anahtarı program bazen vsto'dan. bir InstallShield Limited Edition projeyi derlerken dll.manifest.  
  
 Bu sorunu çözmek için farklı bir çözümde InstallShield Limited Edition projesi oluşturma veya ŞirketAdı.EklentiAdı'nı VSTO eklenti adını içeren kayıt defteri anahtarının değeri kullanın.  
  
## <a name="the-clickonce-installer-for-your-office-solution-doesnt-install-the-primary-interop-assemblies"></a>Office çözümünüz için ClickOnce yükleyici birincil birlikte çalışma derlemelerini yükleme değil  
 Office çözümünüz için ClickOnce oluşturur Kurulum programını çalıştırdığınızda, yalnızca hiçbir PIA zaten yüklüyse Office birincil birlikte çalışma derlemeleri (PIA) için yükleyiciyi çalıştırır.  
  
 Kurulum programı PIA doğru yüklenmiyorsa, bunları el ile yükleme dizininden o2007pia.msi adlı yükleyici dosyasını çalıştırarak yükleyin.  
  
## <a name="reinstalling-office-solutions-causes-an-argument-out-of-range-exception"></a>Office çözümleri yeniden aralığı özel durum dışında bir bağımsız değişken neden olur.  
 Office çözümünü yeniden yüklediğinizde bir <xref:System.ArgumentOutOfRangeException> özel durum şu hata iletisiyle görüntülenebilir: Belirtilen bağımsız değişken geçerli değer aralığının dışında.  
  
 Yükleme konumu için URL için büyük/küçük harf farklıysa, bu durum oluşur. Örneğin, Office çözümünü yüklü değilse bu hata görüneceği [http://fabrikam.com/ExcelSolution.vsto](http://fabrikam.com/ExcelSolution.vsto) ilk kez ve ardından kullanılan [http://fabrikam.com/excelsolution.vsto](http://fabrikam.com/excelsolution.vsto) ikinci kez.  
  
 İletinin görüntülenmesini engellemek için Office çözümleri yüklediğinizde aynı büyük küçük harf kullanın.  
  
## <a name="cant-install-a-clickonce-solution-by-opening-the-deployment-manifest-from-the-web"></a>ClickOnce çözüm Web'den dağıtım bildirimini açarak yükleyemezsiniz  
 Kullanıcıların Office çözümleri Web'den dağıtım bildirimini açarak yükleyebilirsiniz. Ancak, bir bazı yüklemeler Internet Information Services (IIS) .vsto dosya adı uzantısını engeller. Office çözümünü dağıtmak için kullanmadan önce IIS'de MIME türü tanımlamanız gerekir.  
  
 IIS 6 MIME türü tanımlama hakkında daha fazla bilgi için bkz: [yapılandırma MIME türleri (IIS 6.0)](http://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/cd72c0dc-c5b8-42e4-96c2-b3c656f99ead.mspx?mfr=true).  
  
 IIS 7'de MIME türü tanımlama hakkında daha fazla bilgi için bkz: [bir MIME türü (IIS7) ekleyin.](http://technet.microsoft.com/library/cc725608(WS.10).aspx).  
  
 Uzantı kümesine **.vsto** ve için MIME türü **uygulama/x-ms-vsto**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım sorunlarını giderme](/visualstudio/deployment/troubleshooting-clickonce-deployments)   
 [Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)  
  
  