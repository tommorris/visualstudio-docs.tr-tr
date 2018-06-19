---
title: Visual Studio ve Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 1da4064f-af69-472c-8f31-98484be5f790
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 723518fa837803a5245eef2b227e6d593e8f4447
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34454429"
---
# <a name="visual-studio-and-xamarin"></a>Visual Studio ve Xamarin

Xamarin olan yerel iOS, Android ve Windows için mobil uygulama geliştirme platformu uygulamalardan ortak C# / .NET code tabanı. Xamarin ile yazılmış uygulamalar yaklaşık % 100 kodun yeniden platformlar arasındaki %75 elde edebilirsiniz. Bu uygulamaları temel platform API'leri tam erişimi vardır ve yerel kullanıcı arabirimleri dahil edebilirsiniz. Bunlar, çalışma zamanı performans üzerinde çok az etkisi platforma özgü paketlerle derleyin. (Not: Xamarin de destekler F #, ancak bu belgeleri C# üzerinde yalnızca odaklanır. Visual Basic şu anda desteklenmiyor.)  
  
Geliştiriciler C# .NET ve Visual Studio ile tanıdık aynı güç ve üretkenlik mobil uygulamaları için Xamarin ile çalışırken, keyfini çıkarın. Avantajlar uzaktan Android, iOS ve Windows cihazlarda Objective-C ya da Java gibi yerel kodlama dillerini öğrenmek zorunda kalmadan hata ayıklama içerir. Küçük beklenmedik biçimde, böylece güzel kullanıcı arabirimleri ile diğer birçok yüksek performanslı uygulamalar olan — NASCAR, Aviva ve MixRadio gibi — Xamarin kullanılarak oluşturulmuş.  
  
Bu belge gücünü değerlendirmenize yardımcı **Xamarin ile Visual Studio** bu deneyimleri oluşturmak için.  
  
-   İle başlayan [Kurulum ve yükleme](../cross-platform/setup-and-install.md), bir işlemin (genellikle Internet bağlantınızın, hangi zaten yüklediyseniz ve Seçenekler hızına bağlı olarak 2-4 saat) biraz zaman alabilir.  
  
-   Yükleyicileri çalıştırırken yapabilecekleriniz [xamarin'le mobil geliştirme hakkında bilgi edinin](learn-about-mobile-development-with-xamarin.md) hangi söyleyin, Xamarin, karşılaştırma yerel UI Xamarin.Forms ve daha fazlasını doğası hakkında.  
  
-   Yükleme tamamlandıktan sonra [Xamarin ortamınızı doğrulayın](../cross-platform/verify-your-xamarin-environment.md).  
  
-   Son öğreticide giderek [Xamarin.Forms Visual Studio ile uygulama oluşturma temellerini öğrenin](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).  
  
Kullanarak tüm Xamarin özellik ile çalışabilirsiniz [herhangi bir sürümünü Visual Studio 2017](https://www.visualstudio.com/vs) (Community, Professional ve Enterprise). Ayrı bir lisans gereklidir.  
  
> [!NOTE]
>  Bu yönergeler, Windows ve Visual Studio arka plana sahip geliştiriciler için kolay ve en kolay bilgisayar yapılandırması açıklanmaktadır. Yalnızca Internet paylaşımlı aygıtları ve iOS simülatörü kullanmak için Mac ile etkileşim kurmak için gerekli olduğundan, bu yapılandırma ile genel geliştirme deneyimi basitleştirilmiştir. Visual Studio Parallels veya VMWare içinde çalışan veya Mac için Visual Studio kullanarak bir Mac arka planından yerine gelse öneririz Başvurmak [Kurulum, yükleme ve Doğrulamalar Mac kullanıcıları için](../cross-platform/setup-install-and-verifications-for-mac-users.md) yönergeler için.  
  
> [!NOTE]
>  HTML ve CSS dayalı bir platformlar arası geliştirme çözümü arıyorsanız, Visual Studio Araçları Apache Cordova için açıklandığı gibi denetleyin [Visual Studio'da platformlar arası geliştirme](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#HTML).