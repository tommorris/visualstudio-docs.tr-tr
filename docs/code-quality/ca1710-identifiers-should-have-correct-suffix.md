---
title: "CA1710: Tanımlayıcılar doğru olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1710
- IdentifiersShouldHaveCorrectSuffix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectSuffix
- CA1710
ms.assetid: 2b8e6dce-b4e8-4a66-ba9a-6b79be5bfe8c
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d1593800a2cde8ff0aa1bbecd169f5f3ebd601cb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1710-identifiers-should-have-correct-suffix"></a>CA1710: Tanımlayıcıların sonekleri doğru olmalıdır
|||  
|-|-|  
|TypeName|IdentifiersShouldHaveCorrectSuffix|  
|CheckId|CA1710|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Tanımlayıcı doğru son ekine sahip değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kurala göre belli temel türleri genişletmek veya belirli arabirimlerine veya bu türlerinden türetilmiş türler uygulayan türü adlarının temel türü veya arabirim ile ilişkili bir son eke sahip.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.  
  
 Taban türleri ve sonekleri ilişkilendirdiğiniz arabirimleri aşağıdaki tabloda listelenmektedir.  
  
|Temel türü/arabirim|Son eki|  
|--------------------------|------------|  
|<xref:System.Attribute?displayProperty=fullName>|Öznitelik|  
|<xref:System.EventArgs?displayProperty=fullName>|EventArgs|  
|<xref:System.Exception?displayProperty=fullName>|Özel Durum|  
|<xref:System.Collections.ICollection?displayProperty=fullName>|Koleksiyonu|  
|<xref:System.Collections.IDictionary?displayProperty=fullName>|Sözlük|  
|<xref:System.Collections.IEnumerable?displayProperty=fullName>|Koleksiyonu|  
|<xref:System.Collections.Queue?displayProperty=fullName>|Koleksiyon ya da sırası|  
|<xref:System.Collections.Stack?displayProperty=fullName>|Koleksiyon veya yığını|  
|<xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>|Koleksiyonu|  
|<xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|Sözlük|  
|<xref:System.Data.DataSet?displayProperty=fullName>|DataSet|  
|<xref:System.Data.DataTable?displayProperty=fullName>|Koleksiyon ya da DataTable|  
|<xref:System.IO.Stream?displayProperty=fullName>|Akış|  
|<xref:System.Security.IPermission?displayProperty=fullName>|İzin|  
|<xref:System.Security.Policy.IMembershipCondition?displayProperty=fullName>|Koşul|  
|Bir olay işleyici temsilcisi.|EventHandler|  
  
 Türleri uygulayan <xref:System.Collections.ICollection> ve sözlük, yığın veya sıra, izin verilen türde hedeflenen kullanım hakkında anlamlı bilgiler sağlayan adları gibi veri yapısı, genelleştirilmiş bir tür.  
  
 Türleri uygulayan <xref:System.Collections.ICollection> ve belirli öğeleri koleksiyonu 'Koleksiyon' word ile biten adlara sahip olması. Örneğin, bir koleksiyonu <xref:System.Collections.Queue> nesneleri 'QueueCollection' adına sahip olabilir. Koleksiyonun üyeleri kullanarak numaralandırılabilecek 'Koleksiyon' soneki güveninin `foreach` (`For Each` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ifadesi.  
  
 Türleri uygulayan <xref:System.Collections.IDictionary> türü de uygulayan olsa bile, word 'Sözlüğü' ile biten adlara sahip <xref:System.Collections.IEnumerable> veya <xref:System.Collections.ICollection>. Aşağıdaki iki numaralandırma desenleri arasında ayrım yapmak kullanıcılar 'Koleksiyon' ve 'Sözlüğü' soneki adlandırma kuralları etkinleştirin.  
  
 Bu numaralandırma düzeni 'Koleksiyon' soneki türleriyle izleyin.  
  
```  
foreach(SomeType x in SomeCollection) { }  
```  
  
 Bu numaralandırma düzeni 'Sözlüğü' soneki türleriyle izleyin.  
  
```  
foreach(SomeType x in SomeDictionary.Values) { }  
```  
  
 A <xref:System.Data.DataSet> nesne oluşan bir koleksiyonu <xref:System.Data.DataTable> koleksiyonları oluşan nesneleri <xref:System.Data.DataColumn?displayProperty=fullName> ve <xref:System.Data.DataRow?displayProperty=fullName> nesneleri, diğerlerinin yanı sıra. Bu koleksiyonları uygulamak <xref:System.Collections.ICollection> temel aracılığıyla <xref:System.Data.InternalDataCollectionBase?displayProperty=fullName> sınıfı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Böylece doğru terimiyle sonekine türü yeniden adlandırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Tür, genişletilmiş veya çeşitli öğeleri rasgele bir dizi tutacak bir genelleştirilmiş veri yapısı ise 'Koleksiyon' soneki kullanmak için bir uyarı gizlemek güvenlidir. Bu durumda, uygulama, performans veya diğer özelliklerini veri yapısı hakkında yararlı bilgiler sağlayan bir ad (örneğin, BinaryTree) mantıklı olabilir. Türü kullanarak numaralandırılabilir soneki belirten çünkü bu kuraldan bir uyarı türü (örneğin, bir StringCollection) belirli bir türde bir koleksiyonu temsil ettiği durumlarda engelleme bir `foreach` deyimi.  
  
 Diğer sonekleri için bu kural bir uyarıdan engelleme. Sonek hedeflenen kullanım türü adından korumalı olmasını sağlar.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1711: Tanımlayıcıların sonekleri yanlış olmamalıdır](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öznitelikleri](/dotnet/standard/design-guidelines/attributes)   
 [Olaylar oluşturma ve işleme](/dotnet/standard/events/index)  