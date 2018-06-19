---
title: Spy ++'a giriş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Spy++
ms.assetid: 733b514b-63a9-402d-89aa-4f0416766655
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 826ef03bcca176d095c2110ed14227bb5faa2dbd
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31481453"
---
# <a name="introducing-spy"></a>Spy++'a Giriş
Spy ++ aşağıdaki görevleri gerçekleştirmenize olanak sağlar:  
  
-   Sistem nesneleri arasındaki ilişkileri grafik ağacı görüntüler. Bunlar [işlemleri](../debugger/processes-view.md), [iş parçacığı](../debugger/threads-view.md), ve [windows](../debugger/windows-view.md).  
  
-   Belirtilen arama [windows](../debugger/how-to-search-for-a-window-in-windows-view.md), [iş parçacığı](../debugger/how-to-search-for-a-thread-in-threads-view.md), [işlemleri](../debugger/how-to-search-for-a-process-in-processes-view.md), veya [iletileri](../debugger/how-to-search-for-a-message-in-messages-view.md).  
  
-   Özelliklerini görüntülemek seçili [windows](../debugger/how-to-display-window-properties.md), [iş parçacığı](../debugger/how-to-display-thread-properties.md), [işlemleri](../debugger/how-to-display-process-properties.md), veya [iletileri](../debugger/how-to-display-message-properties.md).  
  
-   Pencere, iş parçacığı, işlem veya ileti doğrudan görünümünde seçin.  
  
-   Kullanım [Bulucu Aracı](../debugger/how-to-use-the-finder-tool.md) fare işaretçisini konumlandırma tarafından bir pencere seçin.  
  
-   Ayarlama [ileti seçeneği](../debugger/how-to-open-messages-view-from-find-window.md) karmaşık ileti günlüğü seçimi parametrelerini kullanarak.  
  
 Spy ++ araç çubuğu ve daha hızlı çalışmanıza yardımcı olmak için köprüler vardır. Ayrıca sağlar bir **yenileme** etkin Görünümü güncelleştirmek için komut bir **pencere Bulucu Aracı** daha kolay spying yapmak için ve bir **yazı tipi** iletişim kutusunu görüntüle Windows'u özelleştirmek için. Ayrıca, Spy ++ kaydetme ve kullanıcı tercihleri geri yükleme sağlar.  
  
 Çeşitli Spy ++ windows, sık kullanılan komutlar bir kısayol menüsünü görüntülemek için sağ tıklayabilirsiniz. Hangi komutlar işaretçinin nerede olduğuna bağlıdır. Örneğin, penceresi görünümü bir girişe sağ tıklatın ve seçili pencere görünür ise, tıklatarak **vurgulayın** kısayolu menü bunu daha kolay bulunabilir böylece Flash seçilen pencere kenarlık neden olur.  
  
> [!NOTE]
>  Spy ++ benzeyen iki diğer yardımcı programları vardır: işlemler, iş parçacıklarını ve DDESPY ilgili ayrıntıları gösteren PView. EXE dinamik veri değişimi (DDE) iletileri izlemenize izin verir.  
  
## <a name="64-bit-operating-systems"></a>64-bit işletim sistemleri  
 Spy ++'ın iki sürümü vardır. Spy ++ (spyxx.exe) adlı ilk sürümü, 32 bit işlemde çalıştırılıyor bir pencere gönderilen iletileri görüntülemek için tasarlanmıştır. Örneğin, Visual Studio bir 32 bit işlemde çalıştırır. Bu nedenle, Spy ++ gönderilen iletileri görüntülemek için kullanabileceğiniz **Çözüm Gezgini**. Visual Studio'da çoğu yapılar için varsayılan yapılandırma bir 32 bit işlemde çalıştırmak için bu ilk sürümü Spy ++ olanı olduğundan [kullanılabilir **Araçları** menü](../debugger/how-to-start-spy-increment.md) Visual Studio.  
  
 Spy ++ (64 bit) (spyxx_amd64.exe) adlı ikinci sürümü 64-bit işlemde çalıştırılıyor bir pencere gönderilen iletileri görüntülemek için tasarlanmıştır. Örneğin, bir 64-bit işletim sisteminde 64-bit işlemde Notepad çalışır. Bu nedenle, Spy ++ (64 bit) Not Defteri'ne gönderilen iletileri görüntülemek için kullanabilirsiniz. Spy ++ (64 bit) genellikle bulunur  
  
 .. \\ *Visual Studio yükleme klasörü*\Common7\Tools\spyxx_amd64.exe.  
  
 Her iki sürümü Spy ++ doğrudan komut satırından çalıştırabilirsiniz.  
  
> [!NOTE]
>  Spy ++ (64 bit) dosya adı "amd" içerse de, Windows işletim sistemi herhangi x64 üzerinde çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz. 
 [Nasıl yapılır: Spy ++ hizmetini başlatma](../debugger/how-to-start-spy-increment.md)   
 [Spy ++ kullanma](../debugger/using-spy-increment.md)   
 [Spy ++ görünümleri](../debugger/spy-increment-views.md)   
 [Spy++ Başvurusu](../debugger/spy-increment-reference.md)