---
title: IDebugEngine3::SetJustMyCodeState | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEngine3::SetJustMyCodeState
helpviewer_keywords:
- IDebugEngine3::SetJustMyCodeState
ms.assetid: 8ec17fbf-df93-424a-b2ed-fd1e5ee51256
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e612b39bb71465aff50095dfeecf01cd025c4f2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694727"
---
# <a name="idebugengine3setjustmycodestate"></a>IDebugEngine3::SetJustMyCodeState
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugEngine3::SetJustMyCodeState](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugengine3-setjustmycodestate).  
  
Bu yöntem, hata ayıklama altyapısı JustMyCode durumu bilgilerini söyler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetJustMyCodeState(  
   BOOL           fUpdate,  
   DWORD          dwModules,  
   JMC_CODE_SPEC* rgJMCSpec  
);  
```  
  
```csharp  
int SetJustMyCodeState(  
   int             fUpdate,   
   uint            dwModules,   
   JMC_CODE_SPEC[] rgJMCSpec  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fUpdate`  
 [in] Sıfır olmayan (`TRUE`) geçerli bilgilerini güncelleştirmek için sıfır (`FALSE`) (önceden ayarlanan yoksayar) tüm bilgileri sıfırlanır.  
  
 `dwModules`  
 [in] Bilgi yapılarda sayısı `rgJMCSpec.`  
  
 `rgJMCSpec`  
 [in] Dizi [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md) yapıları kullanılacak.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi halde hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 JustMyCode olan yalnızca bir kullanıcıya ait kodu hata ayıklama ve sistem kodu gibi tüm ara kod yoksayılıyor kavramı — kaynak kodu, sistem kodunu kullanılabilir olsa bile.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)   
 [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)

