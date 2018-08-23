---
title: 'CA2146: Türler kendi taban türleri ve arabirimleri en az kadar kritik olmalıdır | Microsoft Docs'
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
- CA2146
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 36795651a4bf4cb265177d5e8dc8c4f2722c83cd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630530"
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146: Türler en az kendi taban türleri ve arabirimleri kadar kritik olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2146: türler kendi taban türleri ve arabirimleri en az kadar kritik olmalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces).  
  
TypeName | TypesMustBeAtLeastAsCriticalAsBaseTypes |  
| Checkıd | CA2146 |  
| Kategori | Microsoft.Security|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Saydam bir tür ile işaretlenmiş bir tür türetilir <xref:System.Security.SecuritySafeCriticalAttribute> veya <xref:System.Security.SecurityCriticalAttribute>, veya ile işaretlenmiş bir tür <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği ile işaretlenmiş bir tür türetilir <xref:System.Security.SecurityCriticalAttribute> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, kendi temel türü kadar kritik olmayan saydam güvenlik özniteliğine sahip bir tür türetildiğinde veya arabirim uygulandığında tetiklenir. Yalnızca kritik türler, kritik temel türlerden veya kritik arabirimleri uygulayanlardan türeyebilir ve sadece kritik ya da kritik güvenli türler, kritik güvenli temel türler veya kritik güvenli arabirim uygulamalarından türeyebilir. Bu kural, Düzey 2 saydamlık ihlalleri sonuçlanan bir <xref:System.TypeLoadException> türetilmiş bir tür için.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu ihlali gidermek için türetilmiş veya uygulama türü temel türü veya arabirim en az kadar kritik bir saydamlık özniteliği ile işaretleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2146.typesmustbeatleastascriticalasbasetypes/cs/ca2146 - typesmustbeatleastascriticalasbasetypes.cs#1)]



