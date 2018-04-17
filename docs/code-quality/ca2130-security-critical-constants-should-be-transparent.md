---
title: 'CA2130: Güvenlik kritik sabitleri saydam olmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2fbda0886fe05d22ccf61f36792d8bfcf687547a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: Güvenlik kritik sabitleri saydam olmalıdır
|||  
|-|-|  
|TypeName|ConstantsShouldBeTransparent|  
|CheckId|CA2130|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Sabit bir alan veya bir numaralandırma üyesine işaretlenmiş <xref:System.Security.SecurityCriticalAttribute>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Saydamlık zorlaması, sabit değerler için zorlanmaz çünkü derleyiciler sabit değerleri satır içi hale getirir bu nedenle arama, çalışma zamanında gerekli değildir. Sabit alanlar saydam güvenlikli olmalıdır; böylece kodu gözden geçirenler saydam kodun sabitlere erişemediğini varsaymaz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için alan veya değer SecurityCritical özniteliğini kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örneklerde, enum değeri `EnumWithCriticalValues.CriticalEnumValue` ve sabit `CriticalConstant` bu uyarı. Sorunları gidermek için kaldırma [`SecurityCritical`] bunları güvenlik saydam hale getirmek için öznitelik.  
  
 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]