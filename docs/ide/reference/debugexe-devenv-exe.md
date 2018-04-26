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
ms.openlocfilehash: 065648588b51ad6c71ae1a10235da4f096470abe
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
Ayıklanacak belirtilen yürütülebilir dosyasını açar.

## <a name="syntax"></a>Sözdizimi

```
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

```
Devenv.exe /debugexe MyApplication.exe
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)