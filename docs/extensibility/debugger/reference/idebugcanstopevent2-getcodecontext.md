---
title: IDebugCanStopEvent2::GetCodeContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCanStopEvent2::GetCodeContext
helpviewer_keywords:
- IDebugCanStopEvent2::GetCodeContext
ms.assetid: eecf08b6-f9b7-4358-941b-3a448a92ac62
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4b2e12fe5840819394670de9dc0ff677d5ccde60
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcanstopevent2getcodecontext"></a>IDebugCanStopEvent2::GetCodeContext
Bu olay konumunu açıklar kod bağlamını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetCodeContext(   
   IDebugCodeContext2** ppCodeContext  
);  
```  
  
```csharp  
int GetCodeContext(   
   out IDebugCodeContext2 ppCodeContext  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppCodeContext`  
 [out] Döndürür [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) geçerli kod konumu temsil eden nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı mimari için bir kod bağlamı, belirli bir yönerge işaret eden bir adresi bir programın yürütme akış olarak değerlendirilebilir.  
  
 Kaynak kodu satır yönlendirilmiş, belge içerik almak için çağırın [GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)