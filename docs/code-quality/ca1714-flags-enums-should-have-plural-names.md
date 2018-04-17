---
title: 'CA1714: Bayrak numaralandırmalarında çoğul adlar olmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d5dc35718a20743ce6ed1502dbd1d9ed3c8a626e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [CA1027: Numaralandırmaları FlagsAttribute ile işaretleyin](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217: Numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.FlagsAttribute?displayProperty=fullName>   
 [Sabit Listesi Tasarımı](/dotnet/standard/design-guidelines/enum)