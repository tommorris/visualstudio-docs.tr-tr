---
title: "Nasıl yapılır: XML şema Gezgini'nden çalışma alanına düğümleri eklemek | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 3b5a5749-9693-4b29-b0c2-8e07e0e55514
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d79aa5c10559eb67801ef68ad9b44f441736ccfb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer"></a>Nasıl yapılır: XML şema Gezgini'nden çalışma alanına düğümleri eklemek
Bu konuda düğüm ekleme açıklanmaktadır [XML şema Tasarımcısı çalışma](../xml-tools/xml-schema-designer-workspace.md) XML Şeması Gezgini'nden. Bu bir XSD Tasarımcısı görünümü üzerine XML Şeması Gezgini'nden düğümleri bırakarak veya XML Şeması Explorer'ın bağlam menüsünü kullanarak elde edilebilir. XML şema Gezgini tarafından gerçekleştirilen bir arama sonucunda vurgulanmış düğümleri de ekleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: şema ayarlamak arama sonucu düğümleri Ekle çalışma alanına](../xml-tools/how-to-add-schema-set-search-result-nodes-to-the-workspace.md).  
  
> [!NOTE]
>  Yalnızca genel düğümler eklenebilir [XML şema Tasarımcısı çalışma](../xml-tools/xml-schema-designer-workspace.md).  
  
### <a name="to-add-nodes-through-the-xml-explorer-context-menu"></a>XML Explorer bağlam menüsü aracılığıyla düğümleri eklemek için  
  
1.  Adımları [nasıl yapılır: oluşturma ve bir XSD şema dosyası düzenleme](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  Sağ tıklayın `PurchaseOrderType` düğümünde bir XSD Gezgini. Seçin **Göster Grafik görünümünde**.  
  
     `purchaseOrderType` Düğümü grafik görünümü tasarım yüzeyine görüntülenir.  
  
### <a name="to-drag-and-drop-a-node-on-to-a-view"></a>Bir düğüm bir görünümü açın, sürüklenip  
  
1.  Sağ tıklayın `PurchaseOrderType` grafik görünümü düğümünde. Seçin **Göster XML Şeması Explorer'da**.  
  
     Düğüm XML Şeması Gezgini'nde vurgulanır.  
  
2.  Sağ tıklayın `PurchaseOrderType` seçin ve XML Şeması Explorer düğümünde **Göster tüm başvuruları**.  
  
     `purchaseOrder` Düğüm vurgulanacak.  
  
3.  Sürükleme `purchaseOrder` düğümü grafik görünümü açın.  
  
     `purchaseOrder` Düğümü ve `PurchaseOrderType` düğümü birbirinin yanına grafik görünümü tasarım yüzeyine görünür. İki düğüm realted olduğundan ( `purchaseOrder` öğesidir `PurchaseOrderType` türü), bir ok aralarında çizilir.  
  
### <a name="to-add-nodes-using-the-schema-explorer-search-capability"></a>Şema Explorer arama özelliği kullanarak düğümleri eklemek için  
  
1.  "PurchaseOrder" yazın arama metin kutusuna [XML Explorer](../xml-tools/xml-schema-explorer.md) araç çubuğu ve arama düğmesini tıklatın.  
  
     ![XML şema Explorer anahtar sözcük aramasını](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
     Arama sonuçları XML Şeması Gezgini'nde vurgulanır ve çizgilerine dikey kaydırma çubuğunda olarak işaretlenmiş.  
  
2.  Arama sonuçlarını çalışma alanı'na tıklayarak ekleyin **çalışma alanına vurgulanan düğümleri eklemek** Özet Sonuçlar bölmesindeki düğmesi.  
  
     ![XML şema Explorer arama sonucu](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
     `purchaseOrder` Düğümü ve `PurchaseOrderType` düğümünün görünen diğer yanındaki tasarım yüzeyine [grafik görünümü](../xml-tools/graph-view.md). İki düğüm birbiriyle ilişkili olmadığından ( `purchaseOrder` öğesidir `PurchaseOrderType` türü), bir ok aralarında çizilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Şema Gezgini](../xml-tools/xml-schema-explorer.md)