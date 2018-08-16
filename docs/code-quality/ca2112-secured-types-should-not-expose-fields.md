---
title: 'CA2112: Güvenli türler alanları açığa çıkarmamalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9784ec48193ae580d7ed41cb745f0befb1f1fde9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915254"
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: Güvenli türler alanları açığa çıkarmamalıdır
|||
|-|-|
|TypeName|SecuredTypesShouldNotExposeFields|
|CheckId|CA2112|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir genel ya da korumalı türü genel alanlar içeriyor ve tarafından güvenliği sağlanan bir [bağlantı talepleri](/dotnet/framework/misc/link-demands).

## <a name="rule-description"></a>Kural Tanımı
 Bağlantı talebi tarafından güvenli türde bir örnek kod erişimi varsa, kod türün alanlarına erişmek için bağlantı talebine sahip değildir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için alanları özel yapmak ve ortak özellik veya alan verisi döndüren yöntemler ekleyin. LinkDemand güvenlik denetimlerini türlerinde tür özellikleri ve yöntemleri erişimi koruyun. Bununla birlikte, kod erişim güvenliği alanlar için geçerli değildir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Güvenlik sorunları hem iyi tasarım, genel alanlar özel yaparak ihlalleri sorununu çözer. Alan güvenli kalması gereken bilgileri barındırmıyorsa bu kural bir uyarıdan gizleyebilirsiniz ve alan içeriğine güvenmeyin.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte bir kitaplık türü oluşur (`SecuredTypeWithFields`) güvenli alanlarla bir türü (`Distributor`) kitaplığı türünün örneklerini oluşturabilir ve türleri hatalı geçişleri örneklerine bunları oluşturmak için izne sahip değil ve uygulama kodu türü korur izni yok olsa bile bir örneğinin alanları okuyabilir.

 Aşağıdaki kitaplık kodu kuralını ihlal ediyor.

 [!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]

## <a name="example"></a>Örnek
 Uygulamanın bir örneği güvenli türü korur bağlantı isteği nedeniyle oluşturulamıyor. Aşağıdaki sınıf güvenli türünün bir örneği elde etmek uygulama sağlar.

 [!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki uygulama güvenli türünün yöntemleri erişim izni alanlarını kodu nasıl erişebilirsiniz gösterilmektedir.

 [!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]

 Bu örnek şu çıkışı üretir.

 **SecuredTypeWithFields örneği oluşturma. ** 
 **Güvenli tür alanları: 22, 33**
**güvenli tür alanı değiştirme... ** 
 **Önbelleğe nesne alanları: 99, 33**
## <a name="related-rules"></a>İlgili kuralları
 [CA1051: Görünür örnek alanlarını bildirmeyin](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands) [veri ve modelleme](/dotnet/framework/data/index)