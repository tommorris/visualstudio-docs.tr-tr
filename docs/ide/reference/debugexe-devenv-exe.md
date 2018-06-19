---
title: -DebugExe (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 07dfcbb6064d0f1043c0621534b953a5f5c63e82
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704960"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
Ayıklanacak belirtilen yürütülebilir dosyasını açar.

## <a name="syntax"></a>Sözdizimi

```cmd
Devenv /debugexe ExecutableFile
```

## <a name="arguments"></a>Arguments
 `ExecutableFile`

 Gerekli. Bir .exe dosyası yolu ve dosya adı.

 .Exe dosyası bulunamadı veya yok, hiçbir uyarı veya hata görüntülenir ve [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] normal şekilde başlar.

## <a name="remarks"></a>Açıklamalar
 Aşağıdaki dizeleri `ExecutableFile` parametresi, bu dosyaya bağımsız değişken olarak geçirilir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek dosya açılır `MyApplication.exe` hata ayıklama için.

```cmd
Devenv.exe /debugexe MyApplication.exe
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)