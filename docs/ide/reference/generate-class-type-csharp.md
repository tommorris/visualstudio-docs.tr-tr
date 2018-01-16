---
title: "Bir sınıf veya türü - kod oluşturma (C#) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: ebc361fe-d9b1-4c7a-ae28-5e71b5775460
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vsl.GenerateFromUsage
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 87ef385a7e9edf9f975eb579bfab292039d60fa2
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-class-or-type-in-c"></a>Bir sınıf veya türü C# ' ta oluştur #
**Ne:** hemen bir sınıf veya türü için kod oluşturmanıza olanak sağlar. 

**Ne zaman:** yeni bir sınıf veya türü getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.  

**Neden:** ancak, bu özellik sınıfı oluşturmak veya otomatik olarak yazın, kullanmadan önce sınıf veya tür bildirebilirsiniz. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir sınıf kullandığını gösteren bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/class-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve önizleme penceresi açılır seçeneklerinden birini seçin.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve önizleme penceresi açılır seçeneklerinden birini seçin.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Sınıf Önizleme oluşturma](media/class-preview-cs.png)

   Seçim | Açıklama
   --- | ---
   Sınıfı oluşturmak*TypeName*' yeni dosyasında | Adlı bir sınıf oluşturur *TypeName* adlı bir dosyaya *TypeName*.cs/.vb
   Sınıfı oluşturmak*TypeName*' | Adlı bir sınıf oluşturur *TypeName* geçerli dosyasında.
   İç içe geçmiş sınıf oluşturmak*TypeName*' | Adlı bir sınıf oluşturur *TypeName* geçerli sınıf içinde iç içe geçmiş.
   Yeni türü oluştur... | Belirttiğiniz özelliklerin tümünü yeni bir sınıf veya yapı oluşturur.

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Seçerseniz **yeni türünü oluştur...**  öğesi, bir iletişim kutusu açılır, bazı ek eylemleri gerçekleştirmenize olanak sağlar.

   ![Türü](media/class-newtype-cs.png)

   Seçim | Açıklama
   --- | ---
   Access | Sahip türünü ayarlayın *varsayılan*, *dahili* veya *ortak* erişim.
   türü | Bu olarak ayarlanabilir *sınıfı* veya *yapısı*.
   Ad | Bu değiştirilemez ve zaten yazdığınız ad olacaktır.
   Proje | Çözümünüz içinde birden çok proje varsa, dinamik sınıf/yapı istediğiniz seçebilirsiniz.
   Dosya Adı | Yeni bir dosya oluşturabilir veya varolan bir dosyaya türü ekleyebilirsiniz.

1. Sınıf/yapı, kendi kullanımdan çıkarımı yapılan Oluşturucusu ile otomatik olarak oluşturulur.

   ![Sınıf sonuç oluştur](media/class-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)