---
title: Dotfuscator özellikleri
ms.date: 10/10/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
keywords: Dotfuscator Dotfuscator CE, PreEmptive, PreEmptive tarafından çözümleri PreEmptive tarafından koruma, koruma, community edition, gizleme, .NET, ücretsiz, Visual Studio 2017
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
description: Ücretsiz Dotfuscator Community Edition Visual Studio 2017 dahil özelliklerini öğrenin.
ms.assetid: 0ee89c58-c900-48fc-a6a2-65ace00e8bab
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: douge
ms.openlocfilehash: a087af554ab62a77562dcdf449a18e807f9d17fe
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704453"
---
# <a name="capabilities-of-dotfuscator"></a>Dotfuscator özellikleri

Bu sayfa, Gelişmiş Seçenekler aracılığıyla kullanılabilen bazı başvuruları Dotfuscator Community Edition (Dotfuscator CE) özelliklerine odaklanmıştır [yükseltmeler][upgrades].

Dotfuscator olan bir *oluşturma sonrası* sistem .NET uygulamaları için.
Dotfuscator CE ile Visual Studio kullanıcılarına olan [derlemeleri belirsizleştirirseniz] [ obfuscation] ve ekleme [etkin savunma] [ checks] ve [izleme analytics] [ analytics] uygulamasına - tüm Dotfuscator özgün kaynak koduna erişim gerek.
Dotfuscator katmanlı koruma stratejisi oluşturma uygulamanız birden çok yolla korur.

Dotfuscator CE dahil olmak üzere bir geniş .NET derlemesi ve uygulama türlerini destekler, [Evrensel Windows Platformu (UWP)] [ uwp] ve [Xamarin] [ xamarin].

## <a name="intellectual-property-protection"></a>Fikri mülkiyet koruma

Uygulamanızın tasarım, davranış ve uygulama formları fikri mülkiyet (IP) bulunabilir.
Ancak, .NET Framework için oluşturulan uygulamaların temelde books açmak değildir; Ters mühendislik .NET derlemelerini için çok kolaydır [üst düzey meta verileri ve Ara kod içerdiğinden][assemblies].

Dotfuscator CE içeren temel [.NET gizleme] [ obfuscation] biçiminde [yeniden adlandırma][renaming].
Bu önemli adlandırma bilgileri ortak olarak Dotfuscator kodunuzla obfuscating ters mühendislik aracılığıyla kaynak koda yetkisiz erişim riskini azaltır.
Gizleme çaba İnceleme - IP yasal ticari sır korumalı oluşturma bir değerli adımı kodunuzu korumak için çaba da gösterir.

Çoğu [uygulama bütünlüğünü koruma özellikleri](#application-integrity-protection) Dotfuscator CE daha fazla hinder tersine mühendislik.
Örneğin, hatalı aktör çalışan bir program mantığı olduğunu anlamak için uygulamanızın örneği için bir hata ayıklayıcısı eklemeniz girişiminde bulunabilir.
Dotfuscator Ekle [koruma hata ayıklama davranışı] [ debug] bu obstruct için uygulamanıza.

## <a name="application-integrity-protection"></a>Uygulama bütünlük koruması

Kaynak kodunuz korumaya ek olarak, uygulamanızın tasarlandığı gibi kullanıldığından emin olmak önem taşır.
Saldırganlar lisans ilkeleri (yani, yazılım korsanlığını), çalabilir veya uygulama tarafından işlenen hassas verileri işlemek için veya uygulamanın davranışını değiştirmek için aşmak için uygulamanızın çalabilir deneyebilirsiniz.

Dotfuscator CE Ekle [uygulama doğrulama kodu] [ checks] dahil olmak üzere, derlemeler içine [koruma yetkisiz değiştirmeye karşı][tamper], [ Anti-debug][debug], ve [hologram root] [ root] ölçümleri.
Geçersiz uygulama durumu algılandığında, doğrulama kodu olabilir [uygun bir şekilde çağrı uygulama kodu durum adresine bağlı][check-app].
Veya kod yazmayı değil tercih ederseniz tanıtıcı geçersiz uygulamayı kullanır, Dotfuscator de Ekle [telemetri raporlama] [ check-telemetry] ve [yanıt] [ check-action] kaynak kodunuzu kendilerine herhangi bir değişiklik gerektirmeden davranışları.

Bu aynı yöntemleri çoğunu zorlamak için de kullanılabilir [yaşam son son tarihleri] [ shelflife] değerlendirme veya deneme yazılım.

## <a name="application-monitoring"></a>Uygulama İzleme

Bir uygulama geliştirirken, kullanıcılar, beta Test edenlere ve önceki sürümlerin kullanıcıları dahil olmak üzere davranış desenlerini anlaşılması önemlidir.
Uygulama analizi ne sıklıkta uygulama kullanılan izlemenize olanak tanır ve kullanıldığı nasıl hangi hatalar dahil olmak üzere Müşteri deneyimi.

Dotfuscator CE Ekle [özel durum izleme][exceptions], [oturum izleme][sessions], ve [özelliği izleme] [ features] uygulamanıza kod.
Çalıştırdığınızda, işlenen uygulamanın yapılandırılan bir için analiz verileri iletebileceği [PreEmptive tarafından Analytics endpoint][endpoints].

## <a name="see-also"></a>Ayrıca Bkz.

[Bu konuda tam Dotfuscator CE Kullanıcı Kılavuzu][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[assemblies]:  https://docs.microsoft.com/en-us/dotnet/standard/assembly-format
[uwp]:  https://www.preemptive.com/blog/article/856-uwp-applications-in-dotfuscator-ce/91-dotfuscator-ce
[xamarin]:  https://www.preemptive.com/obfuscating-xamarin-with-dotfuscator

[upgrades]:  upgrades.md

[obfuscation]:  https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_overview.html
[renaming]:  https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_renaming.html

[analytics]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_overview.html
[endpoints]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_overview.html#endpoints

[checks]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html
[check-app]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html#app-notification
[check-action]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html#action

[tamper]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_tamper.html
[debug]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_debug.html
[root]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_root.html
[shelflife]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_shelflife.html
[exceptions]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_exceptions.html
[sessions]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_sessions.html
[features]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_features.html
[check-telemetry]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_checks.html

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_capabilities.html