---
title: "Nasıl yapılır: tam zamanında hata ayıklayıcı için yanıt | Microsoft Docs"
ms.custom: 
ms.date: 05/23/17
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
caps.latest.revision: "48"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8c954cd95da7b6dd2ba0c2938852b939ae396525
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-respond-to-the-just-in-time-debugger"></a>Nasıl yapılır: tam zamanında hata ayıklayıcı için yanıt

Zaman içinde sadece gördüğünüzde almalıdır Eylemler hata ayıklayıcı iletişim kutusu bağımlı ne yapmanız çalıştığınız:

#### <a name="if-you-want-to-fix-or-debug-the-error-visual-studio-users"></a>Düzeltin veya (Visual Studio kullanıcılar) hata ayıklama istiyorsanız

- Sahip olmanız gerekir [Visual Studio yüklüyse](https://www.microsoft.com/en-us/download/details.aspx?id=48146) hata hakkında ayrıntılı bilgi görüntülemek ve hata ayıklamak deneyin. Daha fazla bilgi için bkz: [Just-In-Time hata ayıklayıcısı ile hata ayıklama](../debugger/debug-using-the-just-in-time-debugger.md). Hatayı çözün ve uygulama düzeltme, hatayı gidermek için uygulama sahibine başvurun.

#### <a name="if-you-want-to-prevent-the-just-in-time-debugger-dialog-box-from-appearing"></a>Just-In-Time hata ayıklayıcı iletişim kutusunun görüntülenmesini engellemek istiyorsanız

Zaman içinde sadece önlemek üzere adım atabilirsiniz görünmesini hata ayıklayıcı iletişim kutusu. Uygulama hata işleme, uygulama normal olarak çalıştırabilirsiniz.

1. (Web uygulamaları) Bir web uygulamasını çalıştırmak çalışıyorsanız, komut dosyası hata ayıklaması devre dışı bırakabilirsiniz.

    Internet Explorer veya Edge'i için Internet Seçenekleri iletişim kutusunda komut dosyası hata ayıklaması devre dışı bırakın. Bu ayarlardan erişebilirsiniz **Denetim Masası** > **ağ ve Internet** > **Internet Seçenekleri** (tam adımlar bağlıdır, Windows sürümü ve tarayıcınızı).

    ![JITInternetOptions](../debugger/media/jitinternetoptions.png "JITInternetOptions")

    Ardından hata bulunduğu web sayfasını yeniden açın. Bu ayarı değiştirmek sorunu çözmezse, sorunu düzeltmek için web uygulaması sahibine başvurun.

3. (Visual Studio kullanıcılar) Visual Studio yüklü (veya nesneniz varsa daha önce yüklenmiş ve bu kaldırılamaz), [devre dışı bırak sadece zamanında hata ayıklama](../debugger/debug-using-the-just-in-time-debugger.md) ve uygulamayı yeniden çalıştırmayı deneyin.

    > [!IMPORTANT]
    > Zaman içinde sadece devre dışı bırakırsanız hata ayıklama ve uygulama karşılaştığında işlenmeyen bir özel durum (bir hata), bir standart hata iletişim kutusu yerine görürsünüz veya uygulama kilitlenme askıda veya. Hata (veya uygulama sahibi tarafından) düzeltilene kadar uygulama normal şekilde çalışmaz.

2. (ASP.NET ve IIS) IIS'de bir ASP.NET Web uygulaması barındırıyorsanız, sunucu tarafı hata ayıklamasını devre dışı bırakın.

    IIS Yöneticisi'nde, sunucu düğümüne sağ tıklayın ve seçin **özellikler görünümüne geç**. ASP.NET bölümü altında seçin **.NET derleme** ve seçtiğiniz emin **False** (adımları IIS eski sürümleri farklı) hata ayıklama davranışı olarak.
  
## <a name="see-also"></a>Ayrıca Bkz.    
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
