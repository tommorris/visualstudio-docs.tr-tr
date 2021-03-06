---
title: DEBUGPROP_INFO_FLAGS | Microsoft Docs
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
- DEBUGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS enumeration
ms.assetid: 1c7fe777-615e-4929-9ed4-970d9fe0eb81
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 999b9af039513782439ca89826f54c94da79546f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632882"
---
# <a name="debugpropinfoflags"></a>DEBUGPROP_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DEBUGPROP_INFO_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/debugprop-info-flags).  
  
Hangi bilgilerin hakkında bir hata ayıklama özelliği nesnesi alınacağını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_DEBUGPROP_INFO_FLAGS {   
   DEBUGPROP_INFO_FULLNAME          = 0x00000001,  
   DEBUGPROP_INFO_NAME              = 0x00000002,  
   DEBUGPROP_INFO_TYPE              = 0x00000004,  
   DEBUGPROP_INFO_VALUE             = 0x00000008,  
   DEBUGPROP_INFO_ATTRIB            = 0x00000010,  
   DEBUGPROP_INFO_PROP              = 0x00000020,  
   DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,  
   DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,  
   DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,  
   DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000  
   DEBUGPROP_INFO_NONE              = 0x00000000,  
   DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |  
                                      DEBUGPROP_INFO_NAME |  
                                      DEBUGPROP_INFO_TYPE |  
                                      DEBUGPROP_INFO_VALUE,  
   DEBUGPROP_INFO_ALL               = 0xffffffff  
};  
typedef DWORD DEBUGPROP_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGPROP_INFO_FLAGS {   
   DEBUGPROP_INFO_FULLNAME          = 0x00000001,  
   DEBUGPROP_INFO_NAME              = 0x00000002,  
   DEBUGPROP_INFO_TYPE              = 0x00000004,  
   DEBUGPROP_INFO_VALUE             = 0x00000008,  
   DEBUGPROP_INFO_ATTRIB            = 0x00000010,  
   DEBUGPROP_INFO_PROP              = 0x00000020,  
   DEBUGPROP_INFO_VALUE_AUTOEXPAND  = 0x00010000,  
   DEBUGPROP_INFO_VALUE_NOFUNCEVAL  = 0x00020000,  
   DEBUGPROP_INFO_VALUE_RAW         = 0x00040000,  
   DEBUGPROP_INFO_VALUE_NO_TOSTRING = 0x00080000  
   DEBUGPROP_INFO_NONE              = 0x00000000,  
   DEBUGPROP_INFO_STANDARD          = DEBUGPROP_INFO_ATTRIB |  
                                      DEBUGPROP_INFO_NAME |  
                                      DEBUGPROP_INFO_TYPE |  
                                      DEBUGPROP_INFO_VALUE,  
   DEBUGPROP_INFO_ALL               = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 DEBUGPROP_INFO_FULLNAME  
 Başlat/kullanım `bstrFullName` alan.  
  
 DEBUGPROP_INFO_NAME  
 Başlat/kullanım `bstrName` alan.  
  
 DEBUGPROP_INFO_TYPE  
 Başlat/kullanım `bstrType` alan.  
  
 DEBUGPROP_INFO_VALUE  
 Başlat/kullanım `bstrValue` alan.  
  
 DEBUGPROP_INFO_ATTRIB  
 Başlat/kullanım `dwAttrib` alan.  
  
 DEBUGPROP_INFO_PROP,  
 Başlat/kullanım `pProperty` içeren alan bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) arabirimi.  
  
 DEBUGPROP_INFO_VALUE_AUTOEXPAND  
 Varsa, bu nesne türü için değer alanını otomatik olarak genişletilmiş değeri içermesi gerektiğini belirtir.  
  
 DEBUGPROP_INFO_VALUE_NOFUNCEVAL  
 Kullanım dışı.  
  
 DEBUGPROP_INFO_VALUE_RAW  
 Üyeler veya beautified değerlerden döndürmeyen (diğer bir deyişle, değerleri biçimlendirmeyin).  
  
 DEBUGPROP_INFO_VALUE_NO_TOSTRING  
 Herhangi bir özel Sentezlenen değer döndürmeyen (örneğin, çağırmayın `ToString()` bir değer üretmek için bir nesne üzerinde).  
  
 DEBUGPROP_INFO_NONE  
 Bayrak ayarlandığını belirtir.  
  
 DEBUGPROP_INFO_STANDARD  
 Başlat/kullanım `dwAttrib`, `bstrName`, `bstrType`, ve `bstrValue` alanları.  
  
 DEBUGPROP_INFO_All  
 Tüm bayraklar maskesi gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerler geçirilecek [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md), [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md), ve [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) başlatılması için hangi alanların olduğunu göstermek için yöntemlerini [ DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) yapısı.  
  
 Bu değerler için de kullanılır `dwFields` üyesi `DEBUG_PROPERTY_INFO` yapısı yapısı iade edildiğinde yapının hangi alanların kullanılan ve geçerli belirtmek için.  
  
 Bu değerler, bit düzeyinde ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)

