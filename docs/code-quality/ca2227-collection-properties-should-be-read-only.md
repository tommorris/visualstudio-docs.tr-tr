---
title: "CA2227: Koleksiyon Özellikleri salt okunur | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8a1835c5e600320ec8b36102e4749d92cf21eae1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Koleksiyon özellikleri salt okunur olmalıdır
|||  
|-|-|  
|TypeName|CollectionPropertiesShouldBeReadOnly|  
|CheckId|CA2227|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür bir yazılabilir özellik uygulayan bir tür olması <xref:System.Collections.ICollection?displayProperty=fullName>. Diziler, dizin oluşturucular (Özellikleri 'Öğesi' adıyla) ve izin kümeleri kural tarafından göz ardı edilir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Koleksiyon ile tamamen farklı bir koleksiyon değiştirmek bir kullanıcı bir yazılabilir koleksiyon özelliği sağlar. Salt okunur özelliği değiştirilmesini durdurur ancak yine de tekil üyelerin ayarlamasına izin verir. Koleksiyon değiştirme hedefi ise, tercih edilen tasarım deseni koleksiyondaki tüm öğeleri kaldırmak için bir yöntem ve koleksiyon yeniden doldurmak için bir yöntem eklemektir. Bkz: <xref:System.Collections.ArrayList.Clear%2A> ve <xref:System.Collections.ArrayList.AddRange%2A> yöntemlerinin <xref:System.Collections.ArrayList?displayProperty=fullName> sınıfı örneği için bu deseni.  
  
 İkili ve XML serileştirme koleksiyonlar salt okunur özelliklerini destekler. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Sınıfına sahip uygulama türleri için belirli gereksinimler <xref:System.Collections.ICollection> ve <xref:System.Collections.IEnumerable?displayProperty=fullName> seri hale getirilebilir için.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için özelliği salt okunur yapma ve tasarım gerektiriyorsa, temizleyin ve koleksiyon yeniden doldurmak için yöntemleri ekleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir yazılabilir koleksiyon özelliği türüyle gösterir ve koleksiyon nasıl doğrudan değiştirilebilir gösterir. Ayrıca, tercih edilen şekilde salt okunur koleksiyonun özelliği kullanılarak değiştirme `Clear` ve `AddRange` yöntemleri gösterilir.  
  
 [!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
 [!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
 [!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1819: Özellikler diziler döndürmemelidir](../code-quality/ca1819-properties-should-not-return-arrays.md)