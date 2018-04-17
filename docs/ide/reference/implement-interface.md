---
title: Visual Studio'da bir arabirimini uygulayan | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 4d06c10ff5e1c04c79a588cf7842399442afbe18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="implement-an-interface-in-visual-studio"></a>Visual Studio'da bir arabirimini uygulama

Bu kod oluşturma için geçerlidir:

- C#

- Visual Basic

**Ne:** hemen bir arabirim için gereken kod oluşturmanıza olanak sağlar.

**Ne zaman:** arabirimden devralan istiyor.

**Neden:** bu özellik tüm yöntemi imzaları otomatik olarak oluşturur ancak tüm arabirimini birer birer el ile uygulama.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi satıra yerleştirin bir arabirim başvurulan, ancak gerekli tüm üyeleri uygulanmadı gösterir kırmızı bir dalgalı olduğu.

   - C# ' TA:

    ![Vurgulanmış kodu C#](media/interface-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu VB](media/interface-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     - &nbsp; ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

1. Seçin **arabirimi uygulama** açılır menüsünden.

   ![Uygulama arabirimi Önizleme](media/interface-preview-cs.png)

   > [!TIP]
   > - Kullanım **Önizleme değişiklikleri** önizleme penceresinin altındaki bağlantıyı [tüm değişiklikleri görmek için](../../ide/preview-changes.md) , oluşturulacak seçiminizi yaptıktan önce.
   > - Kullanım **belge**, **proje**, ve **çözüm** en uygun yöntem imzaları uygulayan birden çok sınıflar arasında oluşturmak için Önizleme penceresinin altındaki bağlantıları arabirim.

   Arabirimin yöntem imzaları oluşturulur ve uygulanması hazır.

   - C# ' TA:

      ![Uygulama arabirimi sonuç C#](media/interface-result-cs.png)

   - Visual Basic:

      ![Uygulama arabirimi sonuç VB](media/interface-result-vb.png)

   > [!TIP]
   > (Sadece C#) Kullanım **arabirimi açıkça uygulama** her yazdığınızdan seçeneği oluşturulan ad çakışmaları önlemek için arabirim adı ile yöntemi.
   >
   > ![Arabirimi uygulama açıkça sonucu](media/interface-explicitresult-cs.png);

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma](../code-generation-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)
