---
title: "Ayıklama yöntemi Visual Studio'da | Microsoft Docs"
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
- vs.csharp.refactoring.extractmethod
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: d66a0e41f0c68d3d5c4378a664ef36aba0d869b7
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="extract-a-method-refactoring"></a>Ayıklama yöntemi yeniden düzenleme

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** kendi yönteminin içine kod parçacığını kapatmanızı sağlar.

**Ne zaman:** başka bir yönteminden çağrılması gereken bazı yöntemi var olan kod parçacığını sahip.

**Neden:** , kopyalayıp bu kodu yapıştırın, ancak çoğaltma için neden. Bu parça, başka bir yöntemle serbestçe çağrılabilir kendi yöntemiyle yeniden düzenlemeniz daha iyi bir çözümdür.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Ayıklanacak kod vurgula:

   - C# ' TA:

    ![Vurgulanmış kodu - C#](media/extractmethod-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu - Visual Basic](media/extractmethod-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl + R**, ardından **Ctrl + M**. (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **ayıklama yöntemi** gelen önizleme penceresi açılır.
   - **Fare**
     - Seçin **Düzenle > yeniden düzenlemeniz > ayıklamak yöntemi**.
     - Kod sağ tıklatıp **yeniden düzenlemeniz > ayıklamak > ayıklama yöntemi**.
     - Kodu sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **ayıklama yöntemi** gelen önizleme penceresi açılır.

   Yöntem hemen oluşturulur. Buradan, yeni bir ad yazarak şimdi yöntemi adlandırabilirsiniz.

   > [!TIP]
   > Ayrıca açıklamaları ve bu yeni ad kullanmak üzere diğer dizeleri güncelleştirebilirsiniz yanı [Önizleme değişiklikleri](../../ide/preview-changes.md) önce kaydetme, içinde onay kutularını kullanarak **yeniden adlandırmak** üstünde görünür kutusunu IDE'yi sağında.

   - C# ' TA:

    ![Rename method - C#](media/extractmethod-rename-cs.png)

   - Visual Basic:

    ![Yöntem - Visual Basic yeniden adlandırma](media/extractmethod-rename-vb.png)

1. Değişiklikle memnun kaldığınızda, seçin **Uygula** düğmesini veya tuşuna **Enter** ve değişiklikler uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)