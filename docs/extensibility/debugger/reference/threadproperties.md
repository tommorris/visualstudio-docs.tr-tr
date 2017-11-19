---
title: THREADPROPERTIES | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: THREADPROPERTIES
helpviewer_keywords: THREADPROPERTIES structure
ms.assetid: 7d397207-db03-4ec0-9f79-3794056ed89f
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b4ec394deef3b317d91e6cbe22bbc1d95a6aca5e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="threadproperties"></a>THREADPROPERTIES
Bir iş parçacığı özelliklerini açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
 Bayraklarını bileşimini [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md) bu yapı hangi alanların geçerli açıklayan numaralandırması.  
  
 dwThreadId  
 İş parçacığı kimliği  
  
 dwSuspendCount  
 İş parçacığı sayısı askıya alın.  
  
 dwThreadState  
 Arasında bir değer [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md) işletim iş parçacığı durumunu gösteren sabit listesi.  
  
 bstrPriority  
 İş parçacığı önceliği belirten bir dize; Örneğin, "yukarıdaki Normal", "Normal" veya "Zaman kritik".  
  
 bstName  
 İş parçacığı adı.  
  
 bstrLocation  
 İş parçacığı konumu (genellikle en üstteki yığın çerçevesi), genellikle burada yürütme şu anda durdu yöntemi ad olarak ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı için bir çağrı tarafından doldurulur [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) yöntemi. Böylece dönen bilgiyi yerleşiminde de genellikle kullanılan **iş parçacığı** penceresi.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)   
 [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)   
 [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md)