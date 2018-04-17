---
title: 'CA2146: Türler kendi taban türleri ve arabirimleri en az kadar kritik olmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2146
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b956397818c171091e4ad982d92adc5e62370a39
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146: Türler en az kendi taban türleri ve arabirimleri kadar kritik olmalıdır
|||  
|-|-|  
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|  
|CheckId|CA2146|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Saydam bir türü ile işaretli bir türden türetilmiş <xref:System.Security.SecuritySafeCriticalAttribute> veya <xref:System.Security.SecurityCriticalAttribute>, veya ile işaretli bir türe <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği ile işaretlenmiş bir türü türetilen <xref:System.Security.SecurityCriticalAttribute> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, kendi temel türü kadar kritik olmayan saydam güvenlik özniteliğine sahip bir tür türetildiğinde veya arabirim uygulandığında tetiklenir. Yalnızca kritik türler, kritik temel türlerden veya kritik arabirimleri uygulayanlardan türeyebilir ve sadece kritik ya da kritik güvenli türler, kritik güvenli temel türler veya kritik güvenli arabirim uygulamalarından türeyebilir. Düzey 2 saydamlık içinde bu kuralı ihlallerini neden bir <xref:System.TypeLoadException> türetilmiş bir tür için.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu ihlali düzeltmek için temel türü veya arabirim olarak en az kadar kritik bir saydamlık özniteliği türetilmiş veya uygulama türüyle işaretleyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]