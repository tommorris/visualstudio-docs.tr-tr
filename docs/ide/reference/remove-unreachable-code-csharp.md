---
title: "Ulaşılamaz kod için C# Visual Studio'da yeniden düzenleme kaldırma | Microsoft Docs"
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
ms.openlocfilehash: 12b6910aad6399b72b3e4bc10e6b857cc98c09bb
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="remove-unreachable-code-in-c"></a>Ulaşılamaz kod C# ' ta Kaldır #

**Ne:** hiçbir zaman yürütülecek kod kaldırır.

**Ne zaman:** programınız bu kod parçacığını gereksiz yaparak bir kod parçacığı hiçbir yolu vardır.

**Neden:** artırmak okunabilirlik ve bakımı gereksiz kodu kaldırarak ve hiçbir zaman yürütülür.

**Nasıl:**

1. İmlecinizi ulaşılamaz durumda çıkışı soluk kodda herhangi bir yere koyun:

![Soluk ulaşılamaz kod](media/unreachablecode-faded-cs.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **kaldırmak ulaşılamaz kod** gelen önizleme penceresi açılır.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **kaldırmak ulaşılamaz kod** gelen önizleme penceresi açılır.

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

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)