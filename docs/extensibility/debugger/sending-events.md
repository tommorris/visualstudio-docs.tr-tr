---
title: Olayları gönderme | Microsoft Docs
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
ms.openlocfilehash: 87087a2087591b01170b82c0335e4bbffc579cc2
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252459"
---
# <a name="send-events"></a>Olayları gönderme
Hata ayıklayıcı ile hata ayıklama altyapısı (DE) arasındaki iletişim için DCOM bir olay modeline mekanizmadır. Olayları COM nesneleri olarak gönderilir ve her bir olay belirtin parametreleri vardır:  
  
-   Olay adında DE.  
  
-   Ne açıklaması.  
  
-   İşlem, program ve iş parçacığı bilgisi, olayın gerçekleştiği bağlamı tanımlar. İşlem, bir DE gönderilen olaylar için gönderilmez.  
  
-   Zaman uyumlu veya zaman uyumsuz olay olup olmadığını belirten bir olay türü.  
  
 Tüm hata ayıklama olaylarını yöntemi kullanılarak gönderilen [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="in-this-section"></a>Bu bölümde  
 [Olay kaynakları](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 İki olay kaynağını açıklar: hata ayıklama altyapısı (DE) ve oturum Yöneticisi (SDM) hata ayıklama.  
  
 [Desteklenen olay türleri](../../extensibility/debugger/supported-event-types.md)  
 Şu anda desteklenen olay türleri ele alınmaktadır: zaman uyumsuz ve zaman uyumlu.  
  
 [Olay açıklamaları](../../extensibility/debugger/event-descriptions.md)  
 Olayları ve bunların kullanılması nedeniyle tanımlar.  
  
## <a name="related-sections"></a>İlgili bölümler  
 [Bir özel hata ayıklama altyapısı oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Bir DE hata ayıklama hizmetleri sağlamak için yorumlayıcı veya işletim sistemi ile nasıl çalıştığı açıklanır.