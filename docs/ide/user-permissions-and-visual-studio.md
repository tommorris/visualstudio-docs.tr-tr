---
title: Kullanıcı izinleri ve Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 168fb9441080a9c8f61d703485b0274d91dc3189
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="user-permissions-and-visual-studio"></a>Kullanıcı izinleri ve Visual Studio

Güvenlik nedenleriyle, mümkün oldukça Visual Studio'yu normal bir kullanıcı olarak çalıştırmanız gerekir.

> [!WARNING]
> Ayrıca güvenilir bir kişi ya da güvenilir bir konumdan gelmeyen herhangi bir Visual Studio çözümüyle derleme, başlatma veya hata ayıklama yapmadığınızdan emin olmalısınız.

Normal bir kullanıcı olarak Visual Studio IDE içinde hemen her şeyi yapabilirsiniz, ancak şu görevleri tamamlamak için yönetici izinlerine sahip olmanız gerekir:

|Alan|Görev|Daha fazla bilgi için|
|----------|----------|--------------------------|
|Yükleme|Visual Studio yükleyin.|[Visual Studio'yu yükleyin](../install/install-visual-studio.md)|
||Yerel Yardım içeriğini yükleme, güncelleştirme veya kaldırma.|[Yükleme ve yerel içeriği yönetme](../ide/install-and-manage-local-content.md)|
|Uygulama türleri|SharePoint çözümleri geliştirme.|[SharePoint çözümleri geliştirmek için gereksinimler](/office-dev/office-dev/requirements-for-developing-sharepoint-solutions)|
||Geliştirici lisansı alınırken [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)].|[Bir geliştirici lisansı alma](http://go.microsoft.com/fwlink/?LinkID=241313)|
|Araç Kutusu|Klasik COM ekleme denetimleri için **araç**.|[Araç Kutusu](../ide/reference/toolbox.md)|
|Eklentiler|IDE'de klasik COM kullanılarak yazılmış eklentileri yükleme ve kullanma.|[Eklentiler ve sihirbazları oluşturma](http://msdn.microsoft.com/Library/c5a47c21-6668-4de3-898d-afa969317e73)|
|Oluşturma|Bir bileşeni kayıt ettiren oluşturma sonrası olayları kullanma.|[Özel derleme adımları anlayın ve derleme olayları](/cpp/ide/understanding-custom-build-steps-and-build-events)|
||C++ projeleri oluşturduğunuzda kayıt adımı ekleme.|[Özel derleme adımları anlayın ve derleme olayları](/cpp/ide/understanding-custom-build-steps-and-build-events)|
|Hata Ayıklama|Yükseltilmiş izinlerle çalışan uygulamalarda hata ayıklama.|[Hata ayıklayıcısı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)|
||ASP.NET web siteleri gibi farklı bir kullanıcı hesabı altında çalışan uygulamalarda hata ayıklama.|[ASP.NET ve AJAX uygulamalarda hata ayıklama](../debugger/debugging-aspnet-and-ajax-applications.md)|
||XAML Tarayıcı Uygulamaları (XBAP) için bölgede hata ayıklama.|[WPF Konağı (PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|
||Microsoft Azure için bulut hizmeti projelerinde hata ayıklama için öykünücü kullanma.|[Bir bulut hizmeti Visual Studio'da hata ayıklama](http://go.microsoft.com/fwlink/?LinkId=266725)|
||Uzaktan hata ayıklama için bir güvenlik duvarı yapılandırma.|[Uzaktan hata ayıklama](../debugger/remote-debugging.md)|
|Performans araçları|Uygulama profili oluşturma.|[Performans profili oluşturma Başlangıç Kılavuzu](../profiling/beginners-guide-to-performance-profiling.md)|
|Dağıtım|Yerel bir bilgisayarda Internet Information Services'a (IIS) web uygulaması dağıtma.|[Visual Studio veya Visual Web Developer kullanılarak bir barındırma sağlayıcısına ASP.NET Web uygulaması dağıtma: bir test ortamı olarak IIS dağıtma](http://go.microsoft.com/fwlink/?LinkId=266478)|

## <a name="run-visual-studio-as-an-administrator"></a>Visual Studio bir yönetici olarak çalıştır

IDE'yi her başlattığınızda Visual Studio'yu yönetim izinleri ile başlatabilir veya uygulama kısayolunu her zaman yönetim izinleriyle çalışacak şekilde değiştirebilirsiniz. Daha fazla bilgi için bkz. Windows Yardımı.

### <a name="run-visual-studio-with-administrative-permissions"></a>Visual Studio Yönetici izinleriyle çalıştırın

Bu yönergeler, Windows 10 için içindir. Bunlar diğer Windows sürümleri için benzerdir.

1. Açık **Başlat** menü ve Visual Studio 2017 gidin.

1. Sağ tıklatın veya bağlam menüsünde **Visual Studio 2017**seçin **daha fazla** > **yönetici olarak çalıştır**.

     Visual Studio başladığında **(Yönetici)** sonra ürün adı başlık çubuğunda görünür.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlantı noktası, geçirme ve Visual Studio projelerini yükseltme](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Visual Studio'yu yükleyin](../install/install-visual-studio.md)