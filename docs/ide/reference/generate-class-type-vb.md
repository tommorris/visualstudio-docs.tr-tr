---
title: "Bir sınıf veya türü - kod oluşturma (Visual Basic) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: ebc361fe-d9b1-4c7a-ae28-5e71b5775460
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vsl.GenerateFromUsage
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4a4ff45a59fb53964a365f31cc4d5f48a5b159dc
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="generate-a-class-or-type-in-visual-basic"></a>Visual Basic'te bir sınıf veya türü oluşturma
**Ne:** hemen bir sınıf veya türü için kod oluşturmanıza olanak sağlar. 

**Ne zaman:** yeni bir sınıf veya türü getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.  

**Neden:** ancak, bu özellik sınıfı oluşturmak veya otomatik olarak yazın, kullanmadan önce sınıf veya tür bildirebilirsiniz. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir sınıf kullandığını gösteren bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/class-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve önizleme penceresi açılır seçeneklerinden birini seçin.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve önizleme penceresi açılır seçeneklerinden birini seçin.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-vb.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-vb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Sınıf Önizleme oluşturma](media/class-preview-vb.png)

   Seçim | Açıklama
   --- | ---
   Sınıfı oluşturmak*TypeName*' yeni dosyasında | Adlı bir sınıf oluşturur *TypeName* adlı bir dosyaya *TypeName*.cs/.vb
   Sınıfı oluşturmak*TypeName*' | Adlı bir sınıf oluşturur *TypeName* geçerli dosyasında.
   İç içe geçmiş sınıf oluşturmak*TypeName*' | Adlı bir sınıf oluşturur *TypeName* geçerli sınıf içinde iç içe geçmiş.
   Yeni türü oluştur... | Belirttiğiniz özelliklerin tümünü yeni bir sınıf veya yapı oluşturur.

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Seçerseniz **yeni türünü oluştur...**  öğesi, bir iletişim kutusu açılır, bazı ek eylemleri gerçekleştirmenize olanak sağlar.

   ![Türü](media/class-newtype-vb.png)

   Seçim | Açıklama
   --- | ---
   Access | Sahip türünü ayarlayın *varsayılan*, *dahili* veya *ortak* erişim.
   türü | Bu olarak ayarlanabilir *sınıfı* veya *yapısı*.
   Ad | Bu değiştirilemez ve zaten yazdığınız ad olacaktır.
   Proje | Çözümünüz içinde birden çok proje varsa, dinamik sınıf/yapı istediğiniz seçebilirsiniz.
   Dosya Adı | Yeni bir dosya oluşturabilir veya varolan bir dosyaya türü ekleyebilirsiniz.

1. Sınıf/yapı, kendi kullanımdan çıkarımı yapılan Oluşturucusu ile otomatik olarak oluşturulur.

   ![Sınıf sonuç oluştur](media/class-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)