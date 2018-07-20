---
title: Uzaktan hata ayıklayıcı bağlantı noktası atamaları | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: reference
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 988731be4376e1d1e402b3722bed157cc9b655d2
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151008"
---
# <a name="remote-debugger-port-assignments"></a>Uzaktan hata ayıklayıcı bağlantı noktası atamaları
Visual Studio uzaktan hata ayıklayıcı, bir uygulama veya bir arka plan hizmeti olarak çalıştırabilirsiniz. Bir uygulama olarak yürütüldüğünde, varsayılan olarak şu şekilde atanan bir bağlantı noktası kullanır:  

-   Visual Studio 2017:4022

-   Visual Studio 2015:4020  
  
-   Visual Studio 2013:4018  
  
-   Visual Studio 2012:4016  
  
 Diğer bir deyişle, her sürüm için 2 tarafından uzaktan hata ayıklayıcı için atanan bağlantı noktası numarası artırılır. Farklı bir bağlantı noktası numarası gibi ayarlayabilirsiniz. Şu bağlantı noktası numaraları daha sonraki bir bölümde ayarlama açıklanmaktadır.  
  
## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>32 bit işletim sistemlerinde uzaktan hata ayıklayıcı bağlantı noktası  
 TCP 4022 (Visual Studio 2017), ana bağlantı noktası ve tüm senaryolar için gereklidir. Bu komut satırı veya uzaktan hata ayıklayıcı penceresinde yapılandırabilirsiniz.  
  
 Uzaktan hata ayıklayıcı penceresinde **Araçlar > Seçenekler**, TCP/IP bağlantı noktası numarasını ayarlayın.  
  
 Uzaktan hata ayıklayıcı ile komut satırında başlatmak **/bağlantı noktası** geçiş: **msvsmon/Port \<bağlantı noktası numarası >**.  
  
 Komut satırı anahtarları hata ayıklama Uzaktan Yardım'daki tüm uzaktan hata ayıklayıcıyı bulabilirsiniz (basın **F1** veya **Yardım > kullanım** uzaktan hata ayıklayıcı penceresinde).  
  
## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>64-bit işletim sistemlerinde uzaktan hata ayıklayıcı bağlantı noktası  
 Uzaktan hata ayıklayıcı 64-bit sürümünü başlatıldığında varsayılan 4022 bağlantı noktasını kullanır.  Bir 32 bit işlemde hata ayıklamak, uzaktan hata ayıklayıcı 64-bit sürümünü 4023 bağlantı noktası üzerinde uzaktan hata ayıklayıcı bir 32-bit sürümü başlatır. 32-bit uzaktan hata ayıklayıcı çalıştırırsanız, 4022 kullanır ve 4023 kullanılmadığı.  
  
 Komut satırından Bu port yapılandırılabilirdir: **Msvsmon/wow64port \<bağlantı noktası numarası >**.  
  
## <a name="the-discovery-port"></a>Bulma bağlantı noktası  
 UDP 3702, ağ üzerinde çalışan uzaktan hata ayıklayıcı örneklerini bulmak için kullanılır (örneğin, **Bul** iletişim kutusunda **iliştirme** iletişim). Yalnızca makine adı veya IP adresi hedef bilgisayarın olduğunu bilmesinin başka bir şekilde varsa isteğe bağlı, bu nedenle uzaktan hata ayıklayıcı, çalışan bir makine bulmak için kullanılır. Bağlantı noktası numarası yapılandırılamaz için bu bulma, standart bir bağlantı noktasıdır.  
  
 Bulmayı etkinleştirmek istemiyorsanız msvsmon komut satırından devre dışı keşif ile başlayabilirsiniz: **Msvsmon /nodiscovery**.  
  
## <a name="remote-debugger-ports-on-azure"></a>Azure uzaktan hata ayıklayıcı bağlantı noktaları  
 Aşağıdaki bağlantı noktaları, Azure üzerinde uzaktan hata ayıklayıcı tarafından kullanılır. Bulut hizmeti bağlantı noktalarını tek tek bir VM üzerindeki bağlantı noktalarına eşlenir. TCP tüm bağlantı noktaları şunlardır.  
  
|bağlantı|Bulut hizmeti bağlantı noktası|VM üzerindeki bağlantı noktası|
|-|-|-|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)