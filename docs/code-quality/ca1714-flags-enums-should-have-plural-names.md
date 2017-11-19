---
title: "CA1714: Bayrak numaralandırmalarında çoğul adlar olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b83cb82dab5f723c656b51a5322df7d7aad4570c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714: Bayrak numaralandırmalarında çoğul adlar olmalıdır
|||  
|-|-|  
|TypeName|FlagsEnumsShouldHavePluralNames|  
|CheckId|CA1714|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Genel sabit listesi <xref:System.FlagsAttribute?displayProperty=fullName> ve adını bitemez içinde 's'.  
  
## <a name="rule-description"></a>Kural Tanımı  
 İle işaretlenen türleri <xref:System.FlagsAttribute> öznitelik birden fazla değer belirtilebilir gösterir çünkü çoğul adlara sahiptir. Örneğin, haftanın günleri tanımlayan numaralandırma bir uygulamada kullanmak için birden fazla gün belirtebileceğiniz ayarlanmış olabilir. Bu numaralandırma olmalıdır <xref:System.FlagsAttribute> ve 'Gün' çağrılabilir. Belirtilmesi yalnızca tek bir günde imkan tanıyan benzer bir numaralandırma öznitelik sahip değil ve olabilir 'Day' çağrılır.  
  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Numaralandırma adını çoğul word olun ya da kaldırmak <xref:System.FlagsAttribute> birden fazla numaralandırma değerlerinin aynı anda belirtilmemelidir varsa özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Adı çoğul bir sözcük ancak içinde bitmez bir ihlali bastırma güvenlidir 's'. Örneğin, açıklanan birden çok gün numaralandırma daha önce 'DaysOfTheWeek' adlandırılması varsa, bu kural ancak kendi hedefi mantığını ihlal ediyor. Bu tür ihlalleri suppressd olmalıdır.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1027: numaralandırmaları FlagsAttribute ile işaretle](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.FlagsAttribute?displayProperty=fullName>   
 [Enum tasarım](/dotnet/standard/design-guidelines/enum)