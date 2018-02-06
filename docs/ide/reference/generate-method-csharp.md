---
title: "Üretme yöntemi - kod oluşturma (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683790b4-b68b-42d7-8dc4-a68eca05aa01
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: e4caf80bec38305613111f290b80eafb74547598
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-method-in-c"></a>C# ' ta üretme bir yöntemi #
**Ne:** hemen bir yöntem bir sınıfa eklemenizi sağlar. 

**Ne zaman:** yeni bir yöntem ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.  

**Neden:** ancak, bu özellik bildirimi otomatik olarak oluşturur, yöntemi ve parametreleri, kullanmadan önce bildirebilirsiniz. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir yöntem kullandığını gösteren bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/method-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **üretme yöntemi** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **üretme yöntemi** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Yöntem Önizleme oluşturma](media/method-preview-cs.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Yöntemi, kendi kullanımdan çıkarımı yapılan herhangi bir parametre ile otomatik olarak oluşturulur.

   ![Yöntem sonuç oluştur](media/method-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)
