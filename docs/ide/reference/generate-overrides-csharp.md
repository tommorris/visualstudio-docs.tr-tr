---
title: "Equals ve GetHashCode yöntemi geçersiz kılmalar - kod oluşturma (C#) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 56b1753dbdcfbf8ce318e964a16879f02b1482c4
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-c"></a>Eşittir oluşturmak ve GetHashCode yöntemi C# içinde geçersiz kılar #

**Ne:** oluşturmanıza olanak tanır **eşittir** ve **GetHashCode** yöntemleri.

**Ne zaman:** "bazı alanlar tarafından yerine bellekteki nesne konuma göre karşılaştırılmalıdır value" temsil eden bir tür sahip olduğunda bu geçersiz kılmaları oluşturur.

**Neden:** bir değer türü uyguluyorsanız, ValueType eşittir yöntemi varsayılan uygulaması üzerinden daha yüksek performans elde etmek için Equals yöntemini geçersiz kılma düşünmelisiniz.

Bir başvuru türü uyguluyorsanız, türünüz noktası, dize, BigNumber vb. gibi bir taban türü gibi görünüyorsa Equals yöntemini geçersiz kılma düşünmelisiniz.

Bir karma tablosunda düzgün çalışması için bir türü izin vermek için GetHashCode yöntemi yok sayın. Daha fazla kılavuzunu okuyun [eşitlik işleçleri](/dotnet/standard/design-guidelines/equality-operators).

**Nasıl:**

1. İmlecinizi tür bildiriminde yerleştirin.

   ![Vurgulanmış kodu](media/overrides-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **oluşturmak Equals(object)** veya **oluşturmak eşittir ve GetHashCode** gelen önizleme penceresi açılır.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **oluşturmak Equals(object)** veya **oluşturmak eşittir ve GetHashCode** Önizleme penceresinden açılır.
     * ' I tıklatın ![Ampul](media/bulb-cs.png) tür bildirimi ile satırındaki metin imleci ise sol kenar boşluğunda görüntülenen simgesine.

   ![Geçersiz kılmaları Önizleme oluşturma](media/overrides-preview-cs.png)

1. Geçersiz kılma yöntemleri için oluşturmak istediğiniz üyeleri seçin:

    ![Geçersiz kılmaları iletişim oluştur](media/overrides-dialog-cs.png)

    > [!TIP]
    > Üye listesi altındaki onay kutularını kullanarak bu iletişim kutusundan işleçleri oluşturmak seçebilirsiniz.

1. Equals ve GetHashCode geçersiz kılmaları otomatik olarak varsayılan uygulamaları ile oluşturulur.

   ![Yöntem sonuç oluştur](media/overrides-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)
