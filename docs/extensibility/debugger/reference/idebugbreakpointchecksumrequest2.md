---
title: IDebugBreakpointChecksumRequest2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugBreakpointChecksumRequest2 interface
ms.assetid: 9cfdbca5-052c-48e9-8411-e2e9e4065d00
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 51fbcd168500c2ba2cd508b2a9b282896613dd64
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbreakpointchecksumrequest2"></a>IDebugBreakpointChecksumRequest2
Bir belge sağlama kesme isteğini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBreakpointChecksumRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Tarafından uygulanan [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] paket hata ayıklama ve hata ayıklama motoru tarafından tüketilen.  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugBreakpointChecksumRequest2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetChecksum](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-getchecksum.md)|Belge sağlama toplamı kullanmak sağlama toplamı algoritması benzersiz tanıtıcısı verilen bir kesme noktası isteği alır.|  
|[IsChecksumEnabled](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-ischecksumenabled.md)|Bu belge için sağlama toplamı etkin olup olmadığını belirler.|  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll