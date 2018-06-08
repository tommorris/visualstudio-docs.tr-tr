---
title: Yönetici olarak çalıştır
ms.date: 06/05/2018
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
ms.openlocfilehash: 89ba7338645ab6cc421716832a3d6f424bb57dfc
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844397"
---
# <a name="user-permissions-and-visual-studio"></a>Kullanıcı izinleri ve Visual Studio

Güvenlik nedenleriyle, normal bir kullanıcı olarak mümkün olduğunda Visual Studio çalıştırmanız gerekir.

> [!WARNING]
> Ayrıca güvenilir bir kişi ya da güvenilir bir konumdan gelmeyen herhangi bir Visual Studio çözümüyle derleme, başlatma veya hata ayıklama yapmadığınızdan emin olmalısınız.

Visual Studio IDE içinde neredeyse her şeyi normal bir kullanıcı olarak yapabilirsiniz. Aşağıdaki görevleri tamamlamak için yönetici izinlerine sahip olmanız gerekir:

|Alan|Görev|Daha fazla bilgi için|
|----------|----------|--------------------------|
|Yükleme|Visual Studio yükleyin.|[Visual Studio'yu yükleyin](../install/install-visual-studio.md)|
||Yükleme, güncelleştirme veya yerel Yardım içeriği kaldırma.|[Yükleme ve yerel Yardım içeriği yönetme](../ide/install-and-manage-local-content.md)|
|Uygulama türleri|SharePoint çözümleri geliştirmek.|[SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md)|
|Araç Kutusu|Klasik COM denetimleri ekleme **araç**.|[Araç Kutusu](../ide/reference/toolbox.md)|
|Oluşturma|Bir bileşenini kaydettirin sonrası derleme olaylarını kullanma.|[Özel derleme adımları anlayın ve derleme olayları](/cpp/ide/understanding-custom-build-steps-and-build-events)|
||C++ projeleri oluşturma sırasında bir kayıt adımı içerir.||
|Hata Ayıklama|Yükseltilmiş izinler ile çalışan uygulamaları hata ayıklama.|[Hata ayıklayıcısı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)|
||Farklı bir kullanıcı altında bir farklı çalıştır hesabı, ASP.NET Web siteleri gibi uygulamalarda hata ayıklama.|[ASP.NET ve AJAX uygulamalarda hata ayıklama](../debugger/debugging-aspnet-and-ajax-applications.md)|
||XAML tarayıcısı uygulamaları (XBAP) bölgesinde ayıklama.|[WPF Konağı (PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|
||Microsoft Azure için bulut hizmeti projelerinde hata ayıklama için öykünücü kullanın.|[Bir bulut hizmeti Visual Studio'da hata ayıklama](/azure/vs-azure-tools-debug-cloud-services-virtual-machines)|
||Uzaktan hata ayıklama için güvenlik duvarını yapılandırın.|[Uzaktan hata ayıklama](../debugger/remote-debugging.md)|
|Performans araçları|Uygulama profili oluşturma.|[Performans profili oluşturma Başlangıç Kılavuzu](../profiling/beginners-guide-to-performance-profiling.md)|
|Dağıtım|Internet Information Services (IIS) için yerel bir bilgisayardaki bir web uygulaması dağıtın.|[Visual Studio kullanarak bir ASP.NET web uygulaması dağıtma](/aspnet/web-forms/overview/older-versions-getting-started/deployment-to-a-hosting-provider/)|

## <a name="run-visual-studio-as-an-administrator"></a>Visual Studio bir yönetici olarak çalıştır

Visual Studio'yu yönetici olarak çalıştırmanız gerekiyorsa, IDE açmak için şu adımları izleyin:

> [!NOTE]
> Bu yönergeler, Windows 10 için içindir. Bunlar diğer Windows sürümleri için benzerdir.

1. Açık **Başlat** menü ve Visual Studio 2017 gidin.

1. Sağ tıklatın veya bağlam menüsünde **Visual Studio 2017**seçin **daha fazla** > **yönetici olarak çalıştır**.

   Visual Studio başladığında **(Yönetici)** sonra ürün adı başlık çubuğunda görünür.

Her zaman yönetici izinleriyle çalıştırmak için uygulama kısayolunu de değiştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlantı noktası, geçirme ve Visual Studio projelerini yükseltme](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Visual Studio'yu yükleyin](../install/install-visual-studio.md)