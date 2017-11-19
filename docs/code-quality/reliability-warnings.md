---
title: "Güvenilirlik uyarıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d3ac06911009a24640031fd3a2306110f289014f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="reliability-warnings"></a>Güvenilirlik Uyarıları
Güvenilirlik uyarıları doğru bellek ve iş parçacığı kullanımı gibi kitaplığı ve uygulamanın güvenilirliğini destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA2000: kapsamı kaybetmeden önce Dispose nesneleri](../code-quality/ca2000-dispose-objects-before-losing-scope.md)|Bir nesnenin sonlandırıcısının çalışmasını engelleyecek olağanüstü bir durum gerçekleşebileceği için, nesne ona olan tüm başvurular kapsam dışına çıkmadan açıkça atılmalıdır.|  
|[CA2001: sorunlu yöntemleri çağırmaktan kaçının](../code-quality/ca2001-avoid-calling-problematic-methods.md)|Bir üye olası tehlikeli ya da sorunlu yöntemi çağırır.|  
|[CA2002: zayıf kimliği olan nesneleri kilitlemeyin](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|Bir nesneye uygulama etki alanları arasından erişilebiliyorsa o nesnenin zayıf bir kimliğe sahip olduğu söylenir. Zayıf kimliğe sahip bir nesne üzerinde kilit almayı deneyen iş parçacığı aynı nesne üzerinde bir kilide sahip olan farklı uygulama etki alanı içindeki ikinci iş parçacığı tarafından engellenebilir.|  
|[CA2003: lifleri iş parçacığı olarak görmeyin](../code-quality/ca2003-do-not-treat-fibers-as-threads.md)|Yönetilen iş parçacığı bir Win32 iş parçacığı kabul edilir.|  
|[CA2004: GC çağrıları kaldırın. Canlı tutma](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|SafeHandle kullanımı dönüştürüyorsanız GC tüm çağrıları kaldırın. KeepAlive (nesne). Bu durumda, GC çağırmak sınıflar yok. KeepAlive bir sonlandırıcı yoksa ancak işletim sistemi Sonlandır SafeHandle kullanan varsayıldığında, bunlar için işler.|  
|[CA2006: yerel kaynakları kapsamak için SafeHandle kullanın](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|Yönetilen kod içinde IntPtr kullanmak olası bir güvenlik ve güvenilirlik sorunu belirtebilir. IntPtr'nin tüm kullanımları onun yerine bir SafeHandle ya da benzer bir teknolojinin kullanımının gerekip gerekmediğini belirlemek için gözden geçirilmelidir.|