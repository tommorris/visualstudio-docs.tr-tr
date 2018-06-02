---
title: Office çözümleri dağıtımı sorunlarını giderme
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], troubleshooting
- Office development in Visual Studio, troubleshooting
- deploying applications [Office development in Visual Studio], troubleshooting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 854264da676ec52d93030371213fa3d8d57eb69f
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34693214"
---
# <a name="troubleshoot-office-solution-deployment"></a>Office çözümleri dağıtımı sorunlarını giderme
  Bu konu, Office çözümlerini dağıtırken karşılaşabileceğiniz yaygın sorunların nasıl çözüleceği hakkında bilgi içerir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="troubleshoot-office-solutions-by-using-the-event-viewer"></a>Office çözümleri Olay Görüntüleyicisi'ni kullanarak sorun giderme  
 Tarafından kaydedilen hata iletilerini görmek için Windows Olay Görüntüleyicisi'ni kullanabilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yüklediğinizde veya Office çözümleri kaldırın. Bu olay günlükçüsü iletilerden yükleme ve dağıtım sorunlarını gidermek için kullanabilirsiniz. Daha fazla bilgi için bkz: [Office çözümleri için olay günlüğü](../vsto/event-logging-for-office-solutions.md).  
  
## <a name="change-the-assembly-name-causes-conflicts"></a>Değişiklik derleme adı çakışmaları neden olur.  
 Değiştirirseniz **derleme adı** değeri **uygulama** sayfasında **Proje Tasarımcısı** zaten bir çözüm dağıttıktan sonra yayımlama araçları değiştirir Kurulum Paketi için bir *Setup.exe* dosya ve iki dağıtım bildirimleri. İki bildirim dosyası dağıtırsanız, aşağıdaki durumlardan ortaya çıkabilir:  
  
-   Son kullanıcı her iki sürümü de yüklerse, uygulama hem VSTO eklentileri yükler.  
  
-   VSTO eklenti derleme adı değiştirilmeden önce yüklenmişse, son kullanıcı hiçbir zaman güncelleştirmeleri almazlar.  
  
 Bu durumlardan kaçınmak için çözümün değişmez **derleme adı** çözümü dağıttıktan sonra değer.  
  
## <a name="check-for-updates-takes-a-long-time"></a>Güncelleştirmeleri alır uzun süre olup olmadığını denetleyin  
 Office çalışma zamanı için Visual Studio 2010 Araçları Yöneticiler bildirimlerinde ve çözümü indirme zaman aşımı değerini ayarlamak için kullanabileceğiniz bir kayıt defteri girişi sağlar.  
  
#### <a name="to-set-the-time-out-value"></a>Zaman aşımı değerini ayarlamak için  
  
1.  Kayıt defterinde aşağıdaki anahtarına gidin:  
  
     **HKEY_CURRENT_USER\Software\Microsoft\VSTA**  
  
2.  İçinde **AddInTimeout** alt anahtar, zaman aşımı değerini milisaniye olarak ayarlayın.  
  
     Varsa **AddInTimeout** alt değil, mevcut bir DWORD olarak oluşturun.  
  
## <a name="cant-update-or-publish-to-a-network-file-share"></a>Güncelleştirilemiyor veya bir ağ dosya paylaşımına Yayımla  
 Bir ağ dosya paylaşımında bulunan office çözümleri görüntülenebilir yanıltıcı bir ileti güncelleştirmeleri sırasında çözümün *Setup.exe* güncelleştirme yayımlanırken dosya bir işlemde kilitli. Aşağıdaki ileti diyebilirsiniz: "'setup.exe' Web'e eklenemiyor. "Setup.exe' dosyası zaten bu Web'de var."  
  
 Dosya kilitleme önlemeye yardımcı olmak için paylaşımın salt okunur son kullanıcılara yapabilirsiniz. Belgeleri paylaşımında varsa, Bununla birlikte, bunlar Ayrıca son kullanıcılara salt okunur olur.  
  
## <a name="prerequisites-for-microsoft-office-arent-installed"></a>Microsoft Office için Önkoşullar yüklü değil  
 .NET Framework ekleyebilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]ve Office birincil birlikte çalışma derlemeleri Kurulum paketinize Office çözümünüzle birlikte dağıtılan bir önkoşul olarak. Birincil birlikte çalışma derlemelerini yükleme hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md) ve [nasıl yapılır: yükleme Office birincil birlikte çalışma derlemeleri](../vsto/how-to-install-office-primary-interop-assemblies.md).  
  
## <a name="publish-using-localhost-can-cause-installation-problems"></a>Kullanarak yayımlamak 'Localhost' yükleme sorunlara neden olabilir  
 Kullandığınızda, "http://localhost" için belge düzeyi çözümleri yayımlama ya da yükleme konumu olarak **Yayımlama Sihirbazı** dize gerçek bilgisayar adına dönüştürmez. Bu durumda, çözüm geliştirme bilgisayarına yüklenmesi gerekir. Dağıtılan çözümleri geliştirme bilgisayarınızda IIS kullanan yapmak için localhost yerine tüm HTTP/HTTPS/FTP konumları için tam ad kullanın.  
  
## <a name="cached-assemblies-are-loaded-instead-of-updated-assemblies"></a>Önbelleğe alınan derlemelerin yerine güncelleştirilen derlemelerin yüklü olduğundan  
 Fusion, .NET Framework derleme yükleyicisi proje çıktı yolu bir ağ dosya paylaşımında olduğunda, derleme tanımlayıcı bir ad ile imzalanır ve özelleştirme derleme sürümü değişmez derlemeleri önbelleğe alınmış bir kopyasını yükler. Bu koşullara uyan bir derlemeyi güncelleştirirseniz, güncelleştirme önbelleğe alınan kopya yüklendiği proje sonraki çalıştırmanızda görünmez.  
  
 Visual Studio Fusion projenin her çalıştırılışında derlemeleri yükleyecek şekilde yapılandırabilirsiniz.  
  
### <a name="to-download-assemblies-instead-of-loading-cached-copies"></a>Önbelleğe alınan kopyaları yüklenirken yerine derlemeleri indirmek için  
  
1.  Menü çubuğunda seçin **proje**, * ProjectName ***özellikleri**.  
  
2.  Üzerinde **uygulama** sayfasında, **derleme bilgilerini**.  
  
3.  İlk **derleme sürümü** kutusunda, bir yıldız işareti girin (\*) ve ardından **Tamam** düğmesi.  
  
 Derleme sürümünü değiştirdikten sonra derlemeyi tanımlayıcı adla imzalamak devam edebilirsiniz ve Fusion özelleştirmenin en son sürümünü yükler.  
  
## <a name="installation-fails-when-the-uri-has-characters-that-arent-us-ascii"></a>URI US-ASCII olmayan karakterler içeriyor, yükleme başarısız olur.  
 Bir HTTP/HTTPS/FTP konumuna Office çözümü yayımladığınızda, yolun US-ASCII olmayan herhangi bir Unicode karakteri bulunamaz. Bu tür karakterler Kurulum programında tutarsız davranışa neden olabilir. US-ASCII karakter yükleme yolu için kullanın.  
  
## <a name="prompt-to-manually-uninstall-appears-when-you-publish-and-install-a-solution-on-the-development-computer"></a>Yayımlama ve bir çözüm geliştirme bilgisayarınızda yüklediğinizde el ile kaldırmak için istemi belirir.  
 Office çözümünü derlerken, derleme sürümü otomatik olarak kaydedilir. Önceden yayımlanan ve aynı çözüm geliştirme bilgisayarınızda yüklü değilse [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yükleme yolu çözümü sonraki oluşturulduktan sonra yayımlanan sürümü ve yerleşik sürümü farklı için yeniden veya yayımlanan olduğunu algılar. "Başka bir sürümü yüklü olan ve bu konumdan yükseltilemez özelleştirme yüklenemez." hata iletisi diyor. Bir çözümü yeniden her kayıt defteri anahtarlarını güncelleştirilir. Bu nedenle, yayımlama, hata ayıklama veya yeni sürümü çalıştırmadan önce önceki sürümü kaldırmanız gerekir.  
  
 İletinin görünmesini engellemek üzere, dağıtımınızı test etmek için geliştirme bilgisayarınızda başka bir kullanıcı hesabı oluşturun. Alternatif olarak, sonraki yayımlama, hata ayıklama veya çözümü yeniden derleyin önce bilgisayarda yüklü programlar listesinde sürümünü kaldırın.  
  
## <a name="uncaught-exception-or-method-not-found-error-when-you-install-a-solution"></a>Bir çözüm yüklediğinizde Yakalanmayan Özel durum veya yöntemi bulunamadı hatası  
 Dağıtım bildirimini açarak Office çözümleri yüklediğinizde (bir *.vsto* dosyası), aşağıdaki koşullar Office uygulama, belge veya çalışma kitabı, hata iletisi görüntülenebilir:  
  
-   Yöntem bulunamadı.  
  
-   MissingMethodException.  
  
-   Yakalanmayan Özel durum.  
  
 Bu hata iletilerini önlemek için Kurulum programını çalıştırarak çözümü yükleyin.  
  
 Kurulum programı çalıştırmadan çözümü yüklediğinizde, yükleyici için denetleyin değil veya önkoşulları yükleyin. Kurulum programı önkoşulları doğru sürümünü denetler ve bunları gerektiği şekilde yükler.  
  
## <a name="manifest-registry-keys-for-add-ins-change-after-an-installshield-limited-edition-project-is-built"></a>InstallShield Limited Edition Proje oluşturulduktan sonra kayıt defteri anahtarları için eklentileri değişiklik bildirimi  
 VSTO eklenti Kurulum parçasıdır bildirim kayıt defteri anahtarı program bazen değişikliklerden *.vsto* için *. dll.manifest* InstallShield Limited Edition proje oluşturduğunuzda.  
  
 Bu sorunu çözmek için farklı bir çözümde InstallShield Limited Edition projesi oluşturma veya ŞirketAdı.EklentiAdı'nı VSTO eklenti adını içeren kayıt defteri anahtarının değeri kullanın.  
  
## <a name="the-clickonce-installer-for-your-office-solution-doesnt-install-the-primary-interop-assemblies"></a>Office çözümünüz için ClickOnce yükleyici birincil birlikte çalışma derlemelerini yükleme değil  
 Office çözümünüz için ClickOnce oluşturur Kurulum programını çalıştırdığınızda, yalnızca hiçbir PIA zaten yüklüyse Office birincil birlikte çalışma derlemeleri (PIA) için yükleyiciyi çalıştırır.  
  
 Kurulum programı PIA doğru yüklenmiyorsa, bunları el ile adlı yükleyici dosyasını çalıştırarak yüklemesi *o2007pia.msi* yükleme dizininden.  
  
## <a name="reinstall-office-solutions-causes-an-argument-out-of-range-exception"></a>Office çözümleri neden bir bağımsız değişkeni aralık özel durum dışında yeniden yükleyin  
 Office çözümünü yeniden yüklediğinizde bir <xref:System.ArgumentOutOfRangeException> özel durum şu hata iletisiyle görüntülenebilir: Belirtilen bağımsız değişken geçerli değer aralığının dışında.  
  
 Yükleme konumu için URL için büyük/küçük harf farklıysa, bu durum oluşur. Örneğin, Office çözümünü yüklü değilse bu hata görüneceği [ http://fabrikam.com/ExcelSolution.vsto ](http://fabrikam.com/ExcelSolution.vsto) ilk kez ve ardından kullanılan [ http://fabrikam.com/excelsolution.vsto ](http://fabrikam.com/excelsolution.vsto) ikinci kez.  
  
 İletinin görüntülenmesini engellemek için Office çözümleri yüklediğinizde aynı büyük küçük harf kullanın.  
  
## <a name="cant-install-a-clickonce-solution-by-opening-the-deployment-manifest-from-the-web"></a>ClickOnce çözüm Web'den dağıtım bildirimini açarak yükleyemezsiniz  
 Kullanıcıların Office çözümleri Web'den dağıtım bildirimini açarak yükleyebilirsiniz. Ancak, bazı yüklemelerinde Internet Information Services (IIS) blokları *.vsto* dosya adı uzantısı. Office çözümünü dağıtmak için kullanmadan önce IIS'de MIME türü tanımlamanız gerekir.  
  
 IIS 6 MIME türü tanımlama hakkında daha fazla bilgi için bkz: [yapılandırma MIME türleri (IIS 6.0)](http://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/cd72c0dc-c5b8-42e4-96c2-b3c656f99ead.mspx?mfr=true).  
  
 IIS 7'de MIME türü tanımlama hakkında daha fazla bilgi için bkz: [bir MIME türü (IIS7) eklemek](http://technet.microsoft.com/library/cc725608(WS.10).aspx).  
  
 Uzantı kümesine **.vsto** ve için MIME türü **uygulama/x-ms-vsto**.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [ClickOnce dağıtım sorunlarını giderme](/visualstudio/deployment/troubleshooting-clickonce-deployments)   
 [Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)  
  
  