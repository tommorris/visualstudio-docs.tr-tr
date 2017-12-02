---
title: "Başvuru yeniden düzenlemesi (C#) - yakın bildirimi taşıma | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: d79d55ae-f6bb-4902-8db2-e7fe01bdb0bf
author: kuhlenh
ms.author: kaseyu
manager: ghogen
dev_langs: csharp
ms.openlocfilehash: f784ac9fec1dce1f21ba4b9f1f0e83b4b7deb001
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
---
# <a name="move-declaration-near-reference-in-c"></a>C# başvurusu yakın bildirimini taşıyın #
**Ne:** yakın değişken bildirimleri için kullanımı taşımanıza olanak tanır.

**Ne zaman:** daha dar bir kapsamda olabilir değişken bildirimleri sahip.

**Neden:** olduğu, ancak okunabilirlik sorunları veya bilgi gizleme neden olabilir bırakabilir. Okunabilirliğini artırmak için bir fırsat düzenleme için budur.

**Nasıl:**

1. İmlecinizi Değişken bildiriminde yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **taşıma bildirimi başvuru yakın** gelen önizleme penceresi açılır.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **taşıma bildirimi başvuru yakın** gelen önizleme penceresi açılır.

1. Değişiklikle memnun kaldığınızda, basın **Enter** veya düzeltmeyi menüsünde tıklatın ve değişiklikler uygulanır.

Örnek:
```csharp
// Before
int x;
if (condition)
{
    x = 1;
    Console.WriteLine(x);
}

// Move declaration near reference

// After
if (condition)
{
    int x = 1;
    Console.WriteLine(x);
}
```

## <a name="see-also"></a>Ayrıca Bkz.  
[Yeniden düzenlemesi (C#)](../refactoring-csharp.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md)