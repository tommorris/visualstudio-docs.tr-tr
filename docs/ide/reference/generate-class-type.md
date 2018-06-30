---
title: Visual Studio'da bir sınıf veya türü oluşturma
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vsl.GenerateFromUsage
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 35c5854afe5363641979e0f79af70c2d3b925b05
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37116994"
---
# <a name="generate-a-class-or-type-in-visual-studio"></a>Visual Studio'da bir sınıf veya türü oluşturma

Bu kod oluşturma için geçerlidir:

- C#

- Visual Basic

**Ne:** hemen bir sınıf veya türü için kod oluşturmanıza olanak sağlar.

**Ne zaman:** yeni bir sınıf veya türü getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.

**Neden:** ancak, bu özellik sınıfı oluşturmak veya otomatik olarak yazın, kullanmadan önce sınıf veya tür bildirebilirsiniz.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi satıra yerleştirin kırmızı dalgalı olduğu. Kırmızı dalgalı henüz mevcut olmayan bir sınıfı gösterir.

   - C# ' TA:

    ![Vurgulanmış kodu C#](media/class-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu VB](media/class-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     - &nbsp; ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

    ![Sınıf Önizleme oluşturma](media/class-preview-cs.png)

1. Aşağı açılır menüden seçeneklerden birini seçin:

   - Sınıfı oluşturmak*TypeName*' yeni dosyasında&mdash;adlı bir sınıf oluşturur *TypeName* adlı bir dosyaya *TypeName*.cs/.vb
   - Sınıfı oluşturmak*TypeName*'&mdash;adlı bir sınıf oluşturur *TypeName* geçerli dosyasında.
   - İç içe geçmiş sınıf oluşturmak*TypeName*'&mdash;adlı bir sınıf oluşturur *TypeName* geçerli sınıf içinde iç içe geçmiş.
   - Yeni türü oluştur... &mdash;Belirttiğiniz özelliklerin tümünü yeni bir sınıf veya yapı oluşturur.

   > [!TIP]
   > Kullanım **Önizleme değişiklikleri** önizleme penceresinin altındaki bağlantıyı [tüm değişiklikleri görmek için](../../ide/preview-changes.md) , oluşturulacak seçiminizi yaptıktan önce.

1. Seçtiyseniz **yeni türü** öğesi, **oluşturmak türü** iletişim kutusu açılır. Erişilebilirlik, türü ve konumu yeni türünün yapılandırın.

   ![Türü](media/class-newtype-cs.png)

   Seçim | Açıklama
   --- | ---
   Access | Sahip türünü ayarlayın *varsayılan*, *dahili* veya *ortak* erişim.
   türü | Bu olarak ayarlanabilir *sınıfı* veya *yapısı*.
   Ad | Bu değiştirilemez ve zaten yazdığınız ad olacaktır.
   Proje | Çözümünüz içinde birden çok proje varsa, dinamik sınıf/yapı istediğiniz seçebilirsiniz.
   Dosya Adı | Yeni bir dosya oluşturabilir veya varolan bir dosyaya türü ekleyebilirsiniz.

Sınıf veya yapı oluşturulur. C# ' ta bir oluşturucu da oluşturulur.

- C#

   ![Sınıf sonuç C# oluştur](media/class-result-cs.png)

- Visual Basic

   ![Sınıf sonuç VB oluştur](media/class-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma](../code-generation-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)