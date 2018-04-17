---
title: 'CA1003: Genel olay işleyici örnekleri kullan | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c6804adbaa360f6523d9cc3d98d555fb13142dd8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003: Genel olay işleyici örnekleri kullan
|||  
|-|-|  
|TypeName|UseGenericEventHandlerInstances|  
|CheckId|CA1003|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir türü void döndüren, iki parametre (bir nesneye ilk ve ikinci bir EventArgs için atanabilir tür) ve içeren derleme hedefleri, imza içeren bir temsilci içerir [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].  
  
## <a name="rule-description"></a>Kural Tanımı  
 Önce [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]olay işleyicisine özel bilgi aktarmak için yeni bir temsilci öğesinden türetilmiş bir sınıf belirtilen bildirilmesi gerekiyordu <xref:System.EventArgs?displayProperty=fullName> sınıfı. Bu artık geçerlidir [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], hangi sunulan <xref:System.EventHandler%601?displayProperty=fullName> temsilci. Bu genel temsilcisi türetilmiş herhangi bir sınıf sağlar <xref:System.EventArgs> olay işleyicisi ile birlikte kullanılacak.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için temsilci kaldırın ve kullanımını kullanarak değiştirin <xref:System.EventHandler%601?displayProperty=fullName> temsilci. Temsilci tarafından otomatik olarak ise [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] derleyicisi kullanmak için olay bildirimi sözdizimi değiştirmek <xref:System.EventHandler%601?displayProperty=fullName> temsilci.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir temsilci gösterir. İçinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] örnek, Yorumlar kural karşılamak için örnek değiştirme açıklanmaktadır. C# örnek için değiştirilen kodunu gösteren bir örnek izler.  
  
 [!code-vb[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/VisualBasic/ca1003-use-generic-event-handler-instances_1.vb)]
 [!code-csharp[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kural karşılayan ve kullanımını değiştirir önceki örnek temsilci bildirimi kaldırır `ClassThatRaisesEvent` ve `ClassThatHandlesEvent` kullanarak yöntemleri <xref:System.EventHandler%601?displayProperty=fullName> temsilci.  
  
 [!code-csharp[FxCop.Design.GenericEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_2.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)  
  
 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](/dotnet/csharp/programming-guide/generics/index)