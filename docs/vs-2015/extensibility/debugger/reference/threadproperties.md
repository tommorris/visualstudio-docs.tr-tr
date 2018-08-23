---
title: THREADPROPERTIES | Microsoft Docs
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
- THREADPROPERTIES
helpviewer_keywords:
- THREADPROPERTIES structure
ms.assetid: 7d397207-db03-4ec0-9f79-3794056ed89f
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8d95c31818931c7d1bc303318998504ee6f1a43d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632113"
---
# <a name="threadproperties"></a>THREADPROPERTIES
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [THREADPROPERTIES](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/threadproperties).  
  
Bir iş parçacığı özelliklerini açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
typedef struct _tagTHREADPROPERTIES {   
   THREADPROPERTY_FIELDS dwFields;  
   DWORD                 dwThreadId;  
   DWORD                 dwSuspendCount;  
   DWORD                 dwThreadState;  
   BSTR                  bstrPriority;  
   BSTR                  bstrName;  
   BSTR                  bstrLocation;  
} THREADPROPERTIES;  
```  
  
```csharp  
public struct THREADPROPERTIES {   
   public uint   dwFields;  
   public uint   dwThreadId;  
   public uint   dwSuspendCount;  
   public uint   dwThreadState;  
   public string bstrPriority;  
   public string bstrName;  
   public string bstrLocation;  
};  
```  
  
## <a name="members"></a>Üyeler  
 dwFields  
 Bayraklarının bir birleşimi [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md) bu yapının hangi alanlarda geçerli olduğunu açıklayan sabit listesi,.  
  
 dwThreadId  
 İş parçacığı kimliği.  
  
 dwSuspendCount  
 İş parçacığını askıya alma sayısı.  
  
 dwThreadState  
 Bir değer [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md) çalışma iş parçacığı durumunu belirten sabit listesi.  
  
 bstrPriority  
 İş parçacığı önceliği belirten bir dize; Örneğin, "yukarıda Normal", "Normal" veya "Zaman kritik".  
  
 bstName  
 İş parçacığı adı.  
  
 bstrLocation  
 Genellikle burada yürütme şu anda durdu yöntemin adı ifade edilen iş parçacığı konumu (en üstteki yığın çerçevesi genellikle).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı için bir çağrı tarafından doldurulur [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) yöntemi. Bu nedenle döndürülen bilgileri, genellikle doldurma içinde kullanılır **iş parçacıkları** penceresi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)   
 [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)   
 [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md)

