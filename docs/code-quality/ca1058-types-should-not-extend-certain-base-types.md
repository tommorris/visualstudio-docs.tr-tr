---
title: 'CA1058: Türler belli temel türleri genişletmemelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e3c1e4635a654cac608985766884ddb66e353d03
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31898282"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: Türler belli temel türleri genişletmemelidir
|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Dışarıdan görünen tür belirli temel türleri genişletir. Şu anda, bu kural, aşağıdaki türlerden türetilen türler raporları:

-   <xref:System.ApplicationException?displayProperty=fullName>

-   <xref:System.Xml.XmlDocument?displayProperty=fullName>

-   <xref:System.Collections.CollectionBase?displayProperty=fullName>

-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>

-   <xref:System.Collections.Queue?displayProperty=fullName>

-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

-   <xref:System.Collections.SortedList?displayProperty=fullName>

-   <xref:System.Collections.Stack?displayProperty=fullName>

## <a name="rule-description"></a>Kural Tanımı
 İçin [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürüm 1, önerilir yeni özel durumlar çıkarmaya <xref:System.ApplicationException>. Öneri değişti ve yeni özel durumlar türetilen <xref:System.Exception?displayProperty=fullName> veya alt sınıfları <xref:System> ad alanı.

 Öğesinin bir alt oluşturmayın <xref:System.Xml.XmlDocument> , temel alınan bir nesne modeli veya veri kaynağı, bir XML görünümünü oluşturmak istiyorsanız.

### <a name="non-generic-collections"></a>Genel olmayan koleksiyonları
 Kullanın ve/veya genel koleksiyonlar mümkün olduğunca genişletir. Daha önce gönderilen sürece genel olmayan koleksiyonları, kodunuzda genişletmez.

 **Yanlış kullanım örnekleri**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

 **Doğru kullanım örnekleri**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için farklı bir taban türü ya da bir genel koleksiyon türü türetilir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural ihlalleri için uyarıdan hakkında engelleme <xref:System.ApplicationException>. Bu kural ihlalleri için uyarıdan hakkında gizlemek güvenlidir <xref:System.Xml.XmlDocument>. Kodu önceden yayımlanan, genel olmayan koleksiyonu hakkında bir uyarı gizlemek güvenlidir.