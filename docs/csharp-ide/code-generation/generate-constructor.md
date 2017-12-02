---
title: "Bir Oluşturucu - kod oluşturma (C#) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.openlocfilehash: 668036b5a9c963a48255e8425c0d443fce4b8bb7
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
---
# <a name="generate-a-constructor-in-c"></a>Bir oluşturucu C# ' ta oluştur #
**Ne:** hemen bir sınıf üzerinde yeni bir oluşturucu için kod oluşturmanıza olanak sağlar. 

**Ne zaman:** yeni oluşturucu ve düzgün bir şekilde otomatik olarak bildirmek istiyorsanız tanıtmak veya varolan bir oluşturucu değiştirin. 

**Neden:** ancak, bu özellik, uygun parametrelerle birlikte otomatik olarak oluşturur, kullanmadan önce Oluşturucusu bildirebilirsiniz. Ayrıca, varolan bir oluşturucu değiştirme otomatik olarak güncelleştirmek için bu özelliği kullanmak sürece tüm callsites güncelleştirilmesini gerektirir.

**Nasıl:** bir oluşturucu oluşturmak için birkaç yolu vardır:
- [Oluşturucusu oluşturur ve üyeleri seçin](#pick)
- [Seçili alanlardan Oluşturucusu oluştur](#selection)
- [Oluşturucu yeni kullanımdan oluştur](#usage)
- [Parametre için var olan bir oluşturucu ekleyin](#addparameter)
- [Oluşturma ve alan/oluşturucu parametresini özelliğinden başlatma](#create)

## <a id = "pick"></a>Oluşturucusu oluşturur ve üyeleri seçin
1. Herhangi bir sınıf boş satırı imlecinizi koyun:

   ![İmleç boş satır içinde](media/constructor1_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate Oluşturucusu...**  gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate Oluşturucusu...**  gelen önizleme penceresi açılır.
     * ' I tıklatın ![Ampul](media/bulb.png) sınıf boş satırında metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor1_preview.png)

1. Çekme ve yanı sıra Oluşturucusu parametre olarak kullanılması (yukarı ve aşağı ok) sıralamak istediğiniz üyeleri seçmenizi sağlayan bir iletişim kutusu görünür. Tuşuna **Tamam** değişiklikleriniz kaydedilemedi.
  
   ![Çekme üyeleri iletişim](media/constructor1_dialog.png)

   >[!TIP] 
   >Kontrol edebilirsiniz **null denetimlerinin eklemek** Oluşturucusu parametre için null denetimlerinin otomatik olarak oluşturmak için onay kutusunu.

1. Oluşturucu, belirtilen sırada seçilen parametrelerle oluşturulur.
   ![Oluşturucu sonuç oluştur](media/constructor1_result.png)

## <a id="selection"></a>Seçili alanlardan Oluşturucusu oluştur
1. Oluşturulan oluşturucuda sahip istediğiniz üyeleri vurgulayın: ![vurgulayın üyeleri](media/constructor2_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate Oluşturucusu 'TypeName(...)'**  gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate Oluşturucusu 'TypeName(...)'**  gelen önizleme penceresi açılır.
     * ' I tıklatın ![Ampul](media/bulb.png) seçim ile satırındaki metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

     ![Oluşturucu Önizleme oluşturma](media/constructor2_preview.png)

1. Seçili parametrelerle Oluşturucusu oluşturulur.
     ![Oluşturucu sonuç oluştur](media/constructor2_result.png)

## <a id="usage"></a>Oluşturucu yeni kullanımdan oluştur
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

## <a id="selection"></a>Parametre için var olan bir oluşturucu ekleyin
1. Bir parametre var olan bir nesne örneklemesi ekleyin.

1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir oluşturucu kullandığını gösteren bir kırmızı dalgalı olduğu.
    
    ![Oluşturucu Vurgu oluştur](media/constructor4_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **'TypeName(...)' parametre ekleme**  gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **'TypeName(...)' parametresini ekleyin**  gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

    ![Oluşturucu Önizleme oluşturma](media/constructor4_preview.png)

1. Parametresi, kendi kullanımdan çıkarımı yapılan tür ile otomatik olarak eklenir.
   
   ![Oluşturucu sonuç oluştur](media/constructor4_result.png)

## <a id="create"></a>Oluşturma ve alan/oluşturucu parametresini özelliğinden başlatma
1. Varolan bir oluşturucu bir parametre ekleyin:

   ![Oluşturucu Vurgu oluştur](media/constructor5_highlight.png)

1. Yeni eklenen parametresi içinde imlecinizi yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **oluşturma ve başlatma özelliği 'YourProperty'** veya **oluşturma ve başlatma alan 'YourField'** gelen Önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **oluşturma ve başlatma özelliği 'YourProperty'** veya **oluşturma ve başlatma alan 'YourField'**gelen önizleme penceresi açılır.
     * ' I tıklatın ![Ampul](media/bulb.png) eklenen parametresiyle satırındaki metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor5_preview.png)

1. Alanı/özelliği oluşturulur ve türlerinizi eşleşecek şekilde otomatik olarak adlandırılır.

   ![Oluşturucu sonuç oluştur](media/constructor5_result.png)
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Kod oluşturma (C#)](../code-generation-csharp.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md)