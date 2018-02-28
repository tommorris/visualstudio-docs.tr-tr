---
title: IDebugExceptionEvent2::PassToDebuggee | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugExceptionEvent2::PassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::PassToDebuggee
ms.assetid: a20d0f0b-2ca0-4437-bd22-9213c81d2738
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d10f01289fc0a5733586e19bb3b584fa0f95f4aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugexceptionevent2passtodebuggee"></a>IDebugExceptionEvent2::PassToDebuggee
Özel durum yürütme devam ettiğinde ayıklanacak programın geçirileceğini ya da özel durum atılmalıdır belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT PassToDebuggee(  
   BOOL fPass  
);  
```  
  
```csharp  
int PassToDebuggee(  
   int fPass  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fPass`  
 [in] Sıfır olmayan (`TRUE`) özel durum yürütme devam ettiğinde ayıklanacak program veya sıfır iletilmesi gereken varsa (`FALSE`) özel durum atılmalıdır durumunda.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemin çağrılması gerçekte ayıklanacak programa yürütülecek herhangi bir kod neden olmaz. Yalnızca sonraki kod yürütmeyi durumunu ayarlamak için çağrıdır. Örneğin, çağrılar [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) yöntemi döndürebilir `S_OK` ile [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md).`dwState` alan kümesi'ne `EXCEPTION_STOP_SECOND_CHANCE`.  
  
 IDE alabilirsiniz [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) olay ve arama [devam](../../../extensibility/debugger/reference/idebugprogram2-continue.md) yöntemi. Hata ayıklama altyapısı (DE) durum geçerlidir işlemek için varsayılan davranış olmalıdır `PassToDebuggee` yöntemi çağrılmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)   
 [Devam etmek](../../../extensibility/debugger/reference/idebugprogram2-continue.md)