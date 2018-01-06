---
title: DEBUGREF_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEBUGREF_INFO_FLAGS
helpviewer_keywords: DEBUGREF_INFO_FLAGS enumeration
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0ccdf97b532c014636ff19f7416a656ac062f411
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugrefinfoflags"></a>DEBUGREF_INFO_FLAGS
Hata ayıklama başvuru nesnesi hakkında almak için hangi bilgilerin belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
typedef DWORD DEBUGREF_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 DEBUGREF_INFO_NAME  
 Başlatma/kullanım `bstrName` yapısında alan.  
  
 DEBUGREF_INFO_TYPE  
 Başlatma/kullanım `bstrType` yapısında alan.  
  
 DEBUGREF_INFO_VALUE  
 Başlatma/kullanım `bstrValue` yapısında alan.  
  
 DEBUGREF_INFO_ATTRIB  
 Başlatma/kullanım `dwAttrib` yapısında alan.  
  
 DEBUGREF_INFO_REFTYPE  
 Başlatma/kullanım `dwRefType` yapısında alan.  
  
 DEBUGREF_INFO_REF  
 Başlatma/kullanım `pReference` yapısında alan.  
  
 DEBUGREF_INFO_VALUE_AUTOEXPAND  
 Değer alanı varsa, bu nesne türü otomatik genişletilmiş değeri içermelidir.  
  
 DEBUGREF_INFO_NONE  
 Hiçbir bayraklarının ayarlandığını gösterir.  
  
 DEBUGREF_INFO_ALL  
 Bayrakları maskesi gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bayrakların geçirilecek [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) ve [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) hangi alanlarının göstermek için yöntemlerini [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) yapısı başlatılması üzeresiniz.  
  
 İçin kullanılan `dwFields` üyesi `DEBUG_REFERENCE_INFO` yapısı döndürüldüğünde hangi alanların kullanılan ve geçerli olduğunu belirtmek için yapısı.  
  
 Bu değerlerin Bitsel ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)