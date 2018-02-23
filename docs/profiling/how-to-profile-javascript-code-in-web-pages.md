---
title: "Nasıl yapılır: Web sayfalarında JavaScript kodu profil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript performance profiling
- Profiling Tools,JavaScript
- web site performance profiling
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 737ead7c9745fc7cb173d542379f3c0d8ba39e89
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-profile-javascript-code-in-web-pages"></a>Nasıl yapılır: Web sayfalarında JavaScript kodu profili

Visual Studio profil oluşturma araçları içinde yürütür JavaScript kodu için performans verilerini toplayabilir bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, bir rastgele Web sayfası veya JavaScript uygulama izleme profili oluşturma yöntemi kullanarak. Internet Explorer 8 veya sonraki sürümünü gerektirir.

> [!WARNING]
> JavaScript UWP uygulamalarında profil için bkz: [JavaScript belleği](../profiling/javascript-memory.md) 

Performans oturum oluşturmak için profil oluşturma Sihirbazı'nı kullanabilirsiniz. İzleme yöntemini belirtin ve ardından Özellikler iletişim kutusunun araçları sayfasında seçeneğini performans oturumu için profil oluşturma JavaScript belirtin.

JavaScript profil belirttiğinizde, JavaScript kodu yürütmelerinin tarayıcıda ve [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sunucu üzerinde yürütülen kodu profili.

- İçin bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Web uygulaması, tarayıcıda yürüten hem JavaScript kodu ve [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sunucu üzerinde yürütülen kodu profili.

- Rastgele bir Web sayfasını tarayıcıda yürütür JavaScript kodu profili.

## <a name="to-profile-javascript-in-an-aspnet-web-application-project"></a>Bir ASP.NET Web uygulaması projesini JavaScript profilini

1. Açık [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Visual Studio'da Web projesi.

2. Üzerinde **Çözümle** menüsünde tıklatın **başlatma performans Sihirbazı**.

3. Performans Sihirbazı'nın ilk sayfasında belirttiğiniz **Araçları** profili oluşturma yöntemi ve ardından **sonraki**.

4. Sihirbazın ikinci sayfasında geçerli proje hedefleri listesinde seçili olduğundan emin olun ve ardından **sonraki.**

5. Sihirbazın üçüncü sayfasında seçin **profil JavaScript** onay kutusunu işaretleyin ve ardından **sonraki**.

6. Sihirbazının dördüncü sayfasında, tıklatın **son** tarayıcıda Web uygulamasını başlatmak için.

7. Profil oluşturmayı istediğiniz işlevselliği uygular.

8. Profil oluşturma oturumu sona erdirmek için tarayıcıyı kapatın.

### <a name="to-profile-javascript-in-individual-web-pages-or-a-javascript-applications"></a>Tek tek Web sayfalarında JavaScript veya JavaScript uygulamaları profilini

1. Visual Studio'yu açın.

2. Üzerinde **Çözümle** menüsünde tıklatın **başlatma performans Sihirbazı**.

3. Performans Sihirbazı'nın ilk sayfasında belirttiğiniz **Araçları** profili oluşturma yöntemi ve ardından **sonraki**.

4. Sihirbazın ikinci sayfasında ASP.NET veya JavaScript uygulama'yı tıklatın ve ardından **sonraki.**

5. Sihirbazın üçüncü sayfasında:

    1. Sayfanın URL'sini yazın **hangi URL veya yol uygulamanızın çalışacağı** kutusu.

    2. Seçin **profil JavaScript** onay kutusunu işaretleyin ve ardından **sonraki**.

6. Sihirbazının dördüncü sayfasında, tıklatın **son** Web sayfasını tarayıcıda başlatmak için.

7. Profil oluşturmayı istediğiniz işlevselliği uygular.

8. Profil oluşturma oturumu sona erdirmek için tarayıcıyı kapatın.