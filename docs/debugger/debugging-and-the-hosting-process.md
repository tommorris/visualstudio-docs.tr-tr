---
title: "Hata ayıklama ve barındırma işlemi | Microsoft Docs"
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
- debugging [Visual Studio], hosting process
- hosting process
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 01d4ebaada2c8ac65c1f44a5c80525f1b9e66a5d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-and-the-hosting-process"></a>Hata Ayıklama ve Barındırma İşlemi
Barındırma işlemi Visual Studio hata ayıklayıcısı performansını artırır ve kısmi güven hata ayıklama ve tasarım zamanı ifade değerlendirmesi gibi yeni hata ayıklayıcı özellikleri etkinleştirir. Gerekirse, barındırma işlemini devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: barındırma sürecini devre dışı bırakma](../ide/how-to-disable-the-hosting-process.md). Aşağıdaki bölümlerde ile ve barındırma işlemi olmadan hata ayıklama arasındaki bazı farklar açıklanmaktadır.  
  
## <a name="partial-trust-debugging-and-click-once-security"></a>Kısmi güven hata ayıklama ve tıklatın-bir kez güvenlik  
 Kısmi güven hata ayıklama barındırma işlemi gerektirir. Barındırma işlemini devre dışı bırakırsanız, kısmi güven güvenlik etkin olsa bile kısmi güven hata ayıklama çalışmaz **güvenlik** sayfasında **proje özelliklerini**. Daha fazla bilgi için bkz: [nasıl yapılır: barındırma sürecini devre dışı bırakma](../ide/how-to-disable-the-hosting-process.md) ve [nasıl yapılır: bir kısmi güven uygulama hata ayıklama](../debugger/how-to-debug-a-partial-trust-application.md).  
  
## <a name="design-time-expression-evaluation"></a>Tasarım zamanı ifade değerlendirmesi  
 Tasarım zamanı ifade her zaman barındırma işlemi kullanır. Barındırma devre dışı bırakma işlemi **proje özelliklerini** Sınıf Kitaplığı projelerinde için tasarım zamanı ifade değerlendirmesi devre dışı bırakır. Diğer proje türleri için tasarım zamanı ifade değerlendirmesi devre dışı değil. Bunun yerine, Visual Studio gerçek yürütülebilir başlar ve barındırma işlemi olmadan tasarım zamanı değerlendirmesi için kullanır. Bu farkı farklı sonuçlar.  
  
## <a name="appdomaincurrentdomainfriendlyname-differences"></a>AppDomain.CurrentDomain.FriendlyName farklar  
 `AppDomain.CurrentDomain.FriendlyName`barındırma işlemi etkinleştirilip etkinleştirilmediği bağlı olarak farklı sonuçlar döndürür. Çağırırsanız `AppDomain.CurrentDomain.FriendlyName` etkin barındırma işlemi ile döndürdüğü *app_name*`.vhost.exe`. Bunu devre dışı barındırma işlemi çağırdığınızda, döndürür *app_name*`.exe`.  
  
## <a name="assemblygetcallingassemblyfullname-differences"></a>Assembly.GetCallingAssembly(). FullName farklar  
 `Assembly.GetCallingAssembly().FullName`barındırma işlemi etkinleştirilip etkinleştirilmediği bağlı olarak farklı sonuçlar döndürür. Çağırırsanız `Assembly.GetCallingAssembly().FullName` etkin barındırma işlemi ile döndürdüğü `mscorlib`. Çağırırsanız `Assembly.GetCallingAssembly().FullName` isteğe bağlı olarak barındırma işlemini devre dışı uygulama adını döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Barındırma süreci (vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [Nasıl yapılır: kısmen güvenilen uygulamada hata ayıklama](../debugger/how-to-debug-a-partial-trust-application.md)   
 [Nasıl Yapılır: Barındırma Sürecini Devre Dışı Bırakma](../ide/how-to-disable-the-hosting-process.md)