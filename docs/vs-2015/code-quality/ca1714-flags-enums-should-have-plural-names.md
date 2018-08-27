---
title: 'CA1714: Bayrak numaralandırmalarında çoğul adlar olmalıdır. | Microsoft Docs'
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
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c778267df8a54c474e956a5e41388a7f971823f4
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900335"
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714: Bayrak numaralandırmalarında çoğul adlar olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1714: bayrak numaralandırmalarında çoğul adlar olmalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca1714-flags-enums-should-have-plural-names).

|||
|-|-|
|TypeName|FlagsEnumsShouldHavePluralNames|
|CheckId|CA1714|
|Kategori|Microsoft.Naming|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Ortak bir numaralandırma olan <xref:System.FlagsAttribute?displayProperty=fullName> ve adını bitmeyen içinde 's'.

## <a name="rule-description"></a>Kural Tanımı
 İle işaretlenmiş türler <xref:System.FlagsAttribute> öznitelik birden fazla değer belirtilebilir, çünkü çoğul adları vardır. Örneğin, Haftanın günlerinin ingilizceleridir tanımlayan bir numaralandırma kullanılmak üzere bir uygulama birden çok gün belirleyebileceğiniz ayarlanmış olabilir. Bu numaralandırma olmalıdır <xref:System.FlagsAttribute> ve 'Gün' çağrılabilir. Belirtilecek yalnızca tek bir günde izin veren benzer bir sabit listesi özniteliğine sahip değil ve olabilir 'Day' denir.

 Adlandırma kuralları, ortak dil çalışma zamanını hedefleyen kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığına sahip olan kişi tarafından geliştirilmiştir müşterilerinizin size olan güvenini artırır öğrenme eğrisini azaltır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Sabit listesi adı çoğul bir sözcük olun ya da kaldırma <xref:System.FlagsAttribute> özniteliği birden fazla numaralandırma değerlerinin aynı anda belirtilmemelidir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Adın çoğul bir sözcük ancak bitmiyor ihlalinin bastırmak güvenlidir 's'. Örneğin, 'DaysOfTheWeek' daha önce açıklanan birden çok günü numaralandırma adlandırılmışsa, bu kural ancak konuşmanın niyetini mantığını ihlal ediyor. Bu tür ihlalleri suppressd olmalıdır.

## <a name="related-rules"></a>İlgili kuralları
 [CA1027: Numaralandırmaları FlagsAttribute ile işaretleyin](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.FlagsAttribute?displayProperty=fullName> [Sabit listesi tasarımı](http://msdn.microsoft.com/library/dd53c952-9d9a-4736-86ff-9540e815d545)



