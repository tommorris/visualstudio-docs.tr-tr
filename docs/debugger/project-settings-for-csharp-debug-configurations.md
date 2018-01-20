---
title: "Proje ayarları C# hata ayıklama yapılandırmaları için | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debug configurations, C#
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debugging [C#], debugger settings
ms.assetid: e30ca810-66e9-4d6e-9cf6-9f285cd0b100
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 054a015c5fcd6a70696ed6945faa5cbd01547168
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="project-settings-for--c-debug-configurations"></a>C# Hata Ayıklama Yapılandırması Proje Ayarları
Bir C# hata ayıklama yapılandırması proje ayarları değiştirebileceğiniz **özellik sayfaları** anlatıldığı gibi penceresi [hata ayıklama ve dağıtım yapılandırmalarını](../debugger/how-to-set-debug-and-release-configurations.md). Aşağıdaki tablolarda hata ayıklayıcı gizlilikle ilgili ayarların nerede bulacağını Göster **özellik sayfaları** penceresi.  
  
> [!WARNING]
>  Bu konu, UWP uygulamaları için geçerli değil. Bkz: [(VB, C#, C++ ve XAML) bir hata ayıklama oturumu Başlat](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_Debug_tab"></a>Hata ayıklama sekmesi  
  
|**Ayarı**|**Açıklama**|  
|-----------------|---------------------|  
|**Yapılandırma**|Uygulamayı derlemek için modunu ayarlar. Arasından seçim **etkin (hata ayıklama)**, **hata ayıklama**, **sürüm**, **tüm yapılandırmaları**.|  
|**Eylemi Başlat**|Bu denetimler Debug menüsünden Başlat'ı seçtiğinizde gerçekleşecek eylemi belirtir.<br /><br /> -   **Proje başlangıç** varsayılandır ve hata ayıklama için başlangıç projesi başlatır. Daha fazla bilgi için bkz: [başlangıç projesi seçme](http://msdn.microsoft.com/en-us/222e3f32-a6fe-4941-bf37-6b2a921129fd).<br />-   **Dış program Başlat** başlatmak ve değil bir program eklemek sağlar parçası bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Daha fazla bilgi için bkz: [çalışan bir Program ekleme](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4).<br />-   **URL'de tarayıcı başlatmak** bir Web uygulaması ayıklamanızı sağlar.|  
|**Komut satırı bağımsız değişkenleri**|Ayıklanacak programı için komut satırı bağımsız değişkenlerini belirtir. Komut adı başlangıç dış programında belirtilen program adıdır. Eylemi Başlat Başlat URL'sine ayarlarsanız, komut satırı bağımsız değişkenleri belirtilemez.|  
|**Çalışma dizini**|Ayıklanacak programın çalışma dizinini belirtir. İçinde [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], çalışma dizini uygulamanın varsayılan olarak \bin\debug başlatılan dizindir.|  
|**Uzak makine kullanın**|Hata ayıklama amacıyla burada uygulamanın çalışacağı uzak makine adını veya bir [Msvsmon sunucu adı](../debugger/remote-debugging.md). Uzak makinede EXE konumunu yapılandırma özellikleri klasörü, yapı kategorisi çıkış yolu özelliğinde belirtilir. Konumun uzak makinede paylaşılabilir bir dizin olmalıdır.|
|**Yönetilmeyen kod hata ayıklamayı etkinleştir**|Yerel (yönetilmeyen) Win32 kod çağrıları yönetilen uygulamanızdan ayıklamanızı sağlar.|  
|**SQL Server hata ayıklamayı etkinleştir**|SQL Server veritabanı nesneleri hata ayıklama sağlar.|  
  
##  <a name="BKMK_Build_tab"></a>Sekme oluşturma  
  
|Ayar|Açıklama|  
|-------------|-----------------|  
|**Koşullu derleme simgeleri:**|Hata ayıklama ve izleme sabitleri burada tanımlanır.<br /><br /> Bu sabitleri koşullu derlenmesini etkinleştirmek [hata ayıklama sınıfı](/dotnet/api/system.diagnostics.debug) ve [izleme sınıfı](/dotnet/api/system.diagnostics.trace). Tanımlanan Bu sabitler ile hata ayıklama ve izleme sınıfı yöntemleri Oluştur çıktıya [çıktı penceresi](../ide/reference/output-window.md). Bu sabitleri olmadan hata ayıklama ve izleme sınıfı yöntemleri derlenmemiş ve hiçbir çıktı oluşturulur.<br /><br /> -Debug normalde bir program hata ayıklama sürümü tanımlanır ve yayın sürümünde tanımlanmamış.<br />-İzleme hata ayıklama ve yayın sürümlerinde normal olarak tanımlanır.|  
|**Kod en iyi duruma getirme**|Yalnızca en iyi duruma getirilmiş kodda göründüğü bir hatayı bulduğunuz sürece, bu ayar hata ayıklama sürümünü devre dışı bırakmanız gerekir. En iyi duruma getirilmiş daha zor yönergeleri kaynak windows deyimlerinde için doğrudan karşılık gelmediğinden hata ayıklamak için kodudur.|  
|**Çıkış yolu:**|Hata ayıklama için bin\Debug için tipik olarak ayarlayın.|

> [!NOTE]
> Hata ayıklama seçenekleri, bulduğunuz hakkında daha fazla bilgi için **Gelişmiş** düğmesi için bkz: [Gelişmiş derleme Ayarları iletişim kutusu (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md). Taşınabilir biçimi simge (.pdb) dosyalar için en son .NET Core platformlar arası biçimidir. 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)