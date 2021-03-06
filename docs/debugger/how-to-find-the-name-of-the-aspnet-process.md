---
title: 'Nasıl yapılır: ASP.NET işleminin adını bulma | Microsoft Docs'
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
- ASP.NET debugging, ASP.NET process
- ASP.NET process
ms.assetid: 931a7597-b0f0-4a28-931d-46e63344435f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 899860baf5461eb798341cebf775ccde488915b7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31473825"
---
# <a name="how-to-find-the-name-of-the-aspnet-process"></a>Nasıl Yapılır: ASP.NET İşleminin Adını Bulma
Çalışan bir eklemek için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulama, elinizde adını bilmek [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] işlemi:  

-   IIS veya Iısexpress ASP.NET Core çalıştırıyorsanız, işlem dotnet.exe adıdır.

-   ASP.NET daha sonra IIS 6.0 üzerinde çalıştırıyorsanız, w3wp.exe addır.  
  
-   ASP.NET IIS öğesinin önceki bir sürümünü çalıştırıyorsanız, aspnet_wp.exe addır.

-   ASP.NET Iısexpress üzerinde çalıştırıyorsanız, iisexpress.exe addır.
  
Visual Studio 2012'den önceki Visual Studio sürümleri kullanılarak oluşturulan uygulamalar için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] kodu dosya sisteminde bulunan ve test sunucusuna WebDev.WebServer.exe WebDev.WebServer40.exe altında çalıştırın. Bu durumda, WebDev.WebServer.exe veya WebDev.WebServer40.exe yerine eklemeniz gerekir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] işlemi. Bu senaryo için yalnızca yerel hata ayıklama için geçerlidir.
  
İşlem içi çalıştırırken eski ASP uygulamaları IIS işlem inetinfo.exe içinde çalışır.  

### <a name="to-determine-the-iis-version-under-which-the-application-is-running"></a>Uygulamanın altında çalıştığı IIS sürümünü belirlemek için  

1.  Uygulama çalıştığından emin olun ve ardından, Visual Studio'dan [ekleme işlemi için](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md) komutu.

2.  W3wp.exe işlemi hızla bulmak için benzer bir işlem adının ilk harfi yazın **kullanılabilir işlemler** listesi.

    Bu konuda listeden kullanılabilir işlemler IIS hangi sürümlerinin kullanılabilir olduğunu ve hangi işlem uygulamanızı çalıştıran belirtir.

    > [!NOTE]
    > Visual Studio 2017 içinde başlayarak, işlem adı aramak için arama kutusunu kullanabilirsiniz.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir çalışan işleme iliştirilemiyor](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)  
 [Web uygulamalarında hata ayıklama uzaktan önkoşulları](../debugger/prerequistes-for-remote-debugging-web-applications.md)   
 [Sistem gereksinimleri](../debugger/aspnet-debugging-system-requirements.md)   
 [ASP.NET uygulamalarında hata ayıklama](../debugger/how-to-enable-debugging-for-aspnet-applications.md)