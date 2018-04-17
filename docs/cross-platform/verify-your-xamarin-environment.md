---
title: Xamarin ortamınızı doğrulayın | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: fd39882e-06d1-4b39-80d2-4d07b6e4f8f5
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 862af0d8912811aee8e0110b48fa8cc3e8f1c06b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="verify-your-xamarin-environment"></a>Xamarin ortamınızı doğrulayın

Yükleyicileri tamamladıktan sonra (bkz [Kurulum ve yükleme](../cross-platform/setup-and-install.md)), her şeyi Xamarin geliştirme deneyimi için hazır olduğunu doğrulamak için birkaç dakikanızı ayırın.  
  
 Yüklemeyi doğrulama tamamladıktan sonra ya da aşağıdaki izlenecek deneyin:  
  
-   [Visual Studio'da Xamarin.Forms ile uygulama oluşturma temellerini öğrenin](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md) bir Xamarin.Forms uygulaması oluşturmak için.
  
-   [Xamarin Visual Studio kullanarak yerel kullanıcı Arabirimi ile uygulamalar oluşturma](../cross-platform/build-apps-with-native-ui-using-xamarin-in-visual-studio.md) yerel kullanıcı arabirimleri her platformda kullanın, ancak bir .NET standart kitaplığında biraz kod paylaşmak için.
  
## <a name="all-platforms"></a>Tüm platformlar 
 
Visual Studio'da ilk seçin **Araçlar > Uzantılar ve güncelleştirmeler** ve Xamarin bileşenleri güncelleştirmeleri kullanmanızın gerekli olup olmadığını denetleyin.  
  
Ardından, Visual Studio kullanarak yeni bir Xamarin.Forms çözümünü oluşturun. **Dosya > Yeni proje**. İletişim kutusunda, genişletin **Visual C# > platformlar arası**seçin **mobil uygulama (Xamarin.Forms)**, Tamam'ı tıklatın. Aşağıdaki iletişim kutusunda, seçin **boş uygulama**. Altında **kod paylaşımı stratejisini**seçin **.NET standart**. Tamam'ı tıklatın.

Bu eylemler dört projelerle bir çözümü oluşturun: paylaşılan bir .NET standart 2.0 kitaplığı proje ve uygulama projeleri Android, iOS ve evrensel Windows Platformu (UWP):  
  
![Boş uygulama Xamarin.Forms şablondan yeni bir proje oluşturma sonuçlarını](../cross-platform/media/crossplat-xamarin-verify-1.png "CrossPlat Xamarin doğrula 1")  
   
## <a name="android"></a>Android  
  
1. En son Android SDK Araçları giderek yüklü olup olmadığını kontrol edin **Araçlar > Android > Android SDK Manager**. En yeni sürümler, Android SDK Araçları, Android SDK platformu araçları ve Android SDK derleme araçlarını yükleyin. Her zaman en son Android API düzeyi yüklemek gerekli değildir. Gereksinim duyduğunuz API düzeyi hedeflemek istediğiniz platform düzeyi bağlıdır. Genel olarak, Xamarin platform yüklendiğinde gerektirdiği Android platformu düzeyi yüklenir.  
  
2.  Derleme ve bir cihaz veya öykünücü hata ayıklama doğrulama:  
  
    -   Çözüm Gezgini'nde Android projesine sağ tıklatın ve **başlangıç projesi olarak ayarla**.  
  
    -   Araç çubuğunda bir kullanılabilir Android aygıtlar ve Öykünücüler listesini içeren aşağı açılır görmeniz gerekir. 
    
    Android cihazlar USB hata ayıklama cihazın ayarları sayfasının Geliştirici seçenekleri için etkinleştirilmesi gerekir. Cihaz ardından USB kablosuyla bilgisayara eklenir. 
    
    Ayrıca Öykünücüler listelenmiştir. Aygıtları veya Visual Studio Öykünücüler birini seçin:

  ![Hata ayıklama hedefi olarak Android için Visual Studio öykünücüsü seçme](../cross-platform/media/crossplat-xamarin-verify-3.png "CrossPlat Xamarin doğrulayın 3")  
  
  Daha ayrıntılı bilgi için bkz: [Android için giriş Visual Studio öykünücüsü](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/12/introducing-visual-studio-s-emulator-for-android.aspx) (Visual Studio ALM blog). Çalışmak için bkz: öykünücü almada sorunlarla karşılaşmanız halinde [Android için Visual Studio öykünücüsü sorun giderme](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md). Seçerek öykünücüsü yeni cihaz profilleri oluşturabilirsiniz **Araçlar > Android > Android Emulator Manager**.  
  
3. Derleme ve Android cihaz veya öykünücü program dağıtmak için F5 tuşuna basın.
  
## <a name="windows"></a>Windows 
  
1.  Çözüm Gezgini'nde Evrensel Windows projesine sağ tıklatın ve **başlangıç projesi olarak ayarla**.  

2.  İçinde **çözüm platformları** açılan listesinde, select **x86** veya **x64**. Seçin **yerel makine**.

3.  Masaüstüne program dağıtmak için F5 tuşuna basın.
  
## <a name="ios"></a>iOS  
  
1.  Mac açıklandığı gibi Visual Studio ile eşleştirilmiş ve ağ üzerindeki kullanılabilir olduğundan emin olun [Mac bilgisayara bağlayarak](/xamarin/ios/get-started/installation/windows/connecting-to-mac/).  
  
2.  Çözüm Gezgini'nde iOS projesine sağ tıklatın ve **başlangıç projesi olarak ayarla**.  
  
3.  Seçin **iPhoneSimulator** aşağıda gösterildiği gibi Visual Studio'nun yapı açılan listeden hedef veya **iPhone** bir Mac için internet paylaşımlı cihaz varsa, hedef   
  
 ![Hedef derleme iPhoneSimulator seçerek](../cross-platform/media/crossplat-xamarin-verify-5.png "CrossPlat Xamarin 5 doğrulayın") 

 Hiçbir benzeticileri listelenmiyorsa, Mac, select Xcode başlatma **Xcode > Tercihler**, tıklatıp **karşıdan**. Altında **bileşenleri** , başlık indirilebilir simulator sürümleri görmeniz gerekir. Hata ayıklama için ek yönergeler bulunur [iOS hata ayıklama](/xamarin/ios/deploy-test/debugging-in-xamarin-ios/?tabs=vsmac#Debugging_on_the_Simulator) sayfası.
  
4.  Bir öykünücü cihaz hedef Visual Studio açılan listeden seçin:

 ![Bir iPhone hata ayıklama hedefi seçme](../cross-platform/media/crossplat-xamarin-verify-6.png "CrossPlat Xamarin 6 doğrulayın")

5. Hata ayıklayıcı F5 tuşuna basarak başlatın. Benzetici, burada hata ayıklama Visual Studio'da gerçekleşirken uygulamayla etkileşim kuracağınızı Mac üzerinde başlatılır. Bir fiziksel iPhone veya iPad mac'e bağlı varsa listesinde görünür ve bunun yerine seçebilirsiniz. Herhangi bir aygıt veya listelenen benzeticileri görmüyorsanız, Mac bağlantısını denetleyin 1. adımda bağlı makalesini gözden geçirin veya gitmek **Araçlar > iOS > Mac çifti**  
  
6.  Mac bilgisayara bağlayarak sorunlarla karşılaşırsanız, okuma [bağlantı sorunlarını giderme](/xamarin/ios/get-started/installation/windows/connecting-to-mac/troubleshooting/).  
  
7.  "İmzalama anahtarlarının yüklü iOS yüklü hiçbir sağlama profilleri Eşleştir" bildiren bir hata görürseniz, aşağıdaki önerileri deneyin:  
  
  - Apple kimliği hesabınızı, açıklandığı gibi Mac xcode'da eklendiğini denetleyin [hesabınız ekleme Xcode için](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppStoreDistributionTutorial/AddingYourAccounttoXcode/AddingYourAccounttoXcode.html#//apple_ref/doc/uid/TP40013839-CH40-SW1) (apple.com).  Hesabınızı eklendikten sonra Visual Studio ve Xcode yeniden başlattığınızdan emin olun.  
    
  - İOS imzalama sekmesini iOS proje özelliklerinde paket, özel yetkilendirme alan etkin hata ayıklama yapılandırması boş olduğundan emin olun.  Not: Bu ayar, yukarıdaki hata iletisini karşılaştıysanız kaldırma yalnızca denemelisiniz.  
  
  ![CrossPlat Xamarin doğrulayın 8](../cross-platform/media/crossplat-xamarin-verify-8.png "CrossPlat Xamarin 8 doğrulayın")  
