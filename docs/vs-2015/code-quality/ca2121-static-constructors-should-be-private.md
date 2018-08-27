---
title: 'CA2121: Statik oluşturucular özel olmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6b7052a25df5e736276b458247eb625ab584d473
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902919"
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121: Statik oluşturucular özel olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2121: statik oluşturucular özel](https://docs.microsoft.com/visualstudio/code-quality/ca2121-static-constructors-should-be-private).

|||
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Özel olmayan statik Oluşturucu türü vardır.

## <a name="rule-description"></a>Kural Tanımı
 Statik Oluşturucu, bir sınıf oluşturucu olarak da bilinen, bir tür başlatmak için kullanılır. Sistem, türünün ilk örneğinin oluşturulmasından önce statik oluşturucuyu çağırır veya herhangi bir statik üyeye başvurur. Kullanıcının statik Oluşturucu ne zaman çağrıldığını üzerinde denetimi yoktur. Statik oluşturucu özel değilse, sistem dışındaki kod tarafından çağrılabilir. Oluşturucu içinde gerçekleştirilen işlemlere bağlı olarak bu, beklenmeyen davranışlara neden olabilir.

 Bu kural, C# ve Visual Basic .NET derleyiciler tarafından uygulanır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 İhlalleri, genellikle aşağıdaki eylemlerden birini kaynaklanır:

-   Statik Oluşturucu türünüz için tanımlanan ve özel göstermedi.

-   Programlama dili derleyici türünüz için varsayılan bir statik Oluşturucu eklendi ve özel göstermedi.

 İlk tür ihlalinin düzeltmek için bir statik oluşturucu özel yapın. İkinci tür düzeltmek için türünüz için özel bir statik oluşturucu ekleyin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 İhlalleri bastırmayın. Yazılım tasarımı açık bir statik Oluşturucu çağrı gerektiriyorsa, tasarım ciddi sorunlar içeriyor ve gözden geçirilmesi gereken olasıdır.



