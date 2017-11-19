---
title: IDebugExceptionEvent2::CanPassToDebuggee | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugExceptionEvent2::CanPassToDebuggee
helpviewer_keywords: IDebugExceptionEvent2::CanPassToDebuggee
ms.assetid: ae4bbe0a-fbe1-49be-a310-ea64279a434b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ef10fd3ca7f41c2afd1c827fb71ca2178782e3d4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexceptionevent2canpasstodebuggee"></a>IDebugExceptionEvent2::CanPassToDebuggee
Hata ayıklama altyapısı (DE) yürütme devam ettiğinde ayıklanacak programın bu özel durum geçirme seçeneğiniz destekleyip desteklemediğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CanPassToDebuggee(  
   void  
);  
```  
  
```csharp  
int CanPassToDebuggee();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ya da döndürür `S_OK` (özel durum programına aktarılabilecek) veya `S_FALSE` (özel durum geçirilemez).  
  
## <a name="remarks"></a>Açıklamalar  
 DE ayıklayıcı geçişine için varsayılan eylem olması gerekir. IDE alabilirsiniz [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) olay ve arama [devam](../../../extensibility/debugger/reference/idebugprocess3-continue.md) yöntemi çağırmadan `CanPassToDebuggee` yöntemi. Bu nedenle DE özel veya geçirme için varsayılan durumda olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [Devam etmek](../../../extensibility/debugger/reference/idebugprocess3-continue.md)