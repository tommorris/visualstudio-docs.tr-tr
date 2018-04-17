---
title: MESSAGETYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MESSAGETYPE
helpviewer_keywords:
- MESSAGETYPE enumeration
ms.assetid: 800cc77d-3c27-4763-a9df-552a9384bd49
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3fa09d938e0e7c3853431369c7e0634242df2ee0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="messagetype"></a>MESSAGETYPE
Neden ve ileti türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
typedef DWORD MESSAGETYPE;  
```  
  
```csharp  
public enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
```  
  
## <a name="members"></a>Üyeler  
 MT_OUTPUTSTRING  
 İleti için çıkış penceresini gönderilmesi gerektiğini belirtir. Bu gelen birbirini dışlayan `MT_MESSAGEBOX`.  
  
 MT_MESSAGEBOX  
 İleti bir ileti kutusu içinde gösterilen olduğunu gösterir. Bu gelen birbirini dışlayan `MT_OUTPUTSTRING`.  
  
 MT_TYPE_MASK  
 İletinin hedef ayırmak için bir maskesi değeri.  
  
 MT_REASON_EXCEPTION  
 Bir özel durum nedeniyle bir ileti kutusu gösterilen olduğunu gösterir. Bu gelen birbirini dışlayan `MT_REASON_TRACEPOINT`.  
  
 MT_REASON_TRACEPOINT  
 Bir ileti kutusu bir tracepoint basarsa sonucunda gösterildikten gösterir. Birbirini dışlayan budur `MT_REASON_EXCEPTION`.  
  
 MT_REASON_MASK  
 Gösterildikten ileti nedeni ayırmak için bir maskesi değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerleri döndürüldüğü kaynak [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md) ve [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md) yöntemleri.  
  
 Neden değerlerden biri birleştirilebilir bit kullanarak çıktı hedef değerlerden biriyle `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)   
 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md)