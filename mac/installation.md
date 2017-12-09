---
title: "Mac için Visual Studio yükleme | Microsoft Docs"
description: "Mac ve platformlar arası geliştirme için gerekli ek bileşenleri için Visual Studio yükleme konusunda yönergeler."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 22B1F2CD-32AE-464D-80AC-C8AB4786B015
ms.openlocfilehash: 7f91a28449ffad135058438ec767095818cc8527
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
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

## <a name="manual-installation"></a>El ile yükleme

Yükleme başarısız olursa veya herhangi bir tek bileşeni yüklemenizin başarısız olursa, el ile yükleme ile bu sorunu çözmek mümkün olabilir. Gerekli bileşenleri görüntülemek ve her biri karşıdan yüklemek için aşağıdaki adımları uygulayın:

1. Visual Studio yükleyicisi ikinci ekranında, menü çubuğundaki gidin ve seçin **görünümü el ile yükleme yönergeleri**:

    ![El ile gösteren seçeneği menü öğesini yükleyin](media/installer-image12.png)

2. Karşıdan yükle ve bileşenlerini el ile yüklemek için yönergeleri izleyin:

  ![El ile yükleme iletişim kutusu](media/installer-image13.png)

## <a name="install-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Visual Studio Mac için bir güvenlik duvarı veya proxy sunucunun arkasındaki yükleyin.

Visual Studio Mac için bir güvenlik duvarının arkasında yüklemek için belirli uç noktaları, yazılım güncelleştirmeleri ve gerekli araçlar yüklemeleri izin vermek üzere erişilebilir yapılması gerekir.

Aşağıdaki konumlardan erişmesine izin vermek için ağınızı yapılandırın:

* [Visual Studio uç noktaları](https://docs.microsoft.com/visualstudio/install/install-visual-studio-behind-a-firewall-or-proxy-server)