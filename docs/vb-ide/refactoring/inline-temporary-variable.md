---
title: "Satır içi geçici değişken - yeniden düzenleme (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a63d6407-5acb-4d5f-8c0e-ecedddc07177
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3607e646f5f1ccc6121e5ee8a5b71772008f1ce8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="inline-a-temporary-variable-in-visual-basic"></a>Satır içi Visual Basic'te geçici bir değişken
**Ne:** geçici bir değişken kullanımını kaldırmak ve yerine gerçek koduyla değiştirmenizi sağlar.

**Ne zaman:** geçici değişken kullanımını kodunu anlamanın zorlaştırır.  

**Neden:** geçici bir değişken kaldırılması hale kodu belirli durumlarda okunmasını

**Nasıl:**

1. Vurgula veya metin imleci geçici değişkenin içermesinden olmasını içinde:

   ![Vurgulanmış kodu](media/inline_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **satır içi geçici değişken** gelen önizleme penceresi açılır.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **satır içi geçici değişken** gelen önizleme penceresi açılır.

   Değişkeni kaldırılacak ve kendi kullanımları hemen değişkenin değeriyle değiştirilir.

   ![Satır içi sonucu](media/inline_result.png)

## <a name="see-also"></a>Ayrıca Bkz.
[Yeniden düzenleme (Visual Basic)](../refactoring-vb.md)