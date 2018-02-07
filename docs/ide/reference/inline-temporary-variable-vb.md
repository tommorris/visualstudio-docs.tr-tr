---
title: "Visual Basic'de değeriyle geçici bir değişken Değiştir | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7553a67892322a1acb2db33d7a16b399b6f0b23a
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="inline-a-temporary-variable-in-visual-basic"></a>Satır içi Visual Basic'te geçici bir değişken

**Ne:** geçici bir değişken kaldırın ve bunun yerine, değeriyle değiştirmenizi sağlar.

**Ne zaman:** geçici değişken kullanımını kodunu anlamanın zorlaştırır.

**Neden:** geçici bir değişken kaldırılması hale kodu kolay okunur.

**Nasıl:**

1. Vurgula veya metin imleci geçici değişkenin içermesinden olmasını içinde:

   ![Vurgulanmış kodu](media/inline-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.

1. Seçin **satır içi geçici değişken** gelen önizleme penceresi açılır.

   Değişkeni kaldırılacak ve kendi kullanımları hemen değişkenin değeriyle değiştirilir.

   ![Satır içi sonucu](media/inline-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)