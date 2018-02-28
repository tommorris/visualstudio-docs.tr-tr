---
title: IDebugModule3::LoadSymbols | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugModule3::LoadSymbols
helpviewer_keywords:
- IDebugModule3::LoadSymbols
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1b3dda16ac3312e7deec21b06a4df05162bfa692
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmodule3loadsymbols"></a>IDebugModule3::LoadSymbols
Geçerli modülü simgelerini yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT LoadSymbols(  
   void  
);  
```  
  
```csharp  
int LoadSymbols();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa, döndürür `S_OK`. Başarısız olursa bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçerli arama yolundan simgeleri yükler (hangi değiştirilebilir çağırarak [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) yöntemi).  
  
 Bu yöntem üzerinden tercih edilir [ReloadSymbols_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)