---
title: "Nasıl yapılır: Scrollbar özelleştirerek kodunuzu izlemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9ebe7ec-4b6f-4ba2-a79e-80fab3db485b
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e6dd6eab2d607d059967e89030ae92d34b407ff1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-track-your-code-by-customizing-the-scrollbar"></a>Nasıl yapılır: Scrollbar özelleştirerek kodunuzu izleme
Uzun kod dosyaları ile çalışırken, her şeyi göz önünde bulundurmanız zor olabilir. Kaydırma çubuğu neler olduğuna dair kodunuzda bir Kuşbakışı görünüm vermek için kod penceresinin özelleştirebilirsiniz.  
  
### <a name="to-show-annotations-on-the-scroll-bar"></a>Ek açıklamalar kaydırma çubuğunda göstermek için  
  
1.  Kod değişiklikleri, kesme noktaları, hataları ve yer işaretleri göstermek için kaydırma çubuğunun ayarlayabilirsiniz.  
  
     Açık **kaydırma çubuğu** seçenekler sayfası (**Araçlar, metin düzenleyici seçenekleri. Tüm diller** veya belirli bir dil, veya türü **kaydırma çubuğu** hızlı başlatma penceresinde).  
  
2.  Seçin **ek açıklamaları Göster dikey kaydırma çubuğu üzerinden**, görmek istediğiniz ek açıklamaları seçin. ( **İşaretleri** kesme noktaları ve yer işaretleri seçeneği içerir.)  
  
3.  Şimdi deneyin. Büyük kod dosyasını açın ve dosyanın çeşitli yerlerde oluşan bir şey değiştirin. Kaydırma çubuğu şey olması gerekmiyor değiştirirse, değişikliklerinizi yedekleyebilirsiniz şekilde değişiklik etkisini gösterir.  
  
     İşte nasıl bir dize için bir arama sonra kaydırma çubuğu arar. Dizesinin tüm örnekleri görüntülendiğine dikkat edin.  
  
     ![Bir dize için arama sonra kaydırma çubuğu. ] (../ide/media/enhancedscrollbarsearch.png "EnhancedScrollbarSearch")  
  
     Dizesinin tüm örnekleri değiştirildikten sonra kaydırma çubuğu aşağıdadır. İşlemi bazı sorunlara neden hemen görebilirsiniz.  
  
     ![Bir dize hatalarla değiştirildikten sonra scrollbar](../ide/media/enhancedscrollbarreplace.png "EnhancedScrollbarReplace")  
  
### <a name="to-set-the-display-mode-for-the-scroll-bar"></a>Kaydırma çubuğu görüntü modu ayarlamak için  
  
1.  Kaydırma çubuğu iki mod, çubuk modu (varsayılan) ve eşleme modu vardır. Modu yalnızca ek açıklama göstergeleri kaydırma çubuğunda görüntüler. Harita modunda kod satırlarını kaydırma çubuğunda gösterilir. Oldukları nasıl geniş ve fare işaretçisini üzerlerinde getirdiğinizde olup arka plandaki kod gösterdikleri seçebilirsiniz. Bir kaydırma çubuğunun konumunda tıkladığınızda, imleci kodda bu konuma taşır. Daraltılmış bölgeleri farklı gölgeli; bunları çift tıkladığınızda genişletilir.  
  
     Üzerinde **kaydırma çubuğu** seçenekleri sayfasında, seçin **dikey kaydırma çubuğu için kullanım çubuk modu** veya **dikey kaydırma çubuğu için eşleme kullanma modu**. Genişliği seçebilirsiniz **kaynak genel bakış** açılır.  
  
     Arama örnek eşleme modu etkindir ve genişliği Orta olarak ayarlandığında nasıl göründüğünü aşağıda verilmiştir:  
  
     ![Kaydırma çubuğu harita modunda](../ide/media/enhancedscrollbar.png "EnhancedScrollbar")  
  
2.  İmleç kaydırma çubuğu yukarı ve Aşağı Taşı kodunun önizlemeleri etkinleştirmek için eşleme modu seçin **Göster önizleme araç ipucu** seçeneği. İşte bu şekilde görünür:  
  
     ![Kaydırma çubuğu araç ipucu ile](../ide/media/enhancedscrollbarsearchtooltip.png "EnhancedScrollbarSearchTooltip")  
  
     Davranış ve önizleme araç ipucu kaydırma eşleme modu tutmak istiyor, ancak kaynak kod genel bakış görmek istemediğiniz ayarlayabileceğiniz **kaynak genel bakış** için **devre dışı**.