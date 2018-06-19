---
title: 'CA1406: Visual Basic 6 istemcileri için Int64 bağımsız değişkenlerinden kaçının'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e4455373338cda463623c75ff099a1c706f589dc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31897639"
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406: Visual Basic 6 istemcileri için Int64 bağımsız değişkenlerinden kaçının
|||
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|Kategori|Microsoft.Interoperability|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Özellikle Bileşen Nesne Modeli (COM) olarak görünür olarak işaretlenmiş bir tür üyesi o alır bildiren bir <xref:System.Int64?displayProperty=fullName> bağımsız değişkeni.

## <a name="rule-description"></a>Kural Tanımı
 Visual Basic 6 COM istemcilerinde 64 bit tamsayı erişemiyor.

 Varsayılan olarak, COM görünür şunlardır: derlemeleri, genel türleri, genel türlerde ortak örnek üyeleri ve ortak değer türleri tüm üyeleri. Ancak, hatalı pozitif sonuçları azaltmak için bu kural türünü açıkça belirtilen COM görünürlüğünü gerektirir; içeren derleme ile işaretlenmiş olmalıdır <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> kümesine `false` ve tür ile işaretlenmelidir <xref:System.Runtime.InteropServices.ComVisibleAttribute> kümesine `true`.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural için bir parametre değeri her zaman ifade edilir 32-bit integral ihlal düzeltmek için parametre türü değiştirme <xref:System.Int32?displayProperty=fullName>. Parametresinin değeri 32-bit integral ifade edilebilir daha büyük olabilir, parametre türü değiştirme <xref:System.Decimal?displayProperty=fullName>. Unutmayın her ikisi de <xref:System.Single?displayProperty=fullName> ve <xref:System.Double?displayProperty=fullName> en üst aralıklarını duyarlık kaybına <xref:System.Int64> veri türü. COM görünür olmasını üye düşünülmemiştir, kendisiyle işaretlemek <xref:System.Runtime.InteropServices.ComVisibleAttribute> kümesine `false`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Visual Basic 6 COM istemcileri türü erişmeyecek belirli ise bir uyarı bu kuraldan gizlemek güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.

 [!code-csharp[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/CSharp/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.cs)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../code-quality/codesnippet/VisualBasic/ca1406-avoid-int64-arguments-for-visual-basic-6-clients_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407: COM görünebilir türler içinde statik üyelerden kaçının](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: Derlemeleri ComVisibleAttribute ile işaretleyin](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Yönetilmeyen kod ile birlikte](/dotnet/framework/interop/index) [Long veri türü](/dotnet/visual-basic/language-reference/data-types/long-data-type)