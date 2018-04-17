---
title: Devenv.exe kurulum anahtarını | Microsoft Docs
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: eee6e30a7489f5097cb17a19513c2a423187c827
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)

/ Setup nedenler menüleri ve araç çubukları komutu gruplarından tüm kullanılabilir VSPackages açıklayan kaynak meta veriler birleştirmek için Visual Studio geçin.

## <a name="syntax"></a>Sözdizimi

```shell
devenv /setup
```

## <a name="remarks"></a>Açıklamalar

Bu anahtar hiçbir bağımsız değişkenleri alır. `devenv /setup` Komutu genellikle yükleme işleminin son adımı verilir. Kullanımı `/setup` anahtar Visual Studio başlatılmaz.

> [!NOTE]
> Çalıştırmalısınız `devenv` kullanmak için yönetici olarak `/setup` geçin.

## <a name="example"></a>Örnek

Bu örnek son adımı VSPackages içeren Visual Studio sürümünü yüklemeyi gösterir.

```shell
devenv /setup
```

## <a name="see-also"></a>Ayrıca bkz.

[Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)