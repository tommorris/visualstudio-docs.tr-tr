---
title: THREADPROPERTY_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: THREADPROPERTY_FIELDS
helpviewer_keywords: THREADPROPERTY_FIELDS enumeration
ms.assetid: 5b88acb9-03ea-4c29-a788-f0087dccbe23
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 626c4aa309c7ce68eaf5d97c734ec4fd731148c1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="threadpropertyfields"></a>THREADPROPERTY_FIELDS
Bir iş parçacığı hakkında hangi bilgilerin alınması belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD THREADPROPERTY_FIELDS;  
```  
  
```csharp  
public enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 TPF_ID  
 Başlatma/kullanım `dwThreadId` alanını [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) yapısı.  
  
 TPF_SUSPENDCOUNT  
 Başlatma/kullanım `dwSuspendCount` alanını `THREADPROPERTIE`S yapısı.  
  
 TPF_STATE  
 Başlatma/kullanım `dwThreadState` alanını `THREADPROPERTIE`S yapısı.  
  
 TPF_PRIORITY  
 Başlatma/kullanım `bstrPriority` alanını `THREADPROPERTIE`S yapısı.  
  
 TPF_NAME  
 Başlatma/kullanım `bstrName` alanını `THREADPROPERTIE`S yapısı.  
  
 TPF_LOCATION  
 Başlatma/kullanım `bstrLocation` alanını `THREADPROPERTIE`S yapısı.  
  
 TPF_ALLFIELDS  
 Tüm alanlar belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerler için bağımsız değişken olarak geçirilen [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) hangi alanlarının belirtmek için yöntemi [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) yapısı başlatılması üzeresiniz.  
  
 Bu değerleri de içinde kullanılan `dwFields` üyesi `THREADPROPERTIES` hangi alanların kullanılan ve geçerli olduğunu belirtmek için yapısı.  
  
 Bu bayrakların bit ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)