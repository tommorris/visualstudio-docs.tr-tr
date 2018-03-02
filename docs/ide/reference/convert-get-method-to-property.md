---
title: "GET yöntemi özelliğine dönüştürmek ve bir özellik bir Get yöntemi Visual Studio'da dönüştürmek | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
ms.devlang: csharp
author: kuhlenh
ms.author: kaseyu
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.convertmethodtoproperty
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: ab91e95d699b4a7fcc27ca1f6bcdf43b51af9c26
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="convert-get-method-to-property--convert-property-to-get-method-refactorings"></a>GET yöntemi özelliğine Dönüştür / özellik Get yöntemi yapan yeniden düzenlemeler için Dönüştür

Bu yapan yeniden düzenlemeler geçerlidir:

- C#

## <a name="convert-get-method-to-property"></a>GET yöntemi özelliğine Dönüştür

**Ne:** , bir özellik (ve kümesi yönteminizi isteğe bağlı olarak), bir Get yöntemi dönüştürmenize olanak sağlar ve bunun tam tersi.

**Ne zaman:** herhangi bir mantık içermeyen bir Get yöntemine sahip.

### <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi Get yöntemi adınızı yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **özelliğiyle yöntemi Değiştir** gelen önizleme penceresi açılır.
   - **Fare**
     - Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsünde ' nı seçip **özelliğiyle yöntemi Değiştir** gelen önizleme penceresi açılır.

1. (İsteğe bağlı) Set yöntemi varsa, ayrıca kümesi yönteminizi şu anda seçerek dönüştürebilirsiniz **yerini alma yöntemi ve özellik kümesi yöntemiyle**.

1. Kod önizlemede değişiklikle Mutluluk duyuyoruz tuşuna basın **Enter** veya düzeltmeyi menüsünde tıklatın ve değişiklikler uygulanır.

Örnek:

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

## <a name="convert-property-to-get-method"></a>Özellik Get yöntemine Dönüştür

**Ne:** , bir özellik bir Get yöntemi dönüştürmenize olanak sağlar

**Ne zaman:** birden fazla hemen ayarlama ve alma bir değer içeren bir özelliğe sahiptir

### <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi Get yöntemi adınızı yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **yöntemleriyle özelliğini değiştirmek** gelen önizleme penceresi açılır.
   - **Fare**
     - Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **yöntemleriyle özelliğini değiştirmek** gelen önizleme penceresi açılır.

1. Kod önizlemede değişiklikle Mutluluk duyuyoruz tuşuna basın **Enter** veya düzeltmeyi menüsünde tıklatın ve değişiklikler uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)