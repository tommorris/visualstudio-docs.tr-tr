---
title: Güvenilirlik uyarıları | Microsoft Docs
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
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f3bfaff6a434a138024f0baa454935a6da4e67da
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688307"
---
# <a name="reliability-warnings"></a>Güvenilirlik Uyarıları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [güvenilirlik uyarıları](https://docs.microsoft.com/visualstudio/code-quality/reliability-warnings).  
  
Güvenilirlik uyarıları doğru bellek ve iş parçacığı kullanımı gibi kitaplık ve uygulama güvenilirliği destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA2000: Kapsamı kaybetmeden önce verileri atın](../code-quality/ca2000-dispose-objects-before-losing-scope.md)|Bir nesnenin sonlandırıcısının çalışmasını engelleyecek olağanüstü bir durum gerçekleşebileceği için, nesne ona olan tüm başvurular kapsam dışına çıkmadan açıkça atılmalıdır.|  
|[CA2001: Sorunlu yöntemleri çağırmaktan kaçının](../code-quality/ca2001-avoid-calling-problematic-methods.md)|Bir üye olası tehlikeli ya da sorunlu yöntemi çağırır.|  
|[CA2002: Zayıf kimliği olan nesneleri kilitlemeyin](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|Bir nesneye uygulama etki alanları arasından erişilebiliyorsa o nesnenin zayıf bir kimliğe sahip olduğu söylenir. Zayıf kimliğe sahip bir nesne üzerinde kilit almayı deneyen iş parçacığı aynı nesne üzerinde bir kilide sahip olan farklı uygulama etki alanı içindeki ikinci iş parçacığı tarafından engellenebilir.|  
|[CA2003: Lifleri iş parçacığı olarak görmeyin](../code-quality/ca2003-do-not-treat-fibers-as-threads.md)|Yönetilen iş parçacığı bir Win32 iş parçacığı kabul edilir.|  
|[CA2004: GC.KeepAlive'a çağrıları kaldırın](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|SafeHandle kullanımını dönüştürüyorsanız, GC tüm çağrıları kaldırın. KeepAlive (nesne). Bu durumda, GC çağırmak sınıflar olmamalıdır. Bir sonlandırıcı olmayan ancak işletim sistemi sonlandırmak için SafeHandle üzerinde dayanır varsayılarak KeepAlive, bunlar için işler.|  
|[CA2006: Yerel kaynakları kapsamak için SafeHandle kullanın](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|Yönetilen kod içinde IntPtr kullanmak olası bir güvenlik ve güvenilirlik sorunu belirtebilir. IntPtr'nin tüm kullanımları onun yerine bir SafeHandle ya da benzer bir teknolojinin kullanımının gerekip gerekmediğini belirlemek için gözden geçirilmelidir.|



