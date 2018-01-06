---
title: "Hata: Karışık mod hata ayıklama yalnızca Microsoft .NET Framework 4 kullanırken işlemler desteklenir x64 için veya büyük | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 87ca4ffe1a80d6d6fdc948c3a1617f888aba4baf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-mixed-mode-debugging-for-x64-processes-is-supported-only-when-using-microsoft-net-framework-4-or-greater"></a>Hata: x64 işlemleri için karışık modda hata ayıklama yalnızca Microsoft .NET Framework 4 veya daha yenisi kullanılırken desteklenir
64 bitlik bir işlem karışık yerel ve yönetilen kodda hata ayıklamak için bilmeniz gereken [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürüm 4. 64 bit işlemleri ile karışık mod hata ayıklaması [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 4 desteklenmiyor'den önceki sürümleri.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Aşağıdaki adımlardan birini uygulayın:  
  
    -   Yükseltme, [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürüm 4.  
  
    -   Hata ayıklama için uygulamanızın 32-bit sürümünü oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)