---
title: 'CA2102: CLSCompliant olmayan özel durumları genel işleyiciler içinde yakalayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2102
- CatchNonClsCompliantExceptionsInGeneralHandlers
helpviewer_keywords:
- CA2102
ms.assetid: bf2df68f-d386-4379-ad9e-930a2c2e930d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f32e6fa3d1dfc3c8ee0f116a6e06de49c90ea256
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31916440"
---
# <a name="ca2102-catch-non-clscompliant-exceptions-in-general-handlers"></a>CA2102: CLSCompliant olmayan özel durumları genel işleyiciler içinde yakalayın
|||
|-|-|
|TypeName|CatchNonClsCompliantExceptionsInGeneralHandlers|
|CheckId|CA2102|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Üye ile işaretli olmayan bir bütünleştirilmiş <xref:System.Runtime.CompilerServices.RuntimeCompatibilityAttribute> veya işaretlenmiş `RuntimeCompatibility(WrapNonExceptionThrows = false)` işleyen bir catch bloğunun içeren <xref:System.Exception?displayProperty=fullName> ve bir hemen aşağıdaki genel catch bloğu içermiyor. Bu kural yoksayar [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] derlemeler.

## <a name="rule-description"></a>Kural Tanımı
 İşleme bir catch bloğunun <xref:System.Exception> tüm ortak dil belirtimi (CLS) uyumlu özel durumları yakalar. Ancak, CLS dışı uyumlu özel durumları yakalamaz. Olmayan CLS uyumlu özel durumlar yerel koddan veya Microsoft tarafından oluşturulan yönetilen koddan Ara dili (MSIL) Assembler. Dikkat C# ve [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] derleyicileri CLS dışı oluşturulmasına uyumlu özel durumlara izin verme ve [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] uyumlu CLS olmayan özel durumları yakalamaz. Catch bloğu amacı, tüm özel durumları işlemek için ise, aşağıdaki genel catch bloğu sözdizimini kullanın.

-   C# ' TA: `catch {}`

-   C++: `catch(...) {}` veya `catch(Object^) {}`

 Daha önce verilen izinler içindeki yakalama bloğunun kaldırıldığında bir işlenmemiş CLS olmayan uyumlu özel bir güvenlik sorunu haline gelir. CLS dışı uyumlu özel durum yakalandı olduğundan, CLS dışı uyumlu bir durum oluşturduğunda kötü amaçlı bir yöntem yükseltilmiş izinlerle çalıştırabilirsiniz.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal hedefi tümünü yakalamak için olduğunda düzeltmek için özel durumlar, değiştirin ya da bir genel catch bloğu ekleyin ya da derleme işaretleyin `RuntimeCompatibility(WrapNonExceptionThrows = true)`. İzinleri içindeki yakalama bloğunun kaldırdıysanız, yinelenen genel işlevindeki catch bloğu. Tüm özel durumları işleme için amacını değilse, işleme catch bloğu Değiştir <xref:System.Exception> bir özel durum türlerini işlemesi catch bloklarını ile.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Try bloğunun olmayan CLS ile uyumlu bir özel durum oluşturabilir deyimleri içermiyorsa, bu kural bir uyarıdan gizlemek güvenlidir. Herhangi bir yerel veya yönetilen kod CLS dışı uyumlu özel durum çünkü bu bilgi try bloğunun içindeki tüm kod yollarının yürütülme tüm kod gerektirir. CLS dışı uyumlu ortak dil çalışma zamanı tarafından özel durumlar değil dikkat edin.

## <a name="example"></a>Örnek
 Aşağıdaki örnek olmayan CLS ile uyumlu bir özel durum oluşturur MSIL sınıfı gösterir.

```
.assembly ThrowNonClsCompliantException {}
.class public auto ansi beforefieldinit ThrowsExceptions
{
   .method public hidebysig static void
         ThrowNonClsException() cil managed
   {
      .maxstack  1
      IL_0000:  newobj     instance void [mscorlib]System.Object::.ctor()
      IL_0005:  throw
   }
}
```

## <a name="example"></a>Örnek
 Aşağıdaki örnek kural karşılayan bir genel catch bloğu içeren bir yöntemi gösterir.

 [!code-csharp[FxCop.Security.CatchNonClsCompliantException#1](../code-quality/codesnippet/CSharp/ca2102-catch-non-clscompliant-exceptions-in-general-handlers_1.cs)]

 Önceki örneklerde gibi derleyin.

```
ilasm /dll ThrowNonClsCompliantException.il
csc /r:ThrowNonClsCompliantException.dll CatchNonClsCompliantException.cs
```

## <a name="related-rules"></a>İlgili kuralları
 [CA1031: Genel özel durum türlerini yakalamayın](../code-quality/ca1031-do-not-catch-general-exception-types.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Özel durumlar ve özel durum işleme](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling) [Ilasm.exe (IL derleyici)](/dotnet/framework/tools/ilasm-exe-il-assembler) [dil bağımsızlığı ve dilden bağımsız bileşenler](/dotnet/standard/language-independence-and-language-independent-components)