---
title: "Taşıma türü eşleşen dosya - yeniden düzenleme (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 510b984ad2de9476d53e9a5a4bcd667f393d3d4b
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="move-type-to-a-matching-file-in-visual-basic"></a>Visual Basic'te eşleşen bir dosyaya taşıma türü

**Ne:** aynı ada sahip ayrı bir dosyaya seçilen tür taşımanıza olanak tanır.

**Ne zaman:** ayırmak istediğiniz aynı dosyada birden çok sınıflar, yapılar, arabirimler, vb. vardır.  

**Neden:** aynı dosyada birden çok tür yerleştirme zorlaştırabilir bu tür bulunamıyor.  Aynı ada sahip dosyaları türleri taşıyarak, kodu daha okunabilir ve gitmek daha kolay olur.

**Nasıl:**

1. Vurgula veya metin imleci taşımak için türünün adı içinde:

   ![Vurgulanmış kodu](media/movetype-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **türüne taşımak için *TypeName*.vb** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **türüne taşımak için *TypeName*.vb** önizleme penceresi açılan, gelen nerede  *TypeName* seçtiğiniz türünün adı.

   Türü, çözümünüz içinde bu ada sahip yeni bir dosyaya anında taşınmış olur.

   ![Satır içi sonucu](media/movetype-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)