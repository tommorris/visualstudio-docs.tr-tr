---
title: GETNAME_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GETNAME_TYPE
helpviewer_keywords:
- GETNAME_TYPE enumeration
ms.assetid: 2f9f1679-e9e8-4c9c-ac90-aa07bfe69914
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bb73d39aec7f364ce27ab06ef426d1c4a622878a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="getnametype"></a>GETNAME_TYPE
Alınacak dosya adı türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_GETNAME_TYPE {   
   GN_NAME         = 0,  
   GN_FILENAME     = 1,  
   GN_BASENAME     = 2,  
   GN_MONIKERNAME  = 3,  
   GN_URL          = 4,  
   GN_TITLE        = 5,  
   GN_STARTPAGEURL = 6  
};  
typedef DWORD GETNAME_TYPE;  
```  
  
```csharp  
public enum enum_GETNAME_TYPE {   
   GN_NAME         = 0,  
   GN_FILENAME     = 1,  
   GN_BASENAME     = 2,  
   GN_MONIKERNAME  = 3,  
   GN_URL          = 4,  
   GN_TITLE        = 5,  
   GN_STARTPAGEURL = 6  
};  
```  
  
## <a name="members"></a>Üyeler  
 GN_NAME  
 Belge veya içeriği kolay adını belirtir.  
  
 GN_FILENAME  
 Belge veya bağlam tam yolunu belirtir.  
  
 GN_BASENAME  
 Temel dosya adı yerine bir belge veya bağlam tam yolunu belirtir.  
  
 GN_MONIKERNAME  
 Belgenin veya bağlam benzersiz bir ad bir bilinen ad biçiminde belirtir.  
  
 GN_URL  
 Belge veya bağlam URL adını belirtir.  
  
 GN_TITLE  
 Varsa, belgenin, bir başlığı belirtir.  
  
 GN_STARTPAGEURL  
 Başlangıç sayfası URL'si işlemleri için alır.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerler için parametre olarak geçirilen [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md), [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md), ve [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) yöntemleri ne tür bir geri dönmek için ad belirtin.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)   
 [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)   
 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)