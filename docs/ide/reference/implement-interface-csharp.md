---
title: "Bir arabirim - kod oluşturma (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bebff2ad-25b6-4adc-8762-60d23bdd639a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 908e11da78b2a83fb3da23d28b5cc52613f7b0f2
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="implement-an-interface-in-c"></a>Uygulama bir arabirim, C# #
**Ne:** hemen bir arabirim için gereken kod oluşturmanıza olanak sağlar. 

**Ne zaman:** arabirimden devralan istiyor.  

**Neden:** bu özellik tüm yöntemi imzaları otomatik olarak oluşturur ancak tüm arabirimini birer birer el ile uygulama. 

**Nasıl:**

1. İmlecinizi satıra yerleştirin bir arabirim başvurulan, ancak tüm gerekli üyeleri uygulanmadı belirten bir kırmızı dalgalı olduğu.

   ![Vurgulanmış kodu](media/interface-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **arabirimi (açıkça) uygulama** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **arabirimi (açıkça) uygulama** gelen önizleme penceresi açılır.
     * Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Uygulama sınıfı Önizleme](media/interface-preview-cs.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.
   >
   >Ayrıca, kullanabileceğiniz **belge**, **proje**, ve **çözüm** birden çok uygun yöntem imzaları oluşturmak için Önizleme pencerenin altındaki bağlantıları arabirimini uygulayan sınıflar.

1. Arabirimin yöntemi imzalar, otomatik olarak oluşturulan, uygulanması için hazır olacaktır.

   ![Uygulama sınıfı sonucu](media/interface-result-cs.png)

   >[!TIP]
   >Kullanım **arabirimi açıkça uygulama** her yazdığınızdan seçeneği oluşturulan ad çakışmaları önlemek için arabirim adı ile yöntemi.
   >
   >![Arabirimi uygulama açıkça sonucu](media/interface-explicitresult-cs.png); 

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)  
