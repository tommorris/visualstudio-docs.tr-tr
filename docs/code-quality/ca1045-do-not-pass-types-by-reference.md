---
title: 'CA1045: Türleri başvuruya göre geçirmeyin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1045
- DoNotPassTypesByReference
helpviewer_keywords:
- CA1045
- DoNotPassTypesByReference
ms.assetid: bcc3900a-e092-4bb8-896f-cb83f6289968
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ddb9a54b440e4b76ebfac8300278483cf166d4d7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1045-do-not-pass-types-by-reference"></a>CA1045: Türleri başvuruya göre geçirmeyin
|||
|-|-|
|TypeName|DoNotPassTypesByReference|
|CheckId|CA1045|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Ortak tür genel ya da korumalı yönteminde sahip bir `ref` bir ilkel tür, bir başvuru türü veya bir değer türü alan parametresi yerleşik türlerinden biri değil.

## <a name="rule-description"></a>Kural Tanımı
 Türleri başvuruya göre geçirme (kullanarak `out` veya `ref`) nasıl değer türleri ve başvuru türleri farklı anlama ve birden çok dönüş değerleri içeren yöntemler işleme işaretçileri deneyimiyle gerektirir. Ayrıca, arasındaki farkı `out` ve `ref` parametreleri değil yaygın anladım.

 Bir başvuru türü "başvuruya göre" geçirildiğinde, nesnenin farklı bir örneğine geri dönmek için parametre kullanmak üzere yöntemi amaçlamaktadır. (Bir başvuru türü başvuruya göre geçirme da bir işaretçi ya da çift yöneltme işaretçi çift işaretçi kullanarak olarak bilinir.) Çağırma "değeriyle" geçti kuralı varsayılan kullanarak nesnesine bir işaretçi bir başvuru türü zaten götüren bir parametre alır. İşaretçi, bu işaret ettiği, nesnesi değil geçirildi. Yöntem başvuru yeni bir örneğini göstermesi için işaretçiyi değiştiremezsiniz anlamına gelir yazın, ancak işaret ettiği nesnesinin içeriğini değiştirebilirsiniz değere göre geçirme. Çoğu uygulama için bu yeterli ve istediğiniz davranışı verir.

 Bir yöntem farklı bir örnek döndürmesi gerekiyorsa, bunu başarmak için yönteminin dönüş değerini kullanın. Bkz: <xref:System.String?displayProperty=fullName> sınıfı için çeşitli yöntemler dizeleri çalışan ve bir dize yeni bir örneğini döndürür. Bu modeli kullanarak, özgün nesne korunup korunmayacağını karar vermek için çağırana bırakılır.

 Dönüş değerleri sıradan bir hale ve yoğun olarak kullanılan, doğru uygulamasının rağmen `out` ve `ref` parametreleri Ara tasarım ve yetenekleri kodlama gerektirir. Genel bir izleyici ile ana çalışma kullanıcılara beklememeniz gerekir için tasarım kitaplığı mimarları `out` veya `ref` parametreleri.

> [!NOTE]
>  Büyük yapıları olan parametreleri ile çalışırken, değeriyle geçirdiğinizde bu yapıları kopyalamak için gereken ek kaynakları bir performans etkisi neden olabilir. Bu durumlarda, kullanarak düşünebilirsiniz `ref` veya `out` parametreleri.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Değer türü tarafından neden bu kural ihlal düzeltmek için nesneyi dönüş değeri olarak dönmek yöntemi sahip. Yöntemin birden çok değer döndürmesi gerekir, bu değerleri içeren bir nesne tek bir örneğini döndürmek için yeniden tasarlamanız.

 Bir başvuru türüne göre neden bu kural ihlal düzeltmek için istediğiniz davranışı başvuru yeni bir örneğini döndürmek için olduğundan emin olun. İse, yöntem Bunu yapmak için dönüş değerini kullanmanız gerekir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan gizlemek güvenlidir; Ancak, bu tasarım kullanılabilirlik sorunları neden olabilir.

## <a name="example"></a>Örnek
 Aşağıdaki kitaplığı geribildirim kullanıcının yanıtlarını oluşturan bir sınıfın iki uygulamaları gösterir. İlk uygulama (`BadRefAndOut`) üç dönüş değerleri yönetmek için kitaplık kullanıcı zorlar. İkinci uygulama (`RedesignedRefAndOut`) bir kapsayıcı sınıfının bir örneği döndürerek kullanıcı deneyimini basitleştirir (`ReplyData`) verileri tek bir birim olarak yönetir.

 [!code-csharp[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_1.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki uygulama kullanıcı deneyimini gösterilmektedir. Yeniden tasarlanan kitaplığı çağrısına (`UseTheSimplifiedClass` yöntemi) daha kolay olduğundan ve yöntem tarafından döndürülen bilgilerin kolayca yönetilebilir. İki yöntemlerini çıkışı aynıdır.

 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_2.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki örnek kitaplığı gösterilmektedir nasıl `ref` parametreleri başvuru türleri için kullanılır ve bu işlevselliği uygulamak için daha iyi bir yolu gösterir.

 [!code-csharp[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_3.cs)]

## <a name="example"></a>Örnek
 Aşağıdaki uygulama davranışı göstermek için kitaplığında her yöntemini çağırır.

 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1045-do-not-pass-types-by-reference_4.cs)]

 Bu örnek şu çıkışı üretir.

 **Değiştirme işaretçi - değeri tarafından geçirilen:**
**12345**
**12345**
**değiştirme işaretçi - başvuruyla geçirildi:** 
 ** 12345**
**12345 ABCDE**
**dönüş değere göre geçirme:**
**12345 ABCDE**
## <a name="related-rules"></a>İlgili kuralları
 [CA1021: Out parametrelerinden kaçının](../code-quality/ca1021-avoid-out-parameters.md)