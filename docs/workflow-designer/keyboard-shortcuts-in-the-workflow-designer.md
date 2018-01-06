---
title: "Klavye kısayolları iş akışı Tasarımcısı'nda | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: WFDKeyboardShortcuts.UI
ms.assetid: 9be75438-a4a3-4781-94e5-45b7ec082358
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 5fe712caf9e76905dee8307998ea0854a469a71d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="keyboard-shortcuts-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda klavye kısayolları
Tüm çekirdek işlevselliğini [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] klavye kullanılarak erişilebilir.  
  
## <a name="navigating-the-workflow-designer-using-the-keyboard"></a>Klavyeyi kullanarak iş akışı Tasarımcısı gezinme  
 İçinde [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], genel kısayolları ve hata ayıklama kısayolları uygulamak [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Ayrıca, bir dizi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] belirli klavye kısayollarını oluşturuldu. İçinde [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], tüm klavye kısayollarını açmayla. Ancak, bir rehosted uygulamasında bu klavye kısayolları sabit kodlanmış değildir.  
  
### <a name="workflow-designer-keyboard-shortcuts"></a>İş Akışı Tasarımcısı klavye kısayolları  
 Aşağıdaki tabloda özetlenmiştir atanmış varsayılan klavye kısayolları [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] komutları.  
  
|Kısayol|Amaç|  
|--------------|-------------|  
|CTRL + E, A|Gösterir veya bağımsız değişkeni Tasarımcısı gizler.|  
|CTRL + E, C|Seçili etkinlik yerinde daraltır.|  
|CTRL + E, E|Seçili etkinlik yerinde genişletir.|  
|CTRL + E, F|Bir akış çizelgesi seçili etkinlikler bağlanır.|  
|CTRL + E, T|Gösterir veya içeri aktarmalar Tasarımcısı gizler.|  
|CTRL + E, M|Klavye odağını sekme sırasında bir sonraki öğeye taşır.|  
|CTRL + E, N|Seçili etkinlik (veya en yakın) kapsamında yeni bir değişken oluşturur.|  
|CTRL + E, O|Gösterir veya gizler Genel İnceleme haritası.|  
|CTRL + E, P|Seçili etkinlik üst öğeye gider. Bu içerik haritası Gezinti bir düzey yukarı gider ve tasarımcı yüzeyine kök faaliyete değiştirir.|  
|CTRL + E, S|Öğe klavye odağını ile geçerli seçime ekler.|  
|CTRL + E, V|Gösterir veya değişken Tasarımcısı gizler.|  
|CTRL + E, X|İş akışındaki tüm etkinlikler genişletir.|  
|CTRL + ALT + F6|Klavye odağı geçerli kullanıcı Arabirimi alanından dizisi sonraki alanına taşır. Sipariş aşağıdaki gibidir:<br /><br /> 1.  İçerik haritası gezinti çubuğu.<br />2.  Tasarımcı yüzeyine<br />3.  Bağımsız değişkenler/değişkenleri/Imports Tasarımcısı açıksa<br />4.  Kabuk|  
  
### <a name="flowchart"></a>Akış Çizelgesi  
 Aşağıdaki liste bir akış çizelgesi oluşturmak için klavye tarafından kullanılan hareketlerini gösterir. Kalan olduğu gibi [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], etkinlikleri ile sağlanan genel araç kısayolları kullanılarak Tasarımcı yüzeyine eklenir [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].  
  
-   Bir etkinlik taşımak için etkinliği seçin ve onu yeniden konumlandırmak için ok tuşlarını kullanın.  
  
-   Bir akış çizelgesi yeniden boyutlandırmak için ok tuşlarını kullanarak akış geçerli kenarlığının geçmiş bir etkinlik taşıyın. Akış Çizelgesi otomatik olarak yeniden boyutlandırılır.  
  
-   Bir etkinlik başlangıç düğümü olarak ayarlamak için kullanın **BaşlangıçDüğümü ayarlamak** bağlam menüsünden komutu.  
  
-   Etkinlikler bağlanmak için:  
  
    1.  Kaynak etkinliği için etkinlik sekmelerle seçin.  
  
    2.  CTRL + E, klavye odağı hedef etkinliğe taşımak için gereken sayıda tekrar M tuşuna basın.  
  
    3.  CTRL + E, seçime hedef etkinlik eklemek için S tuşuna basın.  
  
    4.  CTRL + E, bağlayıcı kaynaktan hedefe eklemek için F tuşlarına basın.  
  
 Etkinlikler tarafından klavye bağlanma hakkında notlar:  
  
-   CTRL + E, f basmadan seçimi için daha fazla etkinlikler ekleyerek aynı anda birden çok bağlantı yapabilirsiniz Bağlantılar etkinlikleri seçimi eklenen sırada yapılır.  
  
-   Kaynak etkinliği giden bir bağlantı zaten varsa, örneğin etkinlikleri çifti bağlanamaz seçimdeki etkinlikler arasında diğer bağlantılar hala mümkün hale getirilir.  
  
-   Zaman bir **FlowDecision** seçim eklenir ve **FlowDecision** giden bağlayıcı içermiyor, bağlayıcı yerleştirildiği **True** dal.  
  
### <a name="expression-editing"></a>İfade düzenleme  
 Varsayılan olarak, varsayılan klavye kısayolları [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] metin düzenleme uygulamak ifade Düzenleyicisi'nde içinde [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], aşağıdaki kısıtlamalarla:  
  
-   Aşağıdaki komutlar için klavye kısayolları yeniden eşleme hiçbir etkisi olmaz. Klavye kısayolları yalnızca bir ifade düzenlerken bu komutlara erişmek için de kullanabilirsiniz.  
  
    1.  Kes  
  
    2.  Kopyala  
  
    3.  Yapıştır  
  
    4.  Tümünü Seç  
  
    5.  Geri alma  
  
    6.  Yinele  
  
-   İfade içindeki komutları düzenlemek için klavye kısayolları yeniden eşlemek için [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] içinde [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], kısayolları Düzenle [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] kapsam. Metin Düzenleyici kapsamda yapılan değişiklikleri otomatik olarak için geçerli olmayan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Her iki yerde kısayolları yeniden eşlemek istiyorsanız, değişiklikleri iki kez uygulamanız gerekir (her kapsam için bir kez).