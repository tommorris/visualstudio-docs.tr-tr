---
title: "Alan, özelliği veya yerel - kod oluşturma (Visual Basic) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2dd0ef0db74a0ee723c7cd09bd8118e646b8ba3f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="generate-a-field-property-or-local-in-visual-basic"></a>Visual Basic'te bir alan, özelliği veya yerel oluştur
**Ne:** hemen önceden bildirilmemiş alan, özelliği veya yerel kodunu oluşturmak olanak tanır. 

**Ne zaman:** yazarken yeni bir alan, özelliği veya yerel getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.  

**Neden:** ancak bu özellik bildirimi oluşturmak ve otomatik olarak yazın, kullanmadan önce alan, özelliği veya yerel bildirebilirsiniz. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin bir alan, yerel kullandığını gösteren kırmızı dalgalı veya henüz mevcut olmayan özellik olduğu.

   ![Vurgulanmış kodu](media/field_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select  **Generate değişkeni '*adı*' > alanı/özelliği Oluştur/yerel ** önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklayın ve **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin  **Generate değişkeni '*adı*' > alanı/özelliği Oluştur/yerel ** Önizleme pencere açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Özellik/alan/yerel Önizleme oluşturma](media/field_preview.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Alan, özelliği veya yerel kendi kullanımdan çıkarımı yapılan tür ile otomatik olarak oluşturulur.

   ![Özellik/alan/yerel sonuç oluştur](media/field_result.png)

## <a name="see-also"></a>Ayrıca Bkz.  
[Kod oluşturma (Visual Basic)](../code-generation-vb.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md)