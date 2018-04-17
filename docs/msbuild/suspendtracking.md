---
title: SuspendTracking | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- SuspendTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SuspendTracking
ms.assetid: f5e06e5a-8083-444c-99c1-07ba834226b5
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7320f2a109da838124c08e8d036089ee0b49ca10
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="suspendtracking"></a>SuspendTracking
Geçerli bağlamda izleme askıya alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp 
HRESULT WINAPI SuspendTracking(void);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir **HRESULT** ile **başarılı** izleme askıya alınırsa biti ayarlanmamış.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** FileTracker.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ResumeTracking](../msbuild/resumetracking.md)