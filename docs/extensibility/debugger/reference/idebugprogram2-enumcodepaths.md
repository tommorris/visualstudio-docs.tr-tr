---
title: IDebugProgram2::EnumCodePaths | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::EnumCodePaths
helpviewer_keywords:
- IDebugProgram2::EnumCodePaths
ms.assetid: fb100c3c-9c29-4d63-bd1f-a3e531cb395f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56cc9580ec2e434066d1c0a3ce674a4111e433af
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122190"
---
# <a name="idebugprogram2enumcodepaths"></a>IDebugProgram2::EnumCodePaths
Bir kaynak dosyası belirtilen konumda kod yolları bir listesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumCodePaths(   
   LPCOLESTR            pszHint,  
   IDebugCodeContext2*  pStart,  
   IDebugStackFrame2*   pFrame,  
   BOOL                 fSource,  
   IEnumCodePaths2**    ppEnum,  
   IDebugCodeContext2** ppSafety  
);  
```  
  
```csharp  
int EnumCodePaths(   
   string                 pszHint,  
   IDebugCodeContext2     pStart,  
   IDebugStackFrame2      pFrame,  
   Int                    fSource,  
   out IEnumCodePaths2    ppEnum,  
   out IDebugCodeContext2 ppSafety  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszHint`  
 [in] İmleç altındaki sözcüğün **kaynak** veya **ayrıştırılmış** IDE görünümünde.  
  
 `pStart`  
 [in] Bir [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) geçerli kod bağlamı temsil eden nesne.  
  
 `pFrame`  
 [in] Bir [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) geçerli kesme noktası ile ilişkili yığın çerçevesi temsil eden nesne.  
  
 `fSource`  
 [in] Sıfır olmayan (`TRUE`) içindeki IF **kaynak** görünümü ya da sıfır (`FALSE`) içindeki IF **ayrıştırılmış** görünümü.  
  
 `ppEnum`  
 [out] Döndürür bir [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md) kod yolları listesini içeren bir nesne.  
  
 `ppSafety`  
 [out] Döndürür bir [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) atlandı seçilen yolu kod durumunda bir kesme noktası ayarlanması için ek kod bağlamını temsil eden nesne. Bu kısa devre yapılma Boole ifadesi söz konusu olduğunda, örneğin meydana gelebilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir kod yolu bir yöntemi veya programın yürütülmesi geçerli noktaya almak için çağrıldı işlevi adını açıklar. Çağrı yığını kod yolların listesini temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)