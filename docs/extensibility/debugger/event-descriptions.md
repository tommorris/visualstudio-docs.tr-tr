---
title: "Olay açıklamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 09f61652-7e16-4bb0-8055-f61a84bf384e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6ec084c0d985ce5cc3cb0a886bd1fdcaf6cc3e54
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="event-descriptions"></a>Olay açıklamaları
Her olay türü belirli bir amacı vardır.  
  
## <a name="events-and-the-reasons-for-their-use"></a>Olayları ve bunların kullanılması için nedenler  
  
|Olay|Açıklama|  
|-----------|-----------------|  
|Belge olayları etkinleştirme|Hata ayıklama altyapısı (DE) açmak veya bir belge için ön getirmek için IDE istediğinde oluşur.|  
|Kesme noktası bağlı veya kesme noktası hata olayları|Bir kesme noktası bağlı veya ne zaman bir kesme noktası bağlanamaz ve bir hata döndürdü gönderilir.|  
|İlişkisiz kesme olayları|İlişkili bir kesme noktası koddan keser oluşur.|  
|Olayları durdurabilirsiniz|Kullanıcı kodu belirtilen bir noktada durdurmak isteyip istemediğinizi belirlemek için IDE gönderdi.|  
|Kesme noktası olayları|Bir kod veya veri kesme noktası isabet oluşur.|  
|Belge metin olayları|Bir belgedeki metin değiştirildiğinde oluşur. Bu olaylar üzerinden gönderilmez `IDebugEventCallBack2::Event` yöntemi.|  
|Altyapısı olaylar oluşturma|Altyapının ilk oluşturulduğunda gönderilir.|  
|Giriş noktası olayları|Ayıklanacak program başlatma kodu çalıştırmak ve onun ilk kullanıcı giriş noktası sınırına gönderilir.|  
|Özel durum olayları|Çalışan bir program bir özel durum geldiğinde gönderilir.|  
|İfade değerlendirme complete olayları|Zaman uyumsuz ifade değerlendirme tamamlandıktan sonra gönderilir.|  
|Sembol olaylarını Bul|DE sembolleri için bir modülü bulmak için kullanıcıya sor gerektiğinde gönderdi.|  
|Yük complete olayları|Yalnızca ilk program yükleme tamamlandıktan ve programı çalıştırmak üzere ilk kodudur gönderdi.|  
|Message olayları|Kullanıcılara gönderilen iletileri gönderilir.|  
|Modül yük olayları|Yeni bir modül yüklendiğinde veya kaldırıldığında gönderilir.|  
|Çıkış dizesi olayları|Program hata ayıklama çıktısı Yazar gönderilir.|  
|Oluşturabilir ve olayları yok|Visual Studio IDE ayıklanacak programlar durumunu izlemek böylece oluşturma veya işlemleri, programlar, özellikler, oturumlar ve iş parçacıklarını yok etme duyurmaktan gönderdi.|  
|Adım complete olayları|Bir adımı tamamlandıktan sonra gönderilir.|  
|İş parçacığı adı değişikliği olayları|Kullanıcı bir iş parçacığı adı değiştiğinde gönderilir.|  
|Program adı değişikliği olayları|Kullanıcı bir programın adını değiştiğinde gönderilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olayları Gönderme](../../extensibility/debugger/sending-events.md)