---
title: Kanca işlevlerini rapor | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.hooks
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b9a87a9efe91c8a3739b88a39fac5c391218833
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685769"
---
# <a name="report-hook-functions"></a>Kanca İşlevlerini Raporla
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kanca işlevlerini raporlama](https://docs.microsoft.com/visualstudio/debugger/report-hook-functions).  
  
Bir rapor kanca işlevini kullanarak yüklü [_CrtSetReportHook](http://msdn.microsoft.com/library/1ae7c64f-8c84-4797-9574-b59f00f7a509), her zaman çağrılır [_CrtDbgReport](http://msdn.microsoft.com/library/6e581fb6-f7fb-4716-9432-f0145d639ecc) hata ayıklama raporunu oluşturur. Filtreleme raporların ayırmaları belirli türlerde odaklanmak, başka şeylerin yanında, kullanabilirsiniz. Bir rapor kanca işlevini aşağıdaki gibi bir prototipe sahip olmalıdır:  
  
```  
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 Geçirdiğiniz işaretçiyi **_CrtSetReportHook** türünde **_CRT_REPORT_HOOK**CRTDBG içinde tanımlanan gibi. Y:  
  
```  
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 Çalışma zamanı kitaplığı, kanca işlevini çağırdığında *nRptType* bağımsız değişken içeren rapor kategorisi (**_CRT_WARN**, **_CRT_ERROR**, veya **_CRT _ASSERT**), *szMsg* montajı rapor ileti dizeye bir işaretçi içerir ve *retVal* belirtir olup olmadığını `_CrtDbgReport` normal yürütmenin devam etmelidir rapor veya başlangıç hata ayıklayıcı oluşturduktan sonra. (A *retVal* sıfır değeri, yürütme devam eder, hata ayıklayıcı 1 değerini başlatır.)  
  
 Daha fazla raporlama olmadan gerekli olacak şekilde kanca söz konusu iletiyi tamamen işleyen, döndürme zorunluluğu **TRUE**. Döndürürse **FALSE**, `_CrtDbgReport` rapor normalde ileti olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama kanca işlevi yazma](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 örnek](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)



