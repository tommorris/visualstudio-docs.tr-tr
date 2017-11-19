---
title: "Mac için Visual Studio Tanıtımı | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 3A130EC1-DD8C-4125-9034-B08D7AF7EA65
ms.openlocfilehash: bc836806e1acf33b35604419ac1d6aad41a2d795
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="introducing-visual-studio-for-mac"></a>Mac için Visual Studio Tanıtımı

Mac için Visual Studio modern, sofistike IDE taşınabilir, masaüstü ve web uygulamaları oluşturmak için birçok özelliklere sahip olur. Geliştirme aşağıdakileri destekler:

* .NET ile Mobile: Android, iOS, tvOS, watchOS
* Mac Masaüstü uygulamaları
* .NET core uygulamaları
* ASP.NET Core Web uygulamaları
* Platformlar arası Unity oyunlar

Bir zengin Düzenleyicisi, hata ayıklama, iOS, Mac ve Android ile yerel platform tümleştirme içerir ve kaynak denetimi birkaçı özelliklerinin ad tümleşik.

Bu konu, Mac, platformlar arası uygulamalar oluşturmak için güçlü bir araç olun özelliklerinden bazıları bakma sağlamak için Visual Studio çeşitli bölümlerini araştırmalarını.

## <a name="installation"></a>Yükleme

Adımları [yükleme](~/installation.md) indirmek ve Mac için Visual Studio Yükleme Kılavuzu

## <a name="language-support"></a>Dil desteği

Mac için Visual Studio geliştirme, C# ve F #'ta, varsayılan olarak destekler.

### <a name="c"></a>C#

C# en yaygın olarak dil Mac için Visual Studio'da platformlar arası uygulamalar oluşturmak için kullanılır Bu, tüm C# 7 özellikleri için tam destek içerir.

### <a name="f"></a>F#

F # .NET üzerinde çalışması için tasarlanmış bir kesin türü belirtilmiş işlevsel programlama dilidir. Android, Mac ve İos'ta Mac kullanıcıları için Visual Studio bir programlama dili olarak kullanılabilir. F # kullanma ve dilde oluşturulmuş örnekleri görmek için daha fazla bilgi için [F #](https://developer.xamarin.com/guides/cross-platform/fsharp/) kılavuzları.

## <a name="platform-support"></a>Platform desteği

## <a name="net-core"></a>.NET Core

[.NET Core](https://www.microsoft.com/net/core#macos), Windows, Linux ve Mac üzerinde çalıştırılan uygulamalar oluşturmaya yönelik bir platformdur. Mac için Visual Studio’da, .NET Core projelerini yükleme, oluşturma, çalıştırma ve bu projelerde hata ayıklama desteği bulunmaktadır.

.NET Core projelerini çalıştırmak için .NET Core SDK'yi karşıdan yüklenip.

.NET Core desteği şunları içerir:

* C# ve F# IntelliSense.
* Konsol, kitaplık ve web uygulamaları için .NET Core proje şablonları.
* Kesme noktaları, çağrı yığını ve izleme penceresi gibi özellikler de dahil olmak üzere tam hata ayıklama desteği.
* NuGet PackageReferences ve MSBuild tabanlı geri yükleme.
* .NET Core SDK ile birlikte gelen Visual Studio Test platformu ile tümleşik birim testi çalıştırma ve hata ayıklama desteği sınar.
* Eski project.json biçimi geçiş.

Başlamak için ASP.NET Core web uygulamalarını denetleyin [uygulamalı Laboratuvar](https://github.com/Microsoft/vs4mac-labs/tree/master/Web/Getting-Started).

## <a name="xamarin"></a>Xamarin

[Xamarin](https://developer.xamarin.com/) için birinci sınıf destekle Android, macOS, iOS, tvOS ve watchOS için zengin yerel deneyimler geliştirebilirsiniz. Xamarin.Forms platformlar arası uygulamaları, yerel işlevselliğe erişimi sınırlamadan Android, iOS ve macOS arasında XAML tabanlı UI kodunu paylaşmanıza yardımcı olur.

Başlamak için mobil uygulamaları denetleyin [uygulamalı Laboratuvar](https://github.com/Microsoft/vs4mac-labs/tree/master/Mobile/Getting-Started).

### <a name="android"></a>Android

Visual Studio tümleşik kendi Android SDK manager vardır.

Android uygulamaları için Mac için Visual Studio ile Android çalışır kendi Tasarımcısı içeren `.axml` görsel olarak kullanıcı arabirimleri oluşturmak için dosyaları. Mac için Visual Studio bu dosyaları, aşağıda gösterildiği gibi kendi Android Tasarımcısı'nda, açılır:

![](media/intro-image31.png)

Android designer bkz: hakkında daha fazla bilgi için [Tasarımcısı genel bakış](https://developer.xamarin.com/Android/Guides/User_Interface/Designer_Overview) belge.

### <a name="ios"></a>iOS

İOS Tasarımcısı Mac için Visual Studio ile tamamen tümleşiktir ve .xib ve iOS, tvOS ve WatchOS Uı'lar ve geçişler oluşturmak için film şeridi dosya görsel düzenleme sağlar. Tüm kullanıcı arabirimi, olayları işlemek için sezgisel bir yaklaşım kullanırken araç ve tasarım yüzeyi arasında sürükle ve bırak işlevi kullanılarak oluşturulabilir. Tasarımcı de destekler iOS [özel denetimler](https://developer.xamarin.com/guides/ios/user_interface/designer/ios_designable_controls_overview/) avantaj tasarım zamanı işleme ile.

![](media/intro-image30.png)

İOS Tasarımcısı kullanma hakkında daha fazla bilgi için başvurmak [Tasarımcısı](https://developer.xamarin.com/guides/ios/user_interface/designer) belgeleri.

### <a name="mac"></a>Mac

Xamarin yerel Mac API bağlamaları güzel Mac uygulamalar oluşturmanıza olanak sağlar.

Mac için Visual Studio ile Mac uygulamaları yazma hakkında daha fazla bilgi için bkz [Xamarin.Mac](https://developer.xamarin.com/guides/#mac) belgeleri.

## <a name="gaming"></a>Oyun

Mac için Visual Studio Unity 5.6.1 ile platformlar arası oyunlar geliştirme desteği sağlar.

Başlamak için Unity denetleyin [uygulamalı Laboratuvar](https://github.com/Microsoft/vs4mac-labs/tree/master/Unity/Getting-Started).

## <a name="enterprise-features"></a>Kurumsal özellikler

> [!Note]
> Bu ürün yalnızca Visual Studio Enterprise abonelik ile kullanılabilir.

### <a name="profiler"></a>Profil Oluşturucu

Xamarin profil oluşturucu profil oluşturma için üç Instruments kullanılabilir sahiptir. [Xamarin profil oluşturucu giriş](https://developer.xamarin.com/guides/cross-platform/deployment,_testing,_and_metrics/xamarin-profiler/) Kılavuzu ne bu Instruments ölçmek ve bunlar uygulamanızı nasıl analiz inceler ve her ekranda sunulan veriler anlamını açıklar.

### <a name="inspector"></a>Denetleyici

Xamarin denetçisi bir etkileşimli C# Konsolu araçları ile kullanıcılara sağlar. Bu hata ayıklama veya tanılama Yardımı olarak dinamik uygulamalar, bir belge veya bir deney aracını olarak öğretme aracı olarak incelerken kullanılabilir.

![](media/intro-inspector.png)

Çeşitli programlama platformlarında (Android, iOS, Mac ve Windows), IDE hata ayıklama akışına tümleştirme yanı sıra hedefleyen bir zengin C# Konsolu sağlayan bir tek başına uygulaması oluşur.

Daha fazla bilgi için bkz [Xamarin denetçisi](https://developer.xamarin.com/guides/cross-platform/inspector/) Kılavuzu.

## <a name="next-steps"></a>Sonraki adımlar

* **Büyük resim alma** - Mac için Visual Studio'da bulunan önemli özelliklerin çoğunu özetini almak için Visual Studio Mac için bkz [IDE Turu](~/ide-tour.md).
* **Kurulum** - indirin ve Visual Studio yükleme, bkz: hakkında bilgi almak için [yükleme](~/installation.md) Kılavuzu.
* **Xamarin öğreticileri** - Xamarin Git nasıl kod Xamarin ile geliştirme hakkında daha fazla bilgi için [Geliştirici Merkezi](https://developer.xamarin.com).
* **Videolar** - Mac için diğer özellikler ve Visual Studio yönlerini hakkında daha fazla bilgi için üzerinde videosuna göz atın [Xamarin University](https://university.xamarin.com) Web sitesi.
* **Uygulamalı Labs** - Mac için Visual Studio'da bulunan çeşitli iş yükleri ile çalışmaya başlamak için kullanıma [uygulamalı labs](https://github.com/Microsoft/vs4mac-labs).