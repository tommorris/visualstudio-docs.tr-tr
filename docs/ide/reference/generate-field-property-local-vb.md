---
title: "Alan, özelliği veya yerel - kod oluşturma (Visual Basic) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 766311f0ba165c87e61bb873baa3ab2f0b2d1402
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="generate-a-field-property-or-local-in-visual-basic"></a>Visual Basic'te bir alan, özelliği veya yerel oluştur
**Ne:** hemen önceden bildirilmemiş alan, özelliği veya yerel kodunu oluşturmak olanak tanır. 

**Ne zaman:** yazarken yeni bir alan, özelliği veya yerel getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.  

**Neden:** ancak bu özellik bildirimi oluşturmak ve otomatik olarak yazın, kullanmadan önce alan, özelliği veya yerel bildirebilirsiniz. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin bir alan, yerel kullandığını gösteren kırmızı dalgalı veya henüz mevcut olmayan özellik olduğu.

   ![Vurgulanmış kodu](media/field-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **Generate değişkeni '*adı*' > özelliği/alan/yerel oluşturmak** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate değişkeni '*adı*' > özelliği/alan/yerel oluşturmak** Önizleme penceresinden açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-vb.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-vb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Özellik/alan/yerel Önizleme oluşturma](media/field-preview-vb.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Alan, özelliği veya yerel kendi kullanımdan çıkarımı yapılan tür ile otomatik olarak oluşturulur.

   ![Özellik/alan/yerel sonuç oluştur](media/field-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)