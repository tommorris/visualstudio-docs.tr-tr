---
title: Visual Studio'da bir arabirimini uygulayan | Microsoft Docs
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: ebcdad47ebb8ecae9d943acd8e0db60c20ef8378
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
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
     - Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     - ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

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

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)
