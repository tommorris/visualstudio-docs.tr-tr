---
title: "Değişken bildirimi başvuru yakın C# ' ta taşıma | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: ghogen
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: f61fbdc8dd24bb07082081557c875e9149c1c398
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
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

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)