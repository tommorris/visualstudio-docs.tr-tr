---
title: BPERESI_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BPERESI_FIELDS
helpviewer_keywords: BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 36ac591940acaed2ac8b8f92c701580d9d45f94a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bperesifields"></a>BPERESI_FIELDS
Başarısız bir kesme noktası çözümleme hakkında alınması için bilgileri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD BPERESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 PERESI_BPRESLOCATION  
 Başlatma/kullanım `bpResLocation` (kesme noktası çözümleme konum) alanı [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) yapısı.  
  
 BPERESI_PROGRAM  
 Başlatma/kullanım `pProgram` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_THREAD  
 Başlatma/kullanım `pThread` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_MESSAGE  
 Başlatma/kullanım `bstrMessage` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_TYPE  
 Başlatma/kullanım `dwType` (kesme noktası türü) alanı `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_ALLFIELDS  
 Başlat/tüm alanları kullanın `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir parametre olarak geçirilen [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md) hangi alanlarının belirtmek için yöntemi [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) yapısı başlatılması üzeresiniz.  
  
 Bu değerleri ayrıca hangi alanları belirtmek için kullanılan `BP_ERROR_RESOLUTION_INFO` yapısı, kullanılan ve geçerli yapıyı döndürülür.  
  
 Bu değerlerin Bitsel ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)