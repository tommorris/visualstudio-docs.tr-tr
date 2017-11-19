---
title: "Grafik tanılama örnekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45dd86b2-801e-4b07-a8c4-7bd25641d7f8
caps.latest.revision: "33"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0fd05d9b8e45b80c0c8bddf3ea1f776c385378b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="graphics-diagnostics-examples"></a>Grafik Tanılama Örnekleri
Bu örnekler kullanarak işleme sorunları DirectX tabanlı uygulamalarda hata ayıklamak nasıl [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] grafik tanılama.  
  
## <a name="capturing-graphics-information"></a>Graf bilgilerini yakalama  
 Uygulamanızda işleme sorunları tanılamak için grafik tanılamayı kullanmadan önce çalışırken uygulamasından grafik bilgilerini yakalama sahip. Grafik bilgilerini yerel olarak çalışan bir uygulama veya bir uzak bilgisayara veya başka bir aygıt üzerinde çalışan bir uygulama yakalanır. Bu izlenecek yollar nasıl el ile veya program aracılığıyla bir uygulamadan grafik bilgilerini yakalayabilir gösterilmektedir:  
  
-   [İzlenecek yol: Grafik bilgilerini yakalama](walkthrough-capturing-graphics-information.md)  
  
-   [İzlenecek yol: Grafik bilgilerini programla yakalama](walkthrough-capturing-graphics-information-programmatically.md)  
  
## <a name="use-graphics-diagnostics-with-an-arm-based-device"></a>Grafik tanılama ARM tabanlı bir cihaz ile kullanma  
 Uzaktan hata ayıklama kullanarak ARM tabanlı bir cihaz üzerinde Direct3D uygulamanızı hata ayıklamak için grafik tanılamayı kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: bir ARM aygıtıyla kullanım grafik tanılama](how-to-use-graphics-diagnostics-with-an-arm-device.md).  
  
## <a name="playing-back-graphics-information"></a>Grafik bilgilerini tekrar oynatma  
 Çalışan bir uygulamanın grafik bilgilerini yakalama sonra işleme sorunları tanılamak için yakalanan olayları oynatabilirsiniz. Kayıttan yürütmek için geliştirme makinenizde kullanabilirsiniz veya bir uzak makine ya da bağlı cihaz kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: grafik tanılama kayıttan yürütme makinesini değiştirme](how-to-change-the-graphics-diagnostics-playback-machine.md).  
  
## <a name="debugging-missing-objects"></a>Eksik nesneleri hata ayıklama  
 Eksik bir nesne (veya nesneler) deneyimine grafik geliştiriciler en yaygın işleme sorunları biridir. Bu tür sorunlar hataları birkaç farklı türde bir nesne görünüşe göre kayboluyor neden olabileceğinden tanılamak zor olabilir. Eksik nesneleri tipik nedenleri yanlış yapılandırılmış cihaz durumu, nesnenin geometri veya yanlış yapılandırılmış grafik ardışık düzen dönüştürme sorunları olabilir.  
  
 Bu senaryolar, nesneyi neden eksik olduğunu belirlemek ve sorumlu kodu bulmak için grafik tanılama nasıl kullanabileceğiniz gösterilmektedir.  
  
-   [İzlenecek yol: Cihaz durumu nedeniyle nesnelerin eksikliği](walkthrough-missing-objects-due-to-device-state.md)  
  
-   [İzlenecek yol: Köşe gölgeleme nedeniyle nesnelerin eksikliği](walkthrough-missing-objects-due-to-vertex-shading.md)  
  
-   [İzlenecek yol: Yanlış yapılandırılmış ardışık düzen nedeniyle nesnelerin eksikliği](walkthrough-missing-objects-due-to-misconfigured-pipeline.md)  
  
## <a name="debugging-rendering-errors"></a>İşleme hataları hata ayıklama  
 Doğru görünüm olmaması bir nesne (veya nesneler) deneyimine grafik geliştiriciler başka bir yaygın sorun ' dir. Bu tür sorunlar yanlış görünümünü ve onun neden gelen çok belirgin arasında olabilir çünkü tanılamak zor olabilir — yanlış doku bağlama — kadar çok ince — gölgelendirici kod veya beklenmeyen etkileşim gölgelendiriciler arasında bir hata. Bazı sorunlar hataların bir bileşimiyle kaynaklanıyor olabilir.  
  
 Tarafından ikincil gölgelendirici hata nedeniyle bir not şekilde Zarif işleme sorun aşağı izlemek için grafik tanılama nasıl kullanabileceğinizi gösteren bir senaryo aşağıda verilmiştir:  
  
-   [İzlenecek yol: Gölgeleme nedeniyle hataları işleme hata ayıklama](walkthrough-debugging-rendering-errors-due-to-shading.md)  
  
## <a name="debugging-compute-shaders"></a>İşlem gölgelendiriciler hata ayıklama  
 Hatalı sonuçlar üretmek DirectCompute işlem gölgelendirici tekrar hata ayıklamak için grafik tanılamayı kullanabilirsiniz. DirectCompute ile çok sayıda veri öğeleri paralel hesaplamalar için GPU hesaplama gücünü kullanabilirsiniz. Belirli sorun türlerini, GPU kullanılarak birçok kez bile iyi en iyi duruma getirilmiş CPU kodu daha hızlı gerçekleştirebilirsiniz. Ancak, geleneksel hata ayıklayıcıları GPU üzerinde çalışan bir kod algılayamaz. Bu tür bir kod hata ayıklama çoğunlukla satıcıya özgü ve de Visual Studio ile tümleştirmek değil özel araçlar gerektirir. İşlem gölgelendirici hata ayıklama, aralık GPU arasında daha tutarlı hale getirmek için grafik tanılamayı DirectCompute gönderme olayları yakalar — Direct3D işleme olaylarının yanı sıra — böylece sorunları işlem gölgelendirici kodunuzda hata ayıklamak için alıştığınız araçları kullanabilirsiniz.  
  
 Gölgelendiricisinde bir hatadan kaynaklanır benzetimi sorun hata ayıklamak nasıl gösteren bir senaryo için bkz [izlenecek yol: bir işlem gölgelendirici hata ayıklamak için grafik Tanılama'yı kullanarak](walkthrough-using-graphics-diagnostics-to-debug-a-compute-shader.md).