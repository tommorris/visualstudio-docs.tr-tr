---
title: Yükseltme Dotfuscator Community Edition (CE)
ms.date: 02/08/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
keywords: Dotfuscator Dotfuscator CE, PreEmptive, PreEmptive tarafından çözümleri PreEmptive tarafından koruma, koruma, community edition, gizleme, .NET, ücretsiz, Visual Studio 2017, yükseltme, komut satırı
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator upgrade
- upgrade Dotfuscator
- upgrading Dotfuscator
- register Dotfuscator
- registering Dotfuscator
- Dotfuscator command line
- Dotfuscator Professional
description: Ücretsiz Dotfuscator Community Edition Visual Studio 2017 dahil yükseltmeyi öğrenin.
ms.assetid: c7c60904-27f9-4f1f-b79b-ddf65041b810
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: douge
ms.openlocfilehash: f842eb9573f2519525f122dd58d23559df37e54c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="upgrade-dotfuscator-community-edition-ce"></a>Yükseltme Dotfuscator Community Edition (CE)

Dotfuscator Community Edition (Dotfuscator CE) çok sayıda uygulama koruması ve sağlamlaştırma özelliklerini hemen tüm geliştiriciler Microsoft Visual Studio kullanarak sunar.
Ancak, daha fazla özellikler vardır Dotfuscator kendi sürümüne yükseltme kullanıcılar için kullanılabilir.

## <a name="registering-dotfuscator-ce"></a>Dotfuscator CE kaydetme

Dotfuscator CE kayıtlı kullanıcıları almak ek özelliklerine erişimi gibi [komut satırı desteği][cli], hangi Dotfuscator CE otomatik derleme işlemine tümleştirmek yapmayı kolaylaştırır. Kaydetme de erişim verir Lucidator için yerleşik bir aracı için kullanılan [karıştırılmış Yığın izlemeleri kod çözme][decode-obfuscated].

Kayıt hızlı, basit ve ücretsiz olarak değil.
Dotfuscator CE kaydetmek için bkz: [tam Dotfuscator CE Kullanıcı Kılavuzu'na Başlarken sayfasında kaydetme Dotfuscator CE bölümünü][register-ce].

## <a name="dotfuscator-professional"></a>Dotfuscator Professional

Dotfuscator Community Edition temel düzeyde bir koruma sağlarken  **_PreEmptive tarafından koruması - Dotfuscator_ Professional Edition** Gelişmiş gizleme dönüşümler ve koruma içerir yetenekleri. Gelişmiş dönüşümler ve özellikleri içerir:

* *Fikri mülkiyet koruma*
  * Ek seçenekler Enhanced Overload Induction™ ve rastgele tanımlayıcı seçimi de dahil olmak üzere, yeniden adlandırma.
  * Kod çözme için araç Yığın izlemeleri gizlenmiş.
  * Dahil, kurumsal düzeyde gizleme Dönüşümlerin erişimi [iptal ediyor adresindeki hedeflenen dönüşümler otomatik kod kaynak koda dönüştürme][control-flow].
  * Yeteneği [hassas dizeleri soyutlamaması][string-encryption], basit bir arama decompiled kod imkansız yapma.
  * Yeteneği [belirtmeyecek derlemeleriniz sahipliği ve dağıtım dizelerini katıştırma][watermarking], yetkisiz yazılım sızıntıları kaynağını belirlemek olanak sağlar.
  * Yeteneği [tek birden çok derleme birleştirmek][linking], ayrımı kaygıları ortadan gibi daha da zor kod öğeleri rolleri belirlemek saldırganların yapma.
  * Yeteneği [otomatik olarak kullanılmayan kod uygulamanızdan Kaldır][pruning], sevk hassas kod miktarını azaltır.
* *Uygulama bütünlük koruması*
  * Ek [uygulama savunma davranışları][check-actions].
  * Bir uygulamanın yaşam bitiş tarihi önce bir uyarı dönemi sağlama yeteneği.
  * Uygulama kodu bir ömrü bitiş uyarı dönemi sırasında veya son tarihten sonra bildirim yeteneği.
  * Telemetri şifreleme.
* *Uygulama izleme*
  * Toplanan bilgiler geçici ağ kesintileri sırasında özelliği toplayın ve kaydedin.
  * Kişisel bilgi toplama yeteneği.
  * Sınırsız kullanımını [izleme özelliğinin][features].
  * Yakalanan ve işlenmeyen özel durumlar için ayrıca kodunuz tarafından oluşturulan özel durum izleme yeteneği.
  * Özel durumları izleme yeteneği `.dll` derlemeler.
  * Telemetri şifreleme.

Dotfuscator Professional endüstri standardı olan [.NET Obfuscator] [ net-obfuscator] ve devam eden desteği, Bakım ve ürün güncelleştirmelerini gerektiren Kurumsal geliştiriciler için uygundur.
Ayrıca, Dotfuscator Professional Visual Studio ile sıkı tümleştirme sağlar ve Ticari kullanım için lisanslanmıştır.

PreEmptive tarafından çözümleri Dotfuscator Professional Gelişmiş uygulama koruma özellikleri hakkında daha fazla bilgi için ziyaret [Dotfuscator genel bakış sayfasında] [ product-about] ve [için karşılaştırma Community Edition][product-compare].
[Tam olarak desteklenen denemeler preemptive.com][eval].

## <a name="see-also"></a>Ayrıca Bkz.

[Bu makalede tam Dotfuscator CE Kullanıcı Kılavuzu][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

- [control-flow]: https://www.preemptive.com/products/dotfuscator/features#controlflow
- [string-encryption]: https://www.preemptive.com/products/dotfuscator/features#string
- [watermarking]: https://www.preemptive.com/products/dotfuscator/features#watermarking
- [linking]: https://www.preemptive.com/products/dotfuscator/features#linking
- [pruning]: https://www.preemptive.com/products/dotfuscator/features#pruning

- [check-actions]: https://www.preemptive.com/dotfuscator/pro/userguide/en/protection_checks_overview.html#actions
- [features]: https://www.preemptive.com/dotfuscator/pro/userguide/en/instrumentation_features.html

- [net-obfuscator]: https://www.preemptive.com/products/dotfuscator/overview
- [eval]: https://www.preemptive.com/eval-request

- [product-about]: https://www.preemptive.com/products/dotfuscator/overview
- [product-compare]: https://www.preemptive.com/products/dotfuscator/compare-editions

- [cli]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_cli.html
- [register-ce]: https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html#register

- [full]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_upgrades.html
- [decode-obfuscated]: https://www.preemptive.com/dotfuscator/ce/docs/help/gui_decode_stack_trace.html