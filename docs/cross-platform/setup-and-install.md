---
title: Visual Studio için Xamarin'i yükleyin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: 2cfcad00-352c-4161-814c-f5ae32d8ada8
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 8bbb27ad3368b53fc3e333d3260f2f30551c4177
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251198"
---
# <a name="setup-and-install"></a>Kurulum ve yükleme

Yerel iOS, Android ve Windows oluşturmak için uygulamalardan genel C# / .NET kod tabanı kullanarak Xamarin, aşağıdaki donanım ve yazılımlar gerekiyor:

-   Windows ve Android uygulamaları ile çalışmak için: yüklü bir Windows geliştirme bilgisayarı (sanal makine değil) ile Visual Studio 2017 (Xamarin geliştirme özellikleri dahil).

-   İOS uygulamalarıyla çalışmak için: macOS Sierra 10.12 veya üstünde, yüklü Xcode ve yüklü Mac için Visual Studio ile bir Mac.

Xamarin platformunu kullanılacak ayrı lisans gerekir.

Windows ve Mac bilgisayarları aynı anda ayarlayabilirsiniz ve bu yükleyiciler çalışırken geçtiğiniz [Xamarin ile mobil geliştirme hakkında bilgi edinin](../cross-platform/learn-about-mobile-development-with-xamarin.md) okuyup gerekli arka plan bilgilerini izleyin.

Bu kurulum ve yükleme yaptıktan sonra Xamarin platformunu kullanarak sorunları varsa, sorunuzu gönderin [forums.xamarin.com](http://forums.xamarin.com/).

<a name="prereq" />

## <a name="pre-requisites"></a>Ön koşullar

###  <a name="for-targeting-windows-and-android"></a>Windows ve Android hedeflemek için

Bkz: [Visual Studio 2017 ürün ailesi sistem gereksinimleri](/visualstudio/productinfo/vs2017-system-requirements-vs) Visual Studio 2017'yi yüklemek için ayrıntılı ön koşullar için.

Yüklü tüm güncelleştirmeleri ile Windows 10 çalıştıran fiziksel bir bilgisayardaki Windows (sanal makine değil) Visual 2017'yi yükleyin.

### <a name="for-targeting-ios"></a>İOS hedeflemek için

Hedef iOS öykünücüleri ve cihazlara Windows bilgisayarınızdan bir ağ üzerinden Mac ya da Mac ayrıca gerekir mini macOS 10.12 veya üzerini çalıştıran ve Xcode 8.3. Bkz: [Kurulum ve Mac için Visual Studio yükleme](/visualstudio/mac/installation) daha ayrıntılı gereksinimler için.

<a name="windows" />

##  <a name="windows-setup-visual-studio-and-xamarin"></a>Windows Kurulum (Visual Studio ve Xamarin)

Visual Studio 2017'ı henüz yüklemediyseniz, aşağıdaki adımları uygulayın:

1.  [İndirin ve herhangi bir sürümünü Visual Studio 2017 için yükleyiciyi başlatın](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) (Community, Professional veya Enterprise). Visual Studio 2017 Community'yi ücretsiz bir sürümüdür. Professional ve Enterprise sürümleri 30 gün sonra lisans gerekli olduğu için deneme olarak kullanılabilir.

2.  Zaman **yükleme** iletişim kutusu açılır, aşağıdaki kutuları işaretleyin:

    - **Mobil ve oyun > .NET ile Mobil Geliştirme**. Bu seçenek, çeşitli Android araçları ve yazılım geliştirme setleri da otomatik olarak seçer.

        ![Oyun ve mobil geliştirme altında mobil geliştirme seçeneğini](../cross-platform/media/cross-plat-xamarin-setup-2a.png "çapraz-Plat Xamarin Kurulum 2")

    - (İsteğe bağlı) **Windows > Evrensel Windows platformu geliştirme**.

Zaten Visual Studio 2017'in yüklü ancak Xamarin platformunu henüz yüklemediyseniz, aşağıdaki adımları uygulayın:

1. Çalıştırma **Visual Studio yükleyicisi** gelen **Başlat** menüsü.

2.  Installer içinde **daha fazla** düğmesine ve ardından **Değiştir**:

    ![Visual Studio Kurulumu içinde Değiştir seçeneğini seçerek](../cross-platform/media/cross-plat-xamarin-setup-1a.png "çapraz-Plat Xamarin Kurulum 1")

3.  Zaman **yükleme** iletişim kutusu açılır, kontrol **mobil ve oyun > .NET ile Mobil Geliştirme** ve (isteğe bağlı olarak) **Windows > Evrensel Windows platformu geliştirme**. **.NET ile Mobil Geliştirme** seçeneği var olan bir Xamarin yüklemesini da güncelleştirmeniz.

Yükleme devam ederken, Mac kurulum yönergeleri ile devam edin ve Git [Xamarin ile mobil geliştirme hakkında bilgi edinin](../cross-platform/learn-about-mobile-development-with-xamarin.md).

5.  Yükleme tamamlandıktan sonra Visual Studio ve istenirse bir Microsoft hesabıyla oturum başlatın. Windows ile kullandığınız hesabın aynısını hesabıdır.

6.  Android uygulamalarını test etmek için [Android SDK öykünücüsü](/xamarin/android/get-started/installation/android-emulator/) fiziksel bir Android cihazı yoksa.

<a name="mac" />

##  <a name="mac-setup-apple-id-xcode-and-xamarin"></a>Mac kurulumu (Apple kimliği, Xcode ve Xamarin)

1.  Ücretsiz bir Apple kimliği Oluştur [ https://appleid.apple.com ](https://appleid.apple.com/) zaten yoksa. Yükleme ve Xcode ile imzalama için bu Apple Kimliği gereklidir.

2.  Xcode'dan yükleyip [ https://developer.apple.com/xcode/ ](https://developer.apple.com/xcode/), ve Apple Kimliğinizi üzerinde açıklandığı gibi ekleyin [hesabınızı eklemek için Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).

3.  İndirme ve yönergeleri izleyerek Mac için Visual Studio yükleme [Kurulum ve Mac için Visual Studio yükleme](/visualstudio/mac/installation).

4.  Xamarin hem Windows hem de Mac bilgisayarlara yükleme işlemini tamamladıktan sonra yönergeleri takip edin [Mac bilgisayara bağlayarak](/xamarin/ios/get-started/installation/windows/connecting-to-mac/) Windows bilgisayarda iOS ve Mac Visual Studio'dan ile çalışabilirsiniz.

Her iki bilgisayar aynı yerel ağ üzerinde olmalıdır.
