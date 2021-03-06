---
title: Yerel kodda hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a4c8d5c19ea397f8fc23a962a045645740a1164
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631842"
---
# <a name="debugging-native-code"></a>Yerel Kodda Hata Ayıklama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yerel kodda hata ayıklama](https://docs.microsoft.com/visualstudio/debugger/debugging-native-code).  
  
Bu bölüm, bazı yaygın hata ayıklama sorunları ve yerel uygulamalar için teknikleri kapsar. Bu bölümde yer alan teknikleri, üst düzey tekniklerle aynıdır. Visual Studio hata ayıklayıcısını kullanarak mekanizması için bkz: [hata ayıklayıcı yol haritası](../debugger/debugger-basics.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: iyileştirilmiş kodda hata ayıklama](../debugger/how-to-debug-optimized-code.md)  
 Hata ayıklama, program, hata ayıklama ve yayın yapılandırmaları için varsayılan iyileştirme ayarlarını ve yalnızca en iyi duruma getirilmiş kod (açma görünen hataları bulmaya yönelik ipuçları iyileştirilmemiş bir sürümü neden hata ayıklama ipuçları sağlar, özellikle en iyileştirilmiş kodda iyileştirme hata ayıklama yapısı yapılandırması).  
  
 [DebugBreak ve __debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 Win32 açıklar `DebugBreak` işlev ve Platform SDK'sında, başvuru konularına bağlantı sağlar. Ayrıca açıklar `__debugbreak` iç.  
  
 [C/C++ onaylamaları](../debugger/c-cpp-assertions.md)  
 Onaylama deyimleri, nasıl çalıştıklarını, (bir işleminin sonuçlarını denetleme ve hata koşulları test çalýþýrçalýþma yakalama mantık hataları,), bunları kullanmanın avantajları anlatılmaktadır kendi etkileşim `_DEBUG`, desteklenen bir onayları türleri [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 [Nasıl yapılır: satır içi derleme kodunda hata ayıklama](../debugger/how-to-debug-inline-assembly-code.md)  
 YAZMAÇ içerikleri görüntülemek için derleme yönergeleri ve yazmaçlar penceresini görüntülemek için Ayrıştırılmış kod penceresini kullanma hakkında kısa yönerge sağlar ve bu windows ile ilgili konulara bağlantılar sağlar.  
  
 [MFC hata ayıklama teknikleri](../debugger/mfc-debugging-techniques.md)  
 Teknikleri dahil olmak üzere, MFC programları için hata ayıklama için bağlantılar: afxDebugBreak, bellek algılama TRACE makrosu, MFC, MFC onaylar sızıntıları ve MFC hata ayıklama boyutunu küçültmeyi oluşturur.  
  
 [CRT hata ayıklama teknikleri](../debugger/crt-debugging-techniques.md)  
 Bağlantıları, CRT hata ayıklama kitaplığı, raporlama, farklılıklardan malloc ve _malloc_dbg, yazma için makroları kullanma dahil olmak üzere C çalışma zamanı kitaplığı hata ayıklama tekniklerine hata ayıklama kanca işlevlerini ve CRT hata ayıklama yığını.  
  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)  
 Visual C++ programlarında hata ayıklama hakkında sık sorulan soruların yanıtlarını sağlar  
  
 [COM ve ActiveX hata ayıklaması](../debugger/com-and-activex-debugging.md)  
 COM için kullanabileceğiniz araçları da dahil olmak üzere, COM ve ActiveX uygulamalarında hata ayıklama ve ActiveX hata ayıklaması hakkında bilgi sağlar.  
  
 [Nasıl yapılır: yerel DLL'lerde hata ayıklama](../debugger/how-to-debug-native-dlls.md)  
 DLL dosyaları için yerel kod hata ayıklamayı kurma açıklanmaktadır.  
  
 [Nasıl yapılır: Püskürtülen kodda hata ayıklama](../debugger/how-to-debug-injected-code.md)  
 Öznitelikleri kullanan kod hata ayıklamayı konusunda rehberlik yapmaktadır. Kaynak ek açıklama üzerinde devre dışı bırakma, eklenen kodu görüntüleme ve geçerli yürütme noktasına ayrıştırılmış kodu görüntüleme yönergeleri içerir.  
  
 [İzlenecek yol: paralel uygulamada hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Nasıl kullanılacağını açıklar **Paralel Görevler** ve **Paralel Yığınlar** paralel uygulamada hata ayıklamak için windows aracı.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Visual C++ proje türleri](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 Hata ayıklama Visual C++ proje şablonları tarafından oluşturulan yerel proje türleri açıklayan konulara bağlantılar sağlar.  
  
 [Visual Studio’da hata ayıklama](../debugger/debugging-in-visual-studio.md)  
 Hata ayıklama belgesinin en geniş bölümlerine bağlantılar sağlar. Bilgileri içeren hata ayıklayıcı, ayarlar ve hazırlık, kesme noktaları, özel durumların işlenmesi yenilikler Düzenle ve devam et, yönetilen kodda hata ayıklama, yerel kodda hata ayıklama, SQL ve kullanıcı arabirimi başvuruları hata ayıklama.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)   
 [Visual Studio’da hata ayıklama](../debugger/debugging-in-visual-studio.md)



