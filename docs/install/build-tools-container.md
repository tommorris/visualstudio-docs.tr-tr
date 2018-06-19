---
title: Bir kapsayıcıya yapı Visual Studio Araçları yükleme
description: Visual Studio derleme araçları sürekli tümleştirme ve kesintisiz teslim (CI/CD) iş akışlarını desteklemek için Windows kapsayıcıya yüklemeyi öğrenin.
ms.custom: ''
ms.date: 04/18/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: d5c038e2-e70d-411e-950c-8a54917b578a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d9dc5b1add4f81e91d0ea0e2cdc20e2581116525
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
ms.locfileid: "31624898"
---
# <a name="install-build-tools-into-a-container"></a>Bir kapsayıcıya derleme araçlarını yükleme

Visual Studio derleme araçları sürekli tümleştirme ve kesintisiz teslim (CI/CD) iş akışlarını desteklemek için Windows kapsayıcıya yükleyebilirsiniz. Bu makale, hangi Docker yapılandırma değişikliklerini ne yanı sıra gerekli aracılığıyla size rehberlik eder [iş yükleri ve bileşenleri](workload-component-id-vs-build-tools.md) bir kapsayıcıda yükleyebilirsiniz.

[Kapsayıcıları](https://www.docker.com/what-container) yalnızca bir CI/CD sunucu ortamında, ancak geliştirme ortamları için kullanabileceğiniz bir tutarlı yapı sistemi paketlemek için harika bir yoludur. Örneğin, kaynak kodunuzu kodunuzu yazmak için Visual Studio veya diğer araçlar kullanmaya devam ederken özelleştirilmiş ortamı tarafından oluşturulacak bir kapsayıcıya bağlayabilir. CI/CD akışınızı aynı kapsayıcı görüntü kullanıyorsa, kodunuzu tutarlı bir şekilde derlemeler olabilirsiniz tuttuğunuzda. Kapsayıcıları orchestration sistemi ile birden çok kapsayıcı kullanarak mikro hizmetler için ortak olan çalışma zamanı tutarlılık için de kullanabilirsiniz; Ancak, bu makalenin kapsamı dışındadır olur.

Kaynak kodunuz oluşturmanız için gerekli derleme Visual Studio Araçları sahip değilse, diğer Visual Studio ürünler için aynı adımları kullanılabilir. Ancak, tüm komutları otomatik şekilde Windows kapsayıcıları etkileşimli bir kullanıcı arabirimi desteklemeyen unutmayın.

## <a name="overview"></a>Genel Bakış

Kullanarak [Docker](https://www.docker.com/what-docker) kaynak kodu derleme kapsayıcıları içinden oluşturabileceğiniz bir görüntü oluşturun. Örnek, en son Visual Studio derleme araçları 2017 ve genellikle kaynak kodu oluşturmak için kullanılan diğer bazı yardımcı programlar Dockerfile yükler. Daha fazla diğer araçları ve testler, yapı çıktı yayımlamak için komut dosyaları dahil olmak üzere kendi Dockerfile ve daha fazlasını değiştirebilirsiniz.

Windows için Docker daha önce yüklediyseniz, 3. adıma atlayabilirsiniz.

## <a name="step-1-enable-hyper-v"></a>Adım 1. Hyper-V etkinleştir

Hyper-V varsayılan olarak etkin değildir. Windows için Docker başlatmak için etkinleştirilmelidir, yalnızca Hyper-V yalıtım Windows 10 için şu anda itibaren desteklenir.

* [Windows 10 üzerinde Hyper-V etkinleştir](https://docs.microsoft.com/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v)
* [Windows Server 2016 üzerinde Hyper-V etkinleştir](https://docs.microsoft.com/windows-server/virtualization/hyper-v/get-started/install-the-hyper-v-role-on-windows-server)

> [!NOTE]
> Sanallaştırma makinenizde etkinleştirilmesi gerekir. Bu, genellikle varsayılan olarak etkindir; Ancak, Hyper-V yükleme başarısız olursa, sanallaştırma etkinleştirme için sistemi belgelerinize başvurun.

## <a name="step-2-install-docker-for-windows"></a>Adım 2. Windows için Docker yükleyin

Windows 10 kullanıyorsanız, yapabilecekleriniz [Docker Community Edition yükleyip](https://docs.docker.com/docker-for-windows/install). Windows Server 2016 kullanıyorsanız, izleyin [Docker Enterprise Edition'ı yüklemek için yönergeleri](https://docs.docker.com/install/windows/docker-ee).

## <a name="step-3-switch-to-windows-containers"></a>Adım 3. Windows için kapsayıcılar anahtar

Yalnızca derleme araçları 2017 gerektiren Windows'ta yükleyebilirsiniz [geçiş Windows kapsayıcılara](https://docs.docker.com/docker-for-windows/#getting-started-with-windows-containers). Windows 10 Windows kapsayıcıları desteği yalnızca [Hyper-V yalıtım](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container), Windows Server 2016 Windows kapsayıcılarında hem Hyper-V desteklemek ve işlem yalıtım.

## <a name="step-4-expand-maximum-container-disk-size"></a>4. adım. En fazla kapsayıcı disk boyutunu genişletme

Visual Studio Araçları - oluşturmak ve bir büyük ölçüde Visual Studio - yüklü için tüm araçları çok disk alanı gerektirir. Dockerfile örnek paket önbelleğini devre dışı bırakır olsa bile, kapsayıcı görüntülerinin disk boyutunu gerekli alanı uyum sağlamak için daha yüksek olmalıdır. Şu anda, Windows, yalnızca disk boyutu Docker yapılandırma değiştirerek artırabilirsiniz.

**Windows 10**:

1. [Windows için Docker simgesine Rick tıklatma](https://docs.docker.com/docker-for-windows/#docker-settings) tıklatın ve sistem tepsisi **ayarları...** .
2. [Arka plan tıklatın](https://docs.docker.com/docker-for-windows/#docker-daemon) bölümü.
3. [İki durumlu **temel** ](https://docs.docker.com/docker-for-windows/#edit-the-daemon-configuration-file) düğmesine **Gelişmiş**.
4. (Daha fazla yapı araçları için yeterli büyümek için yeriniz olan) 120 GB disk alanı artırmak için aşağıdaki JSON dizisi özelliği ekleyin.

   ```json
   {
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

   Bu özellik zaten bir şey eklenir. Örneğin, varsayılan arka plan programı yapılandırma dosyasına uygulanan bu değişikliklerle görmelisiniz:

   ```json
   {
     "registry-mirrors": [],
     "insecure-registries": [],
     "debug": true,
     "experimental": true,
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

5. Tıklatın **uygulamak**.

**Windows Server 2016**:

1. "Docker" hizmetini durdurun:

   ```shell
   sc.exe stop docker
   ```

2. Yükseltilmiş bir komut isteminden "% ProgramData%\Docker\config\daemon.json" Düzenle (veya ne olursa olsun için belirtilen `dockerd --config-file`).
3. (Daha fazla yapı araçları için yeterli büyümek için yeriniz olan) 120 GB disk alanı artırmak için aşağıdaki JSON dizisi özelliği ekleyin.

   ```json
   {
     "storage-opts": [
       "size=120GB"
     ]
   }
   ```

   Bu özellik zaten bir şey eklenir.
4. Dosyayı kaydedin ve kapatın.
5. "Docker" hizmetini başlatın:

   ```shell
   sc.exe start docker
   ```

## <a name="step-5-create-and-build-the-dockerfile"></a>5. adım. Oluşturun ve Dockerfile yapılandırın

Aşağıdaki örnek Dockerfile diskinizdeki yeni bir dosyaya kaydedin. Dosyayı yalnızca "Dockerfile" ise, varsayılan olarak kabul edilir.

> [!NOTE]
> Bu örnek Dockerfile kapsayıcılarına yüklenemez eski Windows SDK yalnızca dışlar. Eski sürümleri yapı komutunun başarısız olmasına neden.

1. Bir komut istemi açın.
2. (Önerilen) yeni bir dizin oluşturun:

   ```shell
   mkdir C:\BuildTools
   ```

3. Dizinleri bu yeni dizine değiştirin:

   ```shell
   cd C:\BuildTools
   ```

3. Aşağıdaki içeriği için C:\BuildTools\Dockerfile kaydedin.

   ```dockerfile
   # escape=`

   # Use the latest Windows Server Core image with .NET Framework 4.7.1.
   FROM microsoft/dotnet-framework:4.7.1

   # Download the Build Tools bootstrapper.
   ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe

   # Install Build Tools excluding workloads and components with known issues.
   RUN C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
       --installPath C:\BuildTools `
       --all `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
       --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
       --remove Microsoft.VisualStudio.Component.Windows81SDK `
    || IF "%ERRORLEVEL%"=="3010" EXIT 0

   # Start developer command prompt with any other commands specified.
   ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

   # Default to PowerShell if no other command specified.
   CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
   ```

   > [!NOTE]
   > Doğrudan microsoft/windowsservercore üzerinde görüntünüzü dayandırırsanız, .NET Framework yüklenemeyebilir ve hiçbir yükleme hatası gösterilir. Yükleme tamamlandıktan sonra yönetilen kod çalışmayabilir. Görüntünüzü bunun yerine, temel [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) ya da daha yeni.

4. Bu dizin içinde aşağıdaki komutu çalıştırın.

   ```shell
   docker build -t buildtools2017:latest -m 2GB .
   ```

   Bu komut, 2 GB bellek kullanarak geçerli dizinde Dockerfile oluşturur. Bazı iş yükleri yüklendiğinde varsayılan 1 GB yeterli değildir; Ancak, yalnızca 1 GB bellek, yapı gereksinimlerinize bağlı olarak oluşturmak mümkün olabilir.

   Son görüntü etiketli "buildtools2017:latest" olduğundan, hiçbir etiketi belirtilmişse, "en son" etiketi varsayılan olduğundan kolayca bir kapsayıcıda "buildtools2017" çalıştırabilirsiniz. Visual Studio derleme araçları 2017 belirli bir sürümünü daha içinde kullanmak istiyorsanız, [Gelişmiş senaryo](advanced-build-tools-container.md), bunun yerine belirli bir kapsayıcıda etiketi kapsayıcıları belirli bir kullanabilmeniz için yapı numarası yanı sıra "en son"'Visual Studio Sürüm tutarlı bir şekilde.

## <a name="step-6-using-the-built-image"></a>6. adım. Yerleşik görüntü kullanma

Bir görüntü oluşturduğunuza göre etkileşimli ve otomatik yapıları yapmak için bir kapsayıcı çalıştırabilirsiniz. Örnek Geliştirici komut istemi kullanır, bu nedenle, yol ve diğer ortam değişkenleri zaten yapılandırılmış.

1. Bir komut istemi açın.
2. Kapsayıcı tüm developer ile bir PowerShell ortamını başlatmak için ayarlanan ortam değişkenlerine çalıştırın:

   ```shell
   docker run -it buildtools2017
   ```

CI/CD iş akışınız için bu görüntüyü kullanmak için kendi için yayımlayabilirsiniz [Azure kapsayıcı kayıt defteri](https://azure.microsoft.com/services/container-registry) veya diğer iç [Docker kayıt defteri](https://docs.docker.com/registry/deploying) sunucuları yalnızca bu çekme gerekiyor.

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Kapsayıcılar için İleri Düzey Örnek](advanced-build-tools-container.md)
* [Kapsayıcılar için Bilinen Sorunlar](build-tools-container-issues.md)
* [Visual Studio derleme araçları 2017 iş yükü ve Bileşen kimlikleri](workload-component-id-vs-build-tools.md)
