---
title: "Hata ayıklama altyapısı özel oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, implementing
- debug engines, custom
- debugging [Debugging SDK], custom debug engines
ms.assetid: 52794238-6fae-451c-bf1c-99f344c6f173
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fb5971bf86c6b97d38daaf86f3a093da196020da
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Bir özel hata ayıklama altyapısı kaydetme](../../extensibility/debugger/registering-a-custom-debug-engine.md)  
 Böylece kullanılabilmesi için bir hata ayıklama altyapısı Visual Studio ile kaydetmek için gereken adımları açıklar.  
  
 [Ayıklanacak bir Program etkinleştirme](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)  
 Sizin DE bir program ayıklayabilirsiniz önce gerekir ilk DE başlatın veya varolan bir program eklemek olduğunu açıklar.  
  
 [Yürütme denetimi ve durum değerlendirme](../../extensibility/debugger/execution-control-and-state-evaluation.md)  
 Neden bir uygulamada hata ayıklama yürütme denetim özelliklerini uygulama gerektirir açıklanır.  
  
 [Gönderen olaylar](../../extensibility/debugger/sending-events.md)  
 Hata ayıklayıcı DE arasındaki iletişimi DCOM göre bir olay modeli olarak açıklar.  
  
 [Sonlandırma ve ayırma](../../extensibility/debugger/termination-and-detaching.md)  
 Hiçbir kesme noktaları, özel durumlar, çalışma zamanı hataları veya sonsuz döngüler ayıklanacak uygulamada olduğu anlamına gelir normal sonlandırma elde etmek açıklanmaktadır.  
  
 [Arama hata ayıklayıcı olayları](../../extensibility/debugger/calling-debugger-events.md)  
 Hata ayıklama oturumunda gerçekleşen olayların arama sırasını belgeler.  
  
 [Nasıl yapılır: bir özel hata ayıklama altyapısı hata ayıklama](../../extensibility/debugger/how-to-debug-a-custom-debug-engine.md)  
 Özel SE hata ayıklama açıklanmaktadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio hata ayıklayıcısı genişletilebilirliği](../../extensibility/debugger/visual-studio-debugger-extensibility.md)