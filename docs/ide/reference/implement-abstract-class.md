---
title: Visual Studio'da soyut bir sınıf uygulama | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: f91c0a056cb17d1eaf2788c3c7111e2ddbbace2e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="implement-an-abstract-class-in-visual-studio"></a>Visual Studio'da soyut bir sınıf uygulama

Bu kod oluşturma için geçerlidir:

- C#

- Visual Basic

**Ne:** hemen bir Özet sınıf uygulamak için gereken kodu oluşturmanıza olanak sağlar.

**Ne zaman:** bir özet sınıftan istiyor.

**Neden:** bu özellik tüm yöntemi imzaları otomatik olarak oluşturur ancak tüm soyut üyelerini birer birer kendiniz uygulamak.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi satıra yerleştirin bir özet sınıftan devralınan, ancak gerekli tüm üyeleri uygulanmadı gösterir kırmızı bir dalgalı olduğu.

   - C# ' TA:

    ![Vurgulanmış kodu C#](media/abstract-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu VB](media/abstract-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     - &nbsp; ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Uygulama sınıfı Önizleme](media/abstract-preview-cs.png)

1. Seçin **uygulama soyut sınıf** açılır menüsünden.

   > [!TIP]
   > - Kullanım **Önizleme değişiklikleri** önizleme penceresinin altındaki bağlantıyı [tüm değişiklikleri görmek için](../../ide/preview-changes.md) , oluşturulacak seçiminizi yaptıktan önce.
   > - Kullanım **belge**, **proje**, ve **çözüm** bağlantılar pencerenin altındaki devralınan uygun yöntem imzaları arasında birden çok sınıf oluşturmak için Önizleme soyut sınıf.

   Özet yöntem imzaları oluşturulur ve uygulanması hazırsınız.

   - C# ' TA:

      ![Uygulama sınıfı sonuç C#](media/abstract-result-cs.png)

   - Visual Basic:

      ![Uygulama sınıfı sonuç VB](media/abstract-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma](../code-generation-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)
