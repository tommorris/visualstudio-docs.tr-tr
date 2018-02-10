---
title: ResumeTracking | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ResumeTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: af99ba7e34de4db27f503ba4a7608373fee7d4cc
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="resumetracking"></a>ResumeTracking
Geçerli bağlamda izlemeyi sürdürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir **HRESULT** ile **başarılı** izleme devam ettirildi varsa biti ayarlanmamış. **E_FAIL** bağlam kullanılamadığı için izleme ettirilemez durumunda döndürülür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Header:** FileTracker.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SuspendTracking](../msbuild/suspendtracking.md)