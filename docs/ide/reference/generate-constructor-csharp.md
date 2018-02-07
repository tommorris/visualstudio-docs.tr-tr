---
title: "Bir Oluşturucu - kod oluşturma (C#) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: b6e73b3b012547e98934bbcd76d1ee2eb0f3324d
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
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

   ![İmleç boş satır içinde](media/constructor1-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate Oluşturucusu...**  gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate Oluşturucusu...**  gelen önizleme penceresi açılır.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) sınıf boş satırında metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor1-preview-cs.png)

1. Çekme ve yanı sıra Oluşturucusu parametre olarak kullanılması (yukarı ve aşağı ok) sıralamak istediğiniz üyeleri seçmenizi sağlayan bir iletişim kutusu görünür. Tuşuna **Tamam** değişiklikleriniz kaydedilemedi.
  
   ![Çekme üyeleri iletişim](media/constructor1-dialog-cs.png)

   >[!TIP] 
   >Kontrol edebilirsiniz **null denetimlerinin eklemek** Oluşturucusu parametre için null denetimlerinin otomatik olarak oluşturmak için onay kutusunu.

1. Oluşturucu, belirtilen sırada seçilen parametrelerle oluşturulur.
   ![Oluşturucu sonuç oluştur](media/constructor1-result-cs.png)

## <a id="selection"></a>Seçili alanlardan Oluşturucusu oluştur
1. Oluşturulan oluşturucuda sahip istediğiniz üyeleri vurgulayın: ![vurgulayın üyeleri](media/constructor2-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate Oluşturucusu 'TypeName(...)'**  gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate Oluşturucusu 'TypeName(...)'**  gelen önizleme penceresi açılır.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) seçim ile satırındaki metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

     ![Oluşturucu Önizleme oluşturma](media/constructor2-preview-cs.png)

1. Seçili parametrelerle Oluşturucusu oluşturulur.
     ![Oluşturucu sonuç oluştur](media/constructor2-result-cs.png)

## <a id="usage"></a>Oluşturucu yeni kullanımdan oluştur
1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir oluşturucu kullandığını gösteren bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/constructor-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate oluşturucuda '*TypeName*'** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **Generate oluşturucuda '*TypeName*'** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor-preview-cs.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Yapıcı, kendi kullanımdan çıkarımı yapılan herhangi bir parametre ile otomatik olarak oluşturulur.

   ![Oluşturucu sonuç oluştur](media/constructor-result-cs.png)

## <a id="addparameter"></a>Parametre için var olan bir oluşturucu ekleyin
1. Bir parametre var olan bir nesne örneklemesi ekleyin.

1. İmlecinizi satıra yerleştirin henüz mevcut olmayan bir oluşturucu kullandığını gösteren bir kırmızı dalgalı olduğu.
    
    ![Oluşturucu Vurgu oluştur](media/constructor4-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **'TypeName(...)' parametre ekleme**  gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **'TypeName(...)' parametresini ekleyin**  gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

    ![Oluşturucu Önizleme oluşturma](media/constructor4-preview-cs.png)

1. Parametresi, kendi kullanımdan çıkarımı yapılan tür ile otomatik olarak eklenir.
   
   ![Oluşturucu sonuç oluştur](media/constructor4-result-cs.png)

## <a id="create"></a>Oluşturma ve alan/oluşturucu parametresini özelliğinden başlatma
1. Varolan bir oluşturucu bir parametre ekleyin:

   ![Oluşturucu Vurgu oluştur](media/constructor5-highlight-cs.png)

1. Yeni eklenen parametresi içinde imlecinizi yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **oluşturma ve başlatma özelliği 'YourProperty'** veya **oluşturma ve başlatma alan 'YourField'** gelen Önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **oluşturma ve başlatma özelliği 'YourProperty'** veya **oluşturma ve başlatma alan 'YourField'**gelen önizleme penceresi açılır.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) eklenen parametresiyle satırındaki metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

   ![Oluşturucu Önizleme oluşturma](media/constructor5-preview-cs.png)

1. Alanı/özelliği oluşturulur ve türlerinizi eşleşecek şekilde otomatik olarak adlandırılır.

   ![Oluşturucu sonuç oluştur](media/constructor5-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)