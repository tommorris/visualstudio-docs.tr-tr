---
title: DevEnv Build anahtarı
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- builds, command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
- command-line builds
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 777347ba36cf3443a509d1d6c8c44c23a86901e0
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34764975"
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)

Belirtilen çözüm yapılandırma dosyası kullanarak bir çözüm oluşturur.

## <a name="syntax"></a>Sözdizimi

```cmd
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]
```

## <a name="arguments"></a>Arguments

|||
|-|-|
|*solutionName*|Gerekli. Tam yol ve çözüm dosyasının adı.|
|*SolnConfigName*|Gerekli. Adlı çözümü oluşturmak için kullanılan çözüm yapılandırmasının adı *SolutionName*. Birden çok çözüm platformu varsa de platform örneğin belirtmelisiniz **"hata ayıklama\|Win32"**.|
|/ project *ProjName*|İsteğe bağlı. Yol ve çözüm içinde proje dosyasının adı. Gelen göreli bir yol girin *SolutionName* klasörü proje dosyası veya projenin görünen adı veya tam yolunu ve proje dosyasının adı.|
|/ projectconfig *ProjConfigName*|İsteğe bağlı. Bir proje adını derleme adlandırılmış proje oluşturulurken kullanılacak yapılandırma. Birden çok proje platformları varsa de platform örneğin belirtmelisiniz **"hata ayıklama\|Win32"**.|

## <a name="remarks"></a>Açıklamalar

- **/Build** anahtarı ile aynı işlevi gerçekleştirir **yapı çözümü** tümleşik geliştirme ortamı (IDE) içinde menü komutu.

- Çift tırnak içine boşluk dizeler alın.

- Komut penceresinde veya ile belirtilen herhangi bir günlük dosyasını derlemeleri hatalar dahil olmak üzere, ilgili özet bilgileri görüntülenebilir **/out** geçin.

- **/Build** anahtar yalnızca son derlemeden bu yana değişmiş projeleri oluşturur. Bir çözümdeki tüm projeleri oluşturmak üzere kullanmak [/rebuild](../../ide/reference/rebuild-devenv-exe.md) yerine.

- Bildiren bir hata iletisi alırsanız **geçersiz bir proje yapılandırma**, bir çözüm platformu veya proje platform, örneğin belirlediğiniz olduğundan emin olun **"hata ayıklama\|Win32"**.

## <a name="example"></a>Örnek

Aşağıdaki komut "CSharpConsoleApp", "Hata ayıklama" proje derleme yapılandırmasını "MySolution" "Hata ayıklama" Çözüm yapılandırmasını içinde kullanarak proje oluşturur.

```cmd
devenv "C:\Visual Studio Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Ayrıca bkz.

- [Projeleri ve çözümleri oluşturma ve temizleme](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Devenv komut satırı wwitches](../../ide/reference/devenv-command-line-switches.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)