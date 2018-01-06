---
title: BP_ERROR_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_ERROR_TYPE
helpviewer_keywords: BP_ERROR_TYPE enumeration
ms.assetid: c483eaab-db29-46de-bfdb-5c2a9a9cfb68
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c50e5cb9f9ba1edf09a30b13373a680ff8e5a3f2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bperrortype"></a>BP_ERROR_TYPE
Bir kesme noktası hata türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
typedef DWORD BP_ERROR_TYPE;  
```  
  
```csharp  
public enum enum_BP_ERROR_TYPE {   
   BPET_NONE            = 0x00000000,  
   BPET_TYPE_WARNING    = 0x00000001,  
   BPET_TYPE_ERROR      = 0x00000002,  
   BPET_SEV_HIGH        = 0x0F000000,  
   BPET_SEV_GENERAL     = 0x07000000,  
   BPET_SEV_LOW         = 0x01000000,  
   BPET_TYPE_MASK       = 0x0000ffff,  
   BPET_SEV_MASK        = 0xffff0000,  
   BPET_GENERAL_WARNING = BPET_SEV_GENERAL | BPET_TYPE_WARNING,  
   BPET_GENERAL_ERROR   = BPET_SEV_GENERAL | BPET_TYPE_ERROR,  
   BPET_ALL             = 0xffffffff  
};  
```  
  
## <a name="members"></a>Üyeler  
 BPET_NONE  
 Kesme noktası hata belirtir.  
  
 BPET_TYPE_WARNING  
 Bir uyarı stili kesme hatası belirtir.  
  
 BPET_TYPE_ERROR  
 Bir hata stili kesme noktası hata belirtir.  
  
 BPET_SEV_HIGH  
 Bir yüksek önem derecesi kesme hatası belirtir.  
  
 BPET_SEV_GENERAL  
 Orta önem kesme hatası belirtir.  
  
 BPET_SEV_LOW  
 Düşük önem kesme hatası belirtir.  
  
 BPET_TYPE_MASK  
 Bir maskesi stili kesme hatası belirtir.  
  
 BPET_SEV_MASK  
 Bir önem derecesi maskesi stili kesme hatası belirtir.  
  
 BPET_GENERAL_WARNING  
 Genel uyarı stili kesme hatası belirtir.  
  
 BPET_GENERAL_ERROR  
 Bir genel hata stili kesme hatası belirtir.  
  
 BPET_ALL  
 Tüm kesme noktası hata türlerini belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu değerlerin Bitsel ile birleştirilebilir `OR` ve için kullanılan `dwType` üyesi [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) yapısı. Bir parametre olarak geçirilen [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) yöntemi.  
  
 Kesme noktası hata türü bir türü ve bir önem derecesi oluşur. Bu bir kesme noktası hata türü hiçbir zaman yalnızca bir tür olduğu anlamına gelir (örneğin, `BPET_TYPE_ERROR`,) veya bir önem derecesi (örneğin, `BPET_SEV_GENERAL`) kendisi tarafından. `BPET_GENERAL_WARNING`ve `BPET_GENERAL_ERROR` önceden tanımlanmış değerler için genel uyarı ve hata olan kesme noktaları sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)