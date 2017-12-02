---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 109d9d8718a2c46dbd982e58b22dcf43e55b2205
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
---
1.  Cihaz veya sunucu hata ayıklamak istediğiniz makine (yerine Visual Studio çalıştıran makine), uzak Araçlar doğru sürümünü alır.

    |Sürüm|Bağlantı|Notlar|
    |-|-|-|
    |Visual Studio 2017 güncelleştirme 4|[Uzak Araçlar](https://www.visualstudio.com/downloads/#remote-tools-for-visual-studio-2017)|Her zaman eşleştirme (x86 veya x64) aygıt işletim sistemi sürümünü yükleyin. Eski tarayıcılar için doğrudan bu bağlantıları kullanın: [uzak Araçları (x64)](https://go.microsoft.com/fwlink/?LinkId=746570&clcid=0x409) ve [uzak Araçları (x86)](https://go.microsoft.com/fwlink/?LinkId=746569&clcid=0x409).|
    |Visual Studio 2017 (eski)|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202017)|İstenirse, ücretsiz Visual Studio geliştirme Essentials gruba katılma veya geçerli bir Visual Studio abonelik oturum oturum açabilirsiniz. Eski tarayıcılar için istendiğinde Yeni güvenilen siteler eklemeniz gerekir.|
    |Visual Studio 2015 Güncelleştirme 3|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|İstenirse, ücretsiz Visual Studio geliştirme Essentials gruba katılma veya geçerli bir Visual Studio abonelik oturum oturum açabilirsiniz. Eski tarayıcılar için istendiğinde Yeni güvenilen siteler eklemeniz gerekir.|
    |Visual Studio 2015 (eski)|[Uzak Araçlar](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|İstenirse, ücretsiz Visual Studio geliştirme Essentials gruba katılma veya geçerli bir Visual Studio abonelik oturum oturum açabilirsiniz. Eski tarayıcılar için istendiğinde Yeni güvenilen siteler eklemeniz gerekir.|
    |Visual Studio 2013|[Uzak Araçlar](https://msdn.microsoft.com/library/bt727f1t(v=vs.120).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2013 belgelerinde indirme|
    |Visual Studio 2012|[Uzak Araçlar](https://msdn.microsoft.com/library/bt727f1t(v=vs.110).aspx#BKMK_Installing_the_Remote_Tools)|Visual Studio 2012 belgelerinde indirme|
  
2.  İndirme sayfasında işletim sisteminizi (x 86, x64 veya ARM) ile eşleşen araçları sürümü seçin ve uzak araçları indirin.
  
    > [!IMPORTANT]
    >  Visual Studio sürümünüzle eşleşen uzak araçları en son sürümünü yüklemeniz önerilir. Eşleşmeyen sürümleri önerilmez. Ayrıca, yüklemek istediğiniz işletim sistemi olarak aynı mimariye sahip uzak araçları yüklemeniz gerekir. Diğer bir deyişle, bir 64-bit işletim sistemi çalıştıran bir uzak bilgisayarda 32 bit uygulama hata ayıklama istiyorsanız, uzak bilgisayarda Uzak araçları 64-bit sürümünü yüklemeniz gerekir. 
    >   
    >  Yüzey 3 x64 için ARM geçiş mimarisi. Bir uzak Araçlar ARM sürümü için Visual Studio 2017 kullanılabilir değil. Visual Studio 2015 için Visual Studio 2015 RTW indirme ARM sürümü bulunamıyor.
  
3.  Yürütülebilir dosya indirme işlemini tamamladığınızda, sonraki bölüme gidin ve kurulum yönergelerini izleyin.

Uzaktan hata ayıklayıcı (msvsmon.exe) uzak bilgisayara kopyalayın ve bunu çalıştırmak çalışırsanız unutmayın, **uzaktan hata ayıklayıcı Yapılandırma Sihirbazı'nı** (**rdbgwiz.exe**) yalnızca karşıdan yüklenir Araçları. Özellikle bir hizmet olarak çalıştırmak için uzaktan hata ayıklayıcı isterseniz daha sonra Yapılandırma Sihirbazı'nı kullanmanız gerekebilir. Daha fazla bilgi için bkz: [(isteğe bağlı) yapılandırma hizmet olarak uzaktan hata ayıklayıcı](../../debugger/remote-debugging.md#bkmk_configureService).