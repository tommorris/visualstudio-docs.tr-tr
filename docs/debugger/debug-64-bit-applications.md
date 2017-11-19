---
title: "64 Bit uygulamalarda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], 64-bit
- 64-bit debugging
ms.assetid: db648e5f-6375-4e2d-aa98-eb7261958927
caps.latest.revision: "32"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7866b0edf372dd7801d68e3f71212e9989b65ff0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debug-64-bit-applications"></a>64 Bit uygulamalarda hata ayıklama
Yerel bilgisayarda veya uzak bilgisayarda çalışan bir 64-bit uygulama ayıklayabilirsiniz.  
  
 Uzak bir bilgisayarda çalışan bir 64-bit uygulama hata ayıklamak için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).  
  
 64 bit uygulamalarda hata ayıklama için yerel olarak Visual Studio bir 64 bit çalışan işlemi (msvsmon.exe) 32-bit Visual Studio işlemi içinde gerçekleştirilemez düşük düzey işlemler gerçekleştirmek için kullanır.  
  
 .NET Framework sürüm 3.5 veya önceki kullanan 64 bit işlemleri için karışık mod hata ayıklaması desteklenmiyor.  
  
## <a name="debug-a-64-bit-application"></a>64 bit bir uygulama hata ayıklama  
 64 bit bir uygulama hata ayıklama denemek için:  
  
1.  Visual Studio çözümü, örneğin bir C# konsol uygulaması oluşturun.  
  
2.  64-bit Yapılandırma Yöneticisi'ni kullanarak yapılandırmasını ayarlayın. Daha fazla bilgi için bkz: [nasıl yapılır: projeleri hedef platformlar yapılandırma](../ide/how-to-configure-projects-to-target-platforms.md).  
  
3.  Bu aşamada uzaktan hata ayıklayıcı (msvsmon.exe) 64 bit sürümünü başlatır. 64-bit yapılandırma çözümüyle açık olduğu sürece çalıştırır.  
  
4.  Hata ayıklama başlatılamıyor. Aynı deneyimi gibi 32-bit yapılandırmasına sahip olmalıdır. Hataları alırsanız aşağıdaki sorun giderme bölümüne bakın.  
  
## <a name="troubleshooting-64-bit-debugging"></a>64-bit hata ayıklama sorunlarını giderme  
 Bir hata görebilirsiniz: "64-bit hata ayıklama işlemi beklenenden uzun sürüyor." Bu durumda, Visual Studio msvsmon.exe 64-bit sürümü için bir istek gönderdi ve geri dönmeniz bu isteğinin sonucunu uzun bir süredir sürdü.  
  
 Bu hata için iki ana nedeni vardır:  
  
-   Ağ güvenlik yazılımının güvenilir olmadığı ağ yığınını neden oldu, bilgisayarınızda yüklü olması ve localhost giden paketlere bıraktı. Tüm ağ güvenlik yazılımı devre dışı bırakmayı deneyin ve bu giderilip giderilmediğine bakın. Bu durumda, rapor yazılım localhost trafiğini engelliyor olabilir, ağ güvenlik yazılımı satıcınıza için.  
  
-   Visual Studio kilitlenebilir veya Performans sorun içine çalışıyor. Sorun düzenli olarak oluşursa, dökümleri, Visual Studio (devenv.exe) ve (msvsmon.exe) çalışan işlem toplar ve bunları Microsoft'a gönderir. Bir sorun raporlama hakkında daha fazla bilgi için bkz: [Visual Studio ile ilgili bir sorun bildirme](../ide/How-to-Report-a-Problem-with-Visual-Studio-2017.md).
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [64-bit uygulamalar](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)   
 [Programları 64 Bit için yapılandırma](/cpp/build/configuring-programs-for-64-bit-visual-cpp)   
 [Visual Studio IDE 64-Bit desteği](../ide/visual-studio-ide-64-bit-support.md)   
 [Döküm dosyalarını kullanma](../debugger/using-dump-files.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)