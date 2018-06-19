---
title: Visual Studio'da bir oluşturucu oluştur
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 44235bcacf6f60a3c58fa08f01465f6aad9e57f4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31954494"
---
# <a name="generate-a-constructor-in-visual-studio"></a>Visual Studio'da bir oluşturucu oluştur

Bu kod oluşturma için geçerlidir:

- C#

- Visual Basic

**Ne:** hemen bir sınıf üzerinde yeni bir oluşturucu için kod oluşturmanıza olanak sağlar.

**Ne zaman:** yeni oluşturucu ve düzgün bir şekilde otomatik olarak bildirmek istiyorsanız tanıtmak veya varolan bir oluşturucu değiştirin.

**Neden:** ancak, bu özellik, uygun parametrelerle birlikte otomatik olarak oluşturur, kullanmadan önce Oluşturucusu bildirebilirsiniz. Ayrıca, varolan bir oluşturucu değiştirme otomatik olarak güncelleştirmek için bu özelliği kullanmak sürece tüm callsites güncelleştirilmesini gerektirir.

**Nasıl:** bir oluşturucu oluşturmak için birkaç yolu vardır:

   - [Oluşturucusu oluşturur ve üyeleri seçin](#pick)
   - [Seçili alanlardan Oluşturucusu oluştur](#selection)
   - [Oluşturucu yeni kullanımdan oluştur](#usage)
   - [Parametre için var olan bir oluşturucu ekleyin](#addparameter)
   - [Oluşturma ve alan/oluşturucu parametresini özelliğinden başlatma](#create)

## <a id = "pick"></a> Oluşturucusu oluşturur ve üyeleri (C# yalnızca) seçin

1. Herhangi bir sınıf boş satırı imlecinizi koyun:

   ![İmleç boş satır içinde](media/constructor1-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - &nbsp; ![Ampul](media/bulb-cs.png) sınıf boş satırında metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor1-preview-cs.png)

1. Seçin **Generate Oluşturucusu...**  açılan menüsünden.

   **Çekme memebers** iletişim kutusu açılır.

1. Oluşturucu parametreleri eklemek istediğiniz üyeleri seçin. Bunları yukarı kullanarak sıralayın ve aşağı okları. Seçin **Tamam**.

   ![Çekme üyeleri iletişim](media/constructor1-dialog-cs.png)

   > [!TIP]
   > Kontrol edebilirsiniz **null denetimlerinin eklemek** Oluşturucusu parametre için null denetimlerinin otomatik olarak oluşturmak için onay kutusunu.

   Belirtilen parametrelerle Oluşturucusu oluşturulur.

   ![Oluşturucu sonuç oluştur](media/constructor1-result-cs.png)

## <a id="selection"></a> Seçilen alanları (C# yalnızca) Oluşturucusu oluştur

1. Oluşturulan oluşturucuda olmasını istediğiniz üyeleri vurgula:

   ![Üyeleri vurgulayın](media/constructor2-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - &nbsp; ![Ampul](media/bulb-cs.png) seçim ile satırındaki metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

     ![Oluşturucu Önizleme oluşturma](media/constructor2-preview-cs.png)

1. Seçin **Generate Oluşturucusu 'TypeName(...)'**  açılan menüsünden.

   Yapıcı seçili parametrelerle oluşturulur.

   ![Oluşturucu sonuç oluştur](media/constructor2-result-cs.png)

## <a id="usage"></a> Oluşturucusu (C# ve Visual Basic) yeni kullanımdan oluştur

1. İmlecinizi satıra yerleştirin kırmızı dalgalı olduğu. Kırmızı dalgalı henüz mevcut olmayan bir oluşturucu için bir çağrı gösterir.

   - C# ' TA:

    ![Vurgulanmış kodu C#](media/constructor-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu VB](media/constructor-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     - &nbsp; ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

    ![Oluşturucu Önizleme oluşturma](media/constructor-preview-cs.png)

1. Seçin **Generate oluşturucuda '*TypeName*'** açılır menüsünden.

   > [!TIP]
   > Kullanım **Önizleme değişiklikleri** önizleme penceresinin altındaki bağlantıyı [tüm değişiklikleri görmek için](../../ide/preview-changes.md) , oluşturulacak seçiminizi yaptıktan önce.

   Kendi kullanımdan çıkarımı yapılan herhangi bir parametre Oluşturucusu oluşturulur.

   - C# ' TA:

      ![Yöntem sonuç C# oluştur](media/constructor-result-cs.png)

   - Visual Basic:

      ![Yöntem sonuç VB oluştur](media/constructor-result-vb.png)

## <a id="addparameter"></a> Parametresi varolan oluşturucuya (C# yalnızca) ekleyin

1. Bir parametre var olan bir oluşturucu çağrısı ekleyin.

1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir oluşturucu kullandığını gösteren bir kırmızı dalgalı olduğu.

    ![Oluşturucu Vurgu oluştur](media/constructor4-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     - &nbsp; ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

    ![Oluşturucu Önizleme oluşturma](media/constructor4-preview-cs.png)

1. Seçin **'TypeName(...)' parametre ekleme**  açılan menüsünden.

   Parametresi, kullanımdan çıkarımı yapılan tür ile oluşturucuya eklenir.

   ![Oluşturucu sonuç oluştur](media/constructor4-result-cs.png)

## <a id="create"></a> Oluşturma ve bir alan veya bir oluşturucu parametresini (C# yalnızca) özelliğinden başlatma

1. Varolan bir oluşturucu bulun ve bir parametresini ekleyin:

   ![Oluşturucu Vurgu oluştur](media/constructor5-highlight-cs.png)

1. Yeni eklenen parametresi içinde imlecinizi yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - &nbsp; ![Ampul](media/bulb-cs.png) eklenen parametresiyle satırındaki metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor5-preview-cs.png)

1. Seçin **oluşturma ve başlatma özelliği** veya **oluşturma ve başlatma alan** açılır menüsünden.

   Alan veya özellik bildirilen ve türlerinizi eşleşecek şekilde otomatik olarak adlı. Bir kod satırı, alan veya oluşturucusu gövdenin özelliğinde başlatmak için de eklenir.

   ![Oluşturucu sonuç oluştur](media/constructor5-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma](../code-generation-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)