---
title: "CA1018: AttributeUsageAttribute ile işareti öznitelikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
helpviewer_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2b94cb7c11c803e713609036db12c47e2027cb61
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018: Öznitelikleri AttributeUsageAttribute ile işaretleyin
|||  
|-|-|  
|TypeName|MarkAttributesWithAttributeUsage|  
|CheckId|CA1018|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 <xref:System.AttributeUsageAttribute?displayProperty=fullName> Özniteliği özel özniteliği üzerinde mevcut değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Özel bir öznitelik tanımladığınızda, kullanarak işaretlemek <xref:System.AttributeUsageAttribute> özel öznitelik kaynak kodunda uygulanabileceği belirtmek için. Bir özniteliğin anlamı ve amaçlanan kullanımı, kodun içinde onun varolan konumunu tanımlar. Örneğin, kimin Bakımı ve her tür kitaplığında geliştirme sorumludur ve sorumluluk her zaman tür düzeyinde atanır kişi tanımlayan bir öznitelik tanımlayabilirsiniz. Bu durumda, derleyicileri sınıflar, numaralandırmalar ve arabirimler öznitelikte etkinleştirmeniz gerekir, ancak yöntemleri, olayları veya özellikler etkinleştirmemelisiniz. Kuruluş ilkeleri ve yordamlarıyla öznitelik derlemelerini etkin olup olmadığını dikte.  
  
 <xref:System.AttributeTargets?displayProperty=fullName> Numaralandırması için özel bir öznitelik belirtebilirsiniz hedefleri tanımlar. Atlarsanız <xref:System.AttributeUsageAttribute>, özel özniteliği tarafından tanımlanan tüm hedefler için geçerli olmayacak `All` değerini <xref:System.AttributeTargets> numaralandırması.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için öznitelik hedefleri kullanarak belirtin <xref:System.AttributeUsageAttribute>. Aşağıdaki örnekte bakın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 İleti hariç yerine bu kural ihlal sorununu çözer. Öznitelik devralır olsa bile <xref:System.AttributeUsageAttribute>, öznitelik kod bakımı basitleştirmek için mevcut olmalıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki öznitelikleri tanımlar. `BadCodeMaintainerAttribute`yanlış atlar <xref:System.AttributeUsageAttribute> deyimi, ve `GoodCodeMaintainerAttribute` doğru Bu bölümde daha önce açıklanan öznitelik uygular. Unutmayın özelliği `DeveloperName` tasarım kuralı tarafından gerekli [CA1019: öznitelik bağımsız değişkenleri için erişimcileri tanımlayın](../code-quality/ca1019-define-accessors-for-attribute-arguments.md) ve bütünlük açısından dahil edilmiştir.  
  
 [!code-csharp[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/CSharp/ca1018-mark-attributes-with-attributeusageattribute_1.cs)]
 [!code-vb[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/VisualBasic/ca1018-mark-attributes-with-attributeusageattribute_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1019: Öznitelik bağımsız değişkenleri için erişimcileri tanımlayın](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)  
  
 [CA1813: Korumasız özniteliklerden kaçının](../code-quality/ca1813-avoid-unsealed-attributes.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öznitelikler](/dotnet/standard/design-guidelines/attributes)