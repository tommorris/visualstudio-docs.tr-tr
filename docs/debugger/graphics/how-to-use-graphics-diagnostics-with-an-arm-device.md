---
title: "Nasıl yapılır: grafik tanılama bir ARM aygıtla kullanmak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 346fd3c0-9e92-4ab8-bb3b-1aa9000a2483
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eedc7e454c6523c1ab29e4ae685b14954c8e6d98
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-graphics-diagnostics-with-an-arm-device"></a>Nasıl yapılır: grafik tanılama bir ARM aygıtla kullanın
Grafik tanılama Direct3D uygulamaları Windows RT 8.1 veya Windows Phone 8.1 çalıştıran ARM tabanlı cihazlarda uzaktan hata ayıklama destekler. Cihaz üzerinde çalışırken Direct3D uygulamanızdan grafik bilgilerini yakalama veya aygıt daha önce yakalanan grafik bilgilerini kayıttan yürütme makinesini olarak kullanın.  
  
## <a name="using-graphics-diagnostics-with-an-arm-based-device"></a>ARM tabanlı bir cihaz ile grafik tanılamayı kullanma  
 Visual Studio ARM tabanlı cihazlarda çalışma değil çünkü bunlar üzerinde çalışan bir uygulamanın çözümlemek için uzaktan hata ayıklayıcı kullanmak zorunda. İşleme hataları tanılamak ve bu cihazlarda grafik performansı kolayca uygulamanıza bunları ayıklayabilirsiniz olarak değerlendirmek için uzaktan hata ayıklayıcı grafik yakalama ve kayıttan yürütme destekler.  
  
 Grafik tanılama özelliklerini kullanmak için önce aygıtınıza uzaktan hata ayıklama etkinleştirin.  
  
#### <a name="to-enable-remote-debugging-on-your-arm-based-device"></a>ARM tabanlı Cihazınızı uzaktan hata ayıklamayı etkinleştirmek için  
  
1.  Yükleme [ARM Setleri İlkesi](http://msdn.microsoft.com/windows/desktop/dn469188) ARM tabanlı Cihazınızda.  
  
2.  Yükleme [uzaktan hata ayıklama araçları](http://go.microsoft.com/fwlink/?LinkId=393086) ARM tabanlı Cihazınızda.  
  
> [!IMPORTANT]
>  Windows Phone 8.1 cihazları için telefonunuz geliştirme için kaydetmeniz gerekebilir. Bunu yapmak için kayıtlı bir geliştirici olması gerekir. Daha fazla bilgi için bkz: [dağıtmak ve Windows Phone 8 için bir uygulamayı çalıştırmak nasıl](http://msdn.microsoft.com/library/windowsphone/develop/ff402565.aspx).  
  
 Uzaktan hata ayıklama Cihazınızda etkinleştirdikten sonra hata ayıklama hedefi kolaylaştırır ve grafik tanılama başlatın.  
  
#### <a name="to-configure-and-start-graphics-diagnostics-on-your-device"></a>Yapılandırma ve grafik tanılama aygıtınızda başlatmak için  
  
1.  Üzerinde **çözüm platformları** aşağı açılan listesinden, **ARM** ARM tabanlı Cihazınızı uzaktan hata ayıklama hedefi olarak kullanılabilir olmayacaktır.  
  
2.  Üzerinde **hata ayıklama hedefi** aşağı açılan listesinde, ARM Cihazınızı seçin.  
  
3.  Menüsünde, **hata ayıklama**, **grafik**, **Başlat tanılama**. (Klavye: Alt + F5)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir uzak makinede UWP uygulamaları çalıştırma](../run-windows-store-apps-on-a-remote-machine.md)   
 [Nasıl Yapılır: Grafik Tanılama Kayıttan Yürütme Makinesini Değiştirme](how-to-change-the-graphics-diagnostics-playback-machine.md)