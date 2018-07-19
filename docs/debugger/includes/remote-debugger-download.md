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
ms.openlocfilehash: 987193cb7f78947087c6d387e16261d83a20e7c2
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38809264"
---
1.  Cihaz veya sunucu, hata ayıklamak istediğiniz makine (yerine Visual Studio çalıştıran makinenin), uzak Araçlar'ın doğru sürümü alın.

    |Sürüm|Bağlantı|Notlar|
    |-|-|-|
    |Visual Studio 2017 (en son sürüm)|[Uzak Araçlar](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|Her zaman eşleştirme (x 86, x64 veya ARM64), cihaz işletim sistemi sürümü indirin. Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging.md#unblock_msvsmon) uzak araçları indirmek Yardım.|
    |Visual Studio 2017 (eski)|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|Visual Studio 2017'in önceki sürümlerine yönelik uzak araçları My.VisualStudio.com ' kullanılabilir. İstenirse, birleştirme ücretsiz Visual Studio Dev Essentials grubu ya da Visual Studio aboneliğinizde oturum kimliği Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging.md#unblock_msvsmon) uzak araçları indirmek Yardım.|
    |Visual Studio 2015 (eski)|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|İstenirse, birleştirme ücretsiz Visual Studio Dev Essentials grubu ya da Visual Studio aboneliğinizde oturum kimliği Windows Server'da bkz [dosya indirme engellemesini](../../debugger/remote-debugging.md#unblock_msvsmon) uzak araçları indirmek Yardım.|
    |Visual Studio 2013|[Uzak Araçlar](https://msdn.microsoft.com/library/bt727f1t(v=vs.120).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2013 belgeleri sayfasında indirin|
    |Visual Studio 2012|[Uzak Araçlar](https://msdn.microsoft.com/library/bt727f1t(v=vs.110).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2012 belgeleri sayfasında indirin|

2.  İndirme sayfasında işletim sisteminiz (x86, ARM ve ARM64 x64) eşleşen araçları sürümünü seçin ve uzak araçları indirmek.

    > [!IMPORTANT]
    >  Visual Studio sürümünüzle eşleşen uzak Araçlar'ın en son sürümünü yüklemeniz önerilir. Eşleşmeyen sürümler önerilmez. Ayrıca, yüklemek istediğiniz işletim sistemi olarak aynı mimariye sahip uzak araçları yüklemeniz gerekir. Diğer bir deyişle, bir 64-bit işletim sistemi çalıştıran bir uzak bilgisayarda bir 32 bit uygulama hata ayıklamak istiyorsanız, uzak bilgisayarda Uzak Araçlar'ın 64 bit sürümü yüklemeniz gerekir.
    >
    >  Windows 10'da ARM cihazlarda hata ayıklama için Uzak Araçlar'ın en son sürümüyle kullanılabilen ARM64 indirmeyi seçin.  Windows RT cihazları için yalnızca Visual Studio 2015 RTW indirmesinde kullanılabilir ARM sürümünü seçin.

3.  Yürütülebilir dosya indirme işlemini tamamladıktan sonra sonraki bölüme gidin ve kurulum yönergeleri izleyin.

Uzaktan hata ayıklayıcı (msvsmon.exe) uzak bilgisayara kopyalayın ve çalıştırmak çalışırsanız unutmayın, **uzaktan hata ayıklayıcı Yapılandırma Sihirbazı'nı** (**rdbgwiz.exe**) yalnızca karşıdan yüklenir Araçlar. Özellikle bir hizmet olarak çalıştırmak için uzaktan hata ayıklayıcı isterseniz daha sonra Yapılandırma Sihirbazı'nı kullanmak gerekebilir. Daha fazla bilgi için [(isteğe bağlı) yapılandırma hizmet olarak uzaktan hata ayıklayıcı](../../debugger/remote-debugging.md#bkmk_configureService).
