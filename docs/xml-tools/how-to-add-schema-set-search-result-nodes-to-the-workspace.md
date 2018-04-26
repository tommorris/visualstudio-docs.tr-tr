---
title: XML şema kümesi arama sonucu düğümleri çalışma alanıma Ekle
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a9b260c6b0e63801134c3f15eabab5b13e2926e2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>Nasıl yapılır: çalışma alanı'na şema kümesi arama sonucu düğümleri Ekle

Bu konuda, çalışma alanında bir anahtar sözcük arama sonucu olarak XML Şeması Gezgini'nde vurgulanmıştır düğümleri eklemek açıklanmaktadır.

> [!NOTE]
> Yalnızca genel düğümler eklenebilir [çalışma](../xml-tools/xml-schema-designer-workspace.md).


 Bu örnek, örnek kullanır [satın alma siparişi şeması](../xml-tools/sample-xsd-file-purchase-order-schema.md).

## <a name="to-add-schema-set-result-nodes"></a>Şema kümesi sonuç düğümleri eklemek için

1.  Adımları [nasıl yapılır: oluşturma ve bir XSD şema dosyası düzenleme](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2.  "PurchaseOrder" yazın arama metin kutusuna [XML Explorer](../xml-tools/xml-schema-explorer.md) araç çubuğu ve arama düğmesini tıklatın.

     ![XML şema Explorer anahtar sözcük aramasını](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")

     Arama sonuçları XML Şeması Gezgini'nde vurgulanır ve çizgilerine dikey kaydırma çubuğunda olarak işaretlenmiş.

3.  Arama sonuçlarını çalışma alanı'na tıklayarak ekleyin **çalışma alanına vurgulanan düğümleri eklemek** Özet Sonuçlar bölmesindeki düğmesi.

     ![XML şema Explorer arama sonucu](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")

     `purchaseOrder` Düğümü ve `PurchaseOrderType` düğümünün görünen diğer yanındaki tasarım yüzeyine [grafik görünümü](../xml-tools/graph-view.md). İki düğüm birbiriyle ilişkili olmadığından ( `purchaseOrder` öğesidir `PurchaseOrderType` türü), bir ok aralarında çizilir.