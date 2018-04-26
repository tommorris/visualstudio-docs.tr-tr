---
title: 'CA1402: COM görünebilir arabirimler içinde aşırı yüklemelerden kaçının'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
helpviewer_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec1e0f13d3d26973dc2dc46c6a41a2dc962c91bb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1402-avoid-overloads-in-com-visible-interfaces"></a>CA1402: COM görünebilir arabirimler içinde aşırı yüklemelerden kaçının
|||
|-|-|
|TypeName|AvoidOverloadsInComVisibleInterfaces|
|CheckId|CA1402|
|Kategori|Microsoft.Interoperability|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir Bileşen Nesne Modeli (görünür arabirimi bildirir COM) aşırı yüklenmiş yöntemler.

## <a name="rule-description"></a>Kural Tanımı
 Aşırı yüklenmiş yöntemler COM istemcilerine maruz kaldığında, sadece ilk yöntem aşırı yüklemesi adını korur. Sonraki aşırı bir alt çizgi karakteri '_' ve aşırı bildirimi {karşılık gelen bir tamsayı adına ekleyerek benzersiz olarak adlandırılır. Örneğin, aşağıdaki yöntemlerden göz önünde bulundurun.

```
void SomeMethod(int valueOne);
void SomeMethod(int valueOne, int valueTwo, int valueThree);
void SomeMethod(int valueOne, int valueTwo);
```

 Bu yöntemler COM istemcileri aşağıdaki olarak sunulur.

```
void SomeMethod(int valueOne);
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);
void SomeMethod_3(int valueOne, int valueTwo);
```

 Visual Basic 6 COM istemcileri adı alt çizgi kullanarak arabirim yöntemleri uygulayamaz.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için aşırı yüklenmiş yöntemler adları benzersiz şekilde yeniden adlandırın. Alternatif olarak, arabirim COM erişilebilirlik değiştirerek görünmez yapma `internal` (`Friend` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) veya uygulayarak <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> özniteliği kümesine `false`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kuralını ihlal eden bir arabirim ve kural karşılayan bir arabirimi gösterir.

 [!code-vb[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/VisualBasic/ca1402-avoid-overloads-in-com-visible-interfaces_1.vb)]
 [!code-csharp[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/CSharp/ca1402-avoid-overloads-in-com-visible-interfaces_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407: COM görünebilir türler içinde statik üyelerden kaçının](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: Derlemeleri ComVisibleAttribute ile işaretleyin](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Yönetilmeyen kod ile birlikte](/dotnet/framework/interop/index) [Long veri türü](/dotnet/visual-basic/language-reference/data-types/long-data-type)