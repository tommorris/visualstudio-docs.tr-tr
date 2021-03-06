---
title: Kesme noktaları (Visual Studio SDK) | Microsoft Docs
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
- breakpoints
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 194551141ed6d56344a4ed49962df41fd3b8d2ae
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629386"
---
# <a name="breakpoints-visual-studio-sdk"></a>Kesme Noktaları (Visual Studio SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kesme noktaları (Visual Studio SDK)](https://docs.microsoft.com/visualstudio/extensibility/debugger/breakpoints-visual-studio-sdk).  
  
Kesme noktaları üç tür vardır: beklemede, bağlama ve hata.  
  
 **Bir bekleyen kesme noktası:**  
  
-   Bir kesme noktası veya daha fazla program bir veya daha fazla kod bağlamlarda bağlamak için gerekli tüm bilgileri içeren bir soyutlamadır. Her bir program olan yüklemeye neden kodu hata ayıklaması, hata ayıklama altyapısı bunlar bağlanabilir, görmek için tüm bekleyen kesme noktalarını denetler.  
  
     Bir bekleyen kesme hiçbir zaman kod, bağlar ancak bunun yerine toplar ve onu oluşturan tüm bağlı kesme noktalarını içeren kabul edilir.  
  
-   Tarafından temsil edilen bir [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) arabirimi.  
  
 **İlişkili bir kesme noktası:**  
  
-   Bir kesme noktası için bir soyutlamayı ile ilişkili veya tek bir kod bağlamına bağlı. Her bağlı Kesme noktasının yanıt bekleyen bir kesme noktası olarak oluşturulur. Ancak, bir bekleyen kesme noktasının birden fazla bağlı Kesme noktasının oluşturabilirsiniz.  
  
     Kod kaldırıldığında, ilişkili bir kesme noktası ilişkisiz ve atıldı.  
  
-   Tarafından temsil edilen bir [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) arabirimi.  
  
 **Bir hata kesme noktası:**  
  
-   Bir kod bağlamı için bir bekleyen kesme noktasının bağlama girişimi sırasında bir hata tanımlamak için bir soyutlamadır. Bir hata kesme noktası ya da bir hata konumu veya kesme noktası ifadesi açıklar. Daha fazla bilgi için [kesme noktaları bağlama](../../extensibility/debugger/binding-breakpoints.md).  
  
     Bir hata veya uyarı kesme Notası hatası olabilir.  
  
-   Tarafından temsil edilen bir [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Programlar](../../extensibility/debugger/programs.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [Kod bağlamı](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)

