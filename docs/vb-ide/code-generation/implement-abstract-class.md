---
title: "Soyut bir sınıf - kod oluşturma (Visual Basic) uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cfed7f-f090-4369-8a85-2dcd4c7cf12b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 68f60b6159cad7f751dfc47a8af116ef33a164c2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="implement-an-abstract-class-in-visual-basic"></a>Visual Basic'te soyut bir sınıf uygulama
**Ne:** hemen bir Özet sınıf uygulamak için gereken kodu oluşturmanıza olanak sağlar. 

**Ne zaman:** bir özet sınıftan istiyor.  

**Neden:** bu özellik tüm yöntemi imzaları otomatik olarak oluşturur ancak tüm soyut üyelerini birer birer kendiniz uygulamak. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin bir özet sınıftan devralınan ancak tüm gerekli üyeleri uygulanmadı belirten bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/abstract_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **uygulama Özet sınıf** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **uygulama Özet sınıf** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Uygulama sınıfı Önizleme](media/abstract_preview.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.
   >
   >Ayrıca, kullanabileceğiniz **belge**, **proje**, ve **çözüm** birden çok uygun yöntem imzaları oluşturmak için Önizleme pencerenin altındaki bağlantıları soyut sınıftan sınıflar.

1. Özet yöntem imzalar, otomatik olarak oluşturulan, uygulanması için hazır olacaktır.

   ![Uygulama sınıfı sonucu](media/abstract_result.png)

## <a name="see-also"></a>Ayrıca Bkz.  
[Kod oluşturma (Visual Basic)](../code-generation-vb.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md)