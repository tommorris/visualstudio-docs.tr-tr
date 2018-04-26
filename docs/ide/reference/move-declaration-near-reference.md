---
title: Visual Studio'da başvuru yakın taşıma değişken bildirimi
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: douge
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: e98f7b7e9df0a1df3482257c70a661aa22d5980a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="move-declaration-near-reference-refactoring"></a>Başvuru yeniden düzenleme yakın taşıma bildirimi

Bu yeniden düzenleme için geçerlidir:

- C#

**Ne:** yakın değişken bildirimleri için kullanımı taşımanıza olanak tanır.

**Ne zaman:** daha dar bir kapsamda olabilir değişken bildirimleri sahip.

**Neden:** olduğu, ancak okunabilirlik sorunları veya bilgi gizleme neden olabilir bırakabilir. Okunabilirliğini artırmak için bir fırsat düzenleme için budur.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi Değişken bildiriminde yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **taşıma bildirimi başvuru yakın** gelen önizleme penceresi açılır.
   - **Fare**
     - Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **taşıma bildirimi başvuru yakın** gelen önizleme penceresi açılır.

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

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)