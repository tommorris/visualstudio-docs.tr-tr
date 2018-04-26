---
title: İş Akışı Tasarımcısı - iş akışı Tasarımcısı'nda klavye kısayolları
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- WFDKeyboardShortcuts.UI
ms.assetid: 9be75438-a4a3-4781-94e5-45b7ec082358
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 83664d6402c23da89adf332bc9cd34eac89384bb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="keyboard-shortcuts-in-the-workflow-designer"></a>İş Akışı Tasarımcısı'nda klavye kısayolları

Windows iş akışı Tasarımcısı çekirdek işlevselliğini klavye kullanılarak erişilebilir.

## <a name="navigating-the-workflow-designer-using-the-keyboard"></a>Klavyeyi kullanarak iş akışı Tasarımcısı gezinme

Visual Studio 2010 içinde genel kısayolları ve hata ayıklama kısayolları iş akışı Tasarımcısı için geçerlidir. Ayrıca, iş akışı Tasarımcısı belirli klavye kısayollarını sayısı oluşturuldu. Visual Studio 2010'da, tüm klavye kısayollarını açmayla. Ancak, bir rehosted uygulamasında bu klavye kısayolları sabit kodlanmış değildir.

### <a name="workflow-designer-keyboard-shortcuts"></a>İş Akışı Tasarımcısı klavye kısayolları

İş Akışı Tasarımcısı komutları atanmış varsayılan klavye kısayolları aşağıdaki tabloda özetlenmiştir.

|Kısayol|Amaç|
|--------------|-------------|
|CTRL + E, A|Gösterir veya bağımsız değişkeni Tasarımcısı gizler.|
|CTRL+E, C|Seçili etkinlik yerinde daraltır.|
|CTRL + E, E|Seçili etkinlik yerinde genişletir.|
|CTRL + E, F|Bir akış çizelgesi seçili etkinlikler bağlanır.|
|CTRL + E, T|Gösterir veya içeri aktarmalar Tasarımcısı gizler.|
|CTRL + E, M|Klavye odağını sekme sırasında bir sonraki öğeye taşır.|
|CTRL+E, N|Seçili etkinlik (veya en yakın) kapsamında yeni bir değişken oluşturur.|
|CTRL + E, O|Gösterir veya gizler Genel İnceleme haritası.|
|CTRL + E, P|Seçili etkinlik üst öğeye gider. Bu içerik haritası Gezinti bir düzey yukarı gider ve tasarımcı yüzeyine kök faaliyete değiştirir.|
|CTRL + E, S|Öğe klavye odağını ile geçerli seçime ekler.|
|CTRL+E, V|Gösterir veya değişken Tasarımcısı gizler.|
|CTRL+E, X|İş akışındaki tüm etkinlikler genişletir.|
|CTRL+ALT+F6|Klavye odağı geçerli kullanıcı Arabirimi alanından dizisi sonraki alanına taşır. Sipariş aşağıdaki gibidir:<br /><br /> 1.  İçerik haritası gezinti çubuğu.<br />2.  Tasarımcı yüzeyine<br />3.  Bağımsız değişkenler/değişkenleri/Imports Tasarımcısı açıksa<br />4.  Kabuk|

### <a name="flowchart"></a>Akış Çizelgesi

Aşağıdaki liste bir akış çizelgesi oluşturmak için klavye tarafından kullanılan hareketlerini gösterir. İş Akışı Tasarımcısı rest olduğu gibi etkinlikler Visual Studio 2010 ile sağlanan genel araç kısayolları kullanılarak Tasarımcı yüzeyine eklenir.

- Bir etkinlik taşımak için etkinliği seçin ve onu yeniden konumlandırmak için ok tuşlarını kullanın.

- Bir akış çizelgesi yeniden boyutlandırmak için ok tuşlarını kullanarak akış geçerli kenarlığının geçmiş bir etkinlik taşıyın. Akış Çizelgesi otomatik olarak yeniden boyutlandırılır.

- Bir etkinlik başlangıç düğümü olarak ayarlamak için kullanın **BaşlangıçDüğümü ayarlamak** bağlam menüsünden komutu.

- Etkinlikler bağlanmak için:

    1.  Kaynak etkinliği için etkinlik sekmelerle seçin.

    2.  CTRL + E, klavye odağı hedef etkinliğe taşımak için gereken sayıda tekrar M tuşuna basın.

    3.  CTRL + E, seçime hedef etkinlik eklemek için S tuşuna basın.

    4.  CTRL + E, bağlayıcı kaynaktan hedefe eklemek için F tuşlarına basın.

Etkinlikler tarafından klavye bağlanma hakkında notlar:

- CTRL + E, f basmadan seçimi için daha fazla etkinlikler ekleyerek aynı anda birden çok bağlantı yapabilirsiniz Bağlantılar etkinlikleri seçimi eklenen sırada yapılır.

- Kaynak etkinliği giden bir bağlantı zaten varsa, örneğin etkinlikleri çifti bağlanamaz seçimdeki etkinlikler arasında diğer bağlantılar hala mümkün hale getirilir.

- Zaman bir **FlowDecision** seçim eklenir ve **FlowDecision** giden bağlayıcı içermiyor, bağlayıcı yerleştirildiği **True** dal.

### <a name="expression-editing"></a>İfade düzenleme

Varsayılan olarak, Visual Basic metin düzenleme için varsayılan klavye kısayolları iş akışı Tasarımcısı'nda ifade Düzenleyicisi aşağıdaki kısıtlamalarla içinde geçerlidir:

- Aşağıdaki komutlar için klavye kısayolları yeniden eşleme hiçbir etkisi olmaz. Klavye kısayolları yalnızca bir ifade düzenlerken bu komutlara erişmek için de kullanabilirsiniz.

   - Kes
   - Kopyala
   - Yapıştır
   - Tümünü Seç
   - Geri alma
   - Yinele

- İş Akışı Tasarımcısı'nda Visual Studio 2010 içindeki ifade düzenleme komutları için klavye kısayolları yeniden eşlemek için iş akışı Tasarımcısı kapsamında kısayolları düzenleyin. Metin Düzenleyici kapsamda yapılan değişiklikleri otomatik olarak iş akışı Tasarımcısı için geçerli değildir. Her iki yerde kısayolları yeniden eşlemek istiyorsanız, değişiklikleri iki kez uygulamanız gerekir (her kapsam için bir kez).