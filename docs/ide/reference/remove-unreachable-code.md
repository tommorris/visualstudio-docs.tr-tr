---
title: Ulaşılamaz kod Visual Studio'da yeniden düzenleme kaldırma | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: kuhlenh
ms.author: kaseyu
manager: douge
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: 2c4e142582e4ee3a3e0308c5368c58fac79f8c6f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="remove-unreachable-code-refactoring"></a>Ulaşılamaz kod yeniden düzenleme Kaldır

Bu yeniden düzenleme için geçerlidir:

- C#

**Ne:** hiçbir zaman yürütülecek kod kaldırır.

**Ne zaman:** programınız bu kod parçacığını gereksiz yaparak bir kod parçacığı hiçbir yolu vardır.

**Neden:** artırmak okunabilirlik ve bakımı gereksiz kodu kaldırarak ve hiçbir zaman yürütülür.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi ulaşılamaz durumda çıkışı soluk kodda herhangi bir yere koyun:

![Soluk ulaşılamaz kod](media/unreachablecode-faded-cs.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **kaldırmak ulaşılamaz kod** gelen önizleme penceresi açılır.
   - **Fare**
     - Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **kaldırmak ulaşılamaz kod** gelen önizleme penceresi açılır.

1. Değişiklikle memnun kaldığınızda, basın **Enter** veya düzeltmeyi menüsünde tıklatın ve değişiklikler uygulanır.

Örnek:

```csharp
// Before
private void Method()
{
    throw new Exception(nameof(Method));
    Console.WriteLine($"Exception for method {nameof(Method)}");
}

// Remove unreachable code

// After
private void Method()
{
    throw new Exception(nameof(Method));
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)