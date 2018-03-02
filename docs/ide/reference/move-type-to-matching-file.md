---
title: "Eşleşen dosya Visual Studio'da yeniden düzenleme için taşıma türü | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 87619c7938afdf92da6ca1b03c3090ad7d72834c
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="move-a-type-to-a-matching-file-refactoring"></a>Bir eşleşen dosya yeniden düzenleme için bir türü taşıma

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** aynı ada sahip ayrı bir dosyaya seçilen tür taşımanıza olanak tanır.

**Ne zaman:** ayırmak istediğiniz aynı dosyada birden çok sınıflar, yapılar, arabirimler, vb. vardır.

**Neden:** aynı dosyada birden çok tür yerleştirme zorlaştırabilir bu tür bulunamıyor. Aynı ada sahip dosyaları türleri taşıyarak, kodu daha okunabilir ve gitmek daha kolay olur.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Vurgula veya metin imleci taşımak için türünün adı içinde:

   - C# ' TA:

    ![Vurgulanmış kodu - C#](media/movetype-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu - Visual Basic](media/movetype-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **türüne taşımak için *TypeName*.cs** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
   - **Fare**
     - Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **türüne taşımak için *TypeName*.cs** önizleme penceresi açılan, gelen nerede  *TypeName* seçtiğiniz türünün adı.

   Türü, çözümün parçası olarak bu ada sahip yeni bir dosyaya taşınır.

   - C# ' TA:

    ![Satır içi sonucu - C#](media/movetype-result-cs.png)

   - Visual Basic:

    ![Satır içi sonucu - Visual Basic](media/movetype-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)