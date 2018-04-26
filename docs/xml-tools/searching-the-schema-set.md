---
title: XML şema Explorer - şema kümesinde arama
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: ec1395e0-d03c-4130-810d-f2db656937bd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b3aa631ab673f7b6d679cbe39459ecb9a5fbbaf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="searching-the-schema-set"></a>Şema kümesini arama

XML şema Explorer aşağıdaki yollarla ayarlamak şema aramanıza olanak tanır:

-   Anahtar sözcük araması.

-   Şema özgü arama.

## <a name="keyword-search"></a>Anahtar sözcük araması

 İçinde bir alt dizesi girerek anahtar sözcüğü arama gerçekleştirmek **arama SchemaSet** XML Şeması Explorer araç çubuğunun metin kutusu.

 ![XML şema Explorer anahtar sözcük aramasını](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")

 XML şema Explorer ayarlamak için aşağıdaki öznitelikler şema arar:

-   Tüm `name` veya `ref` belirtilen anahtar sözcüğü eşleşen öznitelikleri. Bu öğeler, öznitelikler, türler ve benzeri, ada göre bulmanızı sağlar.

-   `schemaLocation` Özniteliklerini deyimleri içerir.

-   `namespace` İçeri aktarma deyimlerini öznitelikleri.

## <a name="schema-specific-search"></a>Şema belirli arama

 XML şema Explorer XML Şeması Explorer bağlam menüsünü kullanarak erişebilirsiniz yerleşik aramaları da içerir. Kullanılabilir bağlam menülerini hakkında daha fazla bilgi için bkz: [bağlam menülerini](../xml-tools/context-menus-xml-schema-explorer.md). Bir şema özgü Arama Başlat görünümünden de gerçekleştirebilirsiniz; Daha fazla bilgi için "Şema ayrıntılarını ayarlama" bölümüne bakın [Başlangıç'ı](../xml-tools/start-view.md) konu.

## <a name="displaying-and-navigating-search-results"></a>Görüntüleme ve arama sonuçlarını gezinme

 Arama tamamlandıktan sonra arama sonuçlarını araç çubuğunda özet sonuçlar bölmesinde eklenir. Arama sonuçlarını da XML Şeması Explorer'da vurgulanır ve çizgilerine dikey kaydırma çubuğunda olarak işaretlenmiş. Kullanarak arama sonuçlarını gidebilirsiniz **sonraki arama sonucuna Git** ve **önceki arama sonucuna Git** XML Şeması Explorer araç; klavye tuşlarını kullanarak Özet sonuçlar bölmesinde düğmeleri F3 ve Shift + F3; değer çizgilerinin kaydırma çubuğunda tıklatarak veya.

 Arama sonuçlarını çalışma alanı'na tıklayarak ekleyebileceğiniz **çalışma alanına vurgulanan düğümleri eklemek** Özet Sonuçlar bölmesindeki düğmesi.

 ![XML şema Explorer arama sonucu](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")

## <a name="clearing-search-results"></a>Temizleme arama sonuçları

 Arama sonuçlarını temizlemek için tıklatın **x** Özet Sonuçlar bölmesindeki XML Şeması Explorer arama araç çubuğu düğmesi.

## <a name="see-also"></a>Ayrıca Bkz.

- [XML Şema Gezgini](../xml-tools/xml-schema-explorer.md)