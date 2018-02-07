---
title: "GET yöntemi özelliğine dönüştürmek ve C# Get yöntemi bir özellik Dönüştür | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
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
ms.openlocfilehash: a23af31c5099908ed0b6fed07404216a57975f75
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="convert-get-method-to-property--convert-property-to-get-method"></a>GET yöntemi özelliğine Dönüştür / Get yöntemine özelliği Dönüştür

## <a name="convert-get-method-to-property"></a>GET yöntemi özelliğine Dönüştür

**Ne:** , bir özellik (ve kümesi yönteminizi isteğe bağlı olarak), bir Get yöntemi dönüştürmenize olanak sağlar ve bunun tam tersi.

**Ne zaman:** herhangi bir mantık içermeyen bir Get yöntemine sahip.

**Nasıl:**

1. İmlecinizi Get yöntemi adınızı yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **özelliğiyle yöntemi Değiştir** gelen önizleme penceresi açılır. Set yöntemi varsa, ayrıca kümesi yönteminizi şu anda seçerek dönüştürebilirsiniz **yerini alma yöntemi ve özellik kümesi yöntemiyle**.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **özelliğiyle yöntemi Değiştir** gelen önizleme penceresi açılır. Set yöntemi varsa, ayrıca kümesi yönteminizi şu anda seçerek dönüştürebilirsiniz **yerini alma yöntemi ve özellik kümesi yöntemiyle**.

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

**Nasıl:**

1. İmlecinizi Get yöntemi adınızı yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **yöntemleriyle özelliğini değiştirmek** gelen önizleme penceresi açılır.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **yöntemleriyle özelliğini değiştirmek** gelen önizleme penceresi açılır.

1. Kod önizlemede değişiklikle Mutluluk duyuyoruz tuşuna basın **Enter** veya düzeltmeyi menüsünde tıklatın ve değişiklikler uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)