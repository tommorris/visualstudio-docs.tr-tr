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
ms.openlocfilehash: cfb41cf6274238fef2de9b74496a33fba110e04f
ms.sourcegitcommit: fb73b56d45ebc0386cd4de1a706ba9e20c59daf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
Uzak bilgisayarda yönetici izinlerine sahip olması.  
  
1.  Uzaktan hata ayıklayıcı uygulama bulun. (Msvsmon.exe onu yüklendiği konumda bulunamadı veya arayın ve Başlat menüsünden açmak **uzaktan hata ayıklayıcı**.)
  
     Uzaktan hata ayıklayıcı uzak bir sunucuda çalışıyorsa, uzaktan hata ayıklayıcı uygulama sağ tıklatın ve seçin **yönetici olarak çalıştır**. Uzak bir sunucuda bu çalıştırmıyorsanız yalnızca başlatın normalde.
  
3.  Başlattığınızda uzak araçları ilk kez (veya, yapılandırdığınız önce), **uzaktan hata ayıklama yapılandırmasını** iletişim kutusu görüntülenir.  
  
     ![RemoteDebuggerConfWizardPage](../media/remotedebuggerconfwizardpage.png "RemoteDebuggerConfWizardPage")  
  
4.  Windows hizmeti API'si (yalnızca Windows Server 2008 R2 üzerinde gerçekleşen) yüklü değilse seçin **yükleme** düğmesi.  
  
5.  Üzerindeki uzak araçları kullanmak istediğiniz ağ türlerini seçin. En az bir ağ türü seçilmelidir. Bilgisayarlar üzerinden bir etki alanına bağlıysanız, ilk öğe seçmeniz gerekir. Bilgisayar bir çalışma grubu veya ev grubu aracılığıyla bağlıysanız, uygun şekilde ikinci ya da üçüncü öğesini seçmeniz gerekir.  
  
6.  Seçin **uzaktan hata ayıklama yapılandırma** güvenlik duvarını yapılandırın ve Aracı'nı başlatın.  
  
7.  Yapılandırma tamamlandıktan sonra uzaktan hata ayıklayıcı penceresi görüntülenir.
  
     ![RemoteDebuggerWindow](../media/remotedebuggerwindow.png "RemoteDebuggerWindow")
  
     Uzaktan hata ayıklayıcı şimdi bir bağlantı için bekliyor. Sunucu adını not edin ve bu Visual Studio'da daha sonra kullanmak yapılandırma ile eşleşmesi gerekir çünkü görüntülenir, numarası bağlantı noktası.  
  
 Hata ayıklama ve uzak hata ayıklayıcıyı gerek bittiğinde tıklatın **Dosya > çıkış** penceresinde. Buradan yeniden **Başlat** menü veya komut satırından:  
  
 **\<Visual Studio yükleme dizini > \Common7\IDE\Remote hata ayıklayıcı\\< x86, x64 veya Appx > \msvsmon.exe**.  
