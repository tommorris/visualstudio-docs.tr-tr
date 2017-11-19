---
title: "CRT kitaplığını kullanarak bellek sızıntılarını bulma | Microsoft Docs"
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
- breakpoints, on memory allocation
- _CrtMemState
- _CrtMemCheckpoint
- memory leaks
- _CrtMemDifference
- memory leaks, detecting and isolating
- _CrtDumpMemoryLeaks
- _CrtSetBreakAlloc
- _crtBreakAlloc
- _CrtSetReportMode
- memory, debugging
- _CrtMemDumpStatistics
- debugging memory leaks
- _CRTDBG_MAP_ALLOC
- _CrtSetDbgFlag
ms.assetid: cf6dc7a6-cd12-4283-b1b6-ea53915f7ed1
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e3c95f24db0dc158b668f0e324fd5bac066dd4ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="finding-memory-leaks-using-the-crt-library"></a>CRT Kitaplığını Kullanarak Bellek Sızıntılarını Bulma
Bellek sızıntıları, doğru önceden ayrılmış olan bellek ayırması hata olarak tanımlanan en ince ve sabit algılamak hataların C/C++ uygulamalarında arasındadır. Küçük bellek sızıntısı konumundaki ilk ancak zamanla fark edilmesi değil, aşamalı bellek sızıntısı belirtiler bu aralık performansın bellek yetersiz uygulamayı çalıştırdığında, kilitlenen için neden olabilir. Da kötüsü, tüm kullanılabilir bellek kullanan leaking bir uygulamayı Karışıklığı önlemek için hangi uygulama sorumludur oluşturma kilitlenme başka bir uygulamanın neden olabilir. Hatta görünen zararsız bellek sızıntıları düzeltilmesi diğer sorunlarını belirtisi olabilir.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hata ayıklayıcı ve C çalışma zamanı (CRT) kitaplıkları sağlar algılama ve bellek sızıntıları tanımlamak için anlamına gelir.  
  
## <a name="enabling-memory-leak-detection"></a>Bellek sızıntısı algılama etkinleştirme  
 Bellek sızıntıları hata ayıklayıcı ve C çalışma zamanı kitaplıkları (CRT) olan saptamak için birincil Araçlar heap işlevleri hata ayıklama.  
  
 Hata ayıklama yığını işlevleri etkinleştirmek için program aşağıdaki deyimleri ekleyin:  
  
```  
#define _CRTDBG_MAP_ALLOC  
#include <stdlib.h>  
#include <crtdbg.h>  
```  
  
 CRT işlevlerinin düzgün çalışması için için `#include` deyimleri burada gösterilen sırada izlemelidir.  
  
 Crtdbg.h eşlemeleri dahil olmak üzere `malloc` ve [ücretsiz](/cpp/c-runtime-library/reference/free) hata ayıklama sürümlerine işlevlere [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg) ve `free`, bellek ayırma ve ayırmayı kaldırma izleme. Bu eşleme olan yalnızca hata ayıklama derlemelerinde, oluşur `_DEBUG`. Yayın derlemeleri kullanma sıra `malloc` ve `free` işlevleri.  
  
 `#define` Deyimi karşılık gelen hata ayıklama sürümü CRT heap işlevleri temel sürümünü eşler. Atlarsanız `#define` deyimi, bellek sızıntısı dökümü daha az ayrıntılı.  
  
 Bu ifadeler kullanarak hata ayıklama yığını işlevleri etkinleştirdikten sonra yapılan bir çağrı yerleştirebilirsiniz `_CrtDumpMemoryLeaks` uygulamanızı çıkılırken bir bellek sızıntısı raporu görüntülemek için bir uygulama çıkış noktası önce:  
  
```  
_CrtDumpMemoryLeaks();  
```  
  
 Uygulamanız birden çok çıkar varsa, el ile yapılan bir çağrı yerleştirmeniz gerekmez [_CrtDumpMemoryLeaks](/cpp/c-runtime-library/reference/crtdumpmemoryleaks) her bir çıkış noktada. Çağrı `_CrtSetDbgFlag` uygulamanızı başında bir otomatik arama neden olur `_CrtDumpMemoryLeaks` her noktası çıkın. Burada gösterilen iki bit alanları ayarlamanız gerekir:  
  
```  
_CrtSetDbgFlag ( _CRTDBG_ALLOC_MEM_DF | _CRTDBG_LEAK_CHECK_DF );  
```  
  
 Varsayılan olarak, `_CrtDumpMemoryLeaks` bellek sızıntısı raporun çıkarır **hata ayıklama** bölmesinde **çıkış** penceresi. Kullanabileceğiniz `_CrtSetReportMode` rapor başka bir konuma yönlendirmek için.  
  
 Bir kitaplık kullanıyorsanız, kitaplık başka bir konuma çıkış sıfırlayabilir. Bu durumda, çıkış konumu ayarlayabilirsiniz geri **çıkış** penceresinde, aşağıda gösterildiği gibi:  
  
```  
_CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_DEBUG );  
```  
  
## <a name="interpreting-the-memory-leak-report"></a>Bellek sızıntısı raporu yorumlama  
 Uygulamanızı tanımlamaz, `_CRTDBG_MAP_ALLOC`, [_CrtDumpMemoryLeaks](/cpp/c-runtime-library/reference/crtdumpmemoryleaks) aşağıdakine benzer bir bellek sızıntısı raporu görüntüler:  
  
```  
Detected memory leaks!  
Dumping objects ->  
{18} normal block at 0x00780E80, 64 bytes long.  
 Data: <                > CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD  
Object dump complete.  
```  
  
 Uygulamanızı tanımlıyorsa `_CRTDBG_MAP_ALLOC`, bellek sızıntısı rapor şöyle görünür:  
  
```  
Detected memory leaks!  
Dumping objects ->  
c:\users\username\documents\projects\leaktest\leaktest.cpp(20) : {18}   
normal block at 0x00780E80, 64 bytes long.  
 Data: <                > CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD  
Object dump complete.  
```  
  
 İkinci rapor burada sızan bellek ilk ayrılır dosyasının adını ve satır numarası gösterir farktır.  
  
 Tanımladığınız olup `_CRTDBG_MAP_ALLOC` veya değil, aşağıdaki bilgileri görüntüle bellek sızıntısı rapor olacaktır:  
  
-   Bellek ayırma numarası `18` Bu örnekte  
  
-   [Engelleme türü](http://msdn.microsoft.com/en-us/e2f42faf-0687-49e7-aa1f-916038354f97), olduğu `normal` Bu örnekte.  
  
-   Onaltılık bellek konuma `0x00780E80` Bu örnekte.  
  
-   Blok boyutu `64 bytes` Bu örnekte.  
  
-   İlk 16 bayt veri bloğundaki onaltılık biçimde.  
  
 Bellek sızıntısı raporu, normal, istemci ya da CRT olarak bellek bloğu tanımlar. A *normal blok* sıradan bellek programınız tarafından ayrılmış. A *istemci blok* bir yıkıcı gerektiren nesneler için MFC programlar tarafından kullanılan bellek bloğu özel türüdür. MFC `new` işleci normal bloğu ya da oluşturulan nesne için uygun olarak bir istemci bloğu oluşturur. A *CRT blok* kendi kullanımı için CRT kitaplık tarafından ayrılmış. CRT kitaplık ayırmayı kaldırma bu blokları için işler. Bu nedenle, görürsünüz bu bellek sızıntısı rapordaki bir şey önemli ölçüde olmadığı sürece yanlış, örneğin, CRT kitaplık bozuk düşüktür.  
  
 Hiçbir zaman bellek sızıntısı raporlarında görünür bellek blokları diğer iki tür vardır. A *ücretsiz blok* yayımlandı bellektir. Bu, tanım gereği sızmış değil anlamına gelir. Bir *blok Yoksay* bellek sızıntısı rapordan dışlamak için açık olarak işaretlediğiniz bellektir.  
  
 Bu teknikler çalışmak için standart CRT kullanılarak ayrılmış bellek `malloc` işlevi. Programınızı C++ kullanarak bellek ayırır, `new` işleci, ancak yalnızca karşılaşabileceğiniz dosyası ve satır numarası burada genel uygulanması `operator new` çağrıları `_malloc_dbg` bellek sızıntısı rapordaki. Bu davranışı çok yararlı olmadığından ayırma şuna benzer bir makrosu kullanılarak yapılan satır bildirmek için değiştirebilirsiniz: 
 
```C++  
#ifdef _DEBUG
    #define DBG_NEW new ( _NORMAL_BLOCK , __FILE__ , __LINE__ )
    // Replace _NORMAL_BLOCK with _CLIENT_BLOCK if you want the
    // allocations to be of _CLIENT_BLOCK type
#else
    #define DBG_NEW new
#endif
```  
  
Değiştirebileceğiniz artık `new` kullanarak işleci `DBG_NEW` makrosu kodunuzda. Hata ayıklama derlemelerinde, bu genel bir aşırı yüklemesini kullanır `operator new` blok türü, dosya ve satır numarası ek parametreleri alır. Bu aşırı yüklemesini `new` çağrıları `_malloc_dbg` ek bilgileri kaydetmek için. Kullandığınızda `DBG_NEW`, bellek sızıntısı raporları sızan nesneleri burada ayrılan filename ve satır numarası göster. İsteğe bağlı olarak perakende yapılarında varsayılan kullanır `new`. (Adlı önişlemci makrosu oluşturduğunuz önermiyoruz `new`, veya başka bir dil anahtar.) Teknik bir örneği burada verilmiştir:  
  
```C++  
// debug_new.cpp
// compile by using: cl /EHsc /W4 /D_DEBUG /MDd debug_new.cpp
#define _CRTDBG_MAP_ALLOC
#include <cstdlib>
#include <crtdbg.h>

#ifdef _DEBUG
    #define DBG_NEW new ( _NORMAL_BLOCK , __FILE__ , __LINE__ )
    // Replace _NORMAL_BLOCK with _CLIENT_BLOCK if you want the
    // allocations to be of _CLIENT_BLOCK type
#else
    #define DBG_NEW new
#endif

struct Pod {
    int x;
};

void main() {
    Pod* pPod = DBG_NEW Pod;
    pPod = DBG_NEW Pod; // Oops, leaked the original pPod!
    delete pPod;

    _CrtDumpMemoryLeaks();
}
```  
  
Visual Studio'da çağrısı hata ayıklayıcısında bu kodu çalıştırdığınızda `_CrtDumpMemoryLeaks` bir rapor oluşturur **çıkış** penceresinde şuna benzer:  
  
```Output  
Detected memory leaks!
Dumping objects ->
c:\users\username\documents\projects\debug_new\debug_new.cpp(20) : {75}
 normal block at 0x0098B8C8, 4 bytes long.
 Data: <    > CD CD CD CD 
Object dump complete.
```  
  
Bu sızan ayırma debug_new.cpp satır 20 olduğunu bildirir.  
  
## <a name="setting-breakpoints-on-a-memory-allocation-number"></a>Bellek ayırma numaralı kesme noktalarını ayarlama  
 Bellek ayırma sayı ne zaman bir sızan bellek bloğu ayrıldı söyler. Bir blok bellek ayırma sayısıyla 18, örneğin, 18 uygulamanın çalışması sırasında ayrılmış bellek bloğudur. CRT raporun tüm bellek bloğu ayırmaları çalışması sırasında sayar. CRT kitaplık ve MFC gibi diğer kitaplıkları tarafından ayırmaları içerir. Bu nedenle, bir bellek ayırma sayısını 18 olan bir bloğun kodunuz tarafından ayrılan 18 bellek bloğu olmayabilir. Genellikle, bu olmaz.  
  
 Bellek ayırmada bir kesme noktası ayarlamak için ayırma numarası kullanabilirsiniz.  
  
#### <a name="to-set-a-memory-allocation-breakpoint-using-the-watch-window"></a>Gözcü penceresi kullanarak bir bellek ayırma kesme noktası ayarlamak için  
  
1.  Uygulamanızın başlangıç bir kesme noktası ayarlayın ve uygulamanızı başlatın.  
  
2.  Uygulamayı kesme noktasında böldüğünde **izleme** penceresi.  
  
3.  İçinde **izleme** penceresinde, türü `_crtBreakAlloc` içinde içinde **adı** sütun.  
  
     CRT kitaplık (/MD seçeneği) birden çok iş parçacıklı DLL sürümü kullanıyorsanız, context işleci şunları içerir:`{,,ucrtbased.dll}_crtBreakAlloc`  
  
4.  Tuşuna **iade**.  
  
     Hata ayıklayıcı çağrı değerlendirir ve sonuçta yerleştirir **değeri** sütun. Bellek ayırma tüm kesme noktalarını ayarlamadıysanız bu değer -1 olur.  
  
5.  İçinde **değeri** sütun, bellek ayırma ayırma sayısıyla kesmek istediğiniz yeri gösterilen değeri değiştirin.  
  
 Bellek ayırma numaralı bir kesme noktası ayarladıktan sonra hata ayıklama devam edebilirsiniz. Bellek ayırma sipariş değişmeyen aynı koşullarda programın önceki Çalıştır çalıştırılacak dikkatli olun. Programınızı sırasında belirtilen bellek ayırma böldüğünde kullanabileceğiniz **çağrı yığını** penceresini açın ve diğer hata ayıklayıcı windows altında bellek tahsis edildiğinde koşulları belirlemek için. Ardından, nesneye neler izlemek için yürütme devam ve neden, değil doğru serbest belirleyin.  
  
 Bir nesne üzerinde veri kesme noktası ayarlama de bu kadar faydalı olabilir. Daha fazla bilgi için bkz: [kullanarak kesme noktaları](../debugger/using-breakpoints.md).  
  
 Bellek ayırma kesme noktaları kodda de ayarlayabilirsiniz. Bunu yapmak için iki yol vardır:  
  
```  
_crtBreakAlloc = 18;  
```  
  
 veya:  
  
```  
_CrtSetBreakAlloc(18);  
```  
  
## <a name="comparing-memory-states"></a>Bellek durumları karşılaştırma  
 Bellek sızıntılarını bulma için başka bir teknik uygulamanın bellek durumu anahtar noktalarda anlık görüntüleri alma içerir. Belirli bir noktada bellek durumunun anlık uygulamanızda almak için oluşturma bir **_CrtMemState** yapısı ve ona geçirmek `_CrtMemCheckpoint` işlevi. Bu işlev bir anlık görüntü geçerli bellek durumunun yapısıyla doldurur:  
  
```  
_CrtMemState s1;  
_CrtMemCheckpoint( &s1 );  
  
```  
  
 `_CrtMemCheckpoint`yapısında geçerli bellek durumunun bir anlık görüntüsü ile doldurur.  
  
 İçeriğini çıktısını almak için bir **_CrtMemState** yapısı, yapısına geçirin `_ CrtMemDumpStatistics` işlevi:  
  
```  
_CrtMemDumpStatistics( &s1 );  
  
```  
  
 `_ CrtMemDumpStatistics`şuna benzer bellek durumu dökümünü çıkarır:  
  
```  
0 bytes in 0 Free Blocks.  
0 bytes in 0 Normal Blocks.  
3071 bytes in 16 CRT Blocks.  
0 bytes in 0 Ignore Blocks.  
0 bytes in 0 Client Blocks.  
Largest number used: 3071 bytes.  
Total allocations: 3764 bytes.  
  
```  
  
 Bellek sızıntısı kodunu bölümünde oluşup oluşmadığını belirlemek için önce ve sonra bölüm bellek durumu anlık görüntülerini almak ve sonra gerçekleştirebilirsiniz `_ CrtMemDifference` iki durumlu karşılaştırmak için:  
  
```  
_CrtMemCheckpoint( &s1 );  
// memory allocations take place here  
_CrtMemCheckpoint( &s2 );  
  
if ( _CrtMemDifference( &s3, &s1, &s2) )  
   _CrtMemDumpStatistics( &s3 );  
```  
  
 `_CrtMemDifference`bellek durumları karşılaştırır `s1` ve `s2` ve bir sonuç döndürür (`s3`) diğer bir deyişle fark `s1` ve `s2`.  
  
 Bellek sızıntılarını bulma için bir yöntem başlar koyarak `_CrtMemCheckpoint` başlangıcını ve bitişini sonra kullanarak uygulamanızın çağrıları `_CrtMemDifference` sonuçları karşılaştırmak için. Varsa `_CrtMemDifference` ekleyebileceğiniz daha fazla bellek sızıntısı gösterir `_CrtMemCheckpoint` sızıntısı kaynak buluncaya kadar bir ikili arama'yı kullanarak programınızı bölmek için çağrıları.  
  
## <a name="false-positives"></a>Hatalı pozitif sonuç  
 Bazı durumlarda, `_CrtDumpMemoryLeaks` bellek sızıntıları false göstergeleri verebilirsiniz. İç ayırmaları yerine _NORMAL_BLOCKs olarak işaretler bir kitaplık kullanıyorsanız, bu durum ortaya çıkabilir `_CRT_BLOCK`s veya `_CLIENT_BLOCK`s. Bu durumda, `_CrtDumpMemoryLeaks` kullanıcı ayırma ve iç kitaplığı ayırmaları arasındaki farkı söyleyin alamıyor. Burada, çağrı noktadan sonra kitaplık ayırmaları için genel Yıkıcılar çalıştırırsanız, `_CrtDumpMemoryLeaks`, her iç kitaplığı ayırma bellek sızıntısı bildirilir. Standart Şablon kitaplığı, Visual Studio .NET, nedeni'den önceki eski sürümleri `_CrtDumpMemoryLeaks` böyle false bildirmek için pozitif sonuç, ancak bu sabit son sürümlerde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT hata ayıklama öbeği ayrıntıları](../debugger/crt-debug-heap-details.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)
