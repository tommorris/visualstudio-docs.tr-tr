---
title: "Soyut bir sınıf - kod oluşturma (C#) uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96cfed7f-f090-4369-8a85-2dcd4c7cf12b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: f089ffbe33d4a36e84d6d39abb3b3db3c4b2aeb7
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="implement-an-abstract-class-in-c"></a>Soyut bir sınıf C# ' ta uygulama #
**Ne:** hemen bir Özet sınıf uygulamak için gereken kodu oluşturmanıza olanak sağlar. 

**Ne zaman:** bir özet sınıftan istiyor.  

**Neden:** bu özellik tüm yöntemi imzaları otomatik olarak oluşturur ancak tüm soyut üyelerini birer birer kendiniz uygulamak. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin bir özet sınıftan devralınan ancak tüm gerekli üyeleri uygulanmadı belirten bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/abstract-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **uygulama Özet sınıf** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **uygulama Özet sınıf** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Uygulama sınıfı Önizleme](media/abstract-preview-cs.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.
   >
   >Ayrıca, kullanabileceğiniz **belge**, **proje**, ve **çözüm** birden çok uygun yöntem imzaları oluşturmak için Önizleme pencerenin altındaki bağlantıları soyut sınıftan sınıflar.

1. Özet yöntem imzalar, otomatik olarak oluşturulan, uygulanması için hazır olacaktır.

   ![Uygulama sınıfı sonucu](media/abstract-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)
