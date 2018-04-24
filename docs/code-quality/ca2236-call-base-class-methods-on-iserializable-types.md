---
title: 'CA2236: ISerializable türler üzerinde taban sınıf yöntemlerini çağırın'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b7bc90dfd0cf786bbd4e2494a6c65e2c19ff4eb6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236: ISerializable türler üzerinde taban sınıf yöntemlerini çağırın
|||
|-|-|
|TypeName|CallBaseClassMethodsOnISerializableTypes|
|CheckId|CA2236|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Uygulayan türünden bir türü <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi ve aşağıdaki koşullardan biri doğruysa:

-   Türü seri hale getirme oluşturucusu, diğer bir deyişle, bir oluşturucu uygulayan <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>, <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> parametre imzası, ancak temel türü seri hale getirme oluşturucusunun çağırmaz.

-   Tür uygular <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> yöntemi ancak çağrılmayan <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> temel türün yöntemi.

## <a name="rule-description"></a>Kural Tanımı
 İçinde özel seri hale getirme işlemi, bir tür uygulayan <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> alanları ve seri durumdan alanlar için seri hale getirme Oluşturucusu serileştirmek için yöntem. Uygulayan türünden türü varsa <xref:System.Runtime.Serialization.ISerializable> arabirim, temel türü <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> yöntemi ve Serileştirme Oluşturucusu çağrılabilir seri/Kaldır-serialize için temel türünde alanlar. Aksi takdirde türü değil sıralanabilir ve doğru json'dan seri durumdan çıkarılmış. Türetilmiş bir tür yeni alanları eklemez, türü uygulamak değil gerekir <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> yöntemi veya seri hale getirme Oluşturucusu veya temel türü eşdeğerleri çağırın.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için temel türü çağrı <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> karşılık gelen gelen yöntemi veya seri hale getirme Oluşturucusu türetilen tür yöntemi veya Oluşturucusu.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, kural seri hale getirme Oluşturucu çağırarak karşılayan türetilmiş bir tür gösterir ve <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> yöntemi temel sınıf.

 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
 [!code-csharp[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA2240: ISerializable'ı doğru uygulayın](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Serileştirme yöntemlerini doğru uygulama](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Tüm serileştirilebilir olmayan alanları işaretleyin](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: İsteğe bağlı alanlar için seri durumdan çıkarma metotları sağlayın](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Serileştirme oluşturucularının güvenliğini sağlayın](../code-quality/ca2120-secure-serialization-constructors.md)