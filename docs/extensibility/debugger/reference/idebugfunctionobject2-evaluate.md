---
title: IDebugFunctionObject2::Evaluate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugFunctionObject2::Evaluate
ms.assetid: bc54c652-904b-4297-a6db-faa329684881
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8196eb45b2fe7eccbff5c23a7ffc58fd3eb59282
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31112707"
---
# <a name="idebugfunctionobject2evaluate"></a>IDebugFunctionObject2::Evaluate
İşlev çağrılarını ve sonuçta elde edilen değer bir nesne olarak döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Evaluate (  
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwEvalFlags,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```csharp  
int Evaluate (  
   IDebugObject     ppParams,  
   uint             dwParams,  
   uint             dwEvalFlags,  
   uint             dwTimeout,  
   out IDebugObject ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppParams`  
 [in] Bir dizi [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) giriş parametreleri temsil eden nesne. Bu parametrelerin her biri, bu arabirimi oluşturma yöntemlerden birini kullanarak oluşturuldu.  
  
 `dwParams`  
 [in] Parametre sayısı `ppParams` dizi.  
  
 `dwEvalFlags`  
 [in] Bayraklarını bileşimini [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) değerlendirme nasıl gerçekleştirilmesi belirtin numaralandırması.  
  
 `dwTimeout`  
 [in] Bu yöntemle geri dönmeden önce beklenecek milisaniye cinsinden en uzun süreyi belirtir. Kullanım **SONSUZ** sonsuza kadar beklenecek.  
  
 `ppResult`  
 [out] Döndürür bir **IDebugObject** temsil eden bir nesne olarak işlevin değeri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)