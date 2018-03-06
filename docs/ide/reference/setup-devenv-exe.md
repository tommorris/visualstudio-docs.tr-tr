---
title: "Devenv.exe kurulum anahtarını | Microsoft Docs"
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e37fe50eefc36e7b5396f396d2b614851a0bd9cb
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
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