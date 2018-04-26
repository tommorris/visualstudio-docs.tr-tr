---
title: 'CA1035: ICollection uygulamalarında türü kesin olarak belirtilmiş üyeler olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ICollectionImplementationsHaveStronglyTypedMembers
- CA1035
helpviewer_keywords:
- CA1035
- ICollectionImplementationsHaveStronglyTypedMembers
ms.assetid: ad404eb5-cf6a-44b7-b78a-8ebfb654bc7f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f9cda0790128bb279d30a15f75080c375ec68aa1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1035-icollection-implementations-have-strongly-typed-members"></a>CA1035: ICollection uygulamalarında türü kesin olarak belirtilmiş üyeler olmalıdır
|||
|-|-|
|TypeName|ICollectionImplementationsHaveStronglyTypedMembers|
|CheckId|CA1035|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir genel ya da korumalı türü uygulayan <xref:System.Collections.ICollection?displayProperty=fullName> için kesin türü belirtilmiş bir yöntem sağlamaz, ancak <xref:System.Collections.ICollection.CopyTo%2A?displayProperty=fullName>. Kesin türü belirtilmiş sürümünü <xref:System.Collections.ICollection.CopyTo%2A> iki parametre kabul etmeniz gerekir ve olamaz bir <xref:System.Array?displayProperty=fullName> veya bir dizi <xref:System.Object?displayProperty=fullName> birinci parametre olarak.

## <a name="rule-description"></a>Kural Tanımı
 Bu kural gerektirir <xref:System.Collections.ICollection> kesinlikle sağlamak için uygulamaları, böylece kullanıcılar, cast bağımsız değişken gerekmez. üyeleri yazılan <xref:System.Object> arabirimi tarafından sağlanan işlevselliği kullanılırken yazın. Bu kural türü uygulayan varsayar <xref:System.Collections.ICollection> yoksa, bu nedenle daha güçlü bir türün örneklerinin bir koleksiyonunu yönetmek için <xref:System.Object>.

 <xref:System.Collections.ICollection> uygulayan <xref:System.Collections.IEnumerable?displayProperty=fullName> arabirimi. Koleksiyonundaki nesneleri genişletirseniz <xref:System.ValueType?displayProperty=fullName>, kesin türü belirtilmiş bir üye için sağlamalısınız <xref:System.Collections.IEnumerable.GetEnumerator%2A> tarafından kutulama neden performans düşüklüğü önlemek için. Koleksiyon nesnelerin bir başvuru türü olduğunda bu zorunlu değildir.

 Arabirim üyesini kesin türü belirtilmiş sürümünü uygulamak için arabirim üyelerini açıkça biçiminde adları kullanarak uygulama `InterfaceName.InterfaceMemberName`, gibi <xref:System.Collections.ICollection.CopyTo%2A>. Açık arabirim üyeleri arabirimi tarafından bildirilen veri türlerini kullanın. Kesin türü belirtilmiş üyeler arabirim üye adı gibi kullanarak uygulama <xref:System.Collections.ICollection.CopyTo%2A>. Genel olarak kesin türü belirtilmiş üyeleri bildirme ve parametreleri bildirme ve dönüş değerleri koleksiyon tarafından yönetilen güçlü türünde olmalıdır. Güçlü türleri gibi zayıf türlerini değiştirecek <xref:System.Object> ve <xref:System.Array> arabirimi tarafından bildirilmedi.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için arabirim üyesini açıkça uygulama (olarak bildirme <xref:System.Collections.ICollection.CopyTo%2A>). Olarak bildirilen ortak türü kesin belirlenmiş üye ekleme `CopyTo`, ve kesin türü belirtilmiş bir dizi ilk parametre olarak alın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Yeni nesne tabanlı bir koleksiyon, burada yeni koleksiyon genişletmek türleri güçlü tür belirlemek bir ikili ağacı gibi uygularsanız, bu kural bir uyarıdan engelleyin. Bu tür, bu kurala uygun ve kesin türü belirtilmiş üyeler kullanıma sunar.

## <a name="example"></a>Örnek
 Doğru bir şekilde uygulamak için aşağıdaki örnekte gösterilmiştir <xref:System.Collections.ICollection>.

 [!code-csharp[FxCop.Design.ICollectionStrongTypes#1](../code-quality/codesnippet/CSharp/ca1035-icollection-implementations-have-strongly-typed-members_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1038: Numaralandırıcıların türü kesin olarak belirtilmelidir](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

 [CA1039: Listelerin türü kesin olarak belirlenmiştir](../code-quality/ca1039-lists-are-strongly-typed.md)

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Array?displayProperty=fullName> <xref:System.Collections.IEnumerable?displayProperty=fullName> <xref:System.Collections.ICollection?displayProperty=fullName> <xref:System.Object?displayProperty=fullName>