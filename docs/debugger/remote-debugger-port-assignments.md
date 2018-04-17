---
title: Uzaktan hata ayıklayıcı bağlantı noktası atamaları | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 05/18/2017
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3872f11dff614e8fae4deeace7cdf301cd9b5e1c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="remote-debugger-port-assignments"></a>Uzaktan hata ayıklayıcı bağlantı noktası atamaları
Visual Studio uzaktan hata ayıklayıcı bir uygulama veya bir arka plan hizmeti olarak çalıştırabilirsiniz. Bir uygulama olarak çalıştığında, varsayılan olarak aşağıdaki gibi atanan bir bağlantı noktası kullanır:  

-   Visual Studio 2017:4022

-   Visual Studio 2015:4020  
  
-   Visual Studio 2013:4018  
  
-   Visual Studio 2012:4016  
  
 Diğer bir deyişle, her sürüm için 2 tarafından uzaktan hata ayıklayıcı için atanan bağlantı noktası numarası artırılır. Gibi farklı bir bağlantı noktası sayısını ayarlayabilirsiniz. Biz nasıl bir sonraki bölümde bağlantı noktası numaralarını ayarlanacağı açıklanmaktadır.  
  
## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>32-bit işletim sistemlerinde uzaktan hata ayıklayıcı bağlantı noktası  
 TCP 4022 (Visual Studio 2017) içindeki ana bağlantı noktasıdır ve tüm senaryoları için gereklidir. Bu komut satırı veya uzaktan hata ayıklayıcı penceresini yapılandırabilirsiniz.  
  
 Uzaktan hata ayıklayıcı penceresinde **Araçlar > Seçenekler**ve TCP/IP bağlantı noktası numarasını ayarlayın.  
  
 İle uzaktan hata ayıklayıcı komut satırında başlatmak **/bağlantı noktası** geçin: **msvsmon Port \<bağlantı noktası numarası >**.  
  
 Tüm uzaktan hata ayıklayıcı komut satırı anahtarları uzaktan hata ayıklama Yardım'da bulabilirsiniz (basın **F1** veya **yardımcı > kullanım** uzaktan hata ayıklayıcı penceresinde).  
  
## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>64-bit işletim sistemlerinde uzaktan hata ayıklayıcı bağlantı noktası  
 Uzaktan hata ayıklayıcı 64-bit sürümünü başlatıldığında, varsayılan 4022 bağlantı noktasını kullanır.  Bir 32 bit işlemde hata ayıklamak, uzaktan hata ayıklayıcı 64-bit sürümünü uzaktan hata ayıklayıcı 32-bit sürümünü 4023 bağlantı noktasında başlatır. 32-bit uzaktan hata ayıklayıcı çalıştırırsanız, 4022 kullanır ve 4023 kullanılmaz.  
  
 Komut satırından Bu port yapılandırılabilirdir: **Msvsmon /wow64port \<bağlantı noktası numarası >**.  
  
## <a name="the-discovery-port"></a>Bulma bağlantı noktası  
 UDP 3702, ağ üzerinde çalışan uzaktan hata ayıklayıcı örneklerini bulmak için kullanılır (örneğin, **Bul** iletişim kutusunda **ekleme işlemi için** iletişim). Yalnızca makine adı veya IP adresi hedef bilgisayarın bilmesinin başka bir şekilde varsa, isteğe bağlı olacak şekilde uzaktan hata ayıklayıcı çalıştıran bir makineye bulmak için kullanılır. Bağlantı noktası numarasını yapılandırılamaz şekilde bu bulma, standart bir bağlantı noktasıdır.  
  
 Bulmayı etkinleştirmek istemiyorsanız devre dışı bulma ile msvsmon komut satırından başlatabilirsiniz: **Msvsmon /nodiscovery**.  
  
## <a name="remote-debugger-ports-on-azure"></a>Azure üzerinde uzaktan hata ayıklayıcı bağlantı noktaları  
 Aşağıdaki bağlantı noktaları, Azure üzerinde uzaktan hata ayıklayıcı tarafından kullanılır. Bulut hizmeti bağlantı noktalarını tek tek VM üzerindeki bağlantı noktalarına eşlenir. TCP tüm bağlantı noktalarıdır.  
  
||||  
|-|-|-|  
|**Bağlantı**|**Bulut hizmeti bağlantı noktası**|**VM üzerinde bağlantı noktası**|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)