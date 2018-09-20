---
title: Xamarin ortamınızı doğrulama | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: fd39882e-06d1-4b39-80d2-4d07b6e4f8f5
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: e46da7cf39ad816f70454983c56dd5751981f741
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495771"
---
# <a name="verify-your-xamarin-environment"></a>Xamarin ortamınızı doğrulama

Yükleyicileri tamamladıktan sonra (bkz [Kurulum ve yükleme](../cross-platform/setup-and-install.md)), her şeyi Xamarin geliştirme deneyimi hazır olduğunu doğrulamak için birkaç dakikanızı ayırın.

 Yüklemenin doğrulanması tamamladıktan sonra aşağıdaki izlenecek her ikisi de ya da deneyin:

-   [Visual Studio'da Xamarin.Forms ile uygulama oluşturmaya yönelik temel bilgileri öğrenin](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md) bir Xamarin.Forms uygulaması derlemek için.

-   [Visual Studio'da Xamarin kullanarak yerel bir kullanıcı Arabirimi olan uygulamalar geliştirmenize](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md) her platformda yerel kullanıcı arabirimleri kullanabilirsiniz ancak bir .NET Standard Kitaplığı'ndaki bazı kod paylaşın.

## <a name="all-platforms"></a>Tüm platformlar

Visual Studio'da ilk seçin **Araçları** > **Uzantılar ve güncelleştirmeler** ve Xamarin bileşenleri güncelleştirmeleri kullanmanızın gerekli olup olmadığını denetleyin.

Ardından, Visual Studio kullanarak yeni bir Xamarin.Forms çözümü oluşturma **dosya** > **yeni proje**. İletişim kutusunda Genişlet **Visual C#** > **platformlar arası**seçin **mobil uygulama (Xamarin.Forms)**, tıklatıp **Tamam**. Aşağıdaki iletişim kutusunda, seçmek **boş uygulama**. Altında **kod paylaşımı Stratejisi'ni**seçin **.NET Standard**. **Tamam**'ı tıklatın.

Bu Eylemler, dört projeyle bir çözümü oluşturun: paylaşılan bir .NET Standard 2.0 kitaplık projesi ve Android, iOS ve evrensel Windows Platformu (UWP) uygulaması projelerinde:

![Boş uygulama Xamarin.Forms şablondan yeni bir proje oluşturma sonuçlarını](../cross-platform/media/crossplat-xamarin-verify-1.png "CrossPlat Xamarin doğrula 1")

## <a name="android"></a>Android

1. En son Android SDK araçlarının giderek yüklü olup olmadığını denetleyin **Araçlar > Android > Android SDK Yöneticisi**. Android SDK Tools, Android SDK Platform araçları ve Android SDK derleme araçları en yeni sürümlerini yükleyin. Her zaman en son Android API düzeyi yüklemek gerekli değildir. Gereksinim duyduğunuz API düzeyi hedeflemek istediğiniz platformu düzeyine bağlıdır. Genel olarak, Xamarin platformunu yüklendiğinde, gerektirdiği Android platform düzeyi yüklenir.

2.  Derleme ve bir cihaz veya öykünücü üzerinde hata ayıklama doğrulama:

    -   Çözüm Gezgini'nde Android projesine sağ tıklayıp **başlangıç projesi olarak ayarla**.

    -   Araç çubuğunda, kullanılabilir Android cihazlar ve Öykünücüler listesini içeren açılan listesi görürsünüz.

    Android cihazlarında USB hata ayıklama cihazın ayarlar sayfasının Geliştirici seçenekleri için etkinleştirilmesi gerekir. Cihaz ardından bilgisayara USB kablosuyla bağlı.

    Ayrıca öykünücüleri listelenmiştir. Cihazları veya Visual Studio öykünücü birini seçin:

  ![Hata ayıklama hedefi olarak Android için Visual Studio öykünücüsü'nü seçin](../cross-platform/media/crossplat-xamarin-verify-3.png "CrossPlat Xamarin doğrulayın 3")

  Daha ayrıntılı bilgi için bkz. [Karşınızda Visual Studio Emulator for Android](https://blogs.msdn.microsoft.com/devops/2014/11/12/introducing-visual-studios-emulator-for-android/) Microsoft DevOps blogunda. Çalışmak için bkz öykünücü sorun karşılaşmanız halinde [Android için Visual Studio öykünücü sorun giderme](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md). Seçerek ve öykünücüsü için yeni cihaz profilleri oluşturabilirsiniz **Araçlar > Android > Android öykünücü yöneticisi**.

3. Tuşuna **F5** derlemek ve program Android cihazınıza veya öykünücünüze dağıtmak için.

## <a name="windows"></a>Windows

1.  Evrensel Windows projesi Çözüm Gezgini'nde sağ tıklayıp **başlangıç projesi olarak ayarla**.

2.  İçinde **çözüm platformları** açılan listesinde, select **x86** veya **x64**. Seçin **yerel makine**.

3.  Tuşuna **F5** masaüstüne program dağıtmak için.

## <a name="ios"></a>iOS

1.  Ağ üzerinde kullanılabilir ve üzerinde açıklandığı gibi Visual Studio ile eşleştirilmiş Mac'inizde olduğundan emin olun [Mac bilgisayara bağlayarak](/xamarin/ios/get-started/installation/windows/connecting-to-mac/).

2.  Çözüm Gezgini'nde iOS projesine sağ tıklayıp **başlangıç projesi olarak ayarla**.

3.  Seçin **iPhoneSimulator** hedefleyen Visual Studio'nun derleme açılan listeden, aşağıda gösterildiği gibi veya **iPhone** mac'e tethered tamamen bir cihaz varsa hedef

 ![Hedef derleme iPhoneSimulator seçerek](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin 5 doğrulayın")

 Mac bilgisayarınızda, select Xcode hiçbir simülatörleri listede yoksa, başlatma **Xcode** > **tercihleri**, tıklatıp **indirme**. Altında **bileşenleri** , başlık indirilebilir simülatör sürümleri görmelisiniz. Hata ayıklama için ek yönergeler bulunabilir [iOS hata ayıklama](/xamarin/ios/deploy-test/debugging-in-xamarin-ios) sayfası.

4.  Visual Studio açılan listeden bir öykünücü cihaz hedefi seçin:

 ![Bir iPhone hata ayıklama hedefi seçme](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin 6 doğrulayın")

5. Hata ayıklayıcı basarak başlatın **F5**. Burada Visual Studio'da hata ayıklama işlem sırasında uygulamayla etkileşim kuracağınızı Mac üzerinde simülatör başlatılmadı. Bir fiziksel iPhone veya iPad Mac bilgisayara bağlı varsa, listede görünür ve bunun yerine seçebilirsiniz. Herhangi bir cihaz veya simülatör listelenen görmüyorsanız, Mac bağlantısını denetleyin. 1. adımda bağlı makalesini gözden geçirin veya Git **Araçları** > **iOS** > **Mac ile eşleştir**

6.  Mac bilgisayara bağlayarak sorunlarla karşılaşırsanız, okuma [bağlantı sorunlarını giderme](/xamarin/ios/get-started/installation/windows/connecting-to-mac/troubleshooting/).

7.  "İmzalama anahtarı yüklü iOS yüklü hiçbir sağlama profili eşleşen" belirten bir hata görürseniz, aşağıdaki önerileri deneyin:

  - Apple kimliği hesabınızı Xcode Mac üzerinde açıklandığı eklendiğini denetlemek [hesabınızı eklemek için Xcode](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).  Hesabınızı ekledikten sonra hem Visual Studio hem de Xcode yeniden emin olun.

  - İçinde iOS imzalama sekmesine iOS proje özelliklerinde paket, özel yetkilendirme alan etkin hata ayıklama yapılandırması boş olduğunu doğrulayın.  Not: yalnızca yukarıdaki hata iletisi karşılaştığınız varsa bu ayarı kaldırma denemeniz gerekir.

  ![CrossPlat Xamarin doğrulayın 8](../cross-platform/media/crossplat-xamarin-verify-8.png "CrossPlat Xamarin 8 doğrulayın")
