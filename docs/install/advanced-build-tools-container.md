---
title: Gelişmiş örnek kapsayıcıları için
description: ''
ms.custom: ''
ms.date: 04/18/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: e03835db-a616-41e6-b339-92b41d0cfc70
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c941928495dc39dc6b6ecbe9600f39dad969fec2
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
ms.locfileid: "31621151"
---
# <a name="advanced-example-for-containers"></a>Gelişmiş örnek kapsayıcıları için

Dockerfile örnek içinde [bir kapsayıcı halinde derleme araçlarını yükleme](build-tools-container.md) her zaman kullanır [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) görüntü tabanlı en son microsoft/windowsservercore görüntü ve en son Visual Studio derleme araçları 2017 yükleyicisi. Bu görüntü yayımlarsanız bir [Docker kayıt defteri](https://azure.microsoft.com/services/container-registry) başkalarının çıkarmak bu görüntüyü birçok senaryo için uygun olabilir. Bununla birlikte, pratikte hangi temel görüntü hakkında belirli olması için daha yaygın bir durumdur ve yüklediğiniz sürümleri aracı, karşıdan, hangi ikili dosyaları kullanın.

Aşağıdaki örnek Dockerfile belirli sürüm etiketi dotnet/microsoft-framework görüntünün kullanır. Belirli bir etiket için bir temel görüntü kullanarak sıradan bir hale ve bu binanın anımsaması kolay hale getirir ya da aynı temel sahip görüntüleri her zaman yeniden oluşturma.

> [!NOTE]
> Microsoft/windowsservercore:10.0.14393.1593 veya bir kapsayıcı yükleyicisinde başlatma sorunları bilinen temel alan herhangi bir görüntü Visual Studio yükleyemiyor. Daha fazla bilgi için bkz: [bilinen sorunlar](build-tools-container-issues.md).

Aşağıdaki örnek derleme araçları 2017 en son sürümünü yükler. Derleme araçları yükleyebilirsiniz bir kapsayıcıya daha sonra eski bir sürümünü kullanmak istiyorsanız, öncelikle [oluşturma](create-an-offline-installation-of-visual-studio.md) ve [korumak](update-a-network-installation-of-visual-studio.md) bir düzeni.

## <a name="install-script"></a>Komut dosyasını yükleyin

Yükleme hata oluştuğunda günlükleri toplamak için çalışma dizinini aşağıdaki içerik ile "Install.cmd" adlı bir toplu betik oluşturun:

```shell
@if not defined _echo echo off
setlocal enabledelayedexpansion

call %*
if "%ERRORLEVEL%"=="3010" (
    exit /b 0
) else (
    if not "%ERRORLEVEL%"=="0" (
        set ERR=%ERRORLEVEL%
        call C:\TEMP\collect.exe -zip:C:\vslogs.zip

        exit /b !ERR!
    )
)
```

## <a name="dockerfile"></a>Dockerfile

Çalışma dizini "Dockerfile" ile aşağıdaki içeriği oluşturun:

```dockerfile
# escape=`

# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:1a66e2b5f3a5b8b98ac703a8bfd4902ae60d307ed9842978df40dbc04ac86b1b
ARG FROM_IMAGE=microsoft/dotnet-framework:4.7.1-20180410-windowsservercore-1709
FROM ${FROM_IMAGE}

# Copy our Install script.
COPY Install.cmd C:\TEMP\

# Download collect.exe in case of an install failure.
ADD https://aka.ms/vscollect.exe C:\TEMP\collect.exe

# Use the latest release channel. For more control, specify the location of an internal layout.
ARG CHANNEL_URL=https://aka.ms/vs/15/release/channel
ADD ${CHANNEL_URL} C:\TEMP\VisualStudio.chman

# Download and install Build Tools excluding workloads and components with known issues.
ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe
RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
    --installPath C:\BuildTools `
    --channelUri C:\TEMP\VisualStudio.chman `
    --installChannelUri C:\TEMP\VisualStudio.chman `
    --all `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
    --remove Microsoft.VisualStudio.Component.Windows81SDK

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

Geçerli çalışma dizini görüntüde oluşturmak için aşağıdaki komutu çalıştırın:

```shell
docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
```

İsteğe bağlı olarak her ikisi de geçirmek `FROM_IMAGE` veya `CHANNEL_URL` kullanarak bağımsız değişkenleri `--build-arg` farklı bir temel görüntüsü veya bir sabit görüntü korumak için bir iç düzeni konumunu belirtmek için komut satırı anahtarı.

## <a name="diagnosing-install-failures"></a>Yükleme hatalarını tanılama

Bu örnek, belirli araçları indirir ve karmaları eşleştiğini doğrular. Böylece bir yükleme hatası oluşursa, bu hatayı çözümlemek için konak makine günlükleri kopyalayabilirsiniz en son Visual Studio ve .NET günlük toplama yardımcı programının de yükler.

```shell
> docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
Sending build context to Docker daemon
...
Step 8/10 : RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache ...
 ---> Running in 4b62b4ce3a3c
The command 'cmd /S /C C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe ...' returned a non-zero code: 1603

> docker cp 4b62b4ce3a3c:C:\vslogs.zip "%TEMP%\vslogs.zip"
```

Son satırı yürütme sona erdikten sonra "% TEMP%\vslogs.zip" makinenizde açın veya sorun gönderme sırasında [Geliştirici topluluğu](https://developercommunity.visualstudio.com) web sitesi.

## <a name="get-support"></a>Destek alma

Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yükleme başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Derleme Araçlarını Bir Kapsayıcıya Yükleme](build-tools-container.md)
* [Kapsayıcılar için Bilinen Sorunlar](build-tools-container-issues.md)
* [Visual Studio derleme araçları 2017 iş yükü ve Bileşen kimlikleri](workload-component-id-vs-build-tools.md)
