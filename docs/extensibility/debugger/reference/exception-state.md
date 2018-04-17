---
title: EXCEPTION_STATE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EXCEPTION_STATE
helpviewer_keywords:
- EXCEPTION_STATE enumeration
ms.assetid: 597f4f4c-9b70-485c-b5dc-3c2e3aecc664
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1faa847d907af938bb5f91206a5f438bcba886a3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="exceptionstate"></a>EXCEPTION_STATE
Özel durum durumunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_EXCEPTION_STATE {   
   EXCEPTION_NONE                          = 0x0000,  
   EXCEPTION_STOP_FIRST_CHANCE             = 0x0001,  
   EXCEPTION_STOP_SECOND_CHANCE            = 0x0002,  
   EXCEPTION_STOP_USER_FIRST_CHANCE        = 0x0010,  
   EXCEPTION_STOP_USER_UNCAUGHT            = 0x0020,  
   EXCEPTION_STOP_ALL                      = 0x00FF,  
   EXCEPTION_CANNOT_BE_CONTINUED           = 0x0100,  
  
   // These are for exception types only  
   EXCEPTION_CODE_SUPPORTED                = 0x1000,  
   EXCEPTION_CODE_DISPLAY_IN_HEX           = 0x2000,  
   EXCEPTION_JUST_MY_CODE_SUPPORTED        = 0x4000,  
   EXCEPTION_MANAGED_DEBUG_ASSISTANT       = 0x8000,  
  
   // These are no longer used  
   EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT      = 0x0004,  
   EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT     = 0x0008,  
   EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT = 0x0040,  
   EXCEPTION_STOP_USER_UNCAUGHT_USE_PARENT     = 0x0080,  
};  
typedef DWORD EXCEPTION_STATE;  
```  
  
```csharp  
public enum enum_EXCEPTION_STATE {   
   EXCEPTION_NONE                          = 0x0000,  
   EXCEPTION_STOP_FIRST_CHANCE             = 0x0001,  
   EXCEPTION_STOP_SECOND_CHANCE            = 0x0002,  
   EXCEPTION_STOP_USER_FIRST_CHANCE        = 0x0010,  
   EXCEPTION_STOP_USER_UNCAUGHT            = 0x0020,  
   EXCEPTION_STOP_ALL                      = 0x00FF,  
   EXCEPTION_CANNOT_BE_CONTINUED           = 0x0100,  
  
   // These are for exception types only  
   EXCEPTION_CODE_SUPPORTED                = 0x1000,  
   EXCEPTION_CODE_DISPLAY_IN_HEX           = 0x2000,  
   EXCEPTION_JUST_MY_CODE_SUPPORTED        = 0x4000,  
   EXCEPTION_MANAGED_DEBUG_ASSISTANT       = 0x8000,  
  
   // These are no longer used  
   EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT      = 0x0004,  
   EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT     = 0x0008,  
   EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT = 0x0040,  
   EXCEPTION_STOP_USER_UNCAUGHT_USE_PARENT     = 0x0080,  
};  
```  
  
## <a name="members"></a>Üyeler  
 EXCEPTION_NONE  
 Özel durum sırasında durdurmaz.  
  
 EXCEPTION_STOP_FIRST_CHANCE  
 Özel durum ilk tetikleme adresindeki durdurun. Bir özel durum olayı açıklanırken bu bayrağı özel durum olayı ilk fırsat özel durum olayı olduğunu gösterir.  
  
 EXCEPTION_STOP_SECOND_CHANCE  
 Özel durum ikinci tetikleme adresindeki durdurun. Bir özel durum olayı açıklanırken, özel durum olayı ikinci fırsat özel durum olayı olduğunu gösterir.  
  
 EXCEPTION_STOP_USER_FIRST_CHANCE  
 Bir kullanıcı modu özel ilk tetikleme adresindeki durdurun. Bir özel durum olayı açıklanırken, özel durum olayı bir kullanıcı ilk fırsat özel durum olayı olduğunu gösterir.  
  
 EXCEPTION_STOP_USER_UNCAUGHT  
 Kullanıcı modu özel durum yakalanmadı geldiğinizde durun. Bir özel durum olayı açıklanırken, özel durum olayı yakalanmayan kullanıcı modu özel durum olayı olduğunu gösterir.  
  
 EXCEPTION_STOP_ALL  
 Herhangi bir özel durum nedeniyle durdurun. Bir özel durum olayı açıklanırken kullanılmaz.  
  
 EXCEPTION_CANNOT_BE_CONTINUED  
 Bir özel durum olayı açıklanırken, özel durum gelen devam edemiyor gösterir.  
  
 EXCEPTION_CODE_SUPPORTED  
 Özel durum bunu destekleyen koduna sahip olduğunu gösterir. Bir özel durum görüntülenirken kullanılan  
  
 EXCEPTION_CODE_DISPLAY_IN_HEX  
 Özel durum kodu onaltılık görüntüleneceğini belirtir. Bir özel durum görüntüleme kullanılır.  
  
 EXCEPTION_JUST_MY_CODE_SUPPORTED  
 Özel durum kodu JustMyCode desteklediğini belirtir. Bir özel durum görüntüleme kullanılır.  
  
 EXCEPTION_MANAGED_DEBUG_ASSISTANT  
 Yönetilen kod hata ayıklayıcısını özel durumlarını işlemelidir gösterir. Aksi durumda kümesi, varsayılan hata ayıklayıcısı özel durumları işler. Bu geçirilir [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md) yöntemi ve kullanılan değil [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) yapısı.  
  
 EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT  
 KULLANIMDAN KALKTI, KULLANMAYIN.  
  
 EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT  
 KULLANIMDAN KALKTI, KULLANMAYIN.  
  
 EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT  
 KULLANIMDAN KALKTI, KULLANMAYIN.  
  
 EXCEPTION_STOP_USER_SECOND_CHANCE_USE_PARENT  
 KULLANIMDAN KALKTI, KULLANMAYIN.  
  
## <a name="remarks"></a>Açıklamalar  
 Olarak kullanılan `dwState` üyesi [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) özel durumu ve ne hakkında yapılabilir durumunu göstermek için yapısı.  
  
 Bu değerleri de geçirilen [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md) tüm özel durumları durumunu ayarlamak için yöntem.  
  
 Bu bayrakların bit düzeyinde OR ile birleştirilebilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)   
 [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)