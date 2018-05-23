---
title: 'CA2227: Koleksiyon özellikleri salt okunur olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: aa1d8644049f78eccfda7402360bdbc930b61601
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Koleksiyon özellikleri salt okunur olmalıdır

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep

Uygulayan türünde bir harici olarak görünür, yazılabilir özelliği <xref:System.Collections.ICollection?displayProperty=fullName>. Bu kural, dizileri, dizin oluşturucular (Özellikleri 'Öğesi' adıyla) ve izin kümeleri yoksayar.

## <a name="rule-description"></a>Kural açıklaması

Koleksiyon ile tamamen farklı bir koleksiyon değiştirmek bir kullanıcı bir yazılabilir koleksiyon özelliği sağlar. Salt okunur bir özellik değiştirilmekte olan koleksiyondan durdurur, ancak hala ayarlanacak tek tek üyeleri verir. Koleksiyon değiştirme hedefi ise, tercih edilen tasarım deseni tüm öğeleri koleksiyondan kaldırmak için bir yöntem ve koleksiyon yeniden doldurmak için bir yöntem eklemektir. Bkz: <xref:System.Collections.ArrayList.Clear%2A> ve <xref:System.Collections.ArrayList.AddRange%2A> yöntemlerinin <xref:System.Collections.ArrayList?displayProperty=fullName> sınıfı örneği için bu deseni.

İkili ve XML serileştirme koleksiyonlar salt okunur özelliklerini destekler. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Sınıfına sahip uygulama türleri için belirli gereksinimler <xref:System.Collections.ICollection> ve <xref:System.Collections.IEnumerable?displayProperty=fullName> seri hale getirilebilir için.

## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl

Bu kural ihlal düzeltmek için özelliği salt okunur yapın. Tasarım gerektiriyorsa, temizlemek ve koleksiyon dışındaki yöntemleri ekleyin.

## <a name="when-to-suppress-warnings"></a>Ne zaman uyarıları bastırma

Bu kuraldan uyarıları bastırma değil.

## <a name="example"></a>Örnek

Aşağıdaki örnekte bir yazılabilir koleksiyon özelliği türüyle gösterir ve koleksiyon nasıl doğrudan değiştirilebilir gösterir. Ayrıca, tercih edilen şekilde salt okunur koleksiyonun özelliği kullanılarak değiştirme `Clear` ve `AddRange` yöntemleri gösterilir.

[!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
[!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
[!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]

## <a name="related-rules"></a>İlgili kuralları

[CA1819: Özellikler diziler döndürmemelidir](../code-quality/ca1819-properties-should-not-return-arrays.md)