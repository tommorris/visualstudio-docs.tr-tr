---
title: "CA1019: öznitelik bağımsız değişkenleri için erişimcileri tanımlayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
helpviewer_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9f04a49c8c68fcc597ecd98471b46932d467b365
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019: Öznitelik bağımsız değişkenleri için erişimcileri tanımlayın
|||  
|-|-|  
|TypeName|DefineAccessorsForAttributeArguments|  
|CheckId|CA1019|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Kurucusunda, karşılık gelen özelliklere sahip olmayan bağımsız değişkenler özniteliği tanımlar.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Öznitelikler özniteliği işaretlediğinizde özelleştirilen zorunlu bağımsız değişkenleri tanımlayabilir. Ayrıca bunlar konum parametreleri olarak öznitelik yapıcısına verildiğinden duruma bağlı bağımsız değişkenler olarak da bilinirler. Zorunlu her bağımsız değişken için bağımsız değişkenin değeri yürütme zamanından alınması gerektiğinden öznitelik ilgili salt okunur özelliği de sağlamalıdır. Bu kural her Oluşturucusu parametresi için karşılık gelen özellik tanımladığınız denetler.  
  
 Öznitelikler adlandırılmış bağımsız değişkenler olarak bilinen duruma bağlı bağımsız değişkenler olarak da tanımlanabilir. Bu bağımsız öznitelik oluşturucular ad tarafından sağlanır ve karşılık gelen bir okuma/yazma özelliğine sahip olmalıdır.  
  
 Zorunlu ve isteğe bağlı bağımsız değişkenler, karşılık gelen özelliklere ve Oluşturucu parametreleri kullanması gereken için aynı ancak farklı büyük/küçük harf adı. Özellikleri kullanma Pascal büyük/küçük harf ve parametre kullanımı ortası büyük/küçük harf.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için bir yok her Oluşturucusu parametre için salt okunur bir özellik ekleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Alınabilir olmasını zorunlu bağımsız değişkeninin değeri istemiyorsanız, bu kural bir uyarıdan engelleyin.  
  
## <a name="custom-attributes-example"></a>Özel öznitelikler örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek zorunlu (konumsal) parametresini tanımlama iki öznitelikleri gösterir. Öznitelik ilk uyarlamasını hatalı tanımlanmış. İkinci doğru uygulamasıdır.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
 [!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]  
  
## <a name="positional-and-named-arguments"></a>Konumsal ve adlandırılmış bağımsız değişkenler  
  
### <a name="description"></a>Açıklama  
 Konumsal ve adlandırılmış bağımsız değişkenler özniteliği için hangi bağımsız değişkenler zorunludur ve hangi bağımsız değişkenler isteğe bağlı kitaplığınızın tüketicilere temizlemek yapın.  
  
 Aşağıdaki örnek konumsal ve adlandırılmış bağımsız değişkenler sahip bir öznitelik uygulaması gösterir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]  
  
### <a name="comments"></a>Açıklamalar  
 Aşağıdaki örnekte, iki özellik için özel öznitelik uygulamak gösterilmiştir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1813: korumasız özniteliklerden kaçının](../code-quality/ca1813-avoid-unsealed-attributes.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öznitelikleri](/dotnet/standard/design-guidelines/attributes)