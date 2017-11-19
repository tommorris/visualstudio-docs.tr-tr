---
title: "Bir kapsayıcıya derleme araçlarını yükleme | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5c038e2-e70d-411e-950c-8a54917b578a
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: 3a48ba73e51af789e4017a104d7ea2f70338f3e9
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="install-build-tools-into-a-container"></a>Bir kapsayıcıya derleme araçlarını yükleme

Visual Studio derleme araçları sürekli tümleştirme ve kesintisiz teslim (CI/CD) iş akışlarını desteklemek için Windows kapsayıcıya yükleyebilirsiniz. Bu makale, hangi Docker yapılandırma değişikliklerini ne yanı sıra gerekli aracılığıyla size rehberlik eder [iş yükleri ve bileşenleri](workload-component-id-vs-build-tools.md) bir kapsayıcıda yükleyebilirsiniz.

[Kapsayıcıları](https://www.docker.com/what-container) yalnızca bir CI/CD sunucu ortamında, ancak geliştirme ortamları için kullanabileceğiniz bir tutarlı yapı sistemi paketlemek için harika bir yoludur. Örneğin, kaynak kodunuzu kodunuzu yazmak için Visual Studio veya diğer araçlar kullanmaya devam ederken özelleştirilmiş ortamı tarafından oluşturulacak bir kapsayıcıya bağlayabilir. CI/CD akışınızı aynı kapsayıcı görüntü kullanıyorsa, kodunuzu tutarlı bir şekilde derlemeler olabilirsiniz tuttuğunuzda. Kapsayıcıları mikro hizmetler orchestration sistemi ile birden çok kapsayıcı kullanarak yaygın bir durumdur, ancak bu makalenin kapsamı dışındadır çalışma zamanı tutarlılık için de kullanabilirsiniz.

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

Windows 10 kullanıyorsanız, karşıdan yükleyip kurabileceğiniz [için Docker Community Edition Windows](https://www.docker.com/docker-windows). PowerShell kullanabilirsiniz [Windows Server 2016 için Docker Enterprise Edition yüklemek](https://docs.docker.com/engine/installation/windows/docker-ee) istenen durum yapılandırması (DSC) kullanarak veya bir [paket sağlayıcısı](https://docs.microsoft.com/virtualization/windowscontainers/deploy-containers/deploy-containers-on-server) basit, tek bir yükleme için.

## <a name="step-3-switch-to-windows-containers"></a>Adım 3. Windows için kapsayıcılar anahtar

Yalnızca derleme araçları 2017 gerektiren Windows'ta yükleyebilirsiniz [geçiş Windows kapsayıcılara](https://docs.docker.com/docker-for-windows/#getting-started-with-windows-containers). Windows 10 Windows kapsayıcıları desteği yalnızca [Hyper-V yalıtım](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container), Windows Server 2016 Windows kapsayıcılarında hem Hyper-V desteklemek ve işlem yalıtım.

## <a name="step-4-expand-maximum-container-disk-size"></a>4. adım. En fazla kapsayıcı disk boyutunu genişletme

Visual Studio Araçları - oluşturmak ve bir büyük ölçüde Visual Studio - yüklü için tüm araçları çok disk alanı gerektirir. Örneğimizde Dockerfile paket önbelleğini devre dışı bırakır olsa bile, kapsayıcı görüntülerinin disk boyutunu gerekli alanı uyum sağlamak için daha yüksek olmalıdır. Şu anda, Windows, yalnızca disk boyutu Docker yapılandırma değiştirerek artırabilirsiniz.

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

Aşağıdaki örnek Dockerfile diskinizdeki yeni bir dosyaya kaydetmeniz gerekir. Dosyayı yalnızca "Dockerfile" ise, varsayılan olarak kabul edilir.

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
   # Use the latest Windows Server Core image.
   FROM microsoft/windowsservercore

   # Download useful tools to C:\Bin.
   ADD https://dist.nuget.org/win-x86-commandline/v4.1.0/nuget.exe C:\\Bin\\nuget.exe

   # Download the Build Tools bootstrapper outside of the PATH.
   ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\\TEMP\\vs_buildtools.exe

   # Add C:\Bin to PATH and install Build Tools excluding workloads and components with known issues.
   RUN setx /m PATH "%PATH%;C:\Bin" \
    && C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache --installPath C:\BuildTools --all \
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 \
       --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 \
       --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 \
       --remove Microsoft.VisualStudio.Component.Windows81SDK \
    || IF "%ERRORLEVEL%"=="3010" EXIT 0

   # Start developer command prompt with any other commands specified.
   ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

   # Default to PowerShell if no other command specified.
   CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
   ```

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
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sorun giderme ipuçları için sayfa. Ürün sorunları bize de bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı Visual Studio IDE içinde veya üzerinde bir öneri bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579). Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun. Bize ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio) (gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca bkz.

* [Gelişmiş örnek kapsayıcıları için](advanced-build-tools-container.md)
* [Kapsayıcıları için bilinen sorunlar](build-tools-container-issues.md)
