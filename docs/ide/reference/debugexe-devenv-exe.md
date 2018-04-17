---
title: -DebugExe (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
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
ms.openlocfilehash: e0882ae58919cafae71bcb056e74533b7ce64a4e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)