---
title: 'CA2132: Varsayılan oluşturucular en az taban tür varsayılan oluşturucular kadar kritik olmalıdır | Microsoft Docs'
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
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ecf78792e18df4956fa0147754879fb2e80648bc
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902883"
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132: Varsayılan oluşturucular en az taban tür varsayılan oluşturucular kadar kritik olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2132: varsayılan oluşturucular en az taban tür varsayılan oluşturucular kadar kritik olmalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors).

|||
|-|-|
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|
|CheckId|CA2132|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

> [!NOTE]
>  Bu uyarı yalnızca CoreCLR (Silverlight Web uygulamalarına özel olan CLR sürümü) çalışan kodu uygulanır.

## <a name="cause"></a>Sebep
 Türetilmiş bir sınıfın varsayılan oluşturucusu saydamlık özniteliklerini temel sınıf saydamlığı önemli değildir.

## <a name="rule-description"></a>Kural Tanımı
 Türleri ve üyeleri olan <xref:System.Security.SecurityCriticalAttribute> Silverlight uygulama kodu tarafından kullanılamaz. Kritik güvenlik türleri ve üyeleri, yalnızca Silverlight sınıf kütüphanesi için .NET Framework'ündeki güvenilen kod tarafından kullanılabilir. Türetilmiş sınıftaki ortak veya korumalı oluşturma, onun temel sınıfından aynı düzeyde veya daha saydam olması gerektiğinden uygulama içindeki sınıf SecurityCritical olarak işaretlenmiş bir sınıftan türeyemez.

 Ortak veya korumalı saydam olmayan varsayılan bir oluşturucu bir taban türü varsa, CoreCLR platform kodunu ardından türetilmiş bir tür varsayılan oluşturucu devralma kurallara uyan gerekir. Türetilmiş bir tür aynı zamanda bir varsayılan oluşturucusu olmalıdır ve bu oluşturucu temel tür kritik varsayılan oluşturucu en az olmalıdır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 İhlali gidermek için türü kaldırın veya güvenlik saydam olmayan türden türetilmiş değil.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıları bastırmayın. Uygulama kodu tarafından bu kural ihlalleri türüyle yüklenecek reddediyor CoreCLR sonuçlanır bir <xref:System.TypeLoadException>.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2132.defaultconstructorsmusthaveconsistenttransparency/cs/ca2132 - defaultconstructorsmusthaveconsistenttransparency.cs#1)]

### <a name="comments"></a>Açıklamalar



