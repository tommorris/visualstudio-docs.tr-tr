---
title: 'Nasıl yapılır: şema kümesi arama sonucu düğümlerini çalışma alanına ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 19157704019a949a4b2590ff277bcabd3bb320f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693044"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>Nasıl yapılır: şema kümesi arama sonucu düğümlerini çalışma alanına ekleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: ekleme şema kümesi arama sonucu düğümlerini çalışma alanına](https://docs.microsoft.com/visualstudio/xml-tools/how-to-add-schema-set-search-result-nodes-to-the-workspace).  
  
  
Bu konuda, çalışma alanındaki anahtar sözcük arama sonucu olarak, XML şema Gezgini içinde vurgulanmıştır düğümlerini ekleme açıklanmaktadır.  
  
> [!NOTE]
>  Yalnızca genel düğümler eklenebilir [çalışma](../xml-tools/xml-schema-designer-workspace.md).  
  
 Bu örnekte örnek [satınalma siparişi şeması](../xml-tools/sample-xsd-file-purchase-order-schema.md).  
  
### <a name="to-add-schema-set-result-nodes"></a>Şema kümesi sonucu düğümlerini eklemek için  
  
1.  Bağlantısındaki [nasıl yapılır: bir XSD şema dosyası oluşturma ve düzenleme](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).  
  
2.  "PurchaseOrder" yazın arama metin kutusuna [XML Gezgini](../xml-tools/xml-schema-explorer.md) araç çubuğu ve Ara düğmesine tıklayın.  
  
     ![XML şema Gezgini anahtar sözcük arama](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
     Arama sonuçları XML şema Gezgini içinde vurgulanmış ve dikey kaydırma çubuğu üzerinde işaretleri tarafından işaretlenen.  
  
3.  Arama sonuçlarını tıklayarak çalışma alanına ekleme **çalışma alanına vurgulanmış düğümler Ekle** özet sonuçlar bölmesinde düğmesine.  
  
     ![XML şema Gezgini arama sonucu](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")  
  
     `purchaseOrder` Düğüm ve `PurchaseOrderType` düğümünün görünen birbirinin yanına tasarım yüzeyine [graf görünümünü](../xml-tools/graph-view.md). İki düğüm birbiriyle ilişkili olduğundan ( `purchaseOrder` öğesi olduğu `PurchaseOrderType` türü), bir ok, aralarında çizilir.



