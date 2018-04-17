---
title: İş Akışı Tasarımcısı Kabuk özellikleri | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- WFDShellFeatures.UI
ms.assetid: 14bfe312-9592-408e-92ce-e98585ad16e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ecf7d88b6436ba117b85c2ea6cc423520f9fd873
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="workflow-designer-shell-features"></a>İş Akışı Tasarımcısı Kabuk özellikleri

Windows iş akışı Tasarımcısı üç ana UI alandan oluşur: Tasarımcı yüzeyine, içerik haritası çubuğunun üstündeki ve altındaki Kabuk. Ekranın en üstünde konumlandırılmış içerik haritası çubuğunun üst geçerli kök etkinlik öğelerinin listesini görüntülemek için kullanılır. Daha fazla bilgi için bkz: [nasıl yapılır: kullanım içerik haritası Gezinti](../workflow-designer/how-to-use-breadcrumb-navigation.md). Tasarımcı yüzeyine konumlandırılmış ekran Merkezi'nde iş akışları oluşturmak için kullanılır. Ekranın alt kısmında konumlandırılmış Kabuk geçerli görünümü yönetme için düğmeler sayısını içerir.

## <a name="shell-features"></a>Kabuk özellikleri
 Kabuk düğmeleri yakınlaştırmak veya iş akışınızı dışında ekranınızın boyutu iş akışınıza içeriklerin sığması ve Göster veya gizle Genel İnceleme haritası için kullanabileceğiniz çubuğu sağ tarafta vardır. Ayrıca CTRL ++ ve CTRL + klavye kısayollarını kullanarak bir iş akışı dışında ya da yakınlaştırabilirsiniz-.

## <a name="overview-map"></a>Genel İnceleme Haritası
 Genel İnceleme Haritası tüm alt ve tüm genişletilmiş bunların alt öğeleri de dahil olmak üzere geçerli içerik haritası kökündeki tüm etkinlik küçük bir sürümünü görüntüler. Bir Görünüm penceresi, bir dikdörtgen içinde Düzenleyicisi görüntülenmekte etkinlik kısmı vurgular turuncu bir kenarlık yoktur. Genel İnceleme Haritası etrafında dikdörtgen sürükleyerek, iş akışı Tasarımcısı'nı birlikte kayar ve düzenleyici görünümünü değiştirir.

> [!NOTE]
> [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Kullanıcı arabirimi sanallaştırılmış. Etkinlik tasarımcıları, yalnızca gerekli olduğunda işlenir. İş akışı bir kısmı hiçbir zaman Tasarımcı yüzeyine düzenlendi, söz konusu bölümü üzerinde genel bakış eşlemesi beyaz olarak görünür. Genel İnceleme Haritası tamamen kaydırma iş akışı çizer.

## <a name="copying-or-saving-workflows-as-images"></a>Kopyalama veya iş akışları görüntü olarak kaydetme
 İş akışları, bit eşlem biçiminde kopyaladığınız veya bitmap veya vektör biçiminde kaydedilmiş. Kopyalama veya görüntü kaydetme tüm alt öğelerini ve başka bir programa genişletilmiş kendi alt dahil olmak üzere geçerli içerik haritası kökündeki tüm etkinlik görünümünü dışa aktarmak için bir yol sağlar.

 Resim olarak kopyalamak için herhangi bir yere Tasarımcısı seçin sağ tıklayın ve **kopya görüntü olarak**. Resim olarak kaydetmek için herhangi bir yere Tasarımcısı seçin sağ tıklayın ve **resmi olarak kaydetmek**. İş akışları, JPG, GIF, PNG ya da XPS biçiminde kaydedilebilir. Biçimi seçili **Kaydet** iletişim kutusunda **farklı türde Kaydet:** liste kutusu pencerenin altındaki aşağı açılır.

## <a name="fonts-and-colors"></a>Yazı tipleri ve renkler

Kullanılan yazı tipleri [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] içinde [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] ortamı yazı tipi tarafından denetlenir. Görüntülenen renkleri [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] işletim sistemi tema için yüksek karşıtlık renk düzenini kullanıyorsanız değiştirin. Yeniden başlatmanız gerekir [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] değişikliklerin etkili olabilmesi için yazı tipi veya renk ayarlarını değiştirdikten sonra [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)].