---
title: VSPackages sorunlarını giderme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, troubleshooting
- debugging, VSPackages
ms.assetid: 274673e7-72e7-476f-a263-3411b5b874be
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 73c754de72238671dd10235e792c43fb6d0a1b5b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31146202"
---
# <a name="troubleshooting-vspackages"></a>Sorun giderme VSPackages
İle VSPackage olabilir ve sorunları çözmek için ipuçları yaygın sorunlar aşağıda verilmiştir.  
  
### <a name="to-troubleshoot-a-vspackage-that-keeps-visual-studio-from-starting"></a>Visual Studio başlatılmasını tutar VSPackage gidermek için  
  
-   Başlat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] güvenli modda.  
  
     Başlatmak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] güvenli modda, bir komut isteminde yazın **devenv.exe/safemode**.  
  
     Bu işlem sırasında bulunan VSPackages dışında hiçbir VSPackages yüklenen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
### <a name="to-troubleshoot-a-vspackage-that-does-not-load"></a>Yüklemez VSPackage gidermek için  
  
1.  İçinde VSPackage çalıştırmak için genellikle Deneysel kayıt defteri kök kayıtlı olduğu kayıt defteri kök kullandığınızdan emin olun.  
  
     Daha fazla bilgi için bkz: [deneysel örneği](../extensibility/the-experimental-instance.md).  
  
2.  Deneysel kayıt defteri kök dizininde çalıştırmak için VSPackage hedefliyorsa, Deneysel sürümünü çalıştırdığından emin olun [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Deneysel sürümünü çalıştırmak için bir komut penceresinde aşağıdaki komutu yazın: **devenv /rootsuffix exp**.  
  
3.  VSPackage kayıt defteri girişlerini denetleyin.  
  
     Daha fazla bilgi için bkz: [kaydetme VSPackages](http://msdn.microsoft.com/en-us/31e6050f-1457-4849-944a-a3c36b76f3dd) ve [yönetme VSPackages](../extensibility/managing-vspackages.md).  
  
4.  Açık **çıkış** örneğinin penceresi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage yüklemek başarısız. VSPackage yüklemek neden başarısız olduğu hakkında bilgi bu penceresinde görüntülenebilir.  
  
    > [!NOTE]
    >  Deneysel sürümü başlatıyorsanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] gelen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) inceleyin **çıkış** her iki sürümünü de penceresi.  
  
5.  Etkinlik günlüğü inceleyin.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: etkinlik günlüğü kullanın](../extensibility/how-to-use-the-activity-log.md).  
  
6.  IDE tarafından oluşturulan özel durumları hakkında daha fazla bilgi için tıklatın **özel durumları** üzerinde **hata ayıklama** özel durumları etkinleştirmeniz menüsü. İçinde **özel durumları** iletişim kutusu hakkında daha fazla bilgi istediğiniz özel durum türlerini seçin.  
  
### <a name="to-troubleshoot-a-vspackage-that-does-not-register"></a>Kaydetme VSPackage gidermek için  
  
1.  VSPackage derleme güvenilir bir konumda bulunduğundan emin olun. RegPkg bir ağ paylaşımına varsayılan .net güvenlik yapılandırması gibi bir güvenilmeyen veya kısmen güvenilen konumda derlemeleri kaydedilemiyor. Bir kullanıcı bir proje güvenilmeyen bir konumda oluşturur. her bir uyarı görüntülenir, ancak "Bu iletiyi tekrar gösterme" onay kutusunu yinelenmeye öğesinden bu uyarıyı engelleyebilirsiniz.  
  
### <a name="to-troubleshoot-a-command-that-is-not-visible-or-that-generates-an-error-when-you-click-a-command"></a>Bir komut görünür değil ya da bir hata oluşturur, bir komutu tıklattığınızda gidermek için  
  
1.  Aşağıdaki yazarak yeni veya değiştirilmiş menü komutlarını ve IDE de zaten birleştirme [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komut istemi: **Exp/Setup devenv /rootsuffix**.  
  
2.  Olduğundan emin olun [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] UI.dll için VSPackage bulabilirsiniz.  
  
    1.  VSPackage CLSID kayıt paketleri bölümünü bulun:  
  
         HKLM\Software\Microsoft\Visual Studio\\*\<sürüm >* \Packages  
  
    2.  SatelliteDll alt anahtarı tarafından verilen yolun doğru olduğundan emin olun.  
  
### <a name="to-troubleshoot-a-vspackage-that-behaves-unexpectedly"></a>Beklenmedik bir şekilde davranır VSPackage gidermek için  
  
1.  Kesme noktaları kodunuzda ayarlayın.  
  
     Hata ayıklama için iyi bir başlangıç noktası oluşturucusu ve başlatma yöntemini ' dir. Ayrıca, bir menü komutu gibi değerlendirmek istediğiniz alanı kesme noktaları ayarlayabilirsiniz. Kesme noktaları etkinleştirmek için hata ayıklayıcı altında çalıştırmanız gerekir.  
  
    1.  Üzerinde **proje** menüsünde tıklatın **özellikleri**.  
  
    2.  Üzerinde **özellik sayfaları** iletişim kutusunda **hata ayıklama** sekmesi.  
  
    3.  İçinde **komut satırı bağımsız değişkenleri** geliştirme ortamı'nın kök sonekini yazın, VSPackage hedefler. Örneğin, deneysel yapı seçmek için şunu yazın: **RootSuffix Exp**.  
  
    4.  Üzerinde **hata ayıklama** menüsünde tıklatın **hata ayıklamayı Başlat** veya F5 tuşuna basın.  
  
        > [!NOTE]
        >  Bir proje ayıkladığınız yoksa oluşturabilir veya mevcut örneği, projenizin şimdi yükle.  
  
2.  Etkinlik günlüğü kullanın.  
  
     Anahtar noktalarda etkinlik günlüğü için bilgi yazarak VSPackage davranış izleme. Bir perakende ortamında bir VSPackage çalıştırdığınızda, bu özellikle yararlı bir tekniktir. Daha fazla bilgi için bkz: [nasıl yapılır: etkinlik günlüğü kullanın](../extensibility/how-to-use-the-activity-log.md).  
  
3.  Ortak simgeleri kullanın.  
  
     Hata ayıklama sırasında okunabilirliğini artırmak için hata ayıklayıcı için simgeler ekleyebilirsiniz.  
  
    1.  Gelen **Araçlar/Seçenekler** menüsünde gidin **hata ayıklama/simgeleri** iletişim kutusu.  
  
    2.  Bu ekleme **simge (.pdb) dosya konumu**:  
  
         [http://msdl.microsoft.com/download/symbols](http://msdl.microsoft.com/download/symbols)  
  
    3.  Performansı artırmak için örneğin bir simge Önbellek klasörü belirtin:  
  
        ```  
        C:\symbols  
        ```  
  
### <a name="to-troubleshoot-a-missing-vspackage-or-one-of-its-dependencies"></a>Eksik VSPackage veya bağımlılıklarından biri sorunlarını gidermek için  
  
1.  Yönetilen kod için başvuru yollarını doğru olduğundan emin olun.  
  
    1.  Üzerinde **proje** menüsünde tıklatın **özellikleri**.  
  
    2.  Seçin **başvuruları** sekmesinde **özellik sayfaları** iletişim kutusu ve emin olun tüm yolları doğru. Alternatif olarak, kullanabileceğiniz **Nesne Tarayıcısı** başvurulan nesneler için gidin.  
  
         Yönetilen kod için kullandığınız [Fuslogvw.exe (Derleme bağlaması Günlük Görüntüleyici)](/dotnet/framework/tools/fuslogvw-exe-assembly-binding-log-viewer) başarısız derleme yüklerini ayrıntılarını görüntülemek için.  
  
2.  Yönetilmeyen kod için VSPackage CLSID Bul [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] CLSID kayıt defteri düğümü:  
  
     HKLM\Software\Microsoft\Visual Studio\\*\<sürüm >* \CLSID  
  
 Inprocserver32 giriş VSPackage dll için doğru yolu olduğundan emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage’lar](../extensibility/internals/vspackages.md)