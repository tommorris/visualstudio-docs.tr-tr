---
title: Visual Studio için Xamarin yükleme | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: 2cfcad00-352c-4161-814c-f5ae32d8ada8
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 8ae03dfe4ed2e72015ca1f7d91153d862f44ce40
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="setup-and-install"></a>Kurulum ve yükleme

Yerel iOS, Android ve Windows oluşturmak için uygulamalardan ortak C# / .NET kod tabanını kullanarak Xamarin, aşağıdaki donanım ve yazılımlar gereklidir:

-   Windows ve Android uygulamaları ile çalışmak için: yüklü bir Windows geliştirme bilgisayarla (sanal makine değil) Visual Studio 2017 (Xamarin geliştirme özellikleri dahil).  

-   İOS uygulamaları ile çalışmak için: bir Mac macOS Sierra 10,12 veya üstünde, Xcode yüklü ve yüklü Mac için Visual Studio ile.

Ayrı lisansları Xamarin platform kullanması gerekir.
 
Windows ve Mac bilgisayarları aynı anda ayarlayabilir ve bu yükleyiciler çalışırken, geçebilir [xamarin'le mobil geliştirme hakkında bilgi edinin](../cross-platform/learn-about-mobile-development-with-xamarin.md) okuyup gerekli arka plan malzeme izleyin.

Bu kurulum ve yükleme yaptıktan sonra Xamarin platformu kullanarak sorunları varsa, sorunuzu ileti [forums.xamarin.com](http://forums.xamarin.com/).

<a name="prereq" /> 

## <a name="pre-requisites"></a>Ön koşullar

###  <a name="for-targeting-windows-and-android"></a>Windows ve Android hedefleme

Bkz: [Visual Studio 2017 ürün ailesi sistem gereksinimleri](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs) Visual Studio 2017 yüklemek için ayrıntılı ön koşullar için.

Visual 2017 tüm güncellemelerin yüklü Windows 10 çalıştıran fiziksel bir bilgisayardaki Windows (sanal makine değil) yükleyin. 

### <a name="for-targeting-ios"></a>İOS hedefleme

Hedef iOS Öykünücüler ve cihazlara Windows bilgisayarınız bir ağa bağlı Mac veya Mac ihtiyacınız vardır mini macOS 10.12 veya sonraki sürümünü çalıştıran ve Xcode 8.3. Bkz: [Kurulum ve Mac için Visual Studio](/visualstudio/mac/installation.md) daha ayrıntılı gereksinimler için.

<a name="windows" /> 

##  <a name="windows-setup-visual-studio-and-xamarin"></a>Windows Kurulumu (Visual Studio ve Xamarin)

Visual Studio 2017 henüz yüklemediyseniz, aşağıdaki adımları uygulayın:

1.  [Karşıdan yükleme ve herhangi bir sürümünü Visual Studio 2017 için yükleyiciyi başlatma](https://www.visualstudio.com/downloads/) (Community, Professional veya Enterprise). Visual Studio 2017 ücretsiz sürüm bir topluluktur. Professional ve Enterprise sürümleri için bir lisans gerekli olduğu sonra 30 gün deneme amacıyla kullanılabilir.

2.  Zaman **yükleme** iletişim kutusu görüntülenirse, aşağıdaki onay kutularını işaretleyin:    

    - **Mobil ve oyun > .NET ile Mobil Geliştirme**. Bu seçenek, çeşitli Android araçları ve yazılım geliştirme setleri da otomatik olarak seçer. 

        ![Oyun ve mobil geliştirme altında mobil geliştirme seçeneğini](../cross-platform/media/cross-plat-xamarin-setup-2a.png "arası Plat Xamarin Kurulum 2")

    - (İsteğe bağlı) **Windows > Evrensel Windows platformu geliştirme**. 

Zaten yüklü Visual Studio 2017'ı olan ancak henüz Xamarin platform yüklemediniz, aşağıdaki adımları uygulayın:

1. Çalıştırma **Visual Studio yükleyicisi** gelen **Başlat** menüsü.

2.  Yükleyici içinde tıklatın **daha fazla** düğmesine tıklayın ve ardından **Değiştir**:

    ![Visual Studio yüklemesinde Değiştir seçeneğini belirleyerek](../cross-platform/media/cross-plat-xamarin-setup-1a.png "arası Plat Xamarin Kurulum 1")

3.  Zaman **yükleme** iletişim kutusu görüntülenirse, denetleme **mobil ve oyun > Mobil Geliştirme .NET ile** ve (isteğe bağlı) **Windows > Evrensel Windows platformu geliştirme**. **Mobil geliştirme .NET ile** seçeneği olan bir Xamarin yüklemesi da güncelleştirmeniz.

Yükleme devam ederken Mac Kurulum yönergeleriyle devam etmek ve Git [mobil geliştirme hakkında bilgi edinin Xamarin ile](../cross-platform/learn-about-mobile-development-with-xamarin.md).

5.  Yükleme tamamlandıktan sonra Visual Studio ve istenirse Microsoft hesabınızla oturum açın başlatın. Bu hesap, Windows ile kullandığınız aynı hesabıdır.

6.  Android uygulamaları test etmek için [Android SDK öykünücüsü](/xamarin/android/get-started/installation/android-emulator/) fiziksel bir Android cihazı yoksa. 

<a name="mac" />

##  <a name="mac-setup-apple-id-xcode-and-xamarin"></a>Mac kurulumu (Apple kimliği, Xcode ve Xamarin)

1.  Boş bir Apple kimliği oluşturma [ https://appleid.apple.com ](https://appleid.apple.com/) zaten yoksa. Bu Apple kimliği, yükleme ve Xcode imzalamak için gereklidir.

2.  Xcode gelen yükleyip [ https://developer.apple.com/xcode/ ](https://developer.apple.com/xcode/), Apple Kimliğinizi açıklandığı gibi ekleyin [hesabınız ekleme Xcode için](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).

3.  Karşıdan yükleyip Visual Studio için Mac yönergeleri izleyerek [Kurulum ve Mac için Visual Studio](/visualstudio/mac/installation.md).

4.  Xamarin Windows ve Mac bilgisayarlara yüklenmesini tamamladıktan sonra yönergeleri izleyerek [Mac bilgisayara bağlayarak](/xamarin/ios/get-started/installation/windows/connecting-to-mac/) böylece Windows bilgisayarda iOS ve Mac Visual Studio'dan ile çalışabilirsiniz.

Her iki bilgisayar aynı yerel ağ üzerinde olmalıdır.