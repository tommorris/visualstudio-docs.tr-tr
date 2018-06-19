---
title: 'CA1039: Listelerin türü kesin olarak belirlenmiştir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1039
- ListsAreStronglyTyped
helpviewer_keywords:
- CA1039
- ListsAreStronglyTyped
ms.assetid: 5ac366c4-fd87-4d5c-95d5-f755510c8e5c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70bc0065957321894c53726790b73b432dfdea6f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31901046"
---
# <a name="ca1039-lists-are-strongly-typed"></a>CA1039: Listelerin türü kesin olarak belirlenmiştir
|||
|-|-|
|TypeName|ListsAreStronglyTyped|
|CheckId|CA1039|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Genel veya korumalı yazın uygulayan <xref:System.Collections.IList?displayProperty=fullName> ancak bir veya daha fazlasını için kesin türü belirtilmiş bir yöntem sağlamaz:

-   IList.Item

-   IList.Add

-   IList.Contains

-   IList.IndexOf

-   IList.Insert

-   IList.Remove

## <a name="rule-description"></a>Kural Tanımı
 Bu kural gerektirir <xref:System.Collections.IList> kesinlikle sağlamak için uygulamaları, böylece kullanıcılar, cast bağımsız değişken gerekmez. üyeleri yazılan <xref:System.Object?displayProperty=fullName> arabirimi tarafından sağlanan işlevselliği kullanılırken yazın. <xref:System.Collections.IList> Arabirimi dizini tarafından erişilen nesne koleksiyonları tarafından gerçekleştirilir. Bu kural türü uygulayan varsayar <xref:System.Collections.IList> bu daha güçlü bir türün örneklerinin bir koleksiyonunu yönetmenizi <xref:System.Object>.

 <xref:System.Collections.IList> uygulayan <xref:System.Collections.ICollection?displayProperty=fullName> ve <xref:System.Collections.IEnumerable?displayProperty=fullName> arabirimleri. Öğesini uygularsanız <xref:System.Collections.IList>, gerekli kesin türü belirtilmiş üyeler için sağlamalısınız <xref:System.Collections.ICollection>. Koleksiyonundaki nesneleri genişletirseniz <xref:System.ValueType?displayProperty=fullName>, kesin türü belirtilmiş bir üye için sağlamalısınız <xref:System.Collections.IEnumerable.GetEnumerator%2A> performans düşüşünü önlemek için tarafından kutulama neden; koleksiyonu nesnelerin bir başvuru türü olduğunda bu zorunlu değildir.

 Bu kurala uygun için arabirim üyelerini açıkça adları gibi InterfaceName.InterfaceMemberName, formunda kullanarak uygulama <xref:System.Collections.IList.Add%2A>. Açık arabirim üyeleri arabirimi tarafından bildirilen veri türlerini kullanın. Kesin türü belirtilmiş üyeler arabirim üye adı gibi kullanarak uygulama `Add`. Genel olarak kesin türü belirtilmiş üyeleri bildirme ve parametreleri bildirme ve dönüş değerleri koleksiyon tarafından yönetilen güçlü türünde olmalıdır. Güçlü türleri gibi zayıf türlerini değiştirecek <xref:System.Object> ve <xref:System.Array> arabirimi tarafından bildirilmedi.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için açıkça uygulama <xref:System.Collections.IList> üyeleri ve daha önce belirtilen üyeler için kesin türü belirtilmiş alternatifleri sağlayın. Doğru uygulayan kod için <xref:System.Collections.IList> arabirim ve gerekli sağlar kesin türü belirtilmiş üyeler, aşağıdaki örnekte bkz.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Yeni nesne tabanlı bir koleksiyon, burada yeni koleksiyon genişletmek türleri güçlü tür belirlemek bağlantılı bir liste gibi uygularken bu kural bir uyarıdan engelleyin. Bu tür, bu kurala uygun ve kesin türü belirtilmiş üyeler kullanıma sunar.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, türü `YourType` genişletir <xref:System.Collections.CollectionBase?displayProperty=fullName>, tüm kesin türü belirtilmiş koleksiyonları gerektiği gibi. Unutmayın <xref:System.Collections.CollectionBase> açık uygulamasını sağlar <xref:System.Collections.IList> , arabirimi. Bu nedenle, yalnızca kesin türü belirtilmiş üyeler için sağlamanız gereken <xref:System.Collections.IList> ve <xref:System.Collections.ICollection>.

 [!code-csharp[FxCop.Design.IListStrongTypes#1](../code-quality/codesnippet/CSharp/ca1039-lists-are-strongly-typed_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1035: ICollection uygulamalarında türü kesin olarak belirtilmiş üyeler olmalıdır](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)

 [CA1038: Numaralandırıcıların türü kesin olarak belirtilmelidir](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Collections.CollectionBase?displayProperty=fullName> <xref:System.Collections.ICollection?displayProperty=fullName> <xref:System.Collections.IEnumerable?displayProperty=fullName> <xref:System.Collections.IList?displayProperty=fullName> <xref:System.Object?displayProperty=fullName>