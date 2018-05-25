---
title: "Nasıl yapılır: grafik görünümü içinde XML Şeması'nı kullanarak bir şema kümesini genel bir bakış Tasarımcı Al"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8be2666316bdc4d64d4f3dd4ec52c5104a1af5cc
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Nasıl yapılır: grafik görünümü kullanılarak ayarlanan bir şema göz atın

Bu konuda nasıl kullanılacağını açıklar [grafik görünümü](../xml-tools/graph-view.md) şema kümesini ve düğümler arasındaki ilişkileri düğümlerin üst düzey bir görünümünü görmek için.

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Yeni bir XSD dosyası oluşturun ve içerik modeli görünümünde kök öğe görüntülemek için

1.  Yeni bir XML Şeması dosyası oluşturun ve dosyayı farklı Kaydet *Relationships.xsd*.

2.  Tıklatın **görüntülemek ve temel alınan XML şema dosyasını düzenlemek için XML Düzenleyicisi'ni kullanma** Başlat görünümündeki bağlantı.

3.  XML Şeması örnek kodunu kopyalama [örnek XML şeması: ilişkileri](../xml-tools/sample-xsd-file-relationships.md) ve yeni XSD dosyası varsayılan olarak eklenen kodu değiştirmek için yapıştırın.

4.  XML Düzenleyicisi'nde herhangi bir yere sağ tıklatıp **Görünüm Tasarımcısı**.

5.  Grafik görünümünden seçin **XSD araç**.

6.  Seçin **şema ayarlamak** düğümünde **XML Şeması Explorer** ve grafik görünümü suface tasarlamak için düğüm sürükleyin. Tüm genel düğümleri ve ilişkilerine sahip düğümlerini bağlayan okları görmeniz gerekir.

     ![Grafik görünümü](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")

7.  Tasarım yüzeyine herhangi bir düğümde tıklatın ve Seçili düğümün şema kümesinde nerede bulunduğunu görmek için içerik haritası çubuğunu bakın.

8.  Herhangi bir öğe seçin ve yüzey desing düğümde Rick tıklayın **örnek XML oluşturmak** XML örneği belgeyi görmek için.