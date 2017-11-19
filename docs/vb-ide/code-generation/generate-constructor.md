---
title: "Bir Oluşturucu - kod oluşturma (Visual Basic) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0380076319a80ba85aa59c388959baece9008e94
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="generate-a-constructor-in-visual-basic"></a>Visual Basic'te bir oluşturucu oluştur
**Ne:** hemen bir sınıf üzerinde yeni bir oluşturucu için kod oluşturmanıza olanak sağlar. 

**Ne zaman:** yeni Oluşturucusu getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.  

**Neden:** ancak, bu özellik, uygun parametrelerle birlikte otomatik olarak oluşturur, kullanmadan önce Oluşturucusu bildirebilirsiniz. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir oluşturucu kullandığını gösteren bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/constructor_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select  **Generate oluşturucuda '*TypeName*' ** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select  **Generate oluşturucuda '*TypeName*' ** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor_preview.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Yapıcı, kendi kullanımdan çıkarımı yapılan herhangi bir parametre ile otomatik olarak oluşturulur.

   ![Oluşturucu sonuç oluştur](media/constructor_result.png)
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Kod oluşturma (Visual Basic)](../code-generation-vb.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md)