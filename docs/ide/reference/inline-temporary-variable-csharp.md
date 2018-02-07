---
title: "Geçici bir değişken değerini C# ile değiştir | Microsoft Docs"
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
ms.workload:
- dotnet
ms.openlocfilehash: 626224e8ed90196294f7b3ded245bb5272f70595
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="inline-a-temporary-variable-with-c"></a>Satır içi geçici bir değişken C# ile #

**Ne:** geçici bir değişken kaldırın ve bunun yerine, değeriyle değiştirmenizi sağlar.

**Ne zaman:** geçici değişken kullanımını kodunu anlamanın zorlaştırır.

**Neden:** geçici bir değişken kaldırılması hale kodu kolay okunur.

**Nasıl:**

1. Vurgula veya metin imleci geçici değişkenin içermesinden olmasını içinde:

   ![Vurgulanmış kodu](media/inline-highlight-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   * **Fare**
     * Kod sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.

1. Seçin **satır içi geçici değişken** gelen önizleme penceresi açılır.

   Değişkeni kaldırılacak ve kendi kullanımları hemen değişkenin değeriyle değiştirilir.

   ![Satır içi sonucu](media/inline-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)