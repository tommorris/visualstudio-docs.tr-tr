---
title: 'CA1021: out parametrelerinden kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1021
- AvoidOutParameters
helpviewer_keywords:
- AvoidOutParameters
- CA1021
ms.assetid: 970f2304-842c-4fb7-9734-f3871da8d479
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f8748b9943f3a3aa31a6585de07bdc9eff3cc5ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1021-avoid-out-parameters"></a>CA1021: Out parametrelerinden kaçının
|||  
|-|-|  
|TypeName|AvoidOutParameters|  
|CheckId|CA1021|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Ortak tür genel ya da korumalı yönteminde sahip bir `out` parametresi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Türleri başvuruya göre geçirme (kullanarak `out` veya `ref`) nasıl değer türleri ve başvuru türleri farklı anlama ve birden çok dönüş değerleri yöntemleriyle işleme işaretçileri deneyimiyle gerektirir. Ayrıca, arasındaki farkı `out` ve `ref` parametreleri değil yaygın anladım.  
  
 Bir başvuru türü "başvuruya göre" geçirildiğinde, nesnenin farklı bir örneğine geri dönmek için parametre kullanmak üzere yöntemi amaçlamaktadır. Bir başvuru türü başvuruya göre geçirme bir işaretçi ya da çift yöneltme işaretçi çift işaretçi kullanarak olarak da bilinir. Çağırma "değeriyle" geçti kuralı varsayılan kullanarak nesnesine bir işaretçi bir başvuru türü zaten götüren bir parametre alır. İşaretçi, bu işaret ettiği, nesnesi değil geçirildi. Yöntem başvuru türünde yeni bir örneğini göstermesi için işaretçiyi değiştiremezsiniz bir değer yöntemle geçirin. Ancak, bu işaret ettiği nesnesinin içeriğini değiştirebilirsiniz. Çoğu uygulama için bu yeterli ve istenen davranışı verir.  
  
 Bir yöntem farklı bir örnek döndürmesi gerekiyorsa, bunu başarmak için yönteminin dönüş değerini kullanın. Bkz: <xref:System.String?displayProperty=fullName> sınıfı için çeşitli yöntemler dizeleri çalışan ve bir dize yeni bir örneğini döndürür. Bu model kullanıldığında, çağıran özgün nesne korunup korunmayacağını karar vermeniz gerekir.  
  
 Dönüş değerleri sıradan bir hale ve yoğun olarak kullanılan, doğru uygulamasının rağmen `out` ve `ref` parametreleri Ara tasarım ve yetenekleri kodlama gerektirir. Genel bir izleyici ile ana çalışma kullanıcılara beklememeniz gerekir için tasarım kitaplığı mimarları `out` veya `ref` parametreleri.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Değer türü tarafından neden bu kural ihlal düzeltmek için nesneyi dönüş değeri olarak dönmek yöntemi sahip. Yöntemin birden çok değer döndürmesi gerekir, bu değerleri içeren bir nesne tek bir örneğini döndürmek için yeniden tasarlamanız.  
  
 Bir başvuru türüne göre neden bu kural ihlal düzeltmek için istenen davranışı başvuru yeni bir örneğini döndürmek için olduğundan emin olun. İse, yöntem Bunu yapmak için dönüş değerini kullanmanız gerekir.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan gizlemek güvenlidir. Ancak, bu tasarım kullanılabilirlik sorunları neden olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kitaplığı kullanıcı geribildirim yanıtlarını oluşturan bir sınıfın iki uygulamaları gösterir. İlk uygulama (`BadRefAndOut`) üç dönüş değerleri yönetmek için kitaplık kullanıcı zorlar. İkinci uygulama (`RedesignedRefAndOut`) bir kapsayıcı sınıfının bir örneği döndürerek kullanıcı deneyimini basitleştirir (`ReplyData`) verileri tek bir birim olarak yönetir.  
  
 [!code-csharp[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama kullanıcı deneyimini gösterilmektedir. Yeniden tasarlanan kitaplığı çağrısına (`UseTheSimplifiedClass` yöntemi) daha kolay olduğundan ve yöntem tarafından döndürülen bilgi kolayca yönetilebilir. İki yöntemlerini çıkışı aynıdır.  
  
 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_2.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kitaplığı gösterilmektedir nasıl `ref` parametreleri başvuru türleri için kullanılır ve bu işlevselliği uygulamak için daha iyi bir yolu gösterir.  
  
 [!code-csharp[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_3.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama davranışı göstermek için kitaplığında her yöntemini çağırır.  
  
 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_4.cs)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **İşaretçi - değeri tarafından geçirilen değiştirme:**  
**12345**  
**12345**  
**İşaretçi - başvuruya göre geçirilen değiştirme:**  
**12345**  
**12345 ABCDE**  
**Dönüş değere göre geçirme:**  
**12345 ABCDE**   
## <a name="try-pattern-methods"></a>Desen yöntemleri deneyin  
  
### <a name="description"></a>Açıklama  
 Uygulama yöntemleri **deneyin\<bir şey >** gibi desen <xref:System.Int32.TryParse%2A?displayProperty=fullName>, bu ihlali yükseltmeyin. Arabirimini uygulayan bir yapı (değer türü) aşağıdaki örnekte <xref:System.Int32.TryParse%2A?displayProperty=fullName> yöntemi.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Design.TryPattern#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_5.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1045: Türleri başvuruya göre geçirmeyin](../code-quality/ca1045-do-not-pass-types-by-reference.md)