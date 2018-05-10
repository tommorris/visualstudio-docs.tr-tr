---
title: Mac için Visual Studio kaldırma
description: Mac ve ilgili araçlar için Visual Studio kaldırmak için yönergeler.
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.technology: vs-ide-install
ms.assetid: 4EB95F75-BC2E-4982-9564-2975805712D8
ms.openlocfilehash: 14afeefac0bb5aa198b2f62ba00ba85831b23ffb
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="uninstalling-visual-studio-for-mac"></a>Mac için Visual Studio kaldırma

Platformlar arası uygulama geliştirme, Mac için Visual Studio gibi tek başına uygulamalar dahil olmak üzere etkinleştirme Xamarin ürünleri dizi vardır

Bu kılavuz, her ürünün ayrı ayrı ilgili bölümüne giderek kaldırmak için kullanılabilir. Bu kılavuzu izleyerek tüm Xamarin araç takımı kaldırılabilir tüm aracılığıyla.

Xamarin Studio makinenize yüklü önceden varsa, size ayrıca'ndaki yönergeleri izleyin gerekebilir [kaldırma](https://developer.xamarin.com/guides/cross-platform/getting_started/installation/uninstalling_xamarin/) developer.xamarin.com üzerinde aşağıdaki adımları ayrıca Kılavuzu.

## <a name="uninstall-script"></a>Komut dosyası kaldırma

Visual Studio kaldırabilirsiniz ve ilişkili bileşenlerinden birini kullanarak Git [betik kaldırma](https://raw.githubusercontent.com/MicrosoftDocs/visualstudio-docs/master/mac/resources/uninstall-vsmac.sh).

Bu kaldırma komut dosyası makalesinde bulabilirsiniz komutlarının çoğunu içerir. Komut dosyası iki ana atlamalar vardır ve olası dış bağımlılıklar nedeniyle bulunmamaktadır:

- **Mono kaldırma**
- **Android AVD kaldırma**

Komut dosyasını çalıştırmak için aşağıdaki adımları uygulayın:

1. Sağ tıklatın ve komut dosyası **Kaydet...** Mac dosyayı kaydetmek için
2. Terminali açın ve komut dosyasını indirdiğiniz için çalışma dizini değiştirin:

    ```bash
    $ cd /location/of/file
    ```
3. Komut dosyası yürütülebilir ve Çalıştır ile **sudo**:

    ```bash
    $ chmod +x ./uninstall-vsmac.sh
    $ sudo ./uninstall-vsmac.sh
    ```
4. Son olarak, kaldırma komut dosyası silin.

## <a name="uninstall-visual-studio-for-mac"></a>Mac için Visual Studio kaldırma

Visual Studio Mac kaldırma ilk adımı bulmaktır **Visual Studio.app** içinde **/Applications** directory sürükleyin **çöp kutusu**. Alternatif olarak, sağ tıklatın ve seçin **taşımak için çöp** aşağıdaki görüntüde gösterildiği gibi:

![Çöp Kutusu Visual Studio uygulamaya taşı](media/uninstall-image1.png)

Bu uygulama paketi silme olabilir olsa da hala bir dosya sistemi için Xamarin ile ilgili diğer dosyaları Visual Studio, Mac için kaldırır.

Mac için Visual Studio tüm izlerini kaldırmak için aşağıdaki komutları terminale çalıştırılmalıdır:

```bash
sudo rm -rf "/Applications/Visual Studio.app"
rm -rf ~/Library/Caches/VisualStudio
rm -rf ~/Library/Preferences/VisualStudio
rm -rf ~/Library/Preferences/Visual\ Studio
rm -rf ~/Library/Logs/VisualStudio
rm -rf ~/Library/VisualStudio
rm -rf ~/Library/Preferences/Xamarin/
rm -rf ~/Library/Developer/Xamarin
rm -rf ~/Library/Application\ Support/VisualStudio
rm -rf ~/Library/Application\ Support/VisualStudio/7.0/LocalInstall/Addins/
```

## <a name="uninstall-mono-sdk-mdk"></a>Mono SDK'sı (MDK) kaldırma

Mono Microsoft .NET Framework'ün açık kaynak uygulamasıdır ve tüm Xamarin Products—Xamarin.iOS, Xamarin.Android ve Xamarin.Mac tarafından bu platformlar geliştirilmesini C# ' ta izin vermek için kullanılır.

> [!WARNING]
> Ayrıca Unity gibi Mono kullanan diğer uygulamalar Visual Studio dışında Mac için vardır.
> Başka bir bağımlılık üzerinde Mono kaldırmadan önce emin olun.

Mono Framework bir makineden kaldırmak için terminale aşağıdaki komutları çalıştırın:

```bash
sudo rm -rf /Library/Frameworks/Mono.framework
sudo pkgutil --forget com.xamarin.mono-MDK.pkg
sudo rm -rf /etc/paths.d/mono-commands
```

## <a name="uninstall-xamarinandroid"></a>Xamarin.Android kaldırma

Bir Android SDK ve Java SDK'sı gibi Xamarin.Android kullanımını ve yükleme için gerekli öğe sayısı vardır.

Xamarin.Android kaldırmak için aşağıdaki komutları kullanın:

```bash
sudo rm -rf /Developer/MonoDroid
rm -rf ~/Library/MonoAndroid
sudo pkgutil --forget com.xamarin.android.pkg
sudo rm -rf /Library/Frameworks/Xamarin.Android.framework
```

### <a name="uninstall-android-sdk-and-java-sdk"></a>Android SDK ve Java SDK kaldırma

Android SDK'sı, Android uygulamaları geliştirme için gereklidir. Android SDK'ın tüm bölümleri tamamen kaldırmak için dosyasını bulun **~/Library/Developer/Xamarin/** ve taşımak **çöp**.

Bunu zaten Mac OS X bir parçası olarak önceden paketlenmiş gibi Java SDK'sı (JDK) kaldırılması, gerekmez / macOS.

### <a name="uninstall-android-avd"></a>Android AVD kaldırma

> [!WARNING]
> Ayrıca Android AVD ve Android Studio gibi bu ek android bileşenleri kullanan diğer uygulamalar Visual Studio dışında Mac için vardır.
> Bu dizin kaldırma Android Studio'da bölüneceği projeleri neden olabilir. 

Tüm Android AVDs ve ek Android kaldırmak için bileşenleri aşağıdaki komutu kullanın:

```bash
rm -rf ~/.android
```

Kaldırmak için yalnızca Android AVDs aşağıdaki komutu kullanın:

```bash
rm -rf ~/.android/avd
```

 

## <a name="uninstall-xamarinios"></a>Xamarin.iOS kaldırma

Xamarin.iOS iOS C# veya F # Mac için Visual Studio ile kullanarak uygulama geliştirme sağlar.

Aşağıdaki komutları terminale tüm Xamarin.iOS dosyaları dosya sisteminden kaldırmak için kullanın:

```bash
rm -rf ~/Library/MonoTouch
sudo rm -rf /Library/Frameworks/Xamarin.iOS.framework
sudo rm -rf /Developer/MonoTouch
sudo pkgutil --forget com.xamarin.monotouch.pkg
sudo pkgutil --forget com.xamarin.xamarin-ios-build-host.pkg
sudo pkgutil --forget com.xamarin.xamarin.ios.pkg
```

## <a name="uninstall-xamarinmac"></a>Xamarin.Mac kaldırma

Xamarin.Mac makinenizden Mac lisansıyla ve ürün sırasıyla yok etmek aşağıdaki iki komutu kullanılarak kaldırılabilir:

```bash
sudo rm -rf /Library/Frameworks/Xamarin.Mac.framework
rm -rf ~/Library/Xamarin.Mac
```

## <a name="uninstall-workbooks-and-inspector"></a>Çalışma kitapları ve Inspector kaldırma

1.2.2 ile başlayarak, Xamarin çalışma kitaplarını & Denetçisi terminal durumundan çalıştırarak kaldırılabilir:

```bash
sudo /Library/Frameworks/Xamarin.Interactive.framework/Versions/Current/uninstall
```

Eski sürümleri için aşağıdaki yapılar el ile kaldırmanız gerekir:

* Çalışma kitapları uygulamaya Sil `"/Applications/Xamarin Workbooks.app"`
* Inspector uygulamaya Sil `"Applications/Xamarin Inspector.app"`
* Eklentileri silin: `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Interactive"` ve `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Inspector"`
* Inspector silin ve destek dosyaları burada: `/Library/Frameworks/Xamarin.Interactive.framework` ve `/Library/Frameworks/Xamarin.Inspector.framework`

## <a name="uninstall-the-xamarin-profiler"></a>Xamarin profil oluşturucu kaldırma

```bash
sudo rm -rf "/Applications/Xamarin Profiler.app"
```

## <a name="uninstall-the-visual-studio-installer"></a>Visual Studio yükleyicisi kaldırma

Xamarin Evrensel yükleyici tüm izlerini kaldırmak için aşağıdaki komutları kullanın:

```bash
rm -rf ~/Library/Caches/XamarinInstaller/
rm -rf ~/Library/Caches/VisualStudioInstaller/
rm -rf ~/Library/Logs/XamarinInstaller/
rm -rf ~/Library/Logs/VisualStudioInstaller/
rm -rf ~/Library/Preferences/Xamarin/
rm -rf "~/Library/Preferences/Visual Studio/"
```
