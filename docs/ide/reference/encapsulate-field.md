---
title: Visual Studio'da bir özellik için bir alan yeniden düzenlemeniz | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.encapsulatefield
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: b3bb30e262374324952e38cf8b783a96ff6b3f9a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="encapsulate-a-field-refactoring"></a>Yeniden düzenleme alanı Yalıt

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** bir alan bir özellikte açın ve yeni oluşturulan özelliği kullanmak için bu alanın tüm kullanımları güncelleştirmenize olanak sağlar.

**Ne zaman:** bir özellikte alandan ve bu alan için tüm başvuruları güncelleştirmek istiyor.

**Neden:** bir alana diğer sınıflar erişim vermek istediğiniz, ancak doğrudan erişim sağlamak için bu sınıfların istemezsiniz.  Bir özellik alanında kaydırma tarafından örneğin atanmasına değerini doğrulamak için kod yazabilirsiniz.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Vurgula veya metin imleci kapsülleyen alanın adını içinde:

   - C# ' TA:

    ![Vurgulanmış kodu - C#](media/encapsulate-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu - Visual Basic](media/encapsulate-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl + R**, ardından **Ctrl + E**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsünü seçin **yalıtma alan** girişi önizleme penceresi açılır.
   - **Fare**
     - Seçin **Düzenle > yeniden düzenlemeniz > alanı Yalıt**.
     - Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsünü seçin **yalıtma alan** girişi önizleme penceresi açılır.

   Seçim | Açıklama
   --------- | -----------
   **Alanı Yalıt (ve özelliğini kullanın)** | Bir özellik alanıyla yalıtır ve oluşturulan özelliği kullanmak için alanının tüm kullanımları güncelleştirir
   **Alanı Yalıt (ancak hala alanını kullanın)** | Bir özellik alanıyla saklar, ancak alanının tüm kullanımları dokunulmadan bırakır

   Özellik oluşturulur ve seçiliyse Alan başvuruları güncelleştirilir.

   > [!TIP]
   > Kullanım **Önizleme değişiklikleri** açılan penceredeki bağlantı [sonuç görmek için](../../ide/preview-changes.md) kendisine gerçekleştirmeden önce.

   - C# ' TA:

    ![Özellik sonucu - C# yalıtma](media/encapsulate-result-cs.png)

   - Visual Basic:

    ![Özellik sonucu - Visual Basic yalıtma](media/encapsulate-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)