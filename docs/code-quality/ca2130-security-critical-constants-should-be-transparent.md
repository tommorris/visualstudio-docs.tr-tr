---
title: 'CA2130: Güvenlik kritik sabitleri saydam olmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 212bd1bc9f1f5b66fa8ddb485c5ec287ff39c754
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551357"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: Güvenlik kritik sabitleri saydam olmalıdır
|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir sabit alanı ya da bir numaralandırma üyesine ile işaretlenmiş <xref:System.Security.SecurityCriticalAttribute>.

## <a name="rule-description"></a>Kural açıklaması
 Saydamlık zorlaması, sabit değerler için zorlanmaz çünkü derleyiciler sabit değerleri satır içi hale getirir bu nedenle arama, çalışma zamanında gerekli değildir. Sabit alanlar saydam güvenlikli olmalıdır; böylece kodu gözden geçirenler saydam kodun sabitlere erişemediğini varsaymaz.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Bu kural ihlalini düzeltmek için alan veya değer SecurityCritical özniteliği kaldırın.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örneklerde, sabit listesi değeri `EnumWithCriticalValues.CriticalEnumValue` ve sabit `CriticalConstant` bu uyarı oluştur. Sorunları gidermek için kaldırma [`SecurityCritical`] güvenlik saydam olacak şekilde özniteliği.

 [!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]