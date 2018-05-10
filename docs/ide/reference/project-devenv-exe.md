---
title: -Proje (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /project Devenv switch
- projects [Visual Studio], rebuilding
- projects [Visual Studio], building
- deployment projects, specifying
- project Devenv switch (/project)
- Devenv, /project switch
- projects [Visual Studio], cleaning
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 588b56c03dbd14b1b7658b92a67b02a6dc3892eb
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)
Yapı, temizleme, yeniden oluşturun veya dağıtmak için belirtilen çözüm yapılandırma içinde tek bir proje tanımlar.

## <a name="syntax"></a>Sözdizimi

```cmd
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]
```

## <a name="arguments"></a>Arguments
 / BUILD

 Tarafından belirtilen proje derlemeler `/project` `ProjName`.

 / clean

 Tüm aracı dosyaları ve yapılandırma sırasında oluşturulan çıktı dizinleri temizler.

 / Rebuild

 Temizler sonra tarafından belirtilen proje derlemeler `/project` `ProjName`.

 / deploy

 Proje derleme veya yeniden sonra dağıtılması belirtir.

 `SolnConfigName`

 Gerekli. Adlı çözüm için uygulanan çözüm yapılandırmasının adı `SolutionName`.

 `SolutionName`

 Gerekli. Tam yol ve çözüm dosyasının adı.

 / Project `ProjName`

 İsteğe bağlı. Yol ve çözüm içinde proje dosyasının adı. Gelen göreli bir yol girin `SolutionName` klasörü proje dosyası veya projenin görünen adı veya tam yolunu ve proje dosyasının adı.

 / projectconfig `ProjConfigName`

 İsteğe bağlı. Bir proje adını derleme uygulanacak yapılandırma `/project` adlı.

## <a name="remarks"></a>Açıklamalar

-   Kullanılması gereken parçası bir `devenv /build`, /`clean`, `/rebuild`, veya `/deploy` komutu.

-   Çift tırnak işaretleri boşluk dizeler alın.

-   Derlemeleri hatalar dahil olmak üzere, ilgili özet bilgileri görüntülenebilir **komutu** penceresinde veya ile belirtilen herhangi bir günlük dosyasını `/out` geçin.

## <a name="example"></a>Örnek
 Bu örnek proje derlemeler `CSharpConsoleApp`kullanarak `Debug` Proje yapı yapılandırması içinde `Debug` çözüm yapılandırmasını `MySolution`.

```cmd
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)
- [/ ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)
- [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ (Devenv.exe) dağıtma](../../ide/reference/deploy-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)