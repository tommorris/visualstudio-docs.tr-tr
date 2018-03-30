---
title: Visual Studio çevrimdışı yükleme için gerekli sertifikaları yükleyin | Microsoft Docs
description: Visual Studio çevrimdışı yükleme için sertifikaları yüklemek için gereken adımları açıklar
ms.date: 08/30/2017
ms.reviewer: tims
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9750A3F3-89C7-4A8F-BA75-B0B06BD772C2
author: tglee
ms.author: tglee
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a1ffca50b849a273b4ab49955eaf92e4e637cfbb
ms.sourcegitcommit: 064f8678f4a918e1dce60285090a9803d37dc34b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/30/2018
---
# <a name="install-certificates-required-for-visual-studio-offline-installation"></a>Visual Studio çevrimdışı yükleme için gerekli sertifikaları yükleyin

Visual Studio, öncelikle bu yana birçok bileşen düzenli olarak güncelleştirilen bir internet'e bağlı makineye yüklenmesi için tasarlanmıştır. Ancak, bazı ek adımlar ile çalışan bir yerde Visual Studio ortamında dağıtmak mümkündür Internet bağlantısı kullanılamıyor.

Visual Studio Kurulumu altyapısı güvenilir yalnızca içerik yükler. Bunu Authenticode imzaları içerik karşıdan yükleniyor ve yüklemeden önce tüm içeriği güvenilen doğrulama denetleyerek yapar. Bu, ortamınız indirme konumu burada tehlikeye saldırılarına karşı güvenli tutar. Visual Studio Kurulumu, bu nedenle birkaç standart Microsoft kök ve ara sertifika yüklü olmasını gerektirir ve yukarı tarih kullanıcının makinede. Makine Windows Update ile güncel tutulmuştur, imzalama sertifikaları genellikle güncel demektir. Makinenin Internet'e bağlı olup olmadığını yükleme sırasında Visual Studio gerektiğinde dosya imzaları doğrulamak sertifikaları yenileme. Makine çevrimdışıysa, sertifikalar olmalıdır başka bir yolu yenilenir.

## <a name="how-to-refresh-certificates-when-offline"></a>Sertifikaları çevrimdışıyken yenileme

Yükleme veya çevrimdışı bir ortamda sertifikaları güncelleştirme için üç seçeneğiniz vardır.

### <a name="option-1---manually-install-certificates-from-a-layout-folder"></a>Seçenek 1 - sertifikalar bir düzen klasörden el ile yükleme

Bir ağ düzeni oluşturduğunuzda, gerekli sertifikaları Sertifikalar klasörüne yüklenir. Daha sonra el ile sertifikalar sertifika dosyaların her biri çift ve Sertifika Yöneticisi sihirbazda tıklatarak yükleyebilirsiniz. İçin bir parola istenirse, boş bırakın.

### <a name="option-2---distribute-trusted-root-certificates-in-an-enterprise-environment"></a>Seçenek 2 - güvenilen kök dağıtmak bir kuruluş ortamında sertifikaları

En son kök sertifikası olmayan çevrimdışı makinelerle kuruluşlar için bir yönetici yönergeleri kullanabilirsiniz [güvenilen kökler yapılandırmanız ve izin verilmeyen sertifikaları](https://technet.microsoft.com/library/dn265983.aspx) sayfa bunları güncelleştirin.

### <a name="option-3---install-certificates-as-part-of-a-scripted-deployment-of-visual-studio"></a>Seçenek 3 - Visual Studio komut dosyalı bir dağıtımının bir parçası olarak yükleme sertifikaları

Visual Studio dağıtım istemci iş istasyonlarına çevrimdışı bir ortamda komut dosyalarını oluşturuyorsanız, aşağıdaki adımları izlemelisiniz:

1. Kopya [sertifika yönetim aracı](/dotnet/framework/tools/certmgr-exe-certificate-manager-tool) (certmgr.exe) yükleme paylaşımına (örneğin, \\server\share\vs2017). Certmgr.exe dahil değildir ancak kendisi, Windows'un parçası olarak kullanılabilir olarak parçası [Windows SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).

2. Bir toplu iş dosyası aşağıdaki komutlarla oluşturun:

   ```cmd
   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Code Signing PCA 2011" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Time-Stamp PCA 2010" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Code Signing PCA" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
   ```

3. Toplu iş dosyasını istemciye dağıtın. Bu komut, yükseltilmiş bir işleminden çalıştırmanız gerekir.

## <a name="what-are-the-certificates-files-in-the-certificates-folder"></a>Sertifikalar klasörünü sertifikaları dosyalarında nelerdir?

Üç. P12 bu klasördeki dosyaların her bir ara sertifika ve bir kök sertifikası içerir. Windows Update ile güncel çoğu sistemleri bu sertifikaların zaten yüklü.

* **ManifestSignCertificates.p12** içerir:
    * Ara Sertifika: **Microsoft kod imzalama PCA 2011**
        * Gerekli değildir. Varsa, bazı senaryolarda performansı artırır.
    * Kök sertifika: **Microsoft kök sertifika yetkilisi 2011**
        * En son Windows güncelleştirmeleri yüklü olmayan Windows 7 Service Pack 1 sistemlerde gerekli.
* **ManifestCounterSignCertificates.p12** içerir:
    * Ara Sertifika: **Microsoft zaman damgası PCA 2010**
        * Gerekli değildir. Varsa, bazı senaryolarda performansı artırır.
    * Kök sertifika: **Microsoft kök sertifika yetkilisi 2010**
        * En son Windows güncelleştirmeleri yüklü olmayan Windows 7 Service Pack 1 sistemler için gereklidir.
* **Vs_installer_opc. SignCertificates.p12** içerir:
    * Ara Sertifika: **Microsoft kod imzalama PCA**
        * Tüm sistemler için gereklidir. Tüm güncelleştirmeleri Windows Update'ten uygulanan sistemleriyle bu sertifikayı olmayabilir unutmayın.
    * Kök sertifika: **Microsoft kök sertifika yetkilisi**
        * Gerekli. Bu sertifika, Windows 7 veya üstünü çalıştıran sistemleri ile gelir.

## <a name="why-are-the-certificates-from-the-certificates-folder-not-installed-automatically"></a>Neden sertifikaları otomatik olarak yüklenmemiş sertifikaları klasöründen misiniz?

İmza bir çevrimiçi ortamda doğrulandığında, Windows API'ları indirmek ve sertifikaları sisteme eklemek için kullanılır. Sertifika güvenilir ve yönetim ayarları izin doğrulama Bu işlem sırasında oluşur. Bu doğrulama işlemi, en çevrimdışı ortamlarda gerçekleşemez. Sertifikaları el ile yükleme sertifikaları Güvenilen ve bunların kuruluşun güvenlik ilkesi karşıladığından emin olmak kuruluş yöneticileri sağlar.

## <a name="checking-if-certificates-are-already-installed"></a>Sertifikalar zaten yüklü olmadığı denetleniyor

Yükleme sistemde kontrol etmenin bir yolu şu adımları takip etmektir:
1. Çalıştırma **mmc.exe**.<br/>
  a. Dosyasına tıklayın ve ardından **Ekle/Kaldır ek bileşenini**.<br/>
  b. Çift **sertifikaları**seçin **bilgisayar hesabı**ve ardından **sonraki**.<br/>
  c. Seçin **yerel bilgisayar**, tıklatın **son**ve ardından **Tamam**.<br/>
  d. Genişletme **sertifikalar (yerel bilgisayar)**.<br/>
  e. Genişletme **güvenilen kök sertifika yetkilileri**ve ardından **Sertifikalar**.<br/>
    * Bu gerekli kök sertifikalar listesini denetler.<br/>

   f. Genişletme **Ara Sertifika Yetkilileri**ve ardından **Sertifikalar**.<br/>
    * Gerekli Ara sertifikaları için bu listeyi kontrol edin.<br/>

2. Dosya ve Seç'i tıklatın **Ekle/Kaldır ek bileşenini**.<br/>
  a. Çift **sertifikaları**seçin **kullanıcı hesabım**, tıklatın **son**ve ardından **Tamam**.<br/>
  b. Genişletme **Sertifikalar – Geçerli kullanıcı**.<br/>
  c. Genişletme **Ara Sertifika Yetkilileri**ve ardından **Sertifikalar**.<br/>
    * Gerekli Ara sertifikaları için bu listeyi kontrol edin.<br/>

Sertifika adlarını da olsalar **çıkarılan** sütunları, yüklü olması gerekir.  Ara Sertifika yalnızca içinde olduğunda **geçerli kullanıcı** ara sertifika deposu, sonra da günlüğe kaydedilen kullanıcı için kullanılabilir. Diğer kullanıcılar için yüklemeniz gerekebilir.

## <a name="install-visual-studio"></a>Visual Studio yükleme

Sertifikalar yüklendikten sonra Visual Studio dağıtımını yönergeleri kullanarak geçebilmeniz [bir ağ yüklemesinden dağıtma](create-a-network-installation-of-visual-studio.md#deploying-from-a-network-installation) bölümünde "Visual Studio bir ağ yüklemesi oluşturma".

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio'yu yükleyin](install-visual-studio.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio iş yükü ve bileşen kimlikleri](workload-and-component-ids.md)
