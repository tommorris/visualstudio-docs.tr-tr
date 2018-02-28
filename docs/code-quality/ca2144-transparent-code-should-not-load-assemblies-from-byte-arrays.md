---
title: "CA2144: Saydam kod derlemeleri bayt dizilerinden değil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: acc2b60d0099d09f9aaba7ad77fd82c26ccd22ca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144: Saydam kod derlemeleri bayt dizilerinden yüklememelidir
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|  
|CheckId|CA2144|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Saydam bir yöntemi, aşağıdaki yöntemlerden birini kullanarak bir bayt dizisinden bir derleme yükler:  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
-   <xref:System.Reflection.Assembly.Load%2A>  
  
## <a name="rule-description"></a>Kural Tanımı  
 Saydam kod için güvenlik incelemesi kritik kod için güvenlik incelemesi kadar kapsamlı değildir, çünkü saydam kod güvenlik duyarlı eylemleri gerçekleştiremez. Bir bayt dizisinden yüklenen derlemeler saydam kodda fark edilmeyebilir ve o bayt dizisi denetlenmesi gereken kritik ya da daha da önemlisi güvenli kritik kod içerebilir. Bu nedenle, saydam kod derlemeleri bayt dizisinden yüklenmemelidir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için derleme yükleme yöntemini işaretlemek <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Saydam yöntemi bir bayt dizisinden bir derlemeyi yüklediğinden kural aşağıdaki kod ateşlenir.  
  
 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../code-quality/codesnippet/CSharp/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays_1.cs)]