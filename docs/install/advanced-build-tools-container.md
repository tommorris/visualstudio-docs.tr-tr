---
title: "Örnek kapsayıcı için Gelişmiş | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e03835db-a616-41e6-b339-92b41d0cfc70
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: c1eb932eb079bca61eb5cea0959c56f00379114c
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="advanced-example-for-containers"></a>Gelişmiş örnek kapsayıcıları için

Dockerfile örnek içinde [bir kapsayıcı halinde derleme araçlarını yükleme](build-tools-container.md) her zaman en son microsoft/windowsservercore görüntü ve en son Visual Studio derleme araçları 2017 yükleyici kullanır. Bu görüntü yayımlarsanız bir [Docker kayıt defteri](https://azure.microsoft.com/services/container-registry) başkalarının çıkarmak bu görüntüyü birçok senaryo için uygun olabilir. Uygulamada, ancak hangi temel görüntü hakkında belirli olması için daha yaygın bir durumdur ve yüklediğiniz sürümleri aracı, karşıdan, hangi ikili dosyaları kullanın.

Aşağıdaki örnek Dockerfile microsoft/windowsservercore görüntünün belirli sürüm etiketi kullanır. Belirli bir etiket için bir temel görüntü kullanarak sıradan bir hale ve bu binanın anımsaması kolay hale getirir ya da aynı temel sahip görüntüleri her zaman yeniden oluşturma.

> [!NOTE]
> Bir kapsayıcıda yükleyici başlatma sorunlara microsoft/windowsservercore:10.0.14393.1593 Visual Studio yükleyemiyor. Daha fazla bilgi için bkz: [bilinen sorunlar](build-tools-container-issues.md).

Bu örnek ayrıca önyükleyici aynı zamanda yerleşik belirli bir sürümü yükler derleme araçları 2017 önyükleyici kullanır. Ürün sürümü kanal hala güncelleştirilemedi, ancak genellikle yeniden kapsayıcıları için kullanışlı bir senaryo değil. URL'ler için belirli bir kanalı almak istiyorsanız, https://aka.ms/vs/15/release/channel kanalı yükle, JSON dosyasını açın ve önyükleyici URL'leri inceleyin. Daha fazla bilgi için bkz: [Visual Studio bir ağ yüklemesi oluşturmak](create-a-network-installation-of-visual-studio.md).

```dockerfile
# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:d841bd78721c74f9b88e2700f5f3c2d66b54cb855b8acb4ab2c627a76a46301d
FROM microsoft/windowsservercore:10.0.14393.1770

# Use PowerShell commands to download, validate hashes, etc.
SHELL ["powershell.exe", "-ExecutionPolicy", "Bypass", "-Command", "$ErrorActionPreference='Stop'; $ProgressPreference='SilentlyContinue'; $VerbosePreference = 'Continue';"]

# Download Build Tools 15.4.27004.2005 and other useful tools.
ENV VS_BUILDTOOLS_URI=https://aka.ms/vs/15/release/6e8971476/vs_buildtools.exe \
    VS_BUILDTOOLS_SHA256=D482171C7F2872B6B9D29B116257C6102DBE6ABA481FAE4983659E7BF67C0F88 \
    NUGET_URI=https://dist.nuget.org/win-x86-commandline/v4.1.0/nuget.exe \
    NUGET_SHA256=4C1DE9B026E0C4AB087302FF75240885742C0FAA62BD2554F913BBE1F6CB63A0

# Download tools to C:\Bin and install Build Tools excluding workloads and components with known issues.
RUN New-Item -Path C:\Bin, C:\TEMP -Type Directory | Out-Null; \
    [System.Environment]::SetEnvironmentVariable('PATH', "\"${env:PATH};C:\Bin\"", 'Machine'); \
    function Fetch ([string] $Uri, [string] $Path, [string] $Hash) { \
      Invoke-RestMethod -Uri $Uri -OutFile $Path; \
      if ($Hash -and ((Get-FileHash -Path $Path -Algorithm SHA256).Hash -ne $Hash)) { \
        throw "\"Download hash for '$Path' incorrect\""; \
      } \
    }; \
    Fetch -Uri $env:NUGET_URI -Path C:\Bin\nuget.exe -Hash $env:NUGET_SHA256; \
    Fetch -Uri $env:VS_BUILDTOOLS_URI -Path C:\TEMP\vs_buildtools.exe -Hash $env:VS_BUILDTOOLS_SHA256; \
    Fetch -Uri 'https://aka.ms/vscollect.exe' -Path C:\TEMP\collect.exe; \
    $p = Start-Process -Wait -PassThru -FilePath C:\TEMP\vs_buildtools.exe -ArgumentList '--quiet --wait --norestart --nocache --installPath C:\BuildTools --all --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 --remove Microsoft.VisualStudio.Component.Windows81SDK'; \
    if (($ret = $p.ExitCode) -and ($ret -ne 3010)) { C:\TEMP\collect.exe; throw ('Install failed with exit code 0x{0:x}' -f $ret) }

# Restore default shell for Windows containers.
SHELL ["cmd.exe", "/s", "/c"]

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

Bu örnek, belirli araçları indirir ve karmaları eşleştiğini doğrular. Yükleme hatası oluşursa, bu hatayı çözümlemek için konak makine günlükleri kopyalayabilirsiniz. böylece en son Visual Studio ve .NET günlük toplama yardımcı programının de yükler.

```shell
> docker build -t buildtools:15.4.27004.2005 -t buildtools:latest -m 2GB .
Sending build context to Docker daemon
...
Step 4/7 : RUN New-Item -Path C:\Bin, C:\TEMP -Type Directory | Out-Null; ...
 ---> Running in 4b62b4ce3a3c
Install failed with exit code 0x643
At line:1 char:1
+ throw ('Install failed with exit code 0x{0:x}' -f 1603)
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (Install failed with exit code 0x643:String) [], RuntimeException
    + FullyQualifiedErrorId : Install failed with exit code 0x643

> docker cp 4b62b4ce3a3c:C:\Users\ContainerAdministrator\AppData\Local\TEMP\vslogs.zip "%TEMP%\vslogs.zip"
```

Son satırı yürütme sona erdikten sonra "% TEMP%\vslogs.zip" makinenizde açın veya sorun gönderme sırasında [Geliştirici topluluğu](https://developercommunity.visualstudio.com) web sitesi.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sorun giderme ipuçları için sayfa. Ürün sorunları bize de bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı Visual Studio IDE içinde veya üzerinde bir öneri bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579). Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun. Bize ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio) (gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca bkz.
* [Bir kapsayıcıya derleme araçlarını yükleme](build-tools-container.md)
* [Kapsayıcıları için bilinen sorunlar](build-tools-container-issues.md)
