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
ms.workload: multiple
ms.openlocfilehash: 891a33b74927d45434c4614dc4c5d7f1533ba4c0
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-constructor-in-visual-basic"></a>Visual Basic'te bir oluşturucu oluştur
**Ne:** hemen bir sınıf üzerinde yeni bir oluşturucu için kod oluşturmanıza olanak sağlar. 

**Ne zaman:** yeni Oluşturucusu getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.  

**Neden:** ancak, bu özellik, uygun parametrelerle birlikte otomatik olarak oluşturur, kullanmadan önce Oluşturucusu bildirebilirsiniz. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir oluşturucu kullandığını gösteren bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/constructor-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate oluşturucuda '*TypeName*'** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate oluşturucuda '*TypeName*'** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-vb.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-vb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor-preview-vb.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Yapıcı, kendi kullanımdan çıkarımı yapılan herhangi bir parametre ile otomatik olarak oluşturulur.

   ![Oluşturucu sonuç oluştur](media/constructor-result-vb.png)
 
## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)