---
title: Yerel kodda hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: f57f1e559452c64f9f1a7b019d75b52384081d65
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-native-code"></a>Yerel Kodda Hata Ayıklama
Bölüm bazı genel hata ayıklama sorunları ve yerel uygulamalar için teknikleri kapsar. Bu bölümde yer alan teknikleri üst düzey tekniklerle aynıdır. Visual Studio hata ayıklayıcısı kullanarak mekanizması için bkz: [hata ayıklayıcı yol haritası](../debugger/debugger-basics.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Nasıl yapılır: iyileştirilmiş kodda hata ayıklama](../debugger/how-to-debug-optimized-code.md)  
 Hata ayıklama, program, yalnızca (açma iyileştirilmiş kodda yer hataları bulmak için ipuçları ve hata ayıklama ve yayın yapılandırmaları varsayılan iyileştirme ayarlarını iyileştirilmemiş bir sürümü neden hata ayıklama ipuçları verir, özellikle en iyileştirilmiş kodda en iyi duruma getirme, hata ayıklama yapı yapılandırma).  
  
 [DebugBreak ve __debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 Win32 açıklar `DebugBreak` işlev ve Platform SDK'sındaki kendi başvuru konularına bağlantı sağlar. Ayrıca açıklanır `__debugbreak` iç.  
  
 [C/C++ onayları](../debugger/c-cpp-assertions.md)  
 Onaylama deyimleri, nasıl çalıştığını, bunları (bir işlem sonuçlarını denetleme ve hata koşullarını sınama çalýþýrçalýþma yakalama mantık hataları,), kullanmanın avantajları ele alınmaktadır kendi etkileşim `_DEBUG`ve desteklenen onaylar türlerini [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 [Nasıl yapılır: satır içi derleme kodunda hata ayıklama](../debugger/how-to-debug-inline-assembly-code.md)  
 YAZMAÇ içerikleri görüntülemek için derleme yönergeleri ve yazmaçlar penceresini görüntülemek için Ayrıştırılmış kod penceresini kullanarak kısa hakkında yönergeler sağlar ve bu windows ilgili konulara bağlantılar sağlar.  
  
 [MFC hata ayıklama teknikleri](../debugger/mfc-debugging-techniques.md)  
 Teknikleri de dahil olmak üzere, MFC programları için hata ayıklama için bağlantılar: afxDebugBreak, bellek algılama TRACE makrosu sızdırıyor MFC, MFC onaylar ve MFC hata ayıklama boyutunu azaltma oluşturur.  
  
 [CRT hata ayıklama teknikleri](../debugger/crt-debugging-techniques.md)  
 CRT hata ayıklama kitaplığı, raporlama, farklarını malloc ve _malloc_dbg, yazma için makroları kullanma dahil olmak üzere C çalışma zamanı kitaplığı için ayıklama teknikleri size kanca işlevleri ve CRT hata ayıklama bağlantılar hata ayıklama yığını.  
  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)  
 Visual C++ programlarında hata ayıklama hakkında sık sorulan soruların yanıtlarını sağlar  
  
 [COM ve ActiveX hata ayıklaması](../debugger/com-and-activex-debugging.md)  
 COM için kullanabileceğiniz araçları dahil olmak üzere, COM ve ActiveX uygulamalarında hata ayıklama ve ActiveX hata ayıklama hakkında bilgi sağlar.  
  
 [Nasıl yapılır: Püskürtülen kodda hata ayıklama](../debugger/how-to-debug-injected-code.md)  
 Özniteliklerini kullanır kodda hata ayıklama hakkında rehberlik sağlar. Kaynak ek açıklamayı devre dışı bırakma, eklenen kodu görüntüleme ve geçerli yürütme noktada ayrıştırılmış kodu görüntüleme konusunda yönergeler içerir.  
  
 [İzlenecek yol: paralel uygulamada hata ayıklama](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Nasıl kullanılacağını açıklar **Paralel Görevler** ve **Paralel Yığınlar** paralel uygulamada hata ayıklamak için windows aracı.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Visual C++ proje türleri](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 Visual C++ proje şablonları tarafından oluşturulan yerel proje türleri hata ayıklamak nasıl açıklayan konulara bağlantılar sağlar.  

 [DLL projelerinde hata ayıklama](../debugger/debugging-dll-projects.md) yerel ve yönetilen DLL'lerde hata ayıklama hakkında bilgi sağlar.
  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)  
 Hata ayıklama belge büyük bölümlerine bağlantılar sağlar. Bilgi içeren hata ayıklayıcı, ayarları ve hazırlığı, özel durumların işlenmesi kesme noktaları, yenilikler Düzenle ve devam etmek, yönetilen kodda hata ayıklama, yerel kodda hata ayıklama, SQL ve kullanıcı arabirimi başvuruları hata ayıklama.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)  
 [Visual Studio'da hata ayıklamayı](../debugger/index.md) [özelliği turu hata ayıklayıcı](../debugger/debugger-feature-tour.md)