---
title: "Alan, özelliği veya yerel - kod oluşturma (C#) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 7cc27d498cbc082ad76d47d2326d1ee8fb0ebbb0
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-field-property-or-local-in-c"></a>Alan, özelliği veya yerel C# ' ta oluştur #
**Ne:** hemen önceden bildirilmemiş alan, özelliği veya yerel kodunu oluşturmak olanak tanır. 

**Ne zaman:** yazarken yeni bir alan, özelliği veya yerel getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.  

**Neden:** ancak bu özellik bildirimi oluşturmak ve otomatik olarak yazın, kullanmadan önce alan, özelliği veya yerel bildirebilirsiniz. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin bir alan, yerel kullandığını gösteren kırmızı dalgalı veya henüz mevcut olmayan özellik olduğu.

   ![Vurgulanmış kodu](media/field-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **özelliği/alan/yerel oluşturmak** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **özelliği/alan/yerel oluşturmak** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Özellik/alan/yerel Önizleme oluşturma](media/field-preview-cs.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Alan, özelliği veya yerel kendi kullanımdan çıkarımı yapılan tür ile otomatik olarak oluşturulur.

   ![Özellik/alan/yerel sonuç oluştur](media/field-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)
