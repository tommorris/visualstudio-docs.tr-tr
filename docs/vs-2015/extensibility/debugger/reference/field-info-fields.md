---
title: FIELD_INFO_FIELDS | Microsoft Docs
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
- FIELD_INFO_FIELDS
helpviewer_keywords:
- FIELD_INFO_FIELDS enumeration
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c181d1483dc33e8931436c24fc3cf681d182ab34
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694534"
---
# <a name="fieldinfofields"></a>FIELD_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [FIELD_INFO_FIELDS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/field-info-fields).  
  
Hangi bilgilerin hakkında alınacağını belirtir bir [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_FIELD_INFO_FIELDS {   
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
typedef DWORD FIELD_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_FIELD_INFO_FIELDS {  
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
```  
  
## <a name="members"></a>Üyeler  
 FIF_FULLNAME  
 Başlat/kullanım `bstrFullName` alanındaki [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) yapısı.  
  
 FIF_NAME  
 Başlat/kullanım `bstrName` alanındaki `FIELD_INFO` yapısı.  
  
 FIF_TYPE  
 Başlat/kullanım `bstrType` alanındaki `FIELD_INFO` yapısı.  
  
 FIF_MODIFIERS  
 Başlat/kullanım `bstrModifiers` alanındaki `FIELD_INFO` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerleri de bağımsız değişken olarak geçirilen [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) hangi alanları belirlemek için yöntemi [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) yapısı olan başlatılacak.  
  
 Bu değerleri de kullanılan `dwFields` üyesi `FIELD_INFO` yapısı hangi alanların kullanılan ve geçerli olduğunu belirtmek için.  
  
 Bu bayrak bit düzeyinde ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)

