---
title: "Kullanıcı geri bildirim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user model feedback
- environment, context
- IDE, context
- IDE, user feedback
ms.assetid: 2d472a24-3813-4f5f-9783-b491ad8a71ad
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ffc6ecc620f57f0cc1e4dd8baf02f1bd1b17d53b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="feedback-to-the-user"></a>Kullanıcı geri bildirim
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) görsel geribildirim ilgili kullanılabilir İşlevler, kullanıcının geçerli seçim ve genel seçimi bağlam dayanır. Aşağıdaki tabloda farklı seçim bağlamlarında kullanılabilir işlevselliği listeler.  
  
|Seçim bağlamı|Kullanılabilir işlevi|  
|-----------------------|-----------------------------|  
|IDE|Global|  
|Geçerli ürün kümesi|Ürün belirli|  
|Etkin olan hiyerarşi|Hiyerarşi türü özel|  
|Etkin olan hiyerarşi öğesi|Hiyerarşi öğesi türü özel|  
|Etkin belge|Belge türü özel|  
|En üstteki birden çok belge arabirimi (MDI) penceresi|Pencere türü özel|  
|Geçerli seçim bağlamı|Belirli seçim bağlamı|  
  
 Yalnızca kullanıcıların gerekir ve sürekli olarak tutarlı seçimi ve ortam bağlamı geri bildirim sağlayın işlevselliği yüzey, IDE içinde karmaşıklığı azaltın. Her bir pencere IDE içinde açıldığında aşağıdaki kurallar geçerlidir:  
  
-   Pencerenin onun seçimi içeriği değişirse, seçim geri bildirim açıkça penceresinde gösterilen ve dinamik Yardım penceresini geçerli bağlamı yansıtacak şekilde güncelleştirilir gösterilen.  
  
-   Pencerenin genel seçimi bağlam değişirse, tüm özel bağlam menülerini, etkin olan hiyerarşi pencere ve uygulama başlık çubuğunda geçerli bağlamı yansıtacak şekilde güncelleştirilir.  
  
-   Geçerli seçim için Özellikler penceresini yüzey **özellikleri** penceresi ve isteğe bağlı olarak gösterilen, **özellik sayfaları** iletişim kutusu.  
  
-   Pencere özellikleri yüzey veya değil genel seçimi bağlamını değiştirmek artık etkin pencereyi IDE içinde olduğunda seçimi geri bildirim penceresinde kalır değil.  
  
-   Tüm belge özgü aracı windows sürekli etkin belgeyi yansıtmalıdır.  
  
-   Menüleri ve araç çubukları uygulama başlık çubuğunda en üstteki birden çok belge arabirimi (MDI) istemcisi penceresinde yansıtmalıdır.  
  
 Örneğin, ne zaman bir Visual Basic Web uygulaması projesi içinde Web formunun HTML görünümü açılır ve kullanıcının seçtiği bir `<td>` etiketi, geri bildirim aşağıdaki şekilde sağlanır:  
  
-   Seçimi etkin pencerede gösterilen ve yansıtılan **özellikleri** penceresi.  
  
-   Belge özgü **araç** etkin belgeyi yansıtacak şekilde güncelleştirilir.  
  
-   **Düzenleyicisi** araç ve **tablo** menüsü görüntülenir ve başlık çubuğunda Web Form penceresi yansıtacak şekilde güncelleştirir.  
  
-   Genellikle etkin olan hiyerarşi penceresinde **Çözüm Gezgini**ve geçerli bağlamı ve bağlama duyarlı yansıtmak için kendi başlık çubuğu güncelleştirme **proje** menü komutlarını etkin Web şimdi Uygula Uygulama projesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçim ve IDE içinde para birimi](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [Seçim bağlam nesneleri](../../extensibility/internals/selection-context-objects.md)   
 [Hiyerarşileri ve seçimi](../../extensibility/internals/hierarchies-and-selection.md)