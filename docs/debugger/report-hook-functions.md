---
title: Kanca işlevlerini raporlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 562944404d3e02a2e5768fcd74c67302475e6190
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31481184"
---
# <a name="report-hook-functions"></a>Kanca İşlevlerini Raporla
Kullanılarak yüklenen bir rapor kanca işlevini [_CrtSetReportHook](/cpp/c-runtime-library/reference/crtsetreporthook), her seferinde adlı [_CrtDbgReport](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw) hata ayıklama raporunu oluşturur. Bunu, başka şeylerin ayırmaları belirli türlerdeki odaklanmaya filtreleme raporlar için kullanabilirsiniz. Bir rapor kanca işlevini prototip aşağıdaki gibi olmalıdır:  
  
```  
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 Geçirdiğiniz işaretçiyi **_CrtSetReportHook** türü **_CRT_REPORT_HOOK**, CRTDBG içinde tanımlanan. Y:  
  
```  
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 Çalışma zamanı kitaplığı, kanca işlevini çağırdığında *nRptType* bağımsız değişkeni rapor kategorisi içerir (**_CRT_WARN**, **_CRT_ERROR**, veya **_CRT _ASSERT**), *szMsg* tam olarak birleştirilmiş rapor ileti dizesi için bir işaretçi içeriyor ve *retVal* belirtir olup olmadığını `_CrtDbgReport` normal yürütme devam etmelidir rapor veya başlangıç hata ayıklayıcı oluşturduktan sonra. (A *retVal* sıfır değeri yürütme devam ediyorsa, 1 değerini hata ayıklayıcıyı başlatır.)  
  
 Daha fazla raporlama yok gereklidir kanca söz konusu iletinin tamamen işleme varsa, döndürme zorunluluğu **doğru**. Döndürürse **FALSE**, `_CrtDbgReport` rapor ileti normalde olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama kanca işlevi yazma](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 örnek](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)