---
title: Uzaktan hata ayıklayıcı yükleme
description: Uzaktan hata ayıklayıcı için karşıdan yükleme bağlantıları
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 491b01d87e4f1a9980143e9ffcc501b3cda7c922
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39189306"
---
1.  Cihaz veya sunucu, hata ayıklamak istediğiniz makine (yerine Visual Studio çalıştıran makinenin), uzak Araçlar'ın doğru sürümü alın.

    |Sürüm|Bağlantı|Notlar|
    |-|-|-|
    |Visual Studio 2017 (en son sürüm)|[Uzak Araçlar](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|Uzak Araçlar'ın en son sürümü, tüm Visual Studio 2017 sürümleri ile uyumludur. Her zaman eşleştirme (x 86, x64 veya ARM64), cihaz işletim sistemi sürümü indirin. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging-unblock-file-download.md) uzak araçları indirmek Yardım.|
    |Visual Studio 2015|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Visual Studio 2015 için Uzak Araçlar, My.VisualStudio.com kullanılabilir. İstenirse, ücretsiz katılın [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) program ya da Visual Studio abonelik kimliğinizle oturum açın. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging-unblock-file-download.md) uzak araçları indirmek Yardım.|
    |Visual Studio 2013|[Uzak Araçlar](https://msdn.microsoft.com/library/bt727f1t(v=vs.120).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2013 belgeleri sayfasında indirin|
    |Visual Studio 2012|[Uzak Araçlar](https://msdn.microsoft.com/library/bt727f1t(v=vs.110).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2012 belgeleri sayfasında indirin|

2.  İndirme sayfasında işletim sisteminiz (x86, ARM ve ARM64 x64) eşleşen araçları sürümünü seçin ve uzak araçları indirmek.

    > [!IMPORTANT]
    >  Visual Studio sürümünüz için Uzak Araçlar'ın en son sürümünü yüklemenizi öneririz. En son sürümünü (örneğin, 15,8) (örneğin, 15.0); önceki sürümlerle uyumlu Ancak, önceki sürümlerini sonraki sürümlerle uyumlu değildir. Ayrıca, yüklemek istediğiniz işletim sistemi olarak aynı mimariye sahip uzak araçları yüklemeniz gerekir. Diğer bir deyişle, bir 64-bit işletim sistemi çalıştıran bir uzak bilgisayarda bir 32 bit uygulama hata ayıklamak istiyorsanız, uzak bilgisayarda Uzak Araçlar'ın 64 bit sürümü yüklemeniz gerekir.
    >
    >  Windows 10'da ARM cihazlarda hata ayıklama için Uzak Araçlar'ın en son sürümüyle kullanılabilen ARM64 indirmeyi seçin.  Windows RT cihazları için yalnızca Visual Studio 2015 RTW indirmesinde kullanılabilir ARM sürümünü seçin.

3.  Yürütülebilir dosya indirme işlemini tamamladıktan sonra sonraki bölüme gidin ve kurulum yönergeleri izleyin.

Uzaktan hata ayıklayıcı (msvsmon.exe) uzak bilgisayara kopyalayın ve çalıştırmak çalışırsanız unutmayın, **uzaktan hata ayıklayıcı Yapılandırma Sihirbazı'nı** (**rdbgwiz.exe**) yalnızca karşıdan yüklenir Araçlar. Özellikle bir hizmet olarak çalıştırmak için uzaktan hata ayıklayıcı isterseniz daha sonra Yapılandırma Sihirbazı'nı kullanmak gerekebilir. Daha fazla bilgi için [(isteğe bağlı) yapılandırma hizmet olarak uzaktan hata ayıklayıcı](../../debugger/remote-debugging.md#bkmk_configureService).
