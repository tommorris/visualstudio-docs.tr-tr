---
title: -ResetSkipPkgs (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /ResetSkipPkgs Devenv switch
- Devenv, /ResetSkipPkgs switch
- ResetSkipPkgs switch
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6199bf96bc631cf1018b2cb72a4d3c3cf7c703cc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="resetskippkgs-devenvexe"></a>/ResetSkipPkgs (devenv.exe)
Yükleme için VSPackages sorun VSPackages yüklenmesini önlemek amacıyla isteyen kullanıcılar tarafından eklenen atlamak için tüm seçenekleri temizler ve ardından başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

## <a name="syntax"></a>Sözdizimi

```
Devenv /ResetSkipPkgs
```

## <a name="remarks"></a>Açıklamalar
 SkipLoading etiketi varlığını bir VSPackage yüklenmesini devre dışı bırakır; Etiket temizleme VSPackage yüklenmesini yeniden etkinleştirir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, tüm SkipLoading etiketleri temizler.

```
Devenv.exe /ResetSkipPkgs
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)