---
title: 'CA1051: görünür örnek alanlarını bildirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c89e5113e787ca59b4892c64de0077bd27204802
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Görünür örnek alanlarını bildirme
|||  
|-|-|  
|TypeName|DoNotDeclareVisibleInstanceFields|  
|CheckId|CA1051|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir harici olarak görünür bir harici olarak görünür örnek alanı var.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir alanın birincil kullanım alanının uygulama ayrıntısı olması gerekir. Alanlar olmalıdır `private` veya `internal` ve özelliklerini kullanarak açılmamalıdır. Bir özellik olarak bir alana erişmek için olan ve yeni değişiklikler oluşturmaksızın türü özelliklerini genişletin gibi bir özelliğin Erişimcilerde kodu değiştirebilirsiniz erişim kadar kolaydır. Yalnızca bir özel veya dahili alanının değeri döndüren özellikleri bir alan erişme ile eşit düzeye gerçekleştirmek için en iyi duruma getirilir; çok az performans kazancı özellikler üzerinde dışarıdan görünür alanları kullanımı ile ilişkilidir.  
  
 Dışarıdan görünür başvurduğu `public`, `protected`, ve `protected internal` (`Public`, `Protected`, ve `Protected Friend` Visual Basic'te) erişilebilirlik düzeyleri.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için alan olun `private` veya `internal` ve dışarıdan görünür özelliğini kullanarak açın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Dışarıdan görünür alanları özelliklerine kullanılamaz avantajları sağlamaz. Ayrıca, genel alanlar tarafından korunamaz [bağlantı talepleri](/dotnet/framework/misc/link-demands). Bkz: [CA2112: güvenli türler alanları değil kullanıma](../code-quality/ca2112-secured-types-should-not-expose-fields.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür gösterir (`BadPublicInstanceFields`), bu kural ihlal ediyor. `GoodPublicInstanceFields` Düzeltilmiş kodu gösterir.  
  
 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2112: Güvenli türler alanları açığa çıkarmamalıdır](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands)