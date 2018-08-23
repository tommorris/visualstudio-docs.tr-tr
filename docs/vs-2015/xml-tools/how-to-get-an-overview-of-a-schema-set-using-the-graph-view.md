---
title: 'Nasıl yapılır: graf görünümünü kullanarak şema kümesine genel bakış | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0b7c3d1d9f351e496469e5b13552ec78e1548f5c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691466"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Nasıl yapılır: graf görünümünü kullanarak şema kümesine genel bakış
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: graf görünümünü kümesi kullanılarak bir şema özetini almak](https://docs.microsoft.com/visualstudio/xml-tools/how-to-get-an-overview-of-a-schema-set-using-the-graph-view).  
  
  
Bu konu nasıl kullanılacağını açıklar [graf görünümünü](../xml-tools/graph-view.md) düğümlerin ve düğümler arasındaki ilişkileri şema kümesi üst düzey bir görünümünü görmek için.  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Yeni bir XSD dosyası oluşturun ve kök öğe içerik modeli Görünümü'nde görüntülemek için  
  
1.  Yeni bir XML şema dosyası oluşturun ve dosyayı Relationships.xsd kaydedin.  
  
2.  Tıklayın **görüntülemek ve temel alınan XML şema dosyasını düzenlemek için XML Düzenleyicisi'ni kullanma** başlangıç görünümünde bağlantı.  
  
3.  XML şema örnek koddan kopyalama [örnek XML şeması: ilişkileri](../xml-tools/sample-xsd-file-relationships.md) ve varsayılan olarak yeni bir XSD dosyasına eklenen kodu değiştirmek için yapıştırın.  
  
4.  XML Düzenleyicisi'nde herhangi bir yere sağ tıklayıp **Görünüm Tasarımcısı**.  
  
5.  Graf görünümünü XSD araç çubuğundan seçin.  
  
6.  Seçin **şeması Ayarla** düğümünde düğüm sürükleme ve XML Şeması Gezgini suface, graf görünümünü tasarlamak için. Tüm genel düğümleri ve ilişkileri düğümlerini bağlayan oklar görmeniz gerekir.  
  
     ![Graf görünümü](../xml-tools/media/relationshipingraphview.gif "RelationshipInGraphView")  
  
7.  Tasarım yüzeyinde herhangi bir düğümde tıklayın ve şema kümesindeki Seçili düğümün nerede bulunduğunu görmek için içerik haritası çubuğu bakın.  
  
8.  Herhangi bir öğe seçin ve yüzey desing düğümde Rick tıklayın **örnek XML oluşturmak** XML örneği görmek için.



