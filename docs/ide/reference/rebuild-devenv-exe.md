---
title: -Yeniden (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /rebuild switch
- rebuild Devenv switch (/rebuild)
- projects [Visual Studio], rebuilding
- /rebuild Devenv switch
- applications [Visual Studio], rebuilding
ms.assetid: c5a8a4bf-0e2b-46eb-a44a-8aeb29b92c32
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e462e64df90a7672efa890897b48726a0e764e6c
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="rebuild-devenvexe"></a>/Rebuild (devenv.exe)
Temizler ve belirtilen çözüm yapılandırması oluşturur.

## <a name="syntax"></a>Sözdizimi

```cmd
devenv SolutionName /rebuild SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]
```

## <a name="arguments"></a>Arguments
 `SolnConfigName`

 Gerekli. Adlı çözümü yeniden oluşturmak için kullanılan çözüm yapılandırmasının adı `SolutionName`.

 `SolutionName`

 Gerekli. Tam yol ve çözüm dosyasının adı.

 / Project `ProjName`

 İsteğe bağlı. Yol ve çözüm içinde proje dosyasının adı. Gelen göreli bir yol girin `SolutionName` klasörü proje dosyası veya projenin görünen adı veya tam yolunu ve proje dosyasının adı.

 / projectconfig `ProjConfigName`

 İsteğe bağlı. Bir proje adını derleme yeniden oluştururken kullanılacak yapılandırma `/project` adlı.

## <a name="remarks"></a>Açıklamalar

-   Bu anahtarı ile aynı işlevi gerçekleştirir **çözümü yeniden derle** tümleşik geliştirme ortamı (IDE) içinde menü komutu.

-   Çift tırnak işaretleri boşluk dizeler alın.

-   İlgili özet bilgileri temizler ve hatalar da dahil olmak üzere derlemeleri görüntülenebilir **komutu** penceresinde veya ile belirtilen herhangi bir günlük dosyasını `/out` geçin.

## <a name="example"></a>Örnek
 Bu örnek temizler ve projeyi yeniden oluşturur `CSharpWinApp`kullanarak `Debug` Proje yapı yapılandırması içinde `Debug` çözüm yapılandırmasını `MySolution`.

```cmd
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /rebuild Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)
- [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)