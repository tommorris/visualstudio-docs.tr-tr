---
title: IEnumDebugFrameInfo2::Next | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugFrameInfo2::Next
helpviewer_keywords:
- IEnumDebugFrameInfo2::Next
ms.assetid: 64a64eeb-5dea-4119-8a22-03771015d1e5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 87e6010a99a52168dfab22dd3f21d907885b15a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134714"
---
# <a name="ienumdebugframeinfo2next"></a>IEnumDebugFrameInfo2::Next
Numaralandırma içinden öğeleri sonraki kümesini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Next(  
   ULONG       celt,  
   FRAMEINFO** rgelt,  
   ULONG*      pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint        celt,  
   FRAMEINFO[] rgelt,  
   ref uint    pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Alınacak öğe sayısı. Ayrıca en büyük boyutunu belirtir `rgelt` dizi.  
  
 `rgelt`  
 [içinde out] Dizi [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) doldurulacak öğeleri.  
  
 `pceltFetched`  
 [out] Gerçekte döndürülen öğe sayısını döndürür `rgelt`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`. Döndürür `S_FALSE` İstenen öğe sayısından daha az döndürülebilen; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)