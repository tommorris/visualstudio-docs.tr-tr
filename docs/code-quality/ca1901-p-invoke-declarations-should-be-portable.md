---
title: 'CA1901: P-Invoke bildirimleri taşınabilir olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
helpviewer_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed9821d9b80309311a6fd108c4a29f52b2e882bf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901: P/Invoke bildirimleri taşınabilir olmalıdır
|||
|-|-|
|TypeName|PInvokeDeclarationsShouldBePortable|
|CheckId|CA1901|
|Kategori|Microsoft.Portability|
|Yeni Değişiklik|P/Invoke derlemenin dışından görünür durumdaysa - kesiliyor. P/Invoke derlemenin dışından görünür değilse olmayan sonu -.|

## <a name="cause"></a>Sebep
 Bu kural her parametre boyutunu ve P/Invoke dönüş değerini değerlendirir ve 32-bit ve 64 bit platformlarda yönetilmeyen kod için sıralanmış zaman boyutlarına doğru olduğunu doğrular. Bu kural en yaygın ihlalinden, bir platforma bağımlı, işaretçi ölçekli değişkeni gerekli olduğu bir sabit boyutlu tamsayı geçirmektir.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural aşağıdaki senaryolardan biri ihlal oluşur:

-   Olarak yazılmalıdır, parametre ve dönüş değeri bir sabit boyutlu tamsayı olarak yazılan bir `IntPtr`.

-   Dönüş değeri veya parametre olarak yazılan bir `IntPtr` zaman yazdığınız sabit boyutlu tamsayı olarak.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Kullanarak bu ihlali düzeltebilirsiniz `IntPtr` veya `UIntPtr` yerine tanıtıcıları temsil etmek için `Int32` veya `UInt32`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu uyarı engelleme.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural ihlal gösterir.

```csharp
internal class NativeMethods
{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, IntPtr nIconIndex);
}
```

 Bu örnekte, `nIconIndex` parametre olarak bildirilen bir `IntPtr`, 32-bit platformu ve 8 bayt bir 64-bit platformda geniş geniş 4 bayt olduğu. Aşağıdaki yönetilmeyen bildiriminde görebilirsiniz `nIconIndex` tüm platformlarda 4-bayt işaretsiz tamsayı değil.

```csharp
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,
    UINT nIconIndex);
```

## <a name="example"></a>Örnek
 İhlali düzeltmek için bildirimi aşağıdaki gibi değiştirin:

```csharp
internal class NativeMethods{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)] 
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, uint nIconIndex);
}
```

## <a name="see-also"></a>Ayrıca Bkz.
 [Taşınabilirlik Uyarıları](../code-quality/portability-warnings.md)