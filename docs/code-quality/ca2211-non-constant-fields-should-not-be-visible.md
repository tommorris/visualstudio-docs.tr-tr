---
title: 'CA2211: Sabit olmayan alanlar görünür olmamalıdır'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2211
- NonConstantFieldsShouldNotBeVisible
helpviewer_keywords:
- NonConstantFieldsShouldNotBeVisible
- CA2211
ms.assetid: e1e42c40-0acd-4312-af29-70133739a304
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c36de9e19f01bad47bba390975d5ab59f2fd6e5c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2211-non-constant-fields-should-not-be-visible"></a>CA2211: Sabit olmayan alanlar görünür olmamalıdır
|||
|-|-|
|TypeName|NonConstantFieldsShouldNotBeVisible|
|CheckId|CA2211|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Genel veya korumalı bir statik alan sabit değil veya salt okunur durumdadır.

## <a name="rule-description"></a>Kural Tanımı
 Ne sabitler, ne de salt okunur olan statik alanlar güvenli iş parçacığı değildir. Böyle bir alan erişimi dikkatli bir şekilde denetlenmesi gerekir ve sınıf nesneye erişimi eşitlemek için Gelişmiş programlama tekniklerinin gerektirir. Bunlar öğrenmek için zor becerileri ve ana ve böyle bir nesnenin sınama doğurur kendi zorluklar olduğundan, statik alanları en iyi değişmeyen verileri depolamak için kullanılır. Bu kural kitaplıkları için geçerlidir; uygulamaları tüm alanları açığa çıkarmamalıdır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için statik alan sabit veya salt okunur olun. Bu mümkün değilse, kullanılacak türünü temel alan iş parçacığı erişimi yöneten bir iş parçacığı özelliği gibi alternatif bir mekanizma yeniden tasarlamanız. Kilit çakışması ve kilitlenmeleri gibi sorunları performans ve kitaplık davranışını etkileyebilecek unutmayın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bir uygulama geliştiriyorsanız, bu kural bir uyarıdan bastırmak ve bu nedenle statik alan içeren tür erişimi üzerinde tam denetime sahiptir güvenlidir. Kitaplık tasarımcıları bu kural bir uyarıdan engelleme; Sabit olmayan statik alanları kullanarak doğru bir şekilde kullanmak için geliştiricileri için zor kitaplığını kullanarak yapabilirsiniz.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural ihlal eden bir tür gösterir.

 [!code-vb[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/VisualBasic/ca2211-non-constant-fields-should-not-be-visible_1.vb)]
 [!code-csharp[FxCop.Usage.AvoidStaticNonConstants#1](../code-quality/codesnippet/CSharp/ca2211-non-constant-fields-should-not-be-visible_1.cs)]