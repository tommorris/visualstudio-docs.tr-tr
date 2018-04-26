---
title: Devenv.exe kurulum anahtarı
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 0f3d78ebb63434df38735bdf24e9d4fcba8f172c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)