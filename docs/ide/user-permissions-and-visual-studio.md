---
title: "Kullanıcı izinleri ve Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
ms.assetid: 70485ed7-6342-41bf-8250-7a6826e21b98
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3cf223b0b4d2f8ca710a5d5fdb349c7a423b1b86
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="user-permissions-and-visual-studio"></a>Kullanıcı İzinleri ve Visual Studio
Güvenlik nedenleriyle, mümkün oldukça Visual Studio'yu normal bir kullanıcı olarak çalıştırmanız gerekir.  

> [!WARNING]
>  Ayrıca güvenilir bir kişi ya da güvenilir bir konumdan gelmeyen herhangi bir Visual Studio çözümüyle derleme, başlatma veya hata ayıklama yapmadığınızdan emin olmalısınız.  

 Normal bir kullanıcı olarak Visual Studio IDE içinde hemen her şeyi yapabilirsiniz, ancak şu görevleri tamamlamak için yönetici izinlerine sahip olmanız gerekir:  

|Alan|Görev|Daha fazla bilgi için|  
|----------|----------|--------------------------|  
|Yükleme|Visual Studio yükleyin.|[Visual Studio'yu yükleyin](../install/install-visual-studio.md)|  
||Yerel Yardım içeriğini yükleme, güncelleştirme veya kaldırma.|[Yerel İçeriği Yükleme ve Yönetme](../ide/install-and-manage-local-content.md)|  
|Uygulama türleri|SharePoint çözümleri geliştirme.|[SharePoint Çözümleri Geliştirmek için Gereksinimler](/office-dev/office-dev/requirements-for-developing-sharepoint-solutions)|  
||Geliştirici lisansı alınırken [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)].|[Bir geliştirici lisansı alma](http://go.microsoft.com/fwlink/?LinkID=241313)|  
|Araç Kutusu|Klasik COM ekleme denetimleri için **araç**.|[Araç Kutusunu Kullanma](../ide/using-the-toolbox.md)|  
|Eklentiler|IDE'de klasik COM kullanılarak yazılmış eklentileri yükleme ve kullanma.|[Eklentiler ve sihirbazları oluşturma](http://msdn.microsoft.com/Library/c5a47c21-6668-4de3-898d-afa969317e73)|  
|Oluşturma|Bir bileşeni kayıt ettiren oluşturma sonrası olayları kullanma.|[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](/cpp/ide/understanding-custom-build-steps-and-build-events)|  
||C++ projeleri oluşturduğunuzda kayıt adımı ekleme.|[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](/cpp/ide/understanding-custom-build-steps-and-build-events)|  
|Hata Ayıklama|Yükseltilmiş izinlerle çalışan uygulamalarda hata ayıklama.|[Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)|  
||ASP.NET web siteleri gibi farklı bir kullanıcı hesabı altında çalışan uygulamalarda hata ayıklama.|[ASP.NET ve AJAX uygulamalarında hata ayıklama](../debugger/debugging-aspnet-and-ajax-applications.md)|  
||XAML Tarayıcı Uygulamaları (XBAP) için bölgede hata ayıklama.|[WPF Konağı (PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|  
||Microsoft Azure için bulut hizmeti projelerinde hata ayıklama için öykünücü kullanma.|[Bir bulut hizmeti Visual Studio'da hata ayıklama](http://go.microsoft.com/fwlink/?LinkId=266725)|  
||Uzaktan hata ayıklama için bir güvenlik duvarı yapılandırma.|[Uzaktan hata ayıklama](../debugger/remote-debugging.md)|  
|Performans araçları|Uygulama profili oluşturma.|[Performans profili oluşturma Başlangıç Kılavuzu](../profiling/beginners-guide-to-performance-profiling.md)|  
|Dağıtım|Yerel bir bilgisayarda Internet Information Services'a (IIS) web uygulaması dağıtma.|[Visual Studio veya Visual Web Developer kullanılarak bir barındırma sağlayıcısına ASP.NET Web uygulaması dağıtma: bir Test ortamı olarak IIS dağıtma](http://go.microsoft.com/fwlink/?LinkId=266478)|

## <a name="running-visual-studio-as-an-administrator"></a>Visual Studio'yu Yönetici olarak çalıştırma  
 IDE'yi her başlattığınızda Visual Studio'yu yönetim izinleri ile başlatabilir veya uygulama kısayolunu her zaman yönetim izinleriyle çalışacak şekilde değiştirebilirsiniz. Daha fazla bilgi için bkz. Windows Yardımı.  

#### <a name="to-run-visual-studio-with-administrative-permissions-on-includewin8debuggerincludeswin8mdmd-includewin81debuggerincludeswin81mdmd-includewinserver8debuggerincludeswinserver8mdmd-or-includewinblueserver2ideincludeswinblueserver2mdmd"></a>Visual Studio Yönetici izinleriyle çalıştırmak için [!INCLUDE[win8](../debugger/includes/win8_md.md)], [!INCLUDE[win81](../debugger/includes/win81_md.md)], [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)], veya[!INCLUDE[winblue_server_2](../ide/includes/winblue_server_2_md.md)]  

1.  Üzerinde **Başlat** ekranında, yazın **Visual Studio**. Yüklediğiniz Visual Studio sürümünü veya sürümlerini görmeniz gerekir.  

2.  Başlatmak istediğiniz Visual Studio sürümünü seçin ve kısayol menüsünü görüntüleyin (ekranın en altında görünür). Seçin **yönetici olarak çalıştır**.  

     Visual Studio başladığında **(Yönetici)** sonra ürün adı başlık çubuğunda görünür.  

#### <a name="to-run-visual-studio-with-administrative-permissions-on-includewin7debuggerincludeswin7mdmd-or-includewinsvr08r2debuggerincludeswinsvr08r2mdmd"></a>Visual Studio Yönetici izinleriyle çalıştırmak için [!INCLUDE[win7](../debugger/includes/win7_md.md)] veya[!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)]  

1.  Üzerinde **Başlat** menüsünde seçin **tüm programlar**.  

2.  İçinde **Microsoft Visual Studio** *sürüm* klasörü seçin **Visual Studio** *sürüm* kısayol menüsünü açın ve ardından seçin **Yönetici olarak çalıştır**.  

     Visual Studio başladığında **(Yönetici)** sonra ürün adı başlık çubuğunda görünür.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşıma, geçirme ve Visual Studio projelerini yükseltme](../porting/port-migrate-and-upgrade-visual-studio-projects.md)   
 [Visual Studio'yu yükleyin](../install/install-visual-studio.md)
