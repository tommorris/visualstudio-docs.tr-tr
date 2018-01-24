---
title: "Mac için Visual Studio yükleme | Microsoft Docs"
description: "Mac ve platformlar arası geliştirme için gerekli ek bileşenleri için Visual Studio yükleme konusunda yönergeler."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.openlocfilehash: 5de4760b001e82a0c95c593c1308746946b2c630
ms.sourcegitcommit: 65f85389047c5a1938b6d5243ccba8d4f14362ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="setup-and-install-visual-studio-for-mac"></a>Kurulum ve Mac için Visual Studio yükleme

## <a name="setup"></a>Kurulum

Başlangıç yerel geliştirmek için Visual Studio için Mac var. yüklediğinizde platformlar arası uygulamaları yüklemek ve hazırlık ayarlamak şunları bulunur.

Visual Studio iOS ile çalışmak için şu gerekir:

* bir Mac macOS Sierra 10,12 veya üzeri
* Xcode 8.3 veya üstü. En yeni kararlı sürüm genellikle önerilir.
* Bir Apple kimliği Bir Apple kimliği zaten yoksa https://appleid.apple.com en yeni bir tane oluşturabilirsiniz. Yükleme ve Xcode imzalamak için bir Apple kimliği sağlamak gereklidir.

## <a name="install"></a>Yükleme

1. Mac için Visual Studio indirme [https://www.visualstudio.com/](https://www.visualstudio.com/)

2. Yükleyici paketi İndirildikten sonra tıklatın **VisualStudioInstaller.dmg** yükleyici bağlamanız ve ardından çalıştırın logoyu tıklatarak tarafından aşağıdaki resimde gösterildiği gibi dosya:

  ![Yükleyici iletişim](media/installer-image1.png)

3. Aşağıdaki görüntüye benzer bir uyarı iletişim kutusuyla istenebilir. Bu durumda, tıklatın **açık**:

  ![Uyarı iletişim kutusu](media/installer-image2.png)

4. Yükleyici hangi bileşenlerin yüklenmesi veya güncelleştirilmesi gereken doğrulamak için sisteminizi inceler:

  ![Sisteminizin değerlendirme](media/installer-image3.png)

5. Ardından gizlilik ve lisans koşullarını kabul isteyen bir uyarı iletişim kutusu ile sunulur. Tuşuna **devam** düğmesi koşulları kabul etmek için:

  ![Lisans iletişim](media/installer-image4.png)

6. Yükleyici, eksik ve, karşıdan yüklenip gerek gerekli bileşenleri listesini gösterir. Burada indirmek istediğiniz ürünleri seçin:

  ![Öğeleri seçin](media/installer-image5.png)

  Tüm platformlar yüklemek istiyor musunuz yüklemek için hangi platformlar karar vermenize yardımcı olması için aşağıdaki kılavuzu kullanın:

  * **Xamarin kullanarak uygulamaları**:
      - Xamarin.Forms – Select **Android** ve **iOS** platformlar.
      - iOS yalnızca – seçin **iOS** platform (yüklemeniz gerekecek Not [ **Xcode**](https://developer.apple.com/xcode/)).
      - Android yalnızca – seçin **Android** platform (ilgili bağımlılıkları da seçmelisiniz unutmayın).
      - Mac yalnızca – seçin **macOS** platform (yüklemeniz gerekecek Not [ **Xcode**](https://developer.apple.com/xcode/)).
      - Tam olarak platformlar arası Xamarin uygulamaları – seçin **Android**, **iOS**, ve **macOS** platformlar.
  * **.NET core uygulamaları** – Select **.NET Core** platform.
  * **ASP.NET Core Web uygulamaları** – Select **.NET Core** platform.
  * **Platformlar arası Unity oyununuzu geliştirme** – hiçbir ek platformlar Mac için Visual Studio yüklenmesi gerekmez Başvurmak [Unity kurulum kılavuzunu](~/setup-vsmac-tools-unity.md) Unity uzantısı yükleme hakkında daha fazla bilgi.

  Bu yükleme ekranında, sürüm ve tek tek her bileşen boyutunu görüntüler. (Android için) bu bileşen için bağımlılıkları listesini görüntülemek için (.NET Core) yüklemeleri ek paketler Bkz her bileşene tıklayın veya (iOS ve macOS) gerekli ek uygulamaları görüntüleyin:

  ![Android ek bağımlılıklar](media/installer-image6.png)

7. Seçiminiz ile Mutluluk duyuyoruz sonra seçeneğini **yükleme ve güncelleştirme** yükleme işlemini başlatmak için düğmesi.

8. Yükleyici yüklemeyi başlatır ve işlem seçilen öğelerin yükleyin:

  ![Yüklemesi başlatılıyor](media/installer-image7.png)

  ![Xamarin.Mac yükleniyor](media/installer-image8.png)

  ![Yükleme tamamlanıyor](media/installer-image9.png)

9. Yüklemeyi tamamlamak için gereken bileşenleri tek tek gerekli izinleri yükseltmesine istenebilir. Yükleme işlemine devam etmek için yönetici kimlik bilgilerinizi buraya girin:

  ![Yükleyici ile devam etmek için izinleri girin](media/installer-image10.png)

10. Yükleme başarılı olduktan sonra tuşlarına basarak Visual Studio'daki uygulamaları geliştirmeye başlayabilirsiniz **Başlat**:

  ![Açık Visual Studio](media/installer-image11.png)

> [!NOTE]
Öğesini yüklemeyin bir platform veya aracı özgün yükleme sırasında (bunu #6. adımda unselecting tarafından) seçerseniz, çalıştırmalısınız [yükleyici](https://www.visualstudio.com/vs/) yeniden bileşenleri daha sonra eklemek istiyorsanız.


## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Visual Studio Mac için bir güvenlik duvarı veya proxy sunucunun arkasındaki yükleyin.

Visual Studio Mac için bir güvenlik duvarının arkasında yüklemek için belirli uç noktaları, yazılım güncelleştirmeleri ve gerekli araçlar yüklemeleri izin vermek üzere erişilebilir yapılması gerekir.

Aşağıdaki konumlardan erişmesine izin vermek için ağınızı yapılandırın:

* [Visual Studio uç noktaları](/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)

## <a name="next-steps"></a>Sonraki Adımlar

Mac için Visual Studio yükleme, uygulamalarınız için kod yazma başlatmanıza olanak verir. Aşağıdaki kılavuzlar, yazma ve projelerinizi dağıtma sonraki adımları boyunca size yol göstermesi için sağlanır.

### <a name="ios"></a>iOS

1. [Merhaba, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)
2. [Cihaz sağlama](https://developer.xamarin.com/guides/ios/getting_started/installation/device_provisioning)(cihazda uygulamanızı çalıştırmak için).


### <a name="android"></a>Android

1. [Xamarin Android SDK Yöneticisi'ni kullanma](https://developer.xamarin.com/guides/android/getting_started/installation/android-sdk/?ide=xs)
2. [Android SDK öykünücüsü](https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/)
4. [Aygıtı geliştirme için ayarlama](https://developer.xamarin.com/guides/android/getting_started/installation/set_up_device_for_development/)

### <a name="net-core-apps-aspnet-core-web-apps-unity-game-development"></a>.NET core uygulamaları, ASP.NET Core web uygulamaları, Unity oyun geliştirme

Diğer iş yükleri için başvurmak [iş yükleri](~/workloads.md) sayfası.