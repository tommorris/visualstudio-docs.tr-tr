---
title: -SafeMode (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2c678d7304c879cf42c24de9d83704971043676
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
Başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] güvenli modda, yalnızca varsayılan ortamı ve Hizmetleri Yükleniyor.

## <a name="syntax"></a>Sözdizimi

```cmd
devenv /SafeMode
```

## <a name="remarks"></a>Açıklamalar
 Bu anahtar tüm üçüncü taraf VSPackages ne zaman yüklenmesini engeller [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] başlar, bu nedenle kararlı yürütme sağlama.

## <a name="description"></a>Açıklama
 Aşağıdaki örnek başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] güvenli modda.

## <a name="code"></a>Kod

```cmd
Devenv.exe /SafeMode
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)