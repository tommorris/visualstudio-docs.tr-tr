---
title: 'Hata ayıklama hazırlığı: ASP.NET Web uygulamaları | Microsoft Docs'
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
- VB
- CSharp
helpviewer_keywords:
- debugging ASP.NET Web applications
- debugging [Visual Studio], Web applications
ms.assetid: bcfb1080-98d1-42f9-96af-186fb14f232a
caps.latest.revision: 38
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20731f5036a89c3c19fbea0d825d67fc02c13cf9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690940"
---
# <a name="debugging-preparation-aspnet-web-applications"></a>Hata Ayıklama Hazırlığı: ASP.NET Web Uygulamaları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklama hazırlığı: ASP.NET Web uygulamaları](https://docs.microsoft.com/visualstudio/debugger/debugging-preparation-aspnet-web-applications).  
  
[!INCLUDE[vstecasp](../includes/vstecasp-md.md)]Web sitesi şablonu bir Web formu uygulaması oluşturur. Bu şablonu kullanarak bir Web sitesi oluşturduğunuzda [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] hata ayıklama için varsayılan ayarları oluşturur. İçinde **proje özellikleri** iletişim kutusunda, Web sayfası, bir başlangıç sayfası olmasını isteyip istemediğinizi belirtebilirsiniz. Hata ayıklamayı başlattığınızda bir [!INCLUDE[vstecasp](../includes/vstecasp-md.md)]Web sitesi, bu varsayılan ayarlarla [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Internet Explorer'ı başlatan ve hata ayıklayıcıya ekler [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] çalışan işlemi (aspnet_wp.exe veya w3wp.exe). Daha fazla bilgi için [sistem gereksinimleri](../debugger/aspnet-debugging-system-requirements.md).  
  
### <a name="to-create-a-web-forms-application"></a>Bir Web Forms uygulaması oluşturma  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni Web sitesi**.  
  
2.  İçinde **yeni Web sitesi** iletişim kutusunda [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] **Web sitesi**.  
  
3.  **Tamam**'ı tıklatın.  
  
### <a name="to-debug-your-web-form"></a>Web formunda hata ayıklama  
  
1.  İşlevler ve olay işleyicileri içinde bir veya daha fazla kesme noktası ayarlayın.  
  
     Daha fazla bilgi için [kesme noktaları ve izleme noktaları](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583).  
  
2.  Bir kesme noktası isabet edildiğinde işlevin içindeki kodun adım adım. Sorunu yalıtana kadar kodunuzun yürütülmesini gözlemleyin.  
  
     Daha fazla bilgi için [Adımlama](http://msdn.microsoft.com/en-us/8791dac9-64d1-4bb9-b59e-8d59af1833f9) ve [hata ayıklama Web uygulamalarında ve betikte](../debugger/debugging-web-applications-and-script.md).  
  
## <a name="changing-default-configurations"></a>Varsayılan yapılandırmaları değiştirme  
 Yayın yapılandırmaları tarafından oluşturulan ve varsayılan hata ayıklama değiştirmek istiyorsanız [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], bunu yapabilirsiniz. Daha fazla bilgi için [nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md).  
  
#### <a name="to-change-the-default-debug-configuration"></a>Varsayılan hata ayıklama yapılandırmasını değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, Web sitesini sağ tıklatın ve seçin **özellik sayfaları** açmak için **özellik sayfaları** iletişim kutusu.  
  
2.  Tıklayın **Başlat seçenekleri**.  
  
3.  Ayarlama **başlatma eylemi** Web sayfasına ilk görüntülenmesi gerekir.  
  
4.  Altında **hata ayıklayıcıları**, emin **ASP.NET hata ayıklaması** seçilir.  
  
     Daha fazla bilgi için [Web projeleri özellik sayfası ayarlarını](../debugger/property-pages-settings-for-web-projects.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)



