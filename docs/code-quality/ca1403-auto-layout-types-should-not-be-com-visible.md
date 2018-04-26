---
title: 'CA1403: Otomatik yerleşim türleri COM görünebilir olmamalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AutoLayoutTypesShouldNotBeComVisible
- CA1403
helpviewer_keywords:
- CA1403
- AutoLayoutTypesShouldNotBeComVisible
ms.assetid: a7007714-f9b4-4730-94e0-67d3dc68991f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 056b1d254b8544f9a1f0abe364bcb40f15235e64
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1403-auto-layout-types-should-not-be-com-visible"></a>CA1403: Otomatik yerleşim türleri COM görünebilir olmamalıdır
|||
|-|-|
|TypeName|AutoLayoutTypesShouldNotBeComVisible|
|CheckId|CA1403|
|Kategori|Microsoft.Interoperability|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bileşen Nesne Modeli (COM) görünür değer türü ile işaretlenmiş <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=fullName> özniteliği kümesine <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=fullName>.

## <a name="rule-description"></a>Kural Tanımı
 <xref:System.Runtime.InteropServices.LayoutKind> Yerleşim türleri, ortak dil çalışma zamanı tarafından yönetilir. Bu tür düzeni belirli bir düzen beklediğiniz COM istemcileri kesintiye uğrar .NET Framework sürümleri arasında değiştirebilirsiniz. Unutmayın <xref:System.Runtime.InteropServices.StructLayoutAttribute> özniteliği belirtilmezse, C#, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], ve C++ Derleyicileri belirtin <xref:System.Runtime.InteropServices.LayoutKind> değer türleri için düzeni.

 Aksi takdirde işaretlenmiş sürece, tüm genel türlere COM görünür; Tüm özel ve genel türleri COM'a görünmez Ancak, hatalı pozitif sonuçları azaltmak için bu kural türünü açıkça belirtilen COM görünürlüğünü gerektirir; içeren derleme ile işaretlenmiş olmalıdır <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> kümesine `false` ve tür ile işaretlenmelidir <xref:System.Runtime.InteropServices.ComVisibleAttribute> kümesine `true`.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için değerini değiştirme <xref:System.Runtime.InteropServices.StructLayoutAttribute> özniteliğini <xref:System.Runtime.InteropServices.LayoutKind> veya <xref:System.Runtime.InteropServices.LayoutKind>, veya türü COM'a görünmez yapma

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kuralını ihlal eden bir tür ile kural karşılayan bir tür gösterir.

 [!code-csharp[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/CSharp/ca1403-auto-layout-types-should-not-be-com-visible_1.cs)]
 [!code-vb[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/VisualBasic/ca1403-auto-layout-types-should-not-be-com-visible_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1408: AutoDual ClassInterfaceType kullanma](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Birlikte çalışma için .NET türlerini niteleme](/dotnet/framework/interop/qualifying-net-types-for-interoperation) [yönetilmeyen kod ile birlikte çalışma](/dotnet/framework/interop/index)