---
title: "Kesme noktaları (Visual Studio SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoints
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: be8f0b36ebe57041e9d36b8f606bd5bddd0601bd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="breakpoints-visual-studio-sdk"></a>Kesme noktaları (Visual Studio SDK)
Kesme noktaları üç tür vardır: Bekleyen, bağımlı ve hata.  
  
 **Kesme noktası bekleyen bir:**  
  
-   Bir veya daha fazla program bir veya daha fazla kod bağlamlarda bir kesme noktası bağlamak için gerekli tüm bilgileri içeren bir soyutlamadır. Her zaman olan programı yüklemek için neden kod hata ayıklaması, hata ayıklama altyapısı bunlar bağlanabilir olmadığını görmek için tüm bekleyen kesme noktalarını denetler.  
  
     Bir bekleyen kesme hiçbir zaman kod, bağlar ancak bunun yerine toplar ve onu oluşturan tüm ilişkili kesme noktaları içeren söylenir.  
  
-   Tarafından temsil edilen bir [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) arabirimi.  
  
 **İlişkili bir kesme noktası:**  
  
-   Bir kesme noktası için bir Özet ile ilişkili veya tek bir kod bağlamına bağlı. Her bağlı kesme yanıt bekleyen bir kesme noktası olarak oluşturulur. Ancak, bekleyen bir kesme noktası birden fazla bağımlı kesme noktası oluşturabilirsiniz.  
  
     Kod kaldırıldığında ilişkili bir kesme noktası ilişkisiz ve atılır.  
  
-   Tarafından temsil edilen bir [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) arabirimi.  
  
 **Bir hata kesme noktası:**  
  
-   Bekleyen bir kesme noktası kodu bağlamına bağlamak çalışırken bir hata açıklayan bir soyutlamadır. Bir hata kesme noktası ya da bir hata konumu veya kesme noktası ifade açıklanır. Daha fazla bilgi için bkz: [bağlama kesme noktaları](../../extensibility/debugger/binding-breakpoints.md).  
  
     Kesme noktası hata, bir hata veya uyarı olabilir.  
  
-   Tarafından temsil edilen bir [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Programlar](../../extensibility/debugger/programs.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [Kod bağlamı](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)