---
title: Visual Studio ve Xamarin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1da4064f-af69-472c-8f31-98484be5f790
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: e84f946915328eb0ee5a49e690b2ee520d29e968
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-and-xamarin"></a>Visual Studio ve Xamarin
Xamarin olan yerel iOS, Android ve Windows için mobil uygulama geliştirme platformu uygulamalardan ortak C# / .NET yaklaşık % 100 kodun yeniden platformlar arasındaki %75 elde taban, kod. Xamarin, C# ile yazılmış uygulamaların temel platform API'leri tam erişimi ve yerel kullanıcı arabirimleri derleme ve çalışma zamanı performans üzerinde çok az etkisi şekilde platforma özgü paketler derleme olanağı vardır. (Not: Xamarin de destekler F #, ancak bu belgeleri C# üzerinde yalnızca odaklanır. Visual Basic şu anda desteklenmiyor.)  
  
 Yine de, daha iyi geliştiriciler C# .NET ve Visual Studio ile tanıdık aynı güç ve üretkenlik Android, iOS ve Windows cihazlarda uzaktan hata ayıklama dahil olmak üzere, mobil uygulamaları için Xamarin ile çalışırken, keyfini çıkarın — yerel kodlama öğrenin gerek kalmadan Objective-C ya da Java gibi diller. Küçük beklenmedik biçimde, böylece güzel kullanıcı arabirimleri ile diğer birçok yüksek performanslı uygulamalar olan — NASCAR, Aviva ve MixRadio gibi — Xamarin kullanılarak oluşturulmuş.  
  
 Bu belge özelliklerinin tamamı değerlendirmenize yardımcı **Xamarin ile Visual Studio** bu deneyimleri oluşturmak için.  
  
-   İle başlayan [Kurulum ve yükleme](../cross-platform/setup-and-install.md), bir işlemin (genellikle Internet bağlantınızın, hangi zaten yüklediyseniz ve Seçenekler hızına bağlı olarak 2-4 saat) biraz zaman alabilir.  
  
-   Yükleyicileri çalıştırırken yapabilecekleriniz [xamarin'le mobil geliştirme hakkında bilgi edinin](../cross-platform/learn-about-mobile-development-with-xamarin.md) hangi söyleyin, Xamarin, karşılaştırma yerel UI Xamarin.Forms ve daha fazlasını doğası hakkında.  
  
-   Yükleme tamamlandıktan sonra [Xamarin ortamınızı doğrulayın](../cross-platform/verify-your-xamarin-environment.md).  
  
-   Son öğreticide giderek [Xamarin.Forms Visual Studio ile uygulama oluşturma temellerini öğrenin](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).  
  
 Tüm Xamarin özellikleriyle birlikte çalışabilir [herhangi bir sürümünü Visual Studio 2015](https://www.visualstudio.com/vs-2015-product-editions) (Community, Professional ve Enterprise). Ayrıca 31 Mart 2016, itibariyle Xamarin ile Visual Studio 2015'in tüm sürümlerinde bulunur ve artık ayrı bir lisans gerektirir unutmayın. Visual Studio 2013 için Xamarin yükleyebilmek için ayrı ayrı olarak [Kurulum ve yükleme](../cross-platform/setup-and-install.md) konuda açıklanmaktadır.  
  
> [!NOTE]
>  Bu yönergeler, Windows ve Visual Studio bir arka plan olanlar için kolay ve en kolay bilgisayar yapılandırması açıklanmaktadır. Yalnızca iOS simülatörü ve internet paylaşımlı cihaz kullanmayı Mac ile etkileşim kurmak için gerekli olduğundan, bu yapılandırma ile genel geliştirme deneyimi basitleştirilmiştir. Bunun yerine bir Mac arka planından geliyorsa, Visual Studio Parallels/VMWare içinde çalışan veya Xamarin Studio Community kullanarak öneririz. Başvurmak [Kurulum, yükleme ve Doğrulamalar Mac kullanıcıları için](../cross-platform/setup-install-and-verifications-for-mac-users.md) yönergeler için.  
  
> [!NOTE]
>  HTML ve CSS dayalı bir platformlar arası geliştirme çözümü arıyorsanız, Visual Studio Araçları Apache Cordova için açıklandığı gibi denetleyin [Visual Studio'da platformlar arası geliştirme](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#HTML).