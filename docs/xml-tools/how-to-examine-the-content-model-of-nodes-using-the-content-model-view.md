---
title: "Nasıl yapılır: içerik modeli içerik modeli görünümü kullanarak düğümler, İnceleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c42ddac8-b0e3-48d6-9832-112a19d6c104
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 32b87cf771b0eda1ba58973dbc2c197f4898dfd8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-examine-the-content-model-of-nodes-using-the-content-model-view"></a>Nasıl yapılır: içerik modeli içerik modeli görünümü kullanarak düğümler, İnceleme
Bu konu, kullanarak düğümleriniz keşfetmek açıklar [içerik modeli görünümü](../xml-tools/content-model-view.md).  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Yeni bir XSD dosyası oluşturun ve içerik modeli görünümünde kök öğe görüntülemek için  
  
1.  Yeni bir XML Şeması dosyası oluşturun.  
  
2.  Tıklatın **görüntülemek ve temel alınan XML şema dosyasını düzenlemek için XML Düzenleyicisi'ni kullanma** Başlat görünüm.  
  
3.  XML Şeması örnek kodunu kopyalama [örnek XML şeması: satın alma siparişi şeması](../xml-tools/sample-xsd-file-purchase-order-schema.md) ve yeni XSD dosyası varsayılan olarak eklenen kodu değiştirmek için yapıştırın.  
  
4.  Seçin `purchaseOrder` sağ tıklanarak şema Gezgini'nde öğe `purchaseOrder` öğesi XML Düzenleyicisi'ni seçerek **Göster XML Explorer'da**.  
  
5.  Sağ `purchaseOrder` XML Explorer seçip **Göster içerik modeli görünümünde**.  
  
     İçerik modeli görünümü görüntüler `purchaseOrder` tasarım yüzeyinde öğesi.  
  
6.  Genişletme `shipTo`, `billTo`, ve `items` düğümleri her düğümün çift veya her düğüm sağındaki oku çift tıklatarak.  
  
     Düğümleri `purchaseOrder` öğesi artık genişletilmiş ve öğenin içerik modeli görebilirsiniz.  
  
7.  ' Yi tıklatın altında herhangi bir düğümde `purchaseOrder` öğesi ve Seçili düğümün şema kümesinde nerede olduğunu görmek için içerik haritası çubuğunu bakın.  
  
8.  Tıklatın **Göster belgelerine** belgelerine geçiş yapmak için XSD araç çubuğu düğmesi. Ayrıca, belge geçiş yapmak için tasarım yüzeyi sağ.  
  
9. Rick tıklatma `purchaseOrder` düğümü ve select **örnek XML oluşturmak** XML örneği belgeyi görmek için.