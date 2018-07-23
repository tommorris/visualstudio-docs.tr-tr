---
title: 'Nasıl yapılır: tam zamanında hata ayıklayıcı için yanıt | Microsoft Docs'
ms.custom: ''
ms.date: 05/23/17
ms.technology: vs-ide-debug
ms.topic: troubleshooting
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fd3f565d8bb58ae290b0b569bb61d4cb57e8edaa
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179781"
---
# <a name="how-to-respond-to-the-just-in-time-debugger"></a>Nasıl yapılır: tam zamanında hata ayıklayıcı için yanıt

Just-ın-Time gördüğünüzde işlemlerde hata ayıklayıcısı iletişim kutusu bağımlı ne yapılacağını çalışıyorsunuz:

#### <a name="if-you-want-to-fix-or-debug-the-error-visual-studio-users"></a>(Visual Studio kullanıcılarına) hata ayıklama veya düzeltmek istiyorsanız

- Olmalıdır [Visual Studio'nun yüklü](http://visualstudio.microsoft.com) hata hakkında ayrıntılı bilgi görüntülemek ve hata ayıklamak deneyin. Daha fazla bilgi için [tam zamanında hata ayıklayıcı ile hata ayıklama](../debugger/debug-using-the-just-in-time-debugger.md). Hatayı çözün ve uygulama düzeltme, hatayı gidermek için uygulama sahibine başvurun.

#### <a name="if-you-want-to-prevent-the-just-in-time-debugger-dialog-box-from-appearing"></a>Tam zamanında hata ayıklayıcı iletişim kutusunun görünmesini engellemek istiyorsanız

Just-ın-Time önlemek üzere adım atabilirsiniz görüntülenmesini hata ayıklayıcısı iletişim kutusu. Uygulama hata işleme, uygulama normal şekilde çalıştırabilirsiniz.

1. (Web uygulamaları) Bir web uygulamasını çalıştırmak çalışıyorsanız, komut dosyası hata ayıklaması devre dışı bırakabilirsiniz.

    Internet Explorer veya Edge için Internet Seçenekleri iletişim kutusunda betik hata ayıklamasını devre dışı bırakın. Bu ayarlardan erişebileceğiniz **Denetim Masası** > **ağ ve Internet** > **Internet Seçenekleri** (tam adımlar bağlıdır, Windows ve sürümünü tarayıcınızı).

    ![JITInternetOptions](../debugger/media/jitinternetoptions.png "JITInternetOptions")

    Hatanın bulunduğu web sayfasını yeniden açın. Bu ayarı değiştirmeden sorunu çözmezse, sorunu düzeltmek için web uygulama sahibine başvurun.

3. (Visual Studio kullanıcı) Visual Studio yüklü (veya tablonuz varsa daha önce yüklenmiş ve o da kaldırılır), [devre dışı bırakma, Just-ın-Time hata ayıklama](../debugger/debug-using-the-just-in-time-debugger.md) ve uygulamayı yeniden çalıştırmayı deneyin.

    > [!IMPORTANT]
    > Just-ın-Time devre dışı bırakırsanız hata ayıklama ve uygulama karşılaştığında işlenmeyen bir özel durum (hata), standart hata iletişim kutusu yerine görürsünüz ve uygulama kilitlenme veya kapat. (Veya uygulama sahibi tarafından) hata düzeltilene kadar uygulama normal şekilde çalışmaz.

2. (ASP.NET ve IIS) IIS'de ASP.NET Web uygulaması barındırıyorsanız, sunucu tarafı hata ayıklamasını devre dışı bırakın.

    IIS Yöneticisi'nde, sunucu düğümünü sağ tıklatın ve seçin **özellikler görünümüne geç**. ASP.NET bölümü altında seçin **.NET derleme** ve ardından seçtiğinizden emin olun **False** (adımları IIS eski sürümlerinde farklı) hata ayıklama davranışı olarak.

## <a name="see-also"></a>Ayrıca Bkz.
 [Hata ayıklayıcı temel bilgileri](../debugger/getting-started-with-the-debugger.md)
