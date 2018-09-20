---
title: Visual Studio ve Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 1da4064f-af69-472c-8f31-98484be5f790
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: caf1ea462cc69366f11e4768003707e9cc263327
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495745"
---
# <a name="visual-studio-and-xamarin"></a>Visual Studio ve Xamarin

Xamarin yerel iOS, Android ve Windows uygulamaları için mobil uygulama geliştirme platformu olan uygulamalardan genel C# / .NET kod tabanı. Xamarin ile yazılmış uygulamalar neredeyse % 100 yeniden kod platformlar arasında %75 elde edebilirsiniz. Bu uygulamalar, temel alınan platform API'lerini tam erişimi vardır ve yerel kullanıcı arabirimleri birleştirebilirsiniz. Bunlar, platforma özgü paket çalışma zamanı performans üzerinde çok az etki ile derleyin. (Not: Xamarin de destekleyen F #, ancak bu belgeler üzerinde C# yalnızca odaklanır. Visual Basic şu anda desteklenmiyor.)

Geliştiriciler C#, .NET ve Visual Studio ile tanıdık aynı güç ve üretkenlik Xamarin ile mobil uygulamalar için çalışırken keyfini çıkarın. Bu avantajlar uzaktan Android, iOS ve Windows cihazlarında Objective-C ya da Java gibi yerel kodlama dilleri öğrenmek zorunda kalmadan hata ayıklamayı içerir. Küçük şaşkınlık ve ardından, güzel kullanıcı arabirimleri ile diğer birçok yüksek performanslı uygulamaları olan — NASCAR, Aviva ve MixRadio gibi — Xamarin kullanılarak oluşturulan.

Bu belge tam gücünden değerlendirmenize yardımcı olur. **Xamarin ile Visual Studio** bu deneyimler oluşturun.

-   İle başlayan [Kurulum ve yükleme](../cross-platform/setup-and-install.md), (genellikle Internet bağlantınızı, ne zaten yüklediyseniz ve Seçenekler hızına bağlı olarak 2-4 saat) biraz zaman alır bir işlem.

-   Yükleyicileri çalışırken yapabilecekleriniz [Xamarin ile mobil geliştirme hakkında bilgi edinin](learn-about-mobile-development-with-xamarin.md) hangi bahsedin, Xamarin, karşılaştırma yerel UI için Xamarin.Forms ve diğer doğası hakkında.

-   Yükleme tamamlandıktan sonra [Xamarin ortamınızı doğrulama](../cross-platform/verify-your-xamarin-environment.md).

-   Son öğreticide giderek [Visual Studio'da Xamarin.Forms ile uygulama oluşturmaya yönelik temel bilgileri öğrenin](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).

Tüm Xamarin özelliklerini kullanarak çalışabilir [herhangi bir Visual Studio 2017 sürümünü](https://visualstudio.microsoft.com/vs) (Community, Professional ve Enterprise). Ayrı bir lisans gereklidir.

> [!NOTE]
>  Bu yönergeler, Windows ve Visual Studio arka plana sahip geliştiriciler için kolay ve en kolay bilgisayar yapılandırması açıklanmaktadır. Yalnızca internet paylaşımlı cihaz ve iOS simülatörü kullanmak için Mac ile etkileşim kurmak gerektiğinden bu yapılandırma ile genel geliştirme deneyimini basitleştirir. Bunun yerine bir Mac arka planından gelen, Visual Studio'yu Parallels veya VMWare içinde çalışan veya Mac için Visual Studio kullanarak önerilir Başvurmak [Kurulum, yükleme ve Doğrulamalar Mac kullanıcıları için](../cross-platform/setup-install-and-verifications-for-mac-users.md) yönergeler için.

> [!NOTE]
>  HTML ve CSS tabanlı bir platformlar arası geliştirme çözümü arıyorsanız, Visual Studio Araçları Apache Cordova için açıklandığı gibi kontrol [Visual Studio'da platformlar arası geliştirme](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#HTML).