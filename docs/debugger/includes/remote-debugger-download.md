---
title: Uzaktan hata ayıklayıcı indirme
description: Karşıdan yükleme bağlantıları için uzaktan hata ayıklayıcı
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 358dc0b457381bb56532e6cae1156aac9ea2dba2
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
1.  Cihaz veya sunucu hata ayıklamak istediğiniz makine (yerine Visual Studio çalıştıran makine), uzak Araçlar doğru sürümünü alır.

    |Sürüm|Bağlantı|Notlar|
    |-|-|-|
    |Visual Studio 2017 (en son sürüm)|[Uzak Araçlar](https://www.visualstudio.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|Her zaman eşleştirme (x86 veya x64) aygıt işletim sistemi sürümünü yükleyin. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging.md#unblock_msvsmon) uzak araçları yüklemek Yardım.|
    |Visual Studio 2017 (eski)|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|My.VisualStudio.com uzak araçlar Visual Studio 2017 önceki sürümleri için kullanılabilir. İstenirse, birleştirme ücretsiz Visual Studio geliştirme Essentials Grup ya da Visual Studio aboneliğiniz ile oturum kimliği Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging.md#unblock_msvsmon) uzak araçları yüklemek Yardım.|
    |Visual Studio 2015 (eski)|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|İstenirse, birleştirme ücretsiz Visual Studio geliştirme Essentials Grup ya da Visual Studio aboneliğiniz ile oturum kimliği Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging.md#unblock_msvsmon) uzak araçları yüklemek Yardım.|
    |Visual Studio 2013|[Uzak Araçlar](https://msdn.microsoft.com/library/bt727f1t(v=vs.120).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2013 belgelerinde indirme|
    |Visual Studio 2012|[Uzak Araçlar](https://msdn.microsoft.com/library/bt727f1t(v=vs.110).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2012 belgelerinde indirme|
  
2.  İndirme sayfasında işletim sisteminizi (x 86, x64 veya ARM) ile eşleşen araçları sürümü seçin ve uzak araçları indirin.
  
    > [!IMPORTANT]
    >  Visual Studio sürümünüzle eşleşen uzak araçları en son sürümünü yüklemeniz önerilir. Eşleşmeyen sürümleri önerilmez. Ayrıca, yüklemek istediğiniz işletim sistemi olarak aynı mimariye sahip uzak araçları yüklemeniz gerekir. Diğer bir deyişle, bir 64-bit işletim sistemi çalıştıran bir uzak bilgisayarda 32 bit uygulama hata ayıklama istiyorsanız, uzak bilgisayarda Uzak araçları 64-bit sürümünü yüklemeniz gerekir. 
    >   
    >  Yüzey 3 x64 için ARM geçiş mimarisi. Bir uzak Araçlar ARM sürümü için Visual Studio 2017 kullanılabilir değil. Visual Studio 2015 için Visual Studio 2015 RTW indirme ARM sürümü bulunamıyor.
  
3.  Yürütülebilir dosya indirme işlemini tamamladığınızda, sonraki bölüme gidin ve kurulum yönergelerini izleyin.

Uzaktan hata ayıklayıcı (msvsmon.exe) uzak bilgisayara kopyalayın ve bunu çalıştırmak çalışırsanız unutmayın, **uzaktan hata ayıklayıcı Yapılandırma Sihirbazı'nı** (**rdbgwiz.exe**) yalnızca karşıdan yüklenir Araçları. Özellikle bir hizmet olarak çalıştırmak için uzaktan hata ayıklayıcı isterseniz daha sonra Yapılandırma Sihirbazı'nı kullanmanız gerekebilir. Daha fazla bilgi için bkz: [(isteğe bağlı) yapılandırma hizmet olarak uzaktan hata ayıklayıcı](../../debugger/remote-debugging.md#bkmk_configureService).
