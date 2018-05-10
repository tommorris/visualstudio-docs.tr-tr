---
title: Visual Studio için Xamarin Studio üzerinden Mac yararları
description: Bu makalede, Visual Studio Mac için Xamarin Studio sağlayan avantajları ve özellikler açıklanmaktadır
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 6ACF5FD4-D5C1-4050-95E3-467C753F25F1
ms.openlocfilehash: 63f8e0f03797f08383ad3a1ec2b9303a405ed236
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="benefits-of-visual-studio-for-mac-over-xamarin-studio"></a>Visual Studio için Xamarin Studio üzerinden Mac yararları 
 
Visual Studio Mac için Xamarin Studio Mac üzerinde tam özellikli bir IDE olarak değiştirilmiştir Web uygulamaları ve Hizmetleri, platformlar arası mobil ve Masaüstü uygulamaları ve oyunları geliştirmenize olanak tanıyan özellikler sağlar. Ayrıca, Azure'a yayımlama veya Azure işlevlerin oluşturulması anlamına olup Azure ile çok kolay tümleştirme kolaylaştırır. Her şeyin tam özellikli Kaynak Düzenleyici, güçlü bir hata ayıklayıcı, özelleştirilebilir bir çalışma alanı, git tümleştirmesi ve yerel olarak Mac için tasarlanmış zengin uzantı sistemi de dahil olmak üzere modern bir IDE gelen beklediğiniz sahip

Diğer özellikler şunlardır:

* Roslyn tabanlı C# yeniden düzenleme, Çözümleyicileri ve kod düzeltmeleri IntelliSense,
* NuGet tabanlı paket Yönetimi
* Visual Studio uyumlu proje biçimi
* MSBuild yapı altyapısı
* Tümleşik birim testi
* F # out-of--box desteği

## <a name="language-support"></a>Dil Desteği

C# 7 kod Mac'inizde yazma yalnızca Visual Studio Mac için sunulan

## <a name="net-core"></a>.NET Core

[.NET Core](https://www.microsoft.com/net/core#macos), Windows, Linux ve Mac üzerinde çalıştırılan uygulamalar oluşturmaya yönelik bir platformdur. Mac için Visual Studio’da, .NET Core projelerini yükleme, oluşturma, çalıştırma ve bu projelerde hata ayıklama desteği bulunmaktadır.

.NET core, Mac ve kutunun dışında works için Visual Studio ile yüklenir.

.NET Core desteği şunları içerir:

* C# ve F# IntelliSense.
* Konsol, kitaplık ve web uygulamaları için .NET Core proje şablonları.
* Kesme noktaları, çağrı yığını ve izleme penceresi gibi özellikler de dahil olmak üzere tam hata ayıklama desteği. 
* NuGet paket referanslarını ve MSBuild tabanlı geri yükleme. 
* .NET Core SDK ile birlikte gelen Visual Studio Test platformu ile tümleşik birim testi çalıştırma ve hata ayıklama desteği sınar. 
* Eski project.json biçimi geçiş. 
* .NET standart proje desteği.

## <a name="web-development"></a>Web geliştirme  

### <a name="aspnet-core"></a>ASP.NET Core 

Mac için Visual Studio dışında kutusunu MVC ve Web API projeleri için ASP.NET Core şablonlar içerir.
 
![HTML IntelliSense](media/benefits-vsmac-over-xs-image3.png)

Mac için Visual Studio ayrıca yeni web HTML, CSS ve JSON dosyaları için araç desteği ekler. 

### <a name="html"></a>HTML 

* Yeni HTML şablonu. 
* Geliştirilmiş akıllı girintileme ve biçimlendirme. 
* Geliştirilmiş renklendirme. 
* Geliştirilmiş IntelliSense. 
* Kod katlama (etkinleştirilmesi gerekir). 
* Küçültmeyi Geri Alma komutu. 
* Geliştirilmiş Kod Şablonları (kod parçacıkları). 
* `<div>` ile seçimi çevreleme. 
* Yukarı/aşağı seçeneği seçili metni yukarı/aşağı taşır. 

### <a name="css"></a>CSS 

* Geliştirilmiş akıllı girintileme ve biçimlendirme. 
* Geliştirilmiş renklendirme. 
* Geliştirilmiş IntelliSense. 
* Kod katlama. 
* Birçok Kod Şablonu (kod parçacıkları). 
* Yukarı/aşağı seçeneği seçili metni yukarı/aşağı taşır. 

### <a name="json"></a>JSON 
* Schemastore.org sitesine erişimle şema seçici. 
* Şemadan doğrulama. 
* Şemadan IntelliSense. 
* Geliştirilmiş akıllı girintileme ve biçimlendirme. 
* Geliştirilmiş renklendirme. 
* Açıklama ekleme/kaldırma. 
* Tırnak ekleme ve ayraç eşleştirme. 
* Yukarı/aşağı seçeneği seçili metni yukarı/aşağı taşır. 

## <a name="publishing-to-azure"></a>Azure'da yayımlamak için

Mac için Visual Studio ile ASP.NET Core web uygulamaları ve Hizmetleri Azure App Service'te yayımlama mümkündür. 

![Azure'a yayımlama](media/benefits-vsmac-over-xs-image1.png)

### <a name="azure-functions"></a>Azure işlevleri

Azure işlevleri kolayca kodu veya İşlevler, küçük parçalarını bulutta çalıştırmak için bir çözüm olur. Mac için Visual Studio code ve yerel olarak hata ayıklama, Azure işlevleri sağlar. Almak için Azure işlevleri bulut altında Ara yeni proje iletişim kutusuna başlatıldı. 

### <a name="docker-support"></a>Docker Desteği

Şimdi, Docker kapsayıcılara ASP.NET Core uygulamaları yayımlamak ve bunları bir Azure uygulama hizmetinden çalıştırın. 

Projenizdeki Docker desteğini etkinleştirmek için ASP.NET Core web uygulamanıza sağ tıklatın ve seçin **Ekle > Docker destek ekleyin**. 

Docker kapsayıcısı için web uygulamanızı yayımlamak için kullanma **Yayımla > Azure Yayımla** Visual Studio'da Mac için sunulan iş akışı

## <a name="source-editor-improvements"></a>Kaynak Düzenleyici geliştirmeleri 

Roslyn tabanlı C# yeniden düzenleme, IntelliSense yanı sıra, Çözümleyicileri ve kod düzeltmeleri, Visual Studio Mac Kaynak Düzenleyici için Xamarin Studio aşağıdaki iyileştirmeleri sağlar: 

### <a name="language-bundles"></a>Dil paketleri 

Mac için Visual Studio TextMate desteği olan (`.tmBundle`) ve 3 sublime (`.sublime`) eklemek için kullanabileceğiniz dil paketleri: 

* Düzenleyici renk temaları 
* Kod parçacıkları 
* Aynı yeni dilleri için vurgulama ve temel IntelliSense'i etkinleştirme 

Bu paketler halinde ekleyebilirsiniz **Tercihler > Metin Düzenleyicisi > dil paketleri**. 

### <a name="color-theme-support"></a>Renk temasını desteği 

Aşağıdaki renk tema biçimlerini Visual Studio'da Mac için desteklenir: 

* Visual Studio (`.vssettings`) 
* Xamarin studio (`.json`) 
* TextMate (`tmTheme`) 

## <a name="unity"></a>Unity 

[Unity](https://unity3d.com/) önde gelen tüm platformlar için yüksek kaliteli platformlar arası 2B ve 3B oyun oluşturmak için kullanabileceğiniz bir oyun oluşturma aracıdır: kaydettiğinde, masaüstü bilgisayarları, konsolları, AR ve VR cihazlar ve hatta web. 

Unity 5.6.1 ile başlayarak, yazma ve Unity oyununuzu hata ayıklamak için Visual Studio Mac için kullanabilirsiniz. Başlamak için Visual Studio Unity'nın 5.6.1 olacak şekilde ayarlayın. komut dosyası Düzenleyicisi. 

Unity için araçlar şunlardır: 

* C# ile yazılmış komut dosyaları için destek. 
* Unity çözüm panel. 
* Bir hata ayıklama, Unity Düzenleyicisi'ni tıklatın. 
* Unity iletileri için IntelliSense. 
* Unity'nın gölgelendiriciler coloration kodu. 
* Unity belgelere erişimi. 

## <a name="xamarin"></a>Xamarin 

Xamarin platformlar arası özellikleri her zaman birinci sınıf özelliği Xamarin Studio kaldırılmış olsa da, yalnızca Visual Studio Mac için kullanılabilir olan Xamarin özellikler vardır 

### <a name="android"></a>Android 

* [Android SDK Yöneticisi](https://developer.xamarin.com/guides/android/application_fundamentals/using-the-sdk-manager/)  
* Android O yalnızca Visual Studio'da Mac için Xamarin Studio desteklenmez 

### <a name="ios-and-mac"></a>iOS ve Mac 

* [iOS imzalama iş akışı güncelleştirmeleri ](https://developer.xamarin.com/guides/cross-platform/macios/apple-account-management/) 
    * İmzalama kimlikleri oluşturmak ve bunları yerel Anahtarlığa yükleyin. 
    * Sağlama profilleri oluşturun. 
    * Bir imza kimliği için varolan bir profili ekleyin.
    *  Cihazları hazırlamanızı: Apple Geliştirici Portalı'nda bir cihaz kaydetme ve sağlama profiline ekleyin.
* iOS 11, watchOS 4 ve tvOS 2 yalnızca Visual Studio'da Mac için Xamarin Studio desteklenmez 
* MacOS yüksek Sierra yalnızca Visual Studio'da Mac için Xamarin Studio desteklenmez 

### <a name="cross-platform"></a>Çoklu Platform 

* [Xamarin Live Player](https://developer.xamarin.com/guides/cross-platform/live/)