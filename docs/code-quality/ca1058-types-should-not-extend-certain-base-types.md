---
title: "CA1058: Türler belli temel türleri genişletmemelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c042c854e535f764fe4e0eac01a0e66aa5b49f20
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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