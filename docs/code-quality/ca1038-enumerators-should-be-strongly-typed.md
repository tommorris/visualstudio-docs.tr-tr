---
title: 'CA1038: Numaralandırmalar kesinlikle yazılmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
helpviewer_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
ms.assetid: 8919f526-d487-42a4-87dc-2b2ee25260c4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 01b194864f559ff095d8727ff11a4906377aa482
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1038-enumerators-should-be-strongly-typed"></a>CA1038: Numaralandırıcıların türü kesin olarak belirtilmelidir
|||  
|-|-|  
|TypeName|EnumeratorsShouldBeStronglyTyped|  
|CheckId|CA1038|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir genel ya da korumalı türü uygulayan <xref:System.Collections.IEnumerator?displayProperty=fullName> kesin türü belirtilmiş bir sürümünü sağlamamasına rağmen <xref:System.Collections.IEnumerator.Current%2A?displayProperty=fullName> özelliği. Aşağıdaki türlerden türetilmiş türler bu kuraldan muafiyet şunlardır:  
  
-   <xref:System.Collections.CollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>  
  
-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural gerektirir <xref:System.Collections.IEnumerator> de kesin türü belirtilmiş bir sürümünü sağlayın uygulamaları <xref:System.Collections.IEnumerator.Current%2A> özelliği böylece kullanıcı arabirimi tarafından sağlanan işlevselliği kullanılırken dönüş değeri için güçlü tür cast gerekli değildir. Bu kural türü uygulayan varsayar <xref:System.Collections.IEnumerator> daha güçlü bir türün örneklerinin bir koleksiyonunu içerir <xref:System.Object>.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için arabirim özelliği açıkça uygulama (olarak bildirme `IEnumerator.Current`). Genel kesin türü belirtilmiş bir sürümü olarak bildirilen özelliğinin eklemek `Current`, ve kesin türü belirtilmiş bir nesnesi döndürür.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bir ikili ağacı gibi bir nesne tabanlı koleksiyonu ile kullanmak için bir nesne tabanlı Numaralandırıcı uygularken bu kural bir uyarıdan engelleyin. Yeni koleksiyon genişletmek türleri kesin türü belirtilmiş Numaralandırıcı tanımlayın ve türü kesin belirlenmiş bir özellik kullanıma sunar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kesin türü belirtilmiş uygulamak için doğru bir şekilde gösterir <xref:System.Collections.IEnumerator> türü.  
  
 [!code-csharp[FxCop.Design.IEnumeratorStrongTypes#1](../code-quality/codesnippet/CSharp/ca1038-enumerators-should-be-strongly-typed_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1035: ICollection uygulamalarında türü kesin olarak belirtilmiş üyeler olmalıdır](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)  
  
 [CA1039: Listelerin türü kesin olarak belirlenmiştir](../code-quality/ca1039-lists-are-strongly-typed.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Collections.IEnumerator?displayProperty=fullName>   
 <xref:System.Collections.CollectionBase?displayProperty=fullName>   
 <xref:System.Collections.DictionaryBase?displayProperty=fullName>   
 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>