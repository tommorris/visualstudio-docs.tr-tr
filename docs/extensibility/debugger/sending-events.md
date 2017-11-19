---
title: "Olayların gönderilmesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bf4c3b0f494a5825820b8f794ccaf5dc727786e3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sending-events"></a>Gönderen olaylar
Hata ayıklayıcı ve hata ayıklama altyapısı (DE) arasındaki iletişim için DCOM bir olay modeline mekanizmadır. Olayları COM nesneleri olarak gönderilir ve her olay aşağıdakileri belirten sahiptir:  
  
-   Olayı adlı DE.  
  
-   Ne açıklaması.  
  
-   İşlem, program ve olayın gerçekleştiği bağlamı tanımlar iş parçacığı bilgileri. İşlem, SE gönderilen olaylar için gönderilmez.  
  
-   Olay zaman uyumlu veya zaman uyumsuz olduğunu belirten olayı türü.  
  
 Tüm hata ayıklama olayları yöntemi kullanılarak gönderilen [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Olay kaynakları](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 İki olay kaynağını açıklanmaktadır: hata ayıklama altyapısı (DE) ve oturum Yöneticisi'ni (SDM) hata ayıklama.  
  
 [Desteklenen olay türleri](../../extensibility/debugger/supported-event-types.md)  
 Şu anda desteklenen olay türleri açıklanmaktadır: zaman uyumsuz ve zaman uyumlu.  
  
 [Olay açıklamaları](../../extensibility/debugger/event-descriptions.md)  
 Olaylar ve bunların kullanılması nedeniyle tanımlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Bir özel hata ayıklama altyapısı oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Hata ayıklama hizmetleri sağlamak için yorumlayıcı veya işletim sistemi SE nasıl çalıştığı açıklanmaktadır.