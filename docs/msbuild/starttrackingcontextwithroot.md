---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- StartTrackingContextWithRoot
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fcd31ee92733508f4980236d0c6dbd7dff15c128
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
Bir kök işaret belirten bir yanıt dosyası kullanarak bir izleme bağlamı başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp 
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `intermediateDirectory`  
 İzleme günlüğü depolanacağı dizin.  
  
 [in] `taskName`  
 İzleme bağlamı tanımlar. Bu ad, günlük dosyası adı oluşturmak için kullanılır.  
  
 [in] `rootMarkerResponseFile`  
 Bir kök işaret içeren bir yanıt dosyası yol adı. Kök adı tüm izleme için bir bağlam birlikte gruplandırmak için kullanılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir **HRESULT** ile **başarılı** izleme bağlamı oluşturduysanız biti ayarlanmamış.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** FileTracker.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)