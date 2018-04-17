---
title: Visual Studio'da bir alan, özelliği veya yerel değişken oluştur | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: c42a1b22a7ae191fe9024e45df66695d10f102e8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="generate-a-field-property-or-local-variable-in-visual-studio"></a>Visual Studio'da bir alan, özelliği veya yerel değişken oluştur

Bu kod oluşturma için geçerlidir:

- C#

- Visual Basic

**Ne:** hemen önceden bildirilmemiş alan, özelliği veya yerel kodunu oluşturmak olanak tanır.

**Ne zaman:** yazarken yeni bir alan, özelliği veya yerel getirir ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.

**Neden:** ancak bu özellik bildirimi oluşturmak ve otomatik olarak yazın, kullanmadan önce alan, özelliği veya yerel bildirebilirsiniz.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi satıra yerleştirin kırmızı dalgalı olduğu. Kırmızı dalgalı alan, yerel veya henüz mevcut olmayan özellik gösterir.

   - C# ' TA:

    ![Vurgulanmış kodu C#](media/field-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu VB](media/field-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     - &nbsp; ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

    ![Özellik/alan/yerel Önizleme oluşturma](media/field-preview-cs.png)

1. Aşağı açılır menüden oluşturma seçeneklerden birini seçin.

   > [!TIP]
   > Kullanım **Önizleme değişiklikleri** önizleme penceresinin altındaki bağlantıyı [tüm değişiklikleri görmek için](../../ide/preview-changes.md) , oluşturulacak seçiminizi yaptıktan önce.

   Alan, özelliği veya yerel, kendi kullanımdan çıkarımı yapılan tür ile oluşturulur.

   - C# ' TA:

      ![Yöntem sonuç C# oluştur](media/field-result-cs.png)

   - Visual Basic:

      ![Yöntem sonuç VB oluştur](media/field-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma](../code-generation-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)
