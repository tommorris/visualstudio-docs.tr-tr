---
title: Olayların gönderilmesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9bbe7946b866cd751be1f0dac2dba5b8dea57e04
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31125776"
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
  
 [Desteklenen Olay Türleri](../../extensibility/debugger/supported-event-types.md)  
 Şu anda desteklenen olay türleri açıklanmaktadır: zaman uyumsuz ve zaman uyumlu.  
  
 [Olay Açıklamaları](../../extensibility/debugger/event-descriptions.md)  
 Olaylar ve bunların kullanılması nedeniyle tanımlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Özel Hata Ayıklama Altyapısı Oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Hata ayıklama hizmetleri sağlamak için yorumlayıcı veya işletim sistemi SE nasıl çalıştığı açıklanmaktadır.