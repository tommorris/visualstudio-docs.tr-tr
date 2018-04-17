---
title: 'CA2121: Statik oluşturucular özel olmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: 6248371d4089b4d1e651a9ea3c391d293b94f40c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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