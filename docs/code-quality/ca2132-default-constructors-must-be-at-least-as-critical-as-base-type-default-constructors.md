---
title: "CA2132: Varsayılan oluşturucular en az taban tür varsayılan oluşturucular kadar kritik olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 752103825a25c4352ccc21730b8d2b7265f8f41b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132: Varsayılan oluşturucular en az taban tür varsayılan oluşturucular kadar kritik olmalıdır
|||  
|-|-|  
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|  
|CheckId|CA2132|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
> [!NOTE]
>  Bu uyarı yalnızca CoreCLR (Silverlight Web uygulamalarına özeldir CLR sürüm) çalıştıran kod uygulanır.  
  
## <a name="cause"></a>Sebep  
 Varsayılan Oluşturucu türetilmiş sınıf saydamlık özniteliğinin temel sınıfı saydamlığı olarak kritik olarak değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Türleri ve sahip üyeler <xref:System.Security.SecurityCriticalAttribute> Silverlight uygulama kodu tarafından kullanılamaz. Kritik güvenlik türleri ve üyeleri, yalnızca Silverlight sınıf kütüphanesi için .NET Framework'ündeki güvenilen kod tarafından kullanılabilir. Türetilmiş sınıftaki ortak veya korumalı oluşturma, onun temel sınıfından aynı düzeyde veya daha saydam olması gerektiğinden uygulama içindeki sınıf SecurityCritical olarak işaretlenmiş bir sınıftan türeyemez.  
  
 Bir taban türü bir public ya da korumalı saydam olmayan varsayılan oluşturucu varsa CoreCLR platform kodunu sonra türetilmiş bir tür varsayılan oluşturucusu devralma kuralları uyma gerekir. Türetilen türde de varsayılan bir oluşturucu olmalıdır ve bu Oluşturucusu kritik varsayılan oluşturucu temel türün en az olmalıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 İhlali düzeltmek için türünü kaldırmak veya güvenlik saydam olmayan türden türetilmiş değil.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıları bastırma değil. Uygulama kodu tarafından bu kural ihlalleri türüyle yüklenemiyor reddediyor CoreCLR sonuçlanacak bir <xref:System.TypeLoadException>.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors_1.cs)]  
  
### <a name="comments"></a>Açıklamalar