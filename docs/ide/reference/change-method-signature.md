---
title: "Visual Studio'da bir yöntem imzası yeniden düzenlemeniz | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 8358e14ccf9570207b3e52a552990fd2a3a80d49
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="change-a-method-signature-refactoring"></a>Bir yöntem imza yeniden düzenleme değiştirme

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** kaldırın ya da bir yöntemin parametre sırasını değiştirme imkan tanır.

**Ne zaman:** taşımak veya çeşitli konumlara kullanılmakta olan bir yöntem parametresi kaldırmak istediğiniz.

**Neden:** el ile kaldırın ve parametreleri yeniden Sırala sonra bu yöntem tüm çağrıları bulmak ve bunları tek tek değiştirmek, ancak hatalarına neden olabilir.  Bu yeniden düzenleme aracı görevi otomatik olarak gerçekleştirir.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Vurgula veya metin imleci değiştirmek için yöntemi veya kendi kullanımlarından adını içinde:

   - C# ' TA:

    ![Vurgulanmış kodu C#](media/changesignature-highlight-cs.png)

   - VB:

    ![Vurgulanmış kodu Visual Basic](media/changesignature-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl + R**, ardından **Ctrl + V**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     - Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **değişiklik imza** gelen önizleme penceresi açılır.
   - **Fare**
     - Seçin **Düzenle > yeniden düzenlemeniz > kaldırmak parametreleri**.
     - Seçin **Düzenle > yeniden düzenlemeniz > parametreleri yeniden Sırala**.
     - Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **değişiklik imza** gelen önizleme penceresi açılır.

1. İçinde **değiştirmek imza** , POP iletişim yöntemini imza değiştirmek için sağ tarafta düğmeleri kullanabilirsiniz:

   ![İmza iletişim değiştirme](media/changesignature-dialog-cs.png)

   | Düğme | Açıklama
   | ------ | ---
   | **Yukarı/Aşağı** | Seçilen parametre listesi yukarı ve Aşağı Taşı
   | **Kaldır**  | Seçili parametreyi listeden kaldırın
   | **Geri yükleme** | Seçili, çizilmiş parametre listesine geri yükleme

   > [!TIP]
   > Kullanım **başvuru değişikliklerini Önizleme** onay kutusu [sonuç görmek](../../ide/preview-changes.md) kendisine gerçekleştirmeden önce.

1. İşiniz bittiğinde, basın **Tamam** değişiklik yapmak için düğmesi.

   - C# ' TA:

    ![İmza sonucu - C# değiştirme](media/changesignature-result-cs.png)

   - Visual Basic:

    ![İmza sonucu - Visual Basic değiştirme](media/changesignature-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)