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
ms.openlocfilehash: b6e312f7e1913a8b4533c0127b966dc3ac0d981d
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38809277"
---
Uzak bilgisayarda yönetimsel izinleriniz olmalıdır.  
  
1.  Uzaktan hata ayıklayıcı uygulamasını bulun. (Burada, yüklü konumunda msvsmon.exe bulun veya Başlat menüsünü açıp arama **uzaktan hata ayıklayıcı**.)
  
     Uzaktan hata ayıklayıcı uzak bir sunucuda çalışıyorsa, uzaktan hata ayıklayıcı uygulama sağ tıklatın ve seçin **yönetici olarak çalıştır**. Uzak bir sunucuda, çalıştırmıyorsanız yalnızca başlatın normalde.
  
3.  Başladığınızda uzak araçları ilk kez (veya yapılandırmış olduğunuz önce), **uzaktan hata ayıklama Yapılandırması** iletişim kutusu görüntülenir.  
  
     ![RemoteDebuggerConfWizardPage](../media/remotedebuggerconfwizardpage.png "RemoteDebuggerConfWizardPage")  
  
4.  Windows hizmeti API'si (yalnızca Windows Server 2008 R2 üzerinde gerçekleşen) yüklü değilse seçin **yükleme** düğmesi.  
  
5.  Uzak araçları kullanmak istediğiniz ağ türlerini seçin. En az bir ağ türü seçilmelidir. Bilgisayarları bir etki alanına bağlıysanız, ilk öğe seçmeniz gerekir. Bilgisayar bir çalışma grubunda veya ev grubu bağlıysa, uygun şekilde ikinci veya üçüncü öğe seçmek gerekir.  
  
6.  Seçin **uzaktan hata ayıklamayı Yapılandır** güvenlik duvarını ve Aracı'nı başlatın.  
  
7.  Yapılandırma tamamlandıktan sonra uzaktan hata ayıklayıcı penceresi görüntülenir.
  
     ![RemoteDebuggerWindow](../media/remotedebuggerwindow.png "RemoteDebuggerWindow")
  
     Uzaktan hata ayıklayıcı şimdi bir bağlantı için bekliyor. Sunucu adını not edin ve bu daha sonra Visual Studio'da kullandığınız yapılandırma eşleşmelidir çünkü bağlantı noktası görüntülenir, numarası.  
  
 Hata ayıklama ve uzaktan hata ayıklayıcıyı gerek bittiğinde tıklatın **Dosya > çıkış** penceresinde. Buradan yeniden **Başlat** menüsünden veya komut satırından:  
  
 **\<Uzaktan hata ayıklayıcı yükleme dizini >\\< x86, ARM, ARM64 veya Appx x64 > \msvsmon.exe**.  
