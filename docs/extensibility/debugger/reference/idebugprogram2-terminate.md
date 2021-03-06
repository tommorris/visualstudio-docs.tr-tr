---
title: IDebugProgram2::Terminate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5eb14280947ff93a4a0c2ab6d2cf025037fc06aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31115843"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
Program sonlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Terminate(   
   void   
);  
```  
  
```csharp  
int Terminate();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Mümkünse, program sonlandırıldı ve işleminden kaldırıldı; Aksi takdirde hata ayıklama altyapısı (DE) tüm gerekli temizleme gerçekleştirir.  
  
 Bu yöntem veya [Sonlandır](../../../extensibility/debugger/reference/idebugprocess2-terminate.md) yöntemi IDE'de, genellikle tüm hata ayıklama durdurma kullanıcıya yanıt tarafından çağrılır. İdeal olarak, bu yöntemin kullanımı programın işlemi içinde sonlanmalıdır. Bu mümkün değilse, DE program bu işlemde başka engellenmesine (ve tüm gerekli temizleme yapın). Varsa `IDebugProcess2::Terminate` yöntemi tarafından IDE çağrıldı, süre sonra tüm işlem sonlandırılacak `IDebugProgram2::Terminate` yöntemi çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [Sonlandırma](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)