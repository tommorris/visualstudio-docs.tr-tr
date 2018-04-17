---
title: Hata ayıklama altyapısı özel oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, implementing
- debug engines, custom
- debugging [Debugging SDK], custom debug engines
ms.assetid: 52794238-6fae-451c-bf1c-99f344c6f173
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 66ec73a13a3494ae6642e6d0f7397c9f3c1f0b0b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-custom-debug-engine"></a>Bir özel hata ayıklama altyapısı oluşturma
Hata ayıklama altyapısı (DE) belirli çalışma zamanı mimarilerini hata ayıklama sağlayan bir bileşendir. Genellikle çalışma zamanı ortamı başına yalnızca bir DE uygulama yok.  
  
> [!NOTE]
>  Transact-SQL ve JScript için ayrı DE uygulamaları olsa da, VBScript ve JScript tek SE paylaşır.  
  
 Yürütme denetimi, kesme noktaları ve ifade değerlendirme hata ayıklama gibi hizmetleri sağlamak için yorumlayıcı veya işlem sistemiyle SE çalışır. Bu hizmetler DE arabirimleri aracılığıyla uygulanır ve hata ayıklayıcısı farklı işletimsel modlar arasında geçiş için neden olabilir. Daha fazla bilgi için bkz: [işlem modları](../../extensibility/debugger/operational-modes.md).  
  
 SE oluşturma aşağıdaki adımlardan oluşur:  
  
1.  Visual Studio ile SE kaydetme  
  
2.  Ayıklanacak bir program etkinleştirme  
  
3.  Yürütme denetimi ve durum değerlendirme  
  
4.  Gönderen olaylar  
  
5.  Sonlandırma ve ayırma  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Özel Bir Hata Ayıklama Altyapısını Kaydetme](../../extensibility/debugger/registering-a-custom-debug-engine.md)  
 Böylece kullanılabilmesi için bir hata ayıklama altyapısı Visual Studio ile kaydetmek için gereken adımları açıklar.  
  
 [Bir Programı Hataları Ayıklanacak Şekilde Etkinleştirme](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)  
 Sizin DE bir program ayıklayabilirsiniz önce gerekir ilk DE başlatın veya varolan bir program eklemek olduğunu açıklar.  
  
 [Yürütme Denetimi ve Durum Değerlendirmesi](../../extensibility/debugger/execution-control-and-state-evaluation.md)  
 Neden bir uygulamada hata ayıklama yürütme denetim özelliklerini uygulama gerektirir açıklanır.  
  
 [Olayları Gönderme](../../extensibility/debugger/sending-events.md)  
 Hata ayıklayıcı DE arasındaki iletişimi DCOM göre bir olay modeli olarak açıklar.  
  
 [Sonlandırma ve Ayırma](../../extensibility/debugger/termination-and-detaching.md)  
 Hiçbir kesme noktaları, özel durumlar, çalışma zamanı hataları veya sonsuz döngüler ayıklanacak uygulamada olduğu anlamına gelir normal sonlandırma elde etmek açıklanmaktadır.  
  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)  
 Hata ayıklama oturumunda gerçekleşen olayların arama sırasını belgeler.  
  
 [Nasıl Yapılır: Özel Hata Ayıklama Altyapısında Hata Ayıklama](../../extensibility/debugger/how-to-debug-a-custom-debug-engine.md)  
 Özel SE hata ayıklama açıklanmaktadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Hata Ayıklayıcı Genişletilebilirliği](../../extensibility/debugger/visual-studio-debugger-extensibility.md)