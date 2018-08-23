---
title: IDebugBreakpointChecksumRequest2 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugBreakpointChecksumRequest2 interface
ms.assetid: 9cfdbca5-052c-48e9-8411-e2e9e4065d00
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bfccf1afeb521f5557ff20256dfede221ded687a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691760"
---
# <a name="idebugbreakpointchecksumrequest2"></a>IDebugBreakpointChecksumRequest2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugBreakpointChecksumRequest2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbreakpointchecksumrequest2).  
  
Bir kesme noktası istek için bir belge sağlama toplamı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugBreakpointChecksumRequest2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Tarafından uygulanan [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] paket hata ayıklama ve hata ayıklama motoru tarafından tüketilen.  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugBreakpointChecksumRequest2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetChecksum](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-getchecksum.md)|Belgenin sağlama toplamı için kullanılacak benzersiz tanımlayıcısını sağlama algoritması, verilen bir kesme noktası istek alır.|  
|[IsChecksumEnabled](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2-ischecksumenabled.md)|Bu belge için sağlama toplamı etkin olup olmadığını belirler.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll

