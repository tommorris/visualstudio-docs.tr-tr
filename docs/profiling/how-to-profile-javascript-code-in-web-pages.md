---
title: "Nasıl yapılır: Web sayfalarında JavaScript kodu profil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript performance profiling
- Profiling Tools,JavaScript
- web site performance profiling
ms.assetid: 37d02aad-ca4d-4eb0-bf66-ca3ecef31fbe
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 61955ead7996a395745a8869bc38c10dc59b537a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-profile-javascript-code-in-web-pages"></a>Nasıl yapılır: Web sayfalarında JavaScript kodu profili
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Profil Araçları içinde yürütür JavaScript kodu için performans verilerini toplayabilir bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, bir rastgele Web sayfası veya JavaScript uygulama izleme profili oluşturma yöntemi kullanarak.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
-   Internet Explorer 8 veya üzeri.  
  
> [!WARNING]
>  JavaScript UWP uygulamalarında profil için bkz: [JavaScript belleği](../profiling/javascript-memory.md) 
  
 Performans oturum oluşturmak için profil oluşturma Sihirbazı'nı kullanabilirsiniz. İzleme yöntemini belirtin ve ardından Özellikler iletişim kutusunun araçları sayfasında seçeneğini performans oturumu için profil oluşturma JavaScript belirtin.  
  
 JavaScript profil belirttiğinizde, JavaScript kodu yürütmelerinin tarayıcıda ve [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sunucu üzerinde yürütülen kodu profili.  
  
-   İçin bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, tarayıcıda yürüten hem JavaScript kodu ve [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sunucu üzerinde yürütülen kodu profili.  
  
-   Rastgele bir Web sayfasını tarayıcıda yürütür JavaScript kodu profili.  
  
### <a name="to-profile-javascript-in-an-aspnet-web-application-project"></a>Bir ASP.NET Web uygulaması projesini JavaScript profilini  
  
1.  İçinde [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], açık [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web projesi.  
  
2.  Üzerinde **Çözümle** menüsünde tıklatın **başlatma performans Sihirbazı**.  
  
3.  Performans Sihirbazı'nın ilk sayfasında belirttiğiniz **Araçları** profili oluşturma yöntemi ve ardından **sonraki**.  
  
4.  Sihirbazın ikinci sayfasında geçerli proje hedefleri listesinde seçili olduğundan emin olun ve ardından **sonraki.**  
  
5.  Sihirbazın üçüncü sayfasında seçin **profil JavaScript** onay kutusunu işaretleyin ve ardından **sonraki**.  
  
6.  Sihirbazının dördüncü sayfasında, tıklatın **son** tarayıcıda Web uygulamasını başlatmak için.  
  
7.  Profil oluşturmayı istediğiniz işlevselliği uygular.  
  
8.  Profil oluşturma oturumu sona erdirmek için tarayıcıyı kapatın.  
  
### <a name="to-profile-javascript-in-individual-web-pages-or-a-javascript-applications"></a>Tek tek Web sayfalarında JavaScript veya JavaScript uygulamaları profilini  
  
1.  Açık [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)].  
  
2.  Üzerinde **Çözümle** menüsünde tıklatın **başlatma performans Sihirbazı**.  
  
3.  Performans Sihirbazı'nın ilk sayfasında belirttiğiniz **Araçları** profili oluşturma yöntemi ve ardından **sonraki**.  
  
4.  Sihirbazın ikinci sayfasında ASP.NET veya JavaScript uygulama'yı tıklatın ve ardından **sonraki.**  
  
5.  Sihirbazın üçüncü sayfasında:  
  
    1.  Sayfanın URL'sini yazın **hangi URL veya yol uygulamanızın çalışacağı** kutusu.  
  
    2.  Seçin **profil JavaScript** onay kutusunu işaretleyin ve ardından **sonraki**.  
  
6.  Sihirbazının dördüncü sayfasında, tıklatın **son** Web sayfasını tarayıcıda başlatmak için.  
  
7.  Profil oluşturmayı istediğiniz işlevselliği uygular.  
  
8.  Profil oluşturma oturumu sona erdirmek için tarayıcıyı kapatın.