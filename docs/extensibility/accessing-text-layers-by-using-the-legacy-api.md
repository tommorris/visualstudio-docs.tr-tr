---
title: Eski API kullanarak metin katmanları erişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text layers
ms.assetid: 2258fcdd-38d1-479d-b8f8-1d4e6525f72c
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8a5f7a80e8d594f3c9e62ecd2047cc1116948d2c
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="accessing-text-layers-by-using-the-legacy-api"></a>Eski API kullanarak metin katmanları erişme
Bir metin katmanı genellikle metin düzenini bazı yönlerinin yalıtır. Örneğin, "işlevi--bir zamanda" katman önce ve sonra şapka (metin ekleme noktasını) içeren bir işlev metni gizler.  
  
 Metin katmanının bir arabellek ve bir görünüm arasında bulunur ve görünümü arabellek içeriği görür şekilde değiştirir.  
  
## <a name="text-layer-information"></a>Metin katmanı bilgileri  
 Aşağıdaki listede metin katmanları nasıl çalıştığı açıklanmaktadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]:  
  
-   Metni metin katmanı söz dizimi renklendirme ve işaretçileri olan donatılacak.  
  
-   Şu anda kendi Katmanlar uygulayamaz.  
  
-   Bir katman sunan <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>, türetilen <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>. Metin arabelleğini de polymorphically katmanlarda ile mücadele etmek bir görünümünü sağlar bir katmanı olarak uygulanır.  
  
-   Herhangi bir sayıda katmanlar, arabellek ve görünüm arasında kalan. Her katman yalnızca altındaki Katman işler ve görünümü büyük ölçüde en üst katman ile ilgilidir. (Görünümü arabellek hakkında bazı bilgiler sahip.)  
  
-   Bir katman, Katmanlar etkileyebilir. Standart olayları kaynaklanan ötesinde üzerindeki katmanların etkileyemez.  
  
-   Düzenleyicisi'nde gizli metin, yapay metin ve sözcük kaydırma katmanları olarak uygulanır. Gizli ve yapay metin katmanları ile doğrudan etkileşim olmaksızın uygulayabilirsiniz. Daha fazla bilgi için bkz: [eski dil hizmetinde anahat oluşturma](../extensibility/internals/outlining-in-a-legacy-language-service.md) ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSyntheticTextSession>.  
  
-   Her metin katmanı aracılığıyla sunulan yerel kendi koordinat sistemini sahip <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer> arabirimi. Temel metin arabelleğini yalnızca tek bir çizgi içerebilir ancak satır-wrap katmanında, örneğin, iki satır içerebilir.  
  
-   Görünüm katmanlar arasında iletişim kurar <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView> arabirimi. Bu arabirim görünümü koordinatları arabellek koordinatları ile mutabık kılmak için kullanın.  
  
-   Metin kaynaklandığı yapay metin katmanının bir yerel uygulaması sağlamalısınız gibi herhangi bir katman <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A>.  
  
-   Yanında <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>, bir metin katmanı uygulamalıdır <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> ve olayları yangın <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents> arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sözdizimi özel düzenleyicilerde renklendirme](../extensibility/syntax-coloring-in-custom-editors.md)   
 [Metin işaretçileri eski API ile kullanma](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Düzenleyici denetimleri ve menüleri eski API kullanarak özelleştirme](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)