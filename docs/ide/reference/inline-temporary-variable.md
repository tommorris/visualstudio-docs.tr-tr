---
title: Geçici bir değişken değerini Visual Studio'da değiştirin
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: acfbfd2a23c85c81e0956190ff8e9e8501533559
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="inline-a-temporary-variable-refactoring"></a>Satır içi bir geçici değişken yeniden düzenleme

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** geçici bir değişken kaldırın ve bunun yerine, değeriyle değiştirmenizi sağlar.

**Ne zaman:** geçici değişken kullanımını kodunu anlamanın zorlaştırır.

**Neden:** geçici bir değişken kaldırılması hale kodu kolay okunur.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Vurgula veya metin imleci geçici değişkenin içermesinden olmasını içinde:

   - C# ' TA:

    ![Vurgulanmış kodu - C#](media/inline-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu - Visual Basic](media/inline-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Kod sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.

1. Seçin **satır içi geçici değişken** gelen önizleme penceresi açılır.

   Değişkeni kaldırılır ve kendi kullanımları değişkenin değeriyle değiştirilir.

   - C# ' TA:

    ![Satır içi sonucu - C#](media/inline-result-cs.png)

   - Visual Basic:

    ![Satır içi sonucu - Visual Basic](media/inline-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)