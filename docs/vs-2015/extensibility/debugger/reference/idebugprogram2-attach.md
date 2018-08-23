---
title: IDebugProgram2::Attach | Microsoft Docs
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
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6636557c989d415bd9e49d3aa6c8b0e977edf43e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632777"
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugProgram2::Attach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-attach).  
  
Programa ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Attach(   
   IDebugEventCallback2* pCallback  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pCallback`  
 [in] Bir [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) hata ayıklama olayı bildirim için kullanılacak nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Aşağıdaki tabloda bazı olası hata kodları gösterilir.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|Belirtilen program için hata ayıklayıcı zaten iliştirilmiş.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Ekleme işlemi sırasında bir güvenlik ihlali oluştu.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|Bir masaüstü programına için hata ayıklayıcı eklenemiyor.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama altyapısı (DE), hiçbir zaman bir programa eklemek için bu yöntemi çağırır. Programın adres alanında DE çalıştırıyorsa [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) yöntemi çağrılır. Oturum hata ayıklama manager'ın içinde DE çalışır (SDM) adres alanı, [iliştirme](../../../extensibility/debugger/reference/idebugengine2-attach.md) yöntemi çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)

