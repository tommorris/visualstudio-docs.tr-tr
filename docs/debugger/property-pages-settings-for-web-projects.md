---
title: Özellik sayfaları Web projeleri için ayarları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Web applications
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- debugging Web applications, project settings
- debug configurations, Web projects
ms.assetid: 8ec5160a-6408-4f47-8d41-f0e20e79a3b9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0e2559ad8e1c2d233ffcb1873b0f7f5212bd6cf7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31480722"
---
# <a name="property-pages-settings-for-web-projects"></a>Web Projeleri Özellik Sayfası Ayarları
Bir web sitesi hata ayıklama yapılandırmasını da özellik ayarları değiştirebileceğiniz **özellik sayfaları** anlatıldığı gibi iletişim kutusu, [hata ayıklama ve dağıtım yapılandırmalarını](../debugger/how-to-set-debug-and-release-configurations.md). Aşağıdaki tablolarda hata ayıklayıcı gizlilikle ilgili ayarların nerede bulacağını Göster **özellik sayfaları** iletişim kutusu.  
  
### <a name="configuration-properties-folder-start-options-category"></a>Yapılandırma özellikleri klasörü (başlangıç seçenekleri kategori)  
  
|**Ayarı**|**Açıklama**|  
|-----------------|---------------------|  
|**Eylemi Başlat**|Grupları seçenekleri için uygulama başlatma ilgili başlığı.|  
|**Geçerli sayfayı kullanın**|Geçerli sayfanın hata ayıklama için başlangıç noktası olarak belirtir.|  
|**Belirli bir sayfaya:**|Hata ayıklama başlamak istediğiniz Web sayfasını belirtir.|  
|**Dış programı Başlat:**|Hata ayıklamak istediğiniz program başlatmak için komut belirtir.|  
|**Komut satırı bağımsız değişkenleri:**|Yukarıda belirtilen komut bağımsız değişkenlerini belirtir.|  
|**Çalışma dizini:**|Ayıklanacak programın çalışma dizinini belirtir. İçinde [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], çalışma dizini uygulamanın varsayılan olarak, \bin\debug başlatılan dizindir.|  
|**Başlangıç URL'si**|Hata ayıklamak istediğiniz Web uygulamasının konumunu belirtir.|  
|**Bir sayfa açmayın. Dış uygulamadan gelen bir istek bekleyin**|Dış uygulamadan gelen bir istek için beklenecek söyler. Bu seçenek, Internet Explorer veya başka bir uygulama başlatılmaz. Yalnızca bir uygulama tarafından çağrıldığında hata ayıklama için hazırlar.|  
|**Sunucu**|Grupları seçenekleri kullanılacak sunucusuyla ilgili başlığı.|  
|**Varsayılan Web sunucusunu kullan**|Varsayılan Web sunucusu kullanılacağını söyler.|  
|**Özel sunucu kullan**|Sunucusu olarak kullanmak için temel URL'yi girmenizi sağlar.|  
|**Hata ayıklayıcıları**|Grupları seçenekleri yapılması hata ayıklama yazmak için ilgili başlığı.|  
|**ASP.NET hata ayıklama**|Sunucu sayfalar için yazılan hata ayıklamasını etkinleştirir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] geliştirme platformu. Bir URL belirtmelisiniz **Start URL**.|  
|**Yerel kodda hata ayıklama**|Yerel (yönetilmeyen) Win32 kod çağrıları yönetilen uygulamanızdan ayıklamanızı sağlar.|  
|**SQL Server hata ayıklama**|SQL Server veritabanı nesneleri hata ayıklama sağlar.|  
|**Silverlight'ta hata ayıklama**|Silverlight bileşenleri hata ayıklama sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)