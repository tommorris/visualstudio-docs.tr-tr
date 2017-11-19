---
title: DEBUGPROP_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEBUGPROP_INFO_FLAGS
helpviewer_keywords: DBGPROP_INFO_FLAGS enumeration
ms.assetid: 1c7fe777-615e-4929-9ed4-970d9fe0eb81
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 24b0208cdfd49ef07ba85803d03a1e2c4aa91553
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debugpropinfoflags"></a>DEBUGPROP_INFO_FLAGS
Hata ayıklama özelliği nesnesi hakkında almak için hangi bilgilerin belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
 Başlatma/kullanım `bstrFullName` alan.  
  
 DEBUGPROP_INFO_NAME  
 Başlatma/kullanım `bstrName` alan.  
  
 DEBUGPROP_INFO_TYPE  
 Başlatma/kullanım `bstrType` alan.  
  
 DEBUGPROP_INFO_VALUE  
 Başlatma/kullanım `bstrValue` alan.  
  
 DEBUGPROP_INFO_ATTRIB  
 Başlatma/kullanım `dwAttrib` alan.  
  
 DEBUGPROP_INFO_PROP,  
 Başlatma/kullanım `pProperty` içeren alanın bir [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) arabirimi.  
  
 DEBUGPROP_INFO_VALUE_AUTOEXPAND  
 Varsa, bu nesne türü değeri alanı otomatik genişletilmiş değeri içermesi gerektiğini belirtir.  
  
 DEBUGPROP_INFO_VALUE_NOFUNCEVAL  
 Kullanım dışı.  
  
 DEBUGPROP_INFO_VALUE_RAW  
 Herhangi bir beautified değerleri veya üyeleri döndürmeyen (diğer bir deyişle, değerler biçimi değil).  
  
 DEBUGPROP_INFO_VALUE_NO_TOSTRING  
 Tüm özel birleştirilen değerleri döndürmeyen (örneğin, çağırmayın `ToString()` bir değer üretmek için bir nesne üzerinde).  
  
 DEBUGPROP_INFO_NONE  
 Hiçbir bayraklarının ayarlandığını belirtir.  
  
 DEBUGPROP_INFO_STANDARD  
 Başlatma/kullanım `dwAttrib`, `bstrName`, `bstrType`, ve `bstrValue` alanları.  
  
 DEBUGPROP_INFO_All  
 Tüm bayraklar maskesi gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerler geçirilecek [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md), [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md), ve [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) başlatılması için hangi alanların olduğunu göstermek için yöntemlerini [ DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) yapısı.  
  
 Bu değerler için de kullanılır `dwFields` üyesi `DEBUG_PROPERTY_INFO` yapısı döndürüldüğünde hangi alanların yapısı kullanılan ve geçerli olduğunu belirtmek için yapısı.  
  
 Bu değerlerin Bitsel ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)