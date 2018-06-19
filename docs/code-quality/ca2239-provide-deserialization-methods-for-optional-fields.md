---
title: 'CA2239: İsteğe bağlı alanlar için seri durumdan çıkarma metotları sağlayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2239
- ProvideDeserializationMethodsForOptionalFields
helpviewer_keywords:
- ProvideDeserializationMethodsForOptionalFields
- CA2239
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04d3e40c73a02c43ecfb13eda0abcfabcb0d3ad5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919875"
---
# <a name="ca2239-provide-deserialization-methods-for-optional-fields"></a>CA2239: İsteğe bağlı alanlar için seri durumdan çıkarma metotları sağlayın
|||
|-|-|
|TypeName|ProvideDeserializationMethodsForOptionalFields|
|CheckId|CA2239|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 İle işaretlenen bir alan bir türe sahip <xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName> özniteliği ve türü serinin olay işleme yöntemleri sağlamaz.

## <a name="rule-description"></a>Kural Tanımı
 <xref:System.Runtime.Serialization.OptionalFieldAttribute> Özniteliği serileştirme hiçbir etkisi; özniteliğiyle işaretlenmiş bir alan serileştirilmiş. Ancak, alanın serinin üzerinde dikkate alınmaz ve onun türü ile ilişkili varsayılan değerini korur. Serinin olay işleyicileri serinin işlemi sırasında alanın ayarlanacağı bildirilmelidir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için serinin olay işleme yöntemleri türüne ekleyin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan alan serinin işlemi sırasında dikkate alınması durumunda gizlemek güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek türüyle bir isteğe bağlı alan ve serinin olay işleme yöntemleri gösterir.

 [!code-csharp[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/CSharp/ca2239-provide-deserialization-methods-for-optional-fields_1.cs)]
 [!code-vb[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/VisualBasic/ca2239-provide-deserialization-methods-for-optional-fields_1.vb)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2236: ISerializable türler üzerinde taban sınıf yöntemlerini çağırın](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: ISerializable'ı doğru uygulayın](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Serileştirme yöntemlerini doğru uygulama](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Tüm serileştirilebilir olmayan alanları işaretleyin](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2120: Serileştirme oluşturucularının güvenliğini sağlayın](../code-quality/ca2120-secure-serialization-constructors.md)