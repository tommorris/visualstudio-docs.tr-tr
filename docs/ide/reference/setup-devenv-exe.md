---
title: "Devenv.exe kurulum anahtarını | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93f03de74540d130d66ce123b355691e0828b93e
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)

/ Setup nedenler menüleri ve araç çubukları komutu gruplarından tüm kullanılabilir VSPackages açıklayan kaynak meta veriler birleştirmek için Visual Studio geçin.

## <a name="syntax"></a>Sözdizimi

```
devenv /setup
```

## <a name="remarks"></a>Açıklamalar

Bu anahtar hiçbir bağımsız değişkenleri alır. `devenv /setup` Komutu genellikle yükleme işleminin son adımı verilir. Kullanımı `/setup` anahtar Visual Studio başlatılmaz.

Çalıştırmalısınız `devenv` kullanmak için yönetici olarak [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) ve [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) anahtarları.

## <a name="example"></a>Örnek

Bu örnek son adımı VSPackages içeren Visual Studio sürümünü yüklemeyi gösterir.

```
devenv /setup
```

## <a name="see-also"></a>Ayrıca bkz.

[Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)