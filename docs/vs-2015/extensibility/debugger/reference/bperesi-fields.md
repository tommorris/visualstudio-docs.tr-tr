---
title: BPERESI_FIELDS | Microsoft Docs
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
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8207271404811f3da3dd03782974abd9e67fb576
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634029"
---
# <a name="bperesifields"></a>BPERESI_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [BPERESI_FIELDS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bperesi-fields).  
  
Başarısız bir kesme noktası çözünürlüğü hakkında alınacak bilgileri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
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
 Başlat/kullanım `bpResLocation` (kesme noktası çözünürlüğü konumu) alanının [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) yapısı.  
  
 BPERESI_PROGRAM  
 Başlat/kullanım `pProgram` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_THREAD  
 Başlat/kullanım `pThread` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_MESSAGE  
 Başlat/kullanım `bstrMessage` alanını `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_TYPE  
 Başlat/kullanım `dwType` (kesme noktası türü) alanına `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
 BPERESI_ALLFIELDS  
 Başlat/tüm alanları kullanmak `BP_ERROR_RESOLUTION_INFO` yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir parametre olarak geçirilen [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md) hangi alanları göstermek için yöntemi [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) yapısı olan başlatılacak.  
  
 Bu değerler, alanlarını belirtmek için de kullanılır `BP_ERROR_RESOLUTION_INFO` yapısı, kullanılan ve geçerli, yapı döndürülür.  
  
 Bu değerler, bit düzeyinde ile birleştirilebilir `OR`.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)

