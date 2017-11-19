---
title: "CA2240: ISerializable doğru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2240
- ImplementISerializableCorrectly
helpviewer_keywords:
- CA2240
- ImplementISerializableCorrectly
ms.assetid: cf05936d-0d6c-49ed-a1b4-220032e50b97
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c8e3f9ba0e3cb182ec08dd802dc87728a0fb9dc0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2240-implement-iserializable-correctly"></a>CA2240: ISerializable'ı doğru uygulayın
|||  
|-|-|  
|TypeName|ImplementISerializableCorrectly|  
|CheckId|CA2240|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür bir tür için atanabilir olduğundan <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi ve aşağıdaki koşullardan biri doğruysa:  
  
-   Türü devralır, ancak geçersiz <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> yöntemi ve türü ile işaretli olmayan örneği alanları bildirir <xref:System.NonSerializedAttribute?displayProperty=fullName> özniteliği.  
  
-   Türü korumalı değil ve türü uygulayan bir <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> harici olarak görünür ve geçersiz kılınabilir değil yöntemi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Örnek devralan bir tür bildirilen alanları <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimi seri hale getirme işlemi otomatik olarak eklenmemiştir. Tür alanları içerecek şekilde uygulamalıdır <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> yöntemi ve seri hale getirme Oluşturucusu. Alanları seri hale getirilmemelidir, Uygula <xref:System.NonSerializedAttribute> öznitelik alanları kararı açıkça belirtmek için.  
  
 Uygulamaları mühürlendi değil türlerinde <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> yöntemi harici olarak görünür. Bu nedenle, bu yöntem, türetilmiş türler tarafından çağrılabilir ve geçersiz kılınabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için olun <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> yöntemi görünür ve geçersiz kılınabilir ve tüm örneği alanları seri hale getirme işlemine dahil veya açıkça ile işaretli olduğundan emin olun <xref:System.NonSerializedAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kural ihlal iki seri hale getirilebilir türler gösterir.  
  
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_1.cs)]
 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_1.cpp)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_1.vb)]  
  
## <a name="example"></a>Örnek  
 Geçersiz kılınabilir uygulaması sağlayarak aşağıdaki örnekte iki önceki ihlalleri giderir <xref:System.Runtime.Serialization.ISerializable.GetObjectData> defteri sınıfını ve uygulaması sağlayarak `GetObjectData` kitaplığı sınıfı.  
  
 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_2.cpp)]
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_2.cs)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_2.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2236: ISerializable türler üzerinde taban sınıf yöntemlerini çağırın](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
 [CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)  
 [CA2238: Serileştirme yöntemlerini doğru uygulama](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
 [CA2235: tüm serileştirilebilir olmayan alanları işaretleyin](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
 [CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
 [CA2239: Sağlayan yöntemler için isteğe bağlı alanları](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
 [CA2120: Serileştirme oluşturucularının güvenliğini sağlayın](../code-quality/ca2120-secure-serialization-constructors.md)  
