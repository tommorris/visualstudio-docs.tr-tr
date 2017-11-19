---
title: "CA1717: Yalnızca FlagsAttribute numaralandırmalarında çoğul adlar olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 787b2f5c1a838bb6312fe5d08cd8328b07460243
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: Yalnızca FlagsAttribute numaralandırmalarında çoğul adlar olmalıdır
|||  
|-|-|  
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|  
|CheckId|CA1717|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür numaralandırma adını çoğul Word'de sona erer ve numaralandırma ile işaretli olmayan <xref:System.FlagsAttribute?displayProperty=fullName> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Adlandırma kuralları numaralandırması için çoğul ad numaralandırma birden fazla değer aynı anda belirtilebilir gösterir dikte. <xref:System.FlagsAttribute> Derleyicileri numaralandırma numaralandırma üzerinde bit düzeyinde işlemler sağlar bir bit alan olarak değerlendirilmesi gerektiğini bildirir.  
  
 Yalnızca aynı anda tek bir numaralandırma değeri belirtilebilir, numaralandırma adını tekil bir sözcük olmalıdır. Örneğin, haftanın günleri tanımlayan numaralandırma bir uygulamada kullanmak için birden fazla gün belirtebileceğiniz ayarlanmış olabilir. Bu numaralandırma olmalıdır <xref:System.FlagsAttribute> ve 'Gün' çağrılabilir. Belirtilmesi yalnızca tek bir günde imkan tanıyan benzer bir numaralandırma öznitelik sahip değil ve olabilir 'Day' çağrılır.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu yeni bir yazılım kitaplığı öğrenmek için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır süreyi azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Ekleyin veya numaralandırma adını tekil bir sözcük olun <xref:System.FlagsAttribute>.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Adı bir tekil Word'de biterse bir kuraldan gizlemek güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1714: Bayrak numaralandırmalarında çoğul adlar olmalıdır](../code-quality/ca1714-flags-enums-should-have-plural-names.md)  
  
 [CA1027: numaralandırmaları FlagsAttribute ile işaretle](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.FlagsAttribute?displayProperty=fullName>   
 [Enum tasarım](/dotnet/standard/design-guidelines/enum)