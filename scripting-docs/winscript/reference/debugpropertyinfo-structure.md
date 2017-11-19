---
title: "Debugpropertyınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: DebugPropertyInfo
apilocation: scrobj.dll
helpviewer_keywords: DebugPropertyInfo structure
ms.assetid: 3246efbc-c212-4024-8f07-6414c2f85e75
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9baade1a742a06c952906c05c574e752806bc9c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="debugpropertyinfo-structure"></a>DebugPropertyInfo Yapısı
Bir nesnenin adı, türü ve değeri içeren hiyerarşik bir yapı açıklar. Yerel değişkenler, parametreleri, izleme değişkenleri ve ifadeleri hata ayıklama özelliklerini tanımlamak için kullanılır ve kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct DebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   BSTR  bstrName;  
   BSTR  bstrType;  
   BSTR  bstrValue;  
   BSTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
};  
```  
  
## <a name="members"></a>Üyeler  
 dwValidFields  
 Hangi alanların başlatılmış belirtmek için kullanılan bir numaralandırılmış veri türü.  
  
 bstrName  
 Bir bağlam içinde özellik adı.  
  
 bstrType  
 Biçimlendirilmiş bir dize olarak özellik türü.  
  
 bstrValue  
 Biçimlendirilmiş bir dize olarak özellik değeri.  
  
 bstrFullName  
 Özelliğin tam adı.  
  
 dwAttrib  
 Hata ayıklama özellik öznitelikleri bayrakları belirtir numaralandırması.  
  
 pDebugProp  
 `IDebugProperty` Bu bilgileri tarafından açıklanan `DebugPropertyInfo` yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idebugproperty arabirimi](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)