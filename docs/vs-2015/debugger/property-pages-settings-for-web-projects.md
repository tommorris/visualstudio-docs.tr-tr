---
title: Özellik sayfaları Web projeleri için ayarları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Web applications
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- debugging Web applications, project settings
- debug configurations, Web projects
ms.assetid: 8ec5160a-6408-4f47-8d41-f0e20e79a3b9
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 579872bab86e0cd8f127a7222c7fbc9b823e1a5a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695412"
---
# <a name="property-pages-settings-for-web-projects"></a>Web Projeleri Özellik Sayfası Ayarları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Web projeleri özellik sayfası ayarlarını](https://docs.microsoft.com/visualstudio/debugger/property-pages-settings-for-web-projects).  
  
Bir web sitesi hata ayıklama yapılandırmasında özellik ayarları değiştirebilirsiniz **özellik sayfaları** anlatıldığı gibi iletişim kutusu, [hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md). Aşağıdaki tablolarda, hata ayıklayıcı ile ilgili ayarların nerede bulunacağı gösterilmektedir **özellik sayfaları** iletişim kutusu.  
  
### <a name="configuration-properties-folder-start-options-category"></a>Yapılandırma özellikleri klasörü (Başlat seçenekleri kategori)  
  
|**Ayarı**|**Açıklama**|  
|-----------------|---------------------|  
|**Başlatma eylemi**|Grupları seçenekleri için uygulama başlatma ilgili başlığı.|  
|**Geçerli sayfayı kullanın.**|Hata ayıklama için başlangıç noktası olarak geçerli sayfayı belirtir.|  
|**Belirli sayfa:**|Hata ayıklamayı başlatmak için istediğiniz Web sayfası belirtir.|  
|**Dış programı Başlat:**|Hata ayıklamak istediğiniz program başlatmak için komut belirtir.|  
|**Komut satırı bağımsız değişkenleri:**|Yukarıda belirtilen komut için bağımsız değişkenleri belirtir.|  
|**Çalışma dizini:**|Ayıklanan programın çalışma dizini belirtir. İçinde [!INCLUDE[csprcs](../includes/csprcs-md.md)], çalışma dizini, uygulama varsayılan olarak, \bin\debug başlatılan dizinidir.|  
|**Başlangıç URL'si**|Web uygulamasının hatalarını ayıklamak istediğiniz konumu belirtir.|  
|**Bir sayfa açma. Harici uygulamadan istek için bekle**|Harici uygulamadan istek için beklenecek diyor. Bu seçenek, Internet Explorer veya başka bir uygulama başlatılmaz. Yalnızca, bir uygulama tarafından çağrıldığında hata ayıklamaya hazırlar.|  
|**Sunucu**|Grupları seçenekleri kullanılacak sunucunun ilgili başlığı.|  
|**Varsayılan Web sunucusunu kullan**|Varsayılan Web sunucusu kullanacak şekilde söyler.|  
|**Özel sunucu kullan**|Sunucusu olarak kullanmak için temel URL'yi girmenizi sağlar.|  
|**Hata ayıklayıcılar**|Grupları seçenekleri yapılması hata ayıklama bilgisinin türüne ilgili başlığı.|  
|**ASP.NET hata ayıklaması**|Sunucu sayfalar için yazılan hata ayıklamasını etkinleştirir [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] geliştirme platformu. Bir URL belirtmelisiniz **URL'yi Başlat**.|  
|**Yerel kodda hata ayıklama**|Yerel (yönetilmeyen) Win32 koddaki çağrıları yönetilen uygulamanızın hatalarını ayıklamanızı sağlar.|  
|**SQL Server hata ayıklama**|SQL Server veritabanı nesnelerini hata ayıklamasını sağlar.|  
|**Silverlight'ta hata ayıklama**|Silverlight bileşenleri hata ayıklamasını sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)



