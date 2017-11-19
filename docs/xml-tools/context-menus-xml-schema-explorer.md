---
title: "Bağlam menüleri (XML Şeması Gezgini) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42ab17ca-b8c1-40d7-beda-d033f66fe874
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a2839b44af2156ab237bd2b88c0b4c77e41f4b82
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="context-menus-xml-schema-explorer"></a>Bağlam menüleri (XML Şeması Gezgini)
Aşağıdaki bağlam menüsü öğelerine, şema özgü arar ve diğer işlemleri gerçekleştirmek için kullanılır.  
  
## <a name="node-type-schema-set"></a>Düğüm türü: Şema ayarlama  
 Aşağıdaki tabloda bir şema düğüm kümesi için kullanılabilen seçenekler açıklanmaktadır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Büyük olasılıkla kök öğeleri göster**|Bulur ve kendisi dışında genel öğelerden başvurulmayan tüm genel öğelerini vurgular.|  
|**Genel türler Göster**|Bulur ve şema kümesindeki tüm genel türleri vurgular.|  
|**Genel öğeleri göster**|Bulur ve şema kümesindeki tüm genel öğelerini vurgular.|  
|**Özellik penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|  
  
## <a name="node-type-namespace"></a>Düğüm türü: Namespace  
 Aşağıdaki tabloda ad alanı düğüm için kullanılabilir olan seçenekler açıklanmaktadır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Tüm gelen başvuruları göster**|Bulur ve seçilen ad alanı içe dosyaları vurgular.|  
|**Tüm giden başvuruları göster**|Seçili ad alanındaki her dosya için bulur ve aşağıdaki hususları vurgular:<br /><br /> -Başvurulan tüm ad alanlarını alma olmadan deyimleri bir `schemaLocation` özniteliği.<br />-Tüm dosyaları belirtilen seçili bir dışında ad alanlarında `schemaLocation` özniteliği içeri aktarma ve deyimleri ekleyin.|  
|**Genel türler Göster**|Bulur ve seçilen ad alanındaki tüm genel türleri vurgular.|  
|**Genel öğeleri göster**|Bulur ve seçilen ad alanındaki tüm genel öğelerini vurgular.|  
|**Özellik penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|  
  
## <a name="node-type-file"></a>Düğüm türü: dosya  
 Aşağıdaki tabloda dosya düğümü için kullanılabilir olan seçenekler açıklanmaktadır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Tüm gelen başvuruları göster**|Bulur ve seçili dosyasında belirttiğiniz tüm dosyaları vurgular `schemaLocation` kendi dahil etme ve içeri aktarma deyimlerini öznitelikleri.|  
|**Tüm giden başvuruları göster**|Bulur ve aşağıdaki hususları vurgular:<br /><br /> -Tüm ad alanı özniteliklerinde belirtilen tüm ad alanlarını alma olmayan deyimleri `schemaLocation` özniteliği.<br />-Tüm dosyaları belirtilen `schemaLocation` sınıflarının tüm öznitelikleri almak ve deyimleri ekleyin.|  
|**Genel türler Göster**|Bulur ve bu dosyadaki tüm genel türleri vurgular.|  
|**Genel öğeleri göster**|Bulur ve bu dosyadaki tüm genel öğelerini vurgular.|  
|**Görünümü Kodu**|Seçili düğümün XML Düzenleyicisi'nde içeren dosyayı açar. XML şema Explorer'da seçili öğe ayrıca XML Düzenleyicisi'nde seçili olur.|  
|**Özellik penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|  
  
## <a name="all-global-node-types"></a>Tüm genel düğüm türleri  
 Aşağıdaki tabloda tüm genel düğümler için kullanılabilir olan seçenekler açıklanmaktadır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Grafik görünümünde göster**|Grafik görünümü açılır. Seçili düğümün çalışma alanında değilse, çalışma alanına ekler ve düğümünü seçer.|  
|**İçerik modeli görünümde göster**|İçerik modeli görünümünü açar. Seçili düğümün çalışma alanında değilse, çalışma alanına ekler ve düğümünü seçer.|  
|**Görünümü Kodu**|Seçili düğümün XML Düzenleyicisi'nde içeren dosyayı açar. XML şema Explorer'da seçili öğe ayrıca XML Düzenleyicisi'nde seçili olur.|  
|**Özellik penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|  
  
## <a name="node-type-element"></a>Düğüm türü: öğesi  
 Yukarıda açıklanan genel düğüm seçeneklerin yanı sıra, bağlam menüsü öğesini düğümleri için aşağıdaki seçenekler vardır:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Tür tanımı Git**|Seçili öğenin tür tanımına gider. Bu öğe için kullanılan tür genel bir tür olduğunda geçerlidir.|  
|**Özgün öğeye git**|Öğesinin gerçek tanımı öğesi başvuruları için gider.|  
|**Tüm başvuruları göster**|Genel öğeleri için bulur ve tüm başvuruları vurgular (olan öğenin `ref="selectedElement"`) seçili öğe için.|  
|**Değiştirme grubunun üyeleri Göster**|Yedek grup yöneticileri için bulur ve seçilen öğeyi üyesi olduğu değiştirme grubunun üyesi olan tüm öğeleri vurgular. Bu, doğrudan ve dolaylı katılımcıları gösterir.|  
|**Göster değiştirme grubunun kafa sayısı**|Değiştirme grubunun üyesi, bulur ve aşağıdaki gibi seçili öğe için tüm doğrudan ve dolaylı kafa vurgular genel öğeleri için:<br /><br /> -Seçili öğede belirtilen değiştirme Grup head.<br />-Head öğede belirtilen değiştirme Grup head.|  
|**Örnek XML oluştur**|Yalnızca genel öğeler için kullanılabilir. Bir genel öğesi için örnek bir XML dosyası oluşturur.|  
  
## <a name="node-type-global-types"></a>Düğüm türü: Genel türleri  
 Yukarıda açıklanan genel düğüm seçeneklerin yanı sıra, genel tür düğümleri için bağlam menüsünde aşağıdaki seçenekler vardır:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Temel tür Göster**|Seçilen tür genel bir türden türetilmiş, seçili türünün temel türü için gider.|  
|**Tüm başvuruları göster**|Bulur ve tüm başvuruları seçilen türe vurgular. Bu öğeleri ve özniteliklerinin seçilen tür ve seçilen türden türetilmiş türler içerir.|  
|**Tüm türetilmiş türler Göster**|Bulur ve doğrudan ve dolaylı olarak seçilen türünden türetilen tüm türleri vurgular.|  
|**Tüm üst öğelerinden Göster**|Tüm üst (Temel) türlerini göster.|  
  
## <a name="node-type-attribute"></a>Düğüm türü: özniteliği  
 Yukarıda açıklanan genel düğüm seçeneklerin yanı sıra, öznitelik düğümleri için bağlam menüsünde aşağıdaki seçenekler vardır:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Tür tanımı Git**|Öznitelik için kullanılan tür genel bir tür olduğunda, seçili öznitelik türü tanımına gider.|  
|**Orijinal özniteliği gidin**|Öznitelik başvurular için öznitelik gerçek tanımına gider.|  
|**Tüm başvuruları göster**|Genel öznitelikler için bulur ve tüm başvuruları vurgular (sahip diğer öznitelikleri `ref="selectedAttribute"`) seçili öznitelik için.|  
  
## <a name="node-type-attribute-group"></a>Düğüm türü: Öznitelik grubu  
 Yukarıda açıklanan genel düğüm seçeneklerin yanı sıra, öznitelik grubu düğümleri için bağlam menüsünde aşağıdaki seçenekler vardır:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Tanıma gitme**|Başvurular için öznitelik gerçek tanımına gider.|  
|**Tüm üyeleri Göster**|Bulur ve öznitelik grubun tüm üyelerini vurgular.|  
|**Tüm başvuruları göster**|Bulur ve tüm başvuruları vurgular (özniteliği olan grupları `ref="selectedAttributeGroup"`) seçili öznitelik grubu için.|  
  
## <a name="node-type-named-group"></a>Düğüm türü: Adlandırılmış grubu  
 Yukarıda açıklanan genel düğüm seçeneklerin yanı sıra, adlandırılmış Grup düğümleri için bağlam menüsünde aşağıdaki seçenekler vardır:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Tanıma gitme**|Başvurular için öznitelik gerçek tanımına gider.|  
|**Tüm üyeleri Göster**|Bulur ve adlandırılmış grubun tüm üyelerini vurgular.|  
|**Tüm başvuruları göster**|Bulur ve tüm başvuruları vurgular (olan grupları `ref="selectedGroup"`) seçilen gruba.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML şema Gezgini](../xml-tools/xml-schema-explorer.md)   
 [Şema kümesini arama](../xml-tools/searching-the-schema-set.md)