---
title: 'CA2002: zayıf kimliği olan nesneleri kilitlemez | Microsoft Docs'
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
- DoNotLockOnObjectsWithWeakIdentity
- CA2002
helpviewer_keywords:
- CA2002
- DoNotLockOnObjectsWithWeakIdentity
ms.assetid: 16100b39-c6fc-452b-8fca-8b459a26c286
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 95686c7e76fd1ed1dee442d914186ef2cc53bb7c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694748"
---
# <a name="ca2002-do-not-lock-on-objects-with-weak-identity"></a>CA2002: Zayıf kimliği olan nesneleri kilitlemeyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2002: zayıf kimliği olan nesneleri kilitlemeyin](https://docs.microsoft.com/visualstudio/code-quality/ca2002-do-not-lock-on-objects-with-weak-identity).  
  
TypeName | DoNotLockOnObjectsWithWeakIdentity |  
| Checkıd | CA2002 |  
| Kategori | Microsoft.Reliability|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Bir iş parçacığı, zayıf kimliğe sahip bir nesne üzerinde kilit dener.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir nesneye uygulama etki alanları arasından erişilebiliyorsa o nesnenin zayıf bir kimliğe sahip olduğu söylenir. Zayıf kimliğe sahip bir nesne üzerinde kilit almayı deneyen iş parçacığı aynı nesne üzerinde bir kilide sahip olan farklı uygulama etki alanı içindeki ikinci iş parçacığı tarafından engellenebilir. Aşağıdaki türleri zayıf bir kimliğe sahip ve kural tarafından işaretlenir:  
  
-   <xref:System.MarshalByRefObject>  
  
-   <xref:System.ExecutionEngineException>  
  
-   <xref:System.OutOfMemoryException>  
  
-   <xref:System.StackOverflowException>  
  
-   <xref:System.String>  
  
-   <xref:System.Reflection.MemberInfo>  
  
-   <xref:System.Reflection.ParameterInfo>  
  
-   <xref:System.Threading.Thread>  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için açıklama bölümünde listesinde olmayan bir türden bir nesne kullanın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2213: Atılabilen alanlar atılmalıdır](../code-quality/ca2213-disposable-fields-should-be-disposed.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kural ihlal bazı nesne kilitleri gösterir.  
  
 [!code-csharp[FxCop.Reliability.LockWeakObjects#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Reliability.LockWeakObjects/cs/FxCop.Reliability.LockWeakObjects.cs#1)]
 [!code-vb[FxCop.Reliability.LockWeakObjects#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Reliability.LockWeakObjects/vb/FxCop.Reliability.LockWeakObjects.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.Monitor>   
 <xref:System.AppDomain>   
 [lock deyimi](http://msdn.microsoft.com/library/656da1a4-707e-4ef6-9c6e-6d13b646af42)   
 [SyncLock Deyimi](http://msdn.microsoft.com/library/14501703-298f-4d43-b139-c4b6366af176)



