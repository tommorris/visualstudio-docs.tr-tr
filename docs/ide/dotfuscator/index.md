---
title: Dotfuscator Community Edition (CE)
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
description: Visual Studio 2017 içinde bulunan boş Dotfuscator Community Edition ile .NET uygulamalarınızın nasıl Koruyabileceğiniz hakkında bilgi edinin.
ms.assetid: d9550502-0a82-49a6-b005-2caa791fbe02
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: douge
ms.openlocfilehash: c34eec9f8eab1f870344ec6995bfcbd8fea8739c
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704402"
---
# <a name="dotfuscator-community-edition-ce"></a>Dotfuscator Community Edition (CE)

*PreEmptive tarafından koruması - Dotfuscator* kapsamlı .NET uygulama koruması, güvenli yazılım geliştirme yaşam döngüsü içine sığar kolayca sağlar.
Masaüstü, mobil, sunucu ve güvenli ticari sırlar ve diğer fikri mülkiyet (IP), yardımcı olmak için embedded uygulamaları Ayıkla sağlamlaştırmak ve korumak için korsanlık ve sahtekarlığın azaltmak ve izinsiz ve yetkisiz hata ayıklama karşı koruma kullan.
Ek programlama veya kaynak kodu bile erişimine gerek kalmadan derlenmiş derlemeleri Dotfuscator çalışır.

![PreEmptive tarafından koruması - Dotfuscator](media/header.svg)

## <a name="why-protection-matters"></a>Koruma neden önemlidir?

Önemlidir **fikri mülkiyet korumak** (IP).
Uygulamanızın kodunu IP kabul edilebilir, tasarım ve uygulama ayrıntıları içerir.
Ancak, .NET Framework uygulamaları yerleşik [önemli meta verileri ve üst düzey Ara kodu içeren][assemblies], bunları ters mühendislik kolaylaşır, yalnızca birini birçok boş kullanarak otomatik Araçları.
Kesintiye ve durdurma ters mühendislik, yetkisiz IP açığa çıkmasını önlemek, aynı zamanda kodunuzu ticari sır içerdiğini gösterir.
Dotfuscator yapabilirsiniz [belirsizleştirirseniz] [ obfuscation] .NET derlemeleriniz özgün uygulama davranışına koruyarak ters mühendislik azaltabilir.

Ayrıca önemlidir **uygulamanızı bütünlüğünü korumak**.
Ters mühendislik ek olarak, uygulamanızın korsanlığını, çalışma zamanında uygulamanın davranışı değiştirmek veya verileri işlemek kötü aktörleri deneyebilir.
Dotfuscator yeteneği uygulamanızla Ekle [algılamak, rapor ve yetkisiz kullanım yanıt][checks]oynama, üçüncü taraf hata ayıklama ve kökü belirtilmiş cihazlar dahil olmak üzere.

PreEmptive tarafından çözümleri Dotfuscator güvenli yazılım geliştirme yaşam döngüsü nasıl uyduğu hakkında daha fazla bilgi için bkz: [SDL uygulama koruması sayfası][sdl-protection].

## <a name="about-dotfuscator-ce"></a>CE Dotfuscator hakkında

Microsoft Visual Studio 2017 kopyanızı bir kopyasını içeren  ***PreEmptive tarafından koruması - Dotfuscator* Community Edition**, Dotfuscator CE, kişisel kullanım için ücretsiz olarak da bilinir.
Dotfuscator ile Visual Studio 2017 dahil CE sürümünü yüklemek yönergeler için bkz: [yükleme sayfası][install].

Dotfuscator CE sunan bir dizi [yazılım koruma ve sağlamlaştırma] [ software-protection] geliştiriciler, mimarlar ve Sınayıcılar için hizmetler.
Örnekleri [.NET gizleme] [ obfuscation] ve diğer [uygulama koruması] [ app-protection] Dotfuscator CE bulunan özellikler şunlardır:

* *[Yeniden adlandırma] [ renaming]*  ters mühendislik derlenmiş derlemelerin daha zor hale tanımlayıcıların.
* *[Koruma yetkisiz değiştirmeye karşı] [ tamper]*  üzerinde oynanmış uygulamaların yürütülmesini algılamak için olay uyarıları iletmek ve değiştirilen oturumlarını sonlandırın.
* *[Anti-debug] [ debug]*  çalışan bir uygulama bir hata ayıklayıcı eki algılamak için olay uyarıları iletmek ve hata ayıklaması oturumlarını sonlandırın.
* *[Hologram root] [ root]*  uygulama kökü belirtilmiş bir Android cihazında çalışıp çalışmadığını Algıla ve bu cihazlarda oturum sonlandırılacak.
* *[Uygulamanın sona erme davranışları] [ shelflife]*  "son yaşam" tarih kodlamak, uygulamaları kendi sona erme tarihinden sonra yürütülür ve süresi dolan uygulama oturumları sonlandırma uyarıları aktarmak.
* *[Özel Durum İzleme] [ exceptions]*  uygulama içinde gerçekleşen işlenmeyen özel durumları izlemek için.
* *[Oturum] [ sessions] ve [özelliği] [ features] kullanımı izleme* uygulamaları atanmış olması belirlemek için yürütülen, bu hangi sürümleri uygulamalar ve bu uygulamaların hangi özelliklerin kullanılır.

Bunlar uygulama koruma stratejinizi nasıl uyduğunu dahil olmak üzere, bu özellikler hakkında bilgi için bkz [özellikleri sayfasında][capabilities].

Dotfuscator CE temel koruma out-of--box sunar.
Daha fazla uygulama koruma önlemlerinin Dotfuscator CE kayıtlı kullanıcılarına ve kullanıcıları için kullanılabilir *PreEmptive tarafından koruması - Dotfuscator* Professional Edition, dünyanın önde gelen [.NET Obfuscator] [net-obfuscator].
Dotfuscator geliştirme hakkında daha fazla bilgi için bkz: [yükseltmeler sayfasında][upgrades].

## <a name="getting-started"></a>Başlarken

Visual Studio'dan Dotfuscator CE'ı kullanmaya başlamak için yazın `dotfuscator` içine **hızlı başlatma** (Ctrl + Q) arama çubuğu.

* Dotfuscator CE zaten yüklediyseniz, **hızlı başlatma** getirir *menü* Dotfuscator CE kullanıcı arabirimini başlatmak için seçeneği. Ayrıntılar için bkz [tam Dotfuscator CE Kullanıcı Kılavuzu'na Başlarken sayfasında][get-started].
* Dotfuscator CE henüz yüklü değilse, **hızlı başlatma** ilgili getirir *yükleme* seçeneği. Bkz: [yükleme sayfası] [ install] Ayrıntılar için.

Ayrıca alabilirsiniz **en son sürümünü** Dotfuscator CE'den, [preemptive.com Dotfuscator indirmeleri sayfasında][download].

## <a name="full-documentation"></a>Tam belgeleri

Bu sayfayı ve alt sayfalarını Dotfuscator CE'in özellikleri, üst düzey bir genel bakış sağlayan yanı [aracı yüklemek için yönergeleri][install].

Bkz: [tam Dotfuscator CE kullanıcı Guide'a preemptive.com] [ full] dahil olmak üzere ayrıntılı kullanım yönergeleri için [Dotfuscator CE kullanıcı arabirimini kullanarak başlatmak nasıl] [ get-started].

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[assemblies]:  https://docs.microsoft.com/en-us/dotnet/standard/assembly-format
[software-protection]:  https://www.preemptive.com/software-protection
[obfuscation]:  https://www.preemptive.com/obfuscation
[app-protection]:  https://www.preemptive.com/application-protection
[sdl-protection]:  https://www.preemptive.com/solutions/SDL-App-Protection
[net-obfuscator]:  https://www.preemptive.com/products/dotfuscator/overview
[download]:  https://www.preemptive.com/products/dotfuscator/downloads

[install]:  install.md
[capabilities]:  capabilities.md
[upgrades]:  upgrades.md

[get-started]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

[renaming]:  https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_renaming.html

[checks]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html
[tamper]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_tamper.html
[debug]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_debug.html
[root]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_root.html
[shelflife]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_shelflife.html

[exceptions]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_exceptions.html
[sessions]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_sessions.html
[features]:  https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_features.html

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/index.html