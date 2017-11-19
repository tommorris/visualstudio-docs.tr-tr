---
title: "Nasıl yapılır: grafik tanılama kayıttan yürütme makinesini değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b9aa3ea-29a0-4e21-bc57-936f33537b5c
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 35b8eb174ea8e0ca238bafe5a05dfbba54855cda
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-change-the-graphics-diagnostics-playback-machine"></a>Nasıl Yapılır: Grafik Tanılama Kayıttan Yürütme Makinesini Değiştirme
Grafik bilgilerini yerel makinenize veya bir uzak makine ya da cihaz kullanarak geri yürütebilirsiniz.  
  
## <a name="choosing-a-playback-machine"></a>Kayıttan yürütme makinesini seçme  
 Kayıttan yürütme makinesini makine ya da bir grafik günlüğündeki grafik olaylar çalmak için kullanılan aygıt ' dir. Genellikle, yerel makine en uygun seçenektir ancak bir işleme sorun nerede yakalanan farklı bir donanım veya sürücü sürümlerini sayısından olduğu bir makineye oluşturmak değildir; Bu durumda, sorunu daha iyi oluşmazsa bir uzak kayıttan yürütme makinesini seçin ve hala bu tanılamak için geliştirme makinenizde kullanın.  
  
#### <a name="to-use-the-local-machine-to-play-back-graphics-information"></a>Grafik bilgilerini çalmak için yerel makine kullanmak için  
  
1.  Grafik günlük belgesi penceresinde, seçin **kayıttan yürütme makinesini** bağlantı. **Uzaktan hata ayıklayıcı bağlantıları** iletişim kutusu görüntülenir.  
  
2.  Altında **el ile yapılandırma**, **adresi** özelliği girin `localhost`.  
  
3.  Ayarlama **kimlik doğrulama modu** özelliğine **hiçbiri**.  
  
4.  Seçin **seçin** düğmesi.  
  
#### <a name="to-use-a-remote-machine-to-play-back-graphics-information"></a>Grafik bilgilerini çalmak için bir uzak makine kullanmak için  
  
1.  Grafik günlük belgesi penceresinde, seçin **kayıttan yürütme makinesini** bağlantı. **Uzaktan hata ayıklayıcı bağlantıları** iletişim kutusu görüntülenir.  
  
2.  Altında **el ile yapılandırma**, **adresi** özelliği, Windows etki alanı adı veya IP adresini Makine ya da grafik bilgilerini çalmak için kullanmak istediğiniz aygıt girin.  
  
3.  Kayıttan yürütme makinesini bağlantısı güvenliğini sağlamak için kullanmak istediğiniz yetkilendirme türünü belirtin.  
  
    -   Windows kimlik doğrulaması için ayarlanmış **kimlik doğrulama modu** özelliğine **Windows**.  
  
    -   Hiçbir kimlik doğrulamasını ayarlamak **kimlik doğrulama modu** özelliğine **hiçbiri**.  
  
4.  Seçin **seçin** düğmesi.  
  
> [!NOTE]
>  **Uzaktan hata ayıklayıcı bağlantıları** iletişim kutusu, aynı alt ağda geliştirme makinenizde doğrudan bağlı ya da uzaktan hata ayıklama hedeflerini de görüntülenebilir. Bu uzaktan hata ayıklama hedeflerini birini el ile yapılandırma olmadan grafik tanılama kayıttan yürütme makinesini kullanabilirsiniz. İçinde **uzaktan hata ayıklayıcı bağlantıları** iletişim kutusunda, istediğiniz ve ardından hedef seçin **seçin** düğmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik günlük belgesi](graphics-log-document.md)