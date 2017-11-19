---
title: "Bir arabirim - kod oluşturma (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bebff2ad-25b6-4adc-8762-60d23bdd639a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 932cfb092d4106d9afa323aa3689a813ec2dde03
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="implement-an-interface-in-visual-basic"></a>Visual Basic'te bir arabirimini uygulama
**Ne:** hemen bir arabirim için gereken kod oluşturmanıza olanak sağlar. 

**Ne zaman:** arabirimden devralan istiyor.  

**Neden:** bu özellik tüm yöntemi imzaları otomatik olarak oluşturur ancak tüm arabirimini birer birer el ile uygulama. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin bir arabirim başvurulan, ancak tüm gerekli üyeleri uygulanmadı belirten bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/interface_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **arabirimi (açıkça) uygulama** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **arabirimi (açıkça) uygulama** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Uygulama sınıfı Önizleme](media/interface_preview.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.
   >
   >Ayrıca, kullanabileceğiniz **belge**, **proje**, ve **çözüm** birden çok uygun yöntem imzaları oluşturmak için Önizleme pencerenin altındaki bağlantıları arabirimini uygulayan sınıflar.

1. Arabirimin yöntemi imzalar, otomatik olarak oluşturulan, uygulanması için hazır olacaktır.

   ![Uygulama sınıfı sonucu](media/interface_result.png)

## <a name="see-also"></a>Ayrıca Bkz.  
[Kod oluşturma (Visual Basic)](../code-generation-vb.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md)