---
title: "Taşıma türü eşleşen dosyasına düzenlemesi (C#) - | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 4b7b9b1ba52bed5d2bdf042db0149d799c489a7d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="move-a-type-to-a-matching-file-in-c"></a>C# eşleşen bir dosya türü gitme #

**Ne:** aynı ada sahip ayrı bir dosyaya seçilen tür taşımanıza olanak tanır.

**Ne zaman:** ayırmak istediğiniz aynı dosyada birden çok sınıflar, yapılar, arabirimler, vb. vardır.

**Neden:** aynı dosyada birden çok tür yerleştirme zorlaştırabilir bu tür bulunamıyor.  Aynı ada sahip dosyaları türleri taşıyarak, kodu daha okunabilir ve gitmek daha kolay olur.

**Nasıl:**

1. Vurgula veya metin imleci taşımak için türünün adı içinde:

   ![Vurgulanmış kodu](media/movetype-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **türüne taşımak için *TypeName*.cs** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **türüne taşımak için *TypeName*.cs** önizleme penceresi açılan, gelen nerede  *TypeName* seçtiğiniz türünün adı.

   Türü, çözümünüz içinde bu ada sahip yeni bir dosyaya anında taşınmış olur.

   ![Satır içi sonucu](media/movetype-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)