---
title: 'CA2121: Statik oluşturucular özel olmalıdır'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4955feca4bcdde422001eb22a3117fc7fb524ea
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121: Statik oluşturucular özel olmalıdır
|||
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Özel olmayan statik Oluşturucu bir türe sahip.

## <a name="rule-description"></a>Kural Tanımı
 Statik Oluşturucu, bir sınıf oluşturucu olarak da bilinen bir tür başlatmak için kullanılır. Sistem, türünün ilk örneğinin oluşturulmasından önce statik oluşturucuyu çağırır veya herhangi bir statik üyeye başvurur. Kullanıcının statik Oluşturucusu ne zaman çağrıldığını üzerinde denetimi yoktur. Statik oluşturucu özel değilse, sistem dışındaki kod tarafından çağrılabilir. Oluşturucu içinde gerçekleştirilen işlemlere bağlı olarak bu, beklenmeyen davranışlara neden olabilir.

 Bu kural, C# ve Visual Basic derleyicileri tarafından zorlanır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 İhlalleri genellikle aşağıdaki eylemlerden birini kullanarak neden olur:

-   Statik Oluşturucu türünüz için tanımlanan ve özel yapmadınız.

-   Programlama dili derleyici türünüz için varsayılan bir statik Oluşturucu eklenir ve özel yapmadınız.

 İlk tür bir ihlali düzeltmek için statik Oluşturucusu özelleştirin. İkinci türü düzeltmek için türünüz için özel bir statik oluşturucu ekleyin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu ihlali bastırma değil. Yazılım tasarımı statik Oluşturucu için açık bir çağrı gerektiriyorsa, tasarım ciddi açıkları içerir ve gözden geçirilmesi gereken olasıdır.