---
title: "Hata: Web sunucusu doğru yapılandırılmamış | Microsoft Docs"
ms.custom: 
ms.date: 09/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.remote.projnotconfigured
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6f1e206cc9327ef933f52f35960f628170e02c38
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>Hata: Web sunucusu doğru yapılandırılmamış

Burada sorunu gidermek için ayrıntılı adımlar aldıktan sonra ve hata ayıklamak yeniden denemeden önce IIS sıfırlamanız gerekebilir. Bir yönetici komut istemi'ni açıp yazarak bunu, `iisreset`.

Bu sorunu çözmek için aşağıdaki adımları gerçekleştirin:

1. Sunucu üzerinde barındırılan web uygulaması olarak yapılandırılmışsa, yayın derlemesi hata ayıklama derlemesi yeniden yayımlamanız ve web.config dosyasını içerdiğini doğrulayın `debug=true` derleme öğesindeki. IIS ve Yeniden Dene'yi sıfırlayın.

    Örneğin, bir yayın derleme için bir yayımlama profili kullanıyorsanız, hata ayıklama değiştirin ve yeniden yayımlayın. Aksi takdirde hata ayıklama özniteliği olarak ayarlanır `false` yayımladığınızda.

2. (IIS) Fiziksel yolun doğru olduğundan emin olun. IIS, bu ayar Bul **temel ayarlar > fiziksel yolu** (veya **Gelişmiş ayarları** IIS eski sürümlerinde).

    Web uygulaması için farklı bir makineye kopyaladığınız, el ile yeniden adlandırılmış veya taşınırsa fiziksel yolu yanlış olabilir. IIS ve Yeniden Dene'yi sıfırlayın.

3. Visual Studio'da özelliklerinde doğru sunucunun seçili olduğundan emin olun. (Açık **Özellikler > Web > sunucuları** veya **Özellikler > hata ayıklama** proje türüne bağlı olarak. Web Forms projesi için açık **özellik sayfaları > Başlangıç Seçenekleri > sunucu**).

    IIS gibi bir dış (özel) sunucu kullanıyorsanız, URL'nin doğru olması gerekir. Aksi takdirde, IIS Express ve Yeniden Dene'yi seçin.

4. (IIS) ASP.NET doğru sürümü sunucuda yüklü olduğundan emin olun.

    ASP.NET IIS ve Visual Studio projenizi uyumsuz sürümlerini bu soruna neden olabilir. Web.config dosyasında framework sürümü ayarlamanız gerekebilir. IIS üzerinde ASP.NET yüklemek için kullandığınız [Web Platformu Yükleyicisi (Webpı)](https://www.microsoft.com/web/downloads/platform.aspx). Ayrıca bkz [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) veya ASP.NET Core [IIS ile Windows konakta](https://docs.asp.net/en/latest/publishing/iis.html).
  
4. Varsa `maxConnection` IIS'de sınırı çok düşük ve çok fazla bağlantıya sahip, gerekebilir [bağlantı sınırını artırmak](/iis/configuration/system.applicationhost/sites/sitedefaults/limits).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan bir uzak IIS bilgisayarda ASP.NET hata ayıklama](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)   
 [Web uygulamalarında hata ayıklama: Hatalar ve sorun giderme](../debugger/debugging-web-applications-errors-and-troubleshooting.md)