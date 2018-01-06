---
title: "CRT hata ayıklama öbeği ayrıntıları | Microsoft Docs"
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
- debug heap, accessing
- heap functions
- _CRTDBG_CHECK_ALWAYS_DF macro
- _CrtMemDumpStatistics function
- debugging [C++], debug heap
- _CRT_BLOCK macro
- DBGINT.H file
- _CrtMemDumpAllObjectsSince function
- _crtBreakAlloc global variable
- _CrtMemState function
- _CLIENT_BLOCK macro
- _FREE_BLOCK block
- _CrtMemBlockHeader function
- heap state reporting functions
- _CRTDBG_ALLOC_MEM_DF macro
- _CrtSetBreakAlloc function
- memory blocks, allocation types on debug heap
- debugging [C++], CRT debug support
- debug heap, tracking heap allocation requests
- memory allocation, debug heap
- _NORMAL_BLOCK block
- crtBreakAlloc global variable
- _CrtDoForAllClientObjects function
- new operator, using debug heap from C++
- _CrtSetDumpClient function
- debugging [CRT], heap-related problems
- debug heap, solving memory allocation problems
- _CrtMemCheckpoint function
- debug builds, linking to debug heap
- _IGNORE_BLOCK block
- _crtDbgFlag function
- client blocks, specifying subtypes
- memory leaks, tracking
- _CrtSetDbgFlag function
- nBlockUse method
- memory leaks, CRT debug library functions
- _CRTDBG_DELAY_FREE_MEM_DF macro
- allocation request numbers
- _CRTDBG_LEAK_CHECK_DF macro
- debug heap
- memory, debugging
- _CrtReportBlockType function
- _CrtDumpMemoryLeaks function
- _CrtCheckMemory function
- debug heap, CRT
- memory blocks, free
- _BLOCK_TYPE macro
- debug heap, memory blocks
- heap allocation, debug
- debugging memory leaks
- _BLOCK_SUBTYPE macro
- debug heap, using from C++
- _CrtMemDifference function
- heap allocation, tracking requests
- debugging [Visual Studio], debug heap
- delete operator, using debug heap from C++
- blocks, types of on the debug heap
- _CRTDBG_CHECK_CRT_DF macro
- debug heap, reporting functions
ms.assetid: bf78ace6-28e4-4a04-97c6-39e0cdd00ba4
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cc7b945a8c53d290f573eac4565f2240ec7a2d7b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="crt-debug-heap-details"></a>CRT Hata Ayıklama Öbeği Ayrıntıları
Bu konu CRT hata ayıklama yığınını ayrıntılı bir bakış sağlar.  
  
##  <a name="BKMK_Contents"></a>İçeriği  
 [Hata ayıklama yığınını ile arabellek taşmaları Bul](#BKMK_Find_buffer_overruns_with_debug_heap)  
  
 [Hata ayıklama yığınındaki blokları türleri](#BKMK_Types_of_blocks_on_the_debug_heap)  
  
 [Yığın bütünlüğü ve bellek sızıntıları denetle](#BKMK_Check_for_heap_integrity_and_memory_leaks)  
  
 [Hata ayıklama yığınını yapılandırın](#BKMK_Configure_the_debug_heap)  
  
 [Yeni, silme ve _CLIENT_BLOCKs c++ hata ayıklama yığını](#BKMK_new__delete__and__CLIENT_BLOCKs_in_the_C___debug_heap)  
  
 [Yığın durumu raporlama işlevleri](#BKMK_Heap_State_Reporting_Functions)  
  
 [Yığın ayırma isteklerini izleme](#BKMK_Track_Heap_Allocation_Requests)  
  
##  <a name="BKMK_Find_buffer_overruns_with_debug_heap"></a>Hata ayıklama yığınını ile arabellek taşmaları Bul  
 İki programcıları karşılaştığınız en yaygın ve çözümü sorunları (artık gerekli olmayan sonra ayırmaları boşaltmak başarısız olan) bir ayrılmış arabellek ve bellek sızıntıları sonuna üzerine. Hata ayıklama yığınını bu tür bellek ayırma sorunlarını çözmek için güçlü araçlar sağlar.  
  
 Heap işlevleri sürümleri sürümde kullanılan standart ya da temel sürümleri çağrısı hata ayıklama derlemeleri. Bir bellek bloğu istediğinde, hata ayıklama yığını Yöneticisi temel yığınından biraz daha büyük bir blok istenir ve bu bloğu, kısmı için bir işaretçi döndürür daha bellek ayırır. Örneğin, uygulamanızın içeren çağrı varsayalım: `malloc( 10 )`. Yayın derlemesi içinde [malloc](/cpp/c-runtime-library/reference/malloc) 10 bayt ayırma isteyen temel öbek ayırma yordamı çağırırdı. Ancak, bir hata ayıklama derlemesi içinde `malloc` çağırırdı [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg), hangi ardından çağıran bir ayırma 10 bayt artı yaklaşık 36 bayt ek bellek isteme temel öbek ayırma yordamı. Hata ayıklama yığınını ortaya çıkan tüm bellek blokları olduğunda bunlar ayrılan göre sıralanmış tek bağlı bir liste bağlanır.  
  
 Hata ayıklama yığını yordamları tarafından ayrılan ek bellek muhasebe bilgileri bağlantı hata ayıklama bellek blokları birlikte ve yakalamak için verilerinizin her iki tarafında küçük arabellekleri için üzerine yazılacağını ayrılmış bölgesini işaretçileri için kullanılır.  
  
 Şu anda, hata ayıklama yığınını 's muhasebe bilgilerini depolamak için kullanılan bloğu üst bilgisi yapısı şu şekilde DBGINT bildirildi. H üstbilgi dosyası:  
  
```  
typedef struct _CrtMemBlockHeader  
{  
// Pointer to the block allocated just before this one:  
    struct _CrtMemBlockHeader *pBlockHeaderNext;  
// Pointer to the block allocated just after this one:  
    struct _CrtMemBlockHeader *pBlockHeaderPrev;  
    char *szFileName;    // File name  
    int nLine;           // Line number  
    size_t nDataSize;    // Size of user block  
    int nBlockUse;       // Type of block  
    long lRequest;       // Allocation number  
// Buffer just before (lower than) the user's memory:  
    unsigned char gap[nNoMansLandSize];  
} _CrtMemBlockHeader;  
  
/* In an actual memory block in the debug heap,  
 * this structure is followed by:  
 *   unsigned char data[nDataSize];  
 *   unsigned char anotherGap[nNoMansLandSize];  
 */  
```  
  
 `NoMansLand` Arabellek bloğunun kullanıcı veri alanının her iki tarafında şu anda 4 bayt boyutunda olan ve kullanıcının bellek bloğu sınırları değil üzerine yazıldı olduğunu doğrulamak için hata ayıklama yığını yordamları tarafından kullanılan bir bilinen bayt değeri ile doldurulur. Hata ayıklama yığınını ayrıca yeni bellek blokları bilinen bir değerle doldurur. Aşağıda açıklandığı gibi boşaltılmış blokları öbek 's bağlantılı listesinde tutmak seçerseniz, bu boşaltılmış blokları da bilinen bir değerle doldurulur. Şu anda kullanılan gerçek bayt değerleri şunlardır:  
  
 NoMansLand (0xFD)  
 Her iki tarafında bir uygulama tarafından kullanılan bellek "NoMansLand" arabellekleri şu anda 0xFD ile doldurulur.  
  
 Boşaltılmış blokları (0xDD)  
 Hata ayıklama yığınını içinde kullanılmayan tutulan boşaltılmış blokları bağlı ne zaman listesinde `_CRTDBG_DELAY_FREE_MEM_DF` bayrağı ayarlanmış şu anda 0xDD ile doldurulur.  
  
 Yeni nesneler (0xCD)  
 Yeni nesneler bunlar ayırırken 0xCD ile doldurulur.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop")  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Types_of_blocks_on_the_debug_heap"></a>Hata ayıklama yığınındaki blokları türleri  
 Her bellek bloğu hata ayıklama yığınındaki ayırma beş türden biri için atanır. Bu tür izlenen ve farklı sızıntısı algılama ve durumu raporlama amaçları doğrultusunda bildirdi. Hata ayıklama yığın ayırma işlevleri birine doğrudan çağrı gibi kullanarak ayırarak bir bloğun türünü belirtebilirsiniz [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg). Bellek blokları hata ayıklama yığınındaki beş türleri (kümesinde **nBlockUse** üyesi **_CrtMemBlockHeader** yapısı) aşağıdaki gibidir:  
  
 **_NORMAL_BLOCK**  
 Çağrı [malloc](/cpp/c-runtime-library/reference/malloc) veya [calloc](/cpp/c-runtime-library/reference/calloc) Normal bir blok oluşturur. Yalnızca Normal blokları kullanın ve istemci blokları için gerekli olan yapmak istiyorsanız, tanımlamak isteyebilirsiniz [_CRTDBG_MAP_ALLOC](/cpp/c-runtime-library/crtdbg-map-alloc), hata ayıklama eşdeğerlerine hata ayıklama derlemelerinde eşleştirilmesini neden olan tüm yığın ayırma çağırır. Bu dosya adı ve satır numarası hakkında bilgi karşılık gelen blok üstbilgisinde depolanması için her ayırma çağrı olanak tanır.  
  
 `_CRT_BLOCK`  
 Ayrı olarak işlenebilir için dahili olarak birçok çalışma zamanı kitaplığı işlevleri tarafından ayrılan bellek blokları blokları CRT işaretlenir. Sonuç olarak, algılama sızıntısı ve diğer işlemleri onlar tarafından etkilenmez. Bir ayırma gerekir hiçbir zaman ayırmak, yeniden tahsis veya herhangi bir bloğuna CRT türü boş.  
  
 `_CLIENT_BLOCK`  
 Bir uygulama bellek bloğu, hata ayıklama yığını işlevleri için açık çağrılarını kullanarak bu tür olarak ayırarak hata ayıklama amacıyla ayırmalarının belirli bir grupta özel izini kullanmaya devam edebilir. MFC, örneğin, ayırır tüm **CObjects** istemci blokları; diğer uygulamaların istemci bloklarında farklı bellek nesneleri tutabilirsiniz. İstemci blokları subtypes için büyük İzleme ayrıntı düzeyi de belirtilebilir. İstemci blokları subtypes belirtmek için sayı shift tarafından 16 bit sol ve `OR` ile `_CLIENT_BLOCK`. Örneğin:  
  
```  
#define MYSUBTYPE 4  
freedbg(pbData, _CLIENT_BLOCK|(MYSUBTYPE<<16));  
```  
  
 İstemci blokları içinde depolanan nesneleri dökme için bir istemci tarafından sağlanan kanca işlevi kullanılarak yüklenebilir [_CrtSetDumpClient](/cpp/c-runtime-library/reference/crtsetdumpclient)ve bir istemci bloğu hata ayıklama işlevi tarafından yazılan her sonra çağrılır. Ayrıca, [_CrtDoForAllClientObjects](/cpp/c-runtime-library/reference/crtdoforallclientobjects) hata ayıklama yığınındaki her istemci bloğu için uygulama tarafından sağlanan belirli bir işlevi çağırmak için kullanılabilir.  
  
 **_FREE_BLOCK**  
 Normalde, kurtulurlar blokları listesinden kaldırılır. Bellek serbest denetlemek için değil hala olma yazılır veya yetersiz bellek koşulları benzetimini yapmak için ücretsiz işaretlenmiş ve bilinen bayt değeri (şu anda 0xDD) ile doldurulan bağlantılı liste boşaltılmış blokları tutmak seçebilirsiniz.  
  
 **_IGNORE_BLOCK**  
 Bir süre için hata ayıklama yığını işlemleri devre dışı bırakmak mümkündür. Bu süre boyunca bellek blokları listede tutulur, ancak blokları Yoksay olarak işaretlenir.  
  
 Türüne ve alt verilen bloğunun belirlemek için işlevi kullanmak [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype) ve makrolar **_BLOCK_TYPE** ve **_BLOCK_SUBTYPE**. Makrolar (crtdbg.h içinde), şu şekilde tanımlanır:  
  
```  
#define _BLOCK_TYPE(block)          (block & 0xFFFF)  
#define _BLOCK_SUBTYPE(block)       (block >> 16 & 0xFFFF)  
```  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Check_for_heap_integrity_and_memory_leaks"></a>Yığın bütünlüğü ve bellek sızıntıları denetle  
 Hata ayıklama yığınını ait özelliklerin çoğunu kodunuzu içinde erişilen gerekir. Aşağıdaki bölümde bazı özellikleri ve bunların nasıl kullanılacağını açıklar.  
  
 `_CrtCheckMemory`  
 Çağrı kullanabilirsiniz [_CrtCheckMemory](/cpp/c-runtime-library/reference/crtcheckmemory), örneğin, herhangi bir noktada öbek 's bütünlüğünü denetlemek için. Bu işlev her bellek bloğu yığınındaki inceler, bellek bloğu üst bilgileri geçerli olduğunu doğrular ve arabellek değiştirilmemiş onaylar.  
  
 `_CrtSetDbgFlag`  
 Nasıl hata ayıklama yığınını kullanan bir iç bayrağı ayırmaları izler denetleyebilirsiniz [_crtDbgFlag](/cpp/c-runtime-library/crtdbgflag), hangi okunabilir ve kullanılarak ayarlanan [_CrtSetDbgFlag](/cpp/c-runtime-library/reference/crtsetdbgflag) işlevi. Bu bayrak değiştirilerek, program çıktığında bellek sızıntıları için denetleyin ve algılanan sızıntıları raporlamak için hata ayıklama yığınını söyleyebilirsiniz. Benzer şekilde, boşaltılmış bellek blokları düşük bellek durumlarda benzetimini yapmak için bağlantılı listesinden kaldırılmaması belirtebilirsiniz. Öbek işaretlendiğinde, bu boşaltılmış blokları kendi bütün bunlar rahatsız edilmemiş emin olmak için denetlenir.  
  
 **_CrtDbgFlag** bayrağı aşağıdaki bit alanları içerir:  
  
|Bit alan|Varsayılan<br /><br /> value|Açıklama|  
|---------------|-----------------------|-----------------|  
|**_CRTDBG_ALLOC_MEM_DF**|Açık|Hata ayıklama ayırma açar. Birbirine zincirlenmiş bu bit olduğunda kapalı, ayırmaları kalır ancak bunların blok türü **_ıgnore_block**.|  
|**_CRTDBG_DELAY_FREE_MEM_DF**|Kapalı|Aslında, düşük bellek koşulları benzetimi için olduğu gibi bırakılan gelen bellek engeller. Bu bit açık olduğunda, boşaltılmış blokları hata ayıklama yığınını 's bağlantılı listesinde tutulur ancak olarak işaretlenmiş **_FREE_BLOCK** ve özel bayt değeri ile doldurulur.|  
|**_CRTDBG_CHECK_ALWAYS_DF**|Kapalı|Neden **_CrtCheckMemory** her ayırma ve ayırmayı kaldırma sırasında çağrılabilir. Bu, yürütme yavaşlatır, ancak hataları hızla yakalar.|  
|**_CRTDBG_CHECK_CRT_DF**|Kapalı|Neden türü olarak işaretlenmiş blokları **_CRT_BLOCK** sızıntısı algılama ve durumu fark işlemlerinde dahil edilecek. Bu bit kapalıyken, dahili olarak çalışma zamanı kitaplığı tarafından kullanılan bellek gibi işlemleri sırasında göz ardı edilir.|  
|**_CRTDBG_LEAK_CHECK_DF**|Kapalı|Programdan çıkılırken bir çağrı aracılığıyla gerçekleştirilmek üzere sızıntısı denetimi neden **_CrtDumpMemoryLeaks**. Uygulama, ayrılmış tüm belleği boşaltmak başarısız olursa bir hata raporu oluşturulur.|  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Configure_the_debug_heap"></a>Hata ayıklama yığınını yapılandırın  
 Heap işlevleri gibi tüm çağrıları `malloc`, `free`, `calloc`, `realloc`, `new`, ve `delete` hata ayıklama sürümleri hata ayıklama yığınında çalışması bu işlevlerin çözümlenemiyor. Bir bellek bloğu boş olduğunda hata ayıklama yığınını otomatik olarak ayrılmış alanınızı her iki tarafında arabellekleri bütünlüğünü denetler ve üzerine oluştu, hata raporu verir.  
  
 **Hata ayıklama yığınını kullanmak için**  
  
-   C çalışma zamanı kitaplığı hata ayıklama sürümü, uygulamanızın hata ayıklama derlemesi bağlayın.  
  
 **Bir veya daha fazla _crtDbgFlag bit alanları değiştirin ve bayrağı için yeni bir durum oluşturmak için**  
  
1.  Çağrı `_CrtSetDbgFlag` ile `newFlag` parametre kümesine `_CRTDBG_REPORT_FLAG` (geçerli edinme `_crtDbgFlag` durumu) ve döndürülen değer geçici bir değişkende saklayın.  
  
2.  Herhangi bir BITS tarafından Aç `OR`- lık (bit düzeyinde &#124; sembol) (uygulama kodunda bildirim sabitler tarafından gösterilen) karşılık gelen bit maskesi geçici değişkenle.  
  
3.  Diğer BITS tarafından devre dışı bırakma `AND`- lık (bit düzeyinde & simgesi) değişkenle bir `NOT` (bit düzeyinde ~ simgesi), uygun bit maskesi.  
  
4.  Çağrı `_CrtSetDbgFlag` ile `newFlag` parametre kümesine geçici değişkeninde depolanan değer için yeni durum oluşturmak için `_crtDbgFlag`.  
  
 Örneğin, aşağıdaki kod satırlarını otomatik sızıntısı algılamayı etkinleştirme ve türü bloklarını için denetimini devre dışı bırakma `_CRT_BLOCK`:  
  
```  
// Get current flag  
int tmpFlag = _CrtSetDbgFlag( _CRTDBG_REPORT_FLAG );  
  
// Turn on leak-checking bit.  
tmpFlag |= _CRTDBG_LEAK_CHECK_DF;  
  
// Turn off CRT block checking bit.  
tmpFlag &= ~_CRTDBG_CHECK_CRT_DF;  
  
// Set flag to the new value.  
_CrtSetDbgFlag( tmpFlag );  
```  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_new__delete__and__CLIENT_BLOCKs_in_the_C___debug_heap"></a>Yeni, silme ve _CLIENT_BLOCKs c++ hata ayıklama yığını  
 C çalışma zamanı kitaplığı hata ayıklama sürümleri C++ hata ayıklama sürümleri içeren `new` ve `delete` işleçler. Kullanırsanız `_CLIENT_BLOCK` ayırma türü, hata ayıklama sürümü çağırmalıdır `new` doğrudan işleci veya değiştirme makroları oluşturmak `new` hata ayıklama modunda aşağıdaki örnekte gösterildiği gibi işleci:  
  
```  
/* MyDbgNew.h  
 Defines global operator new to allocate from  
 client blocks  
*/  
  
#ifdef _DEBUG  
   #define DEBUG_CLIENTBLOCK   new( _CLIENT_BLOCK, __FILE__, __LINE__)  
#else  
   #define DEBUG_CLIENTBLOCK  
#endif // _DEBUG  
  
/* MyApp.cpp  
        Use a default workspace for a Console Application to  
 *      build a Debug version of this code  
*/  
  
#include "crtdbg.h"  
#include "mydbgnew.h"  
  
#ifdef _DEBUG  
#define new DEBUG_CLIENTBLOCK  
#endif  
  
int main( )   {  
    char *p1;  
    p1 =  new char[40];  
    _CrtMemDumpAllObjectsSince( NULL );  
}  
```  
  
 Hata ayıklama sürümü `delete` tüm blok işleci çalışır türleri ve yayın sürümünü derlediğinizde programınızdaki herhangi bir değişiklik gerektirmez.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Heap_State_Reporting_Functions"></a>Yığın durumu raporlama işlevleri  
 **_CrtMemState**  
  
 Belirli bir zamanda öbek durumunun Özet bir anlık görüntü yakalamak için CRTDBG içinde tanımlanan _CrtMemState yapısı kullanın. Y:  
  
```  
typedef struct _CrtMemState  
{  
    // Pointer to the most recently allocated block:  
    struct _CrtMemBlockHeader * pBlockHeader;  
    // A counter for each of the 5 types of block:  
    size_t lCounts[_MAX_BLOCKS];  
    // Total bytes allocated in each block type:  
    size_t lSizes[_MAX_BLOCKS];  
    // The most bytes allocated at a time up to now:  
    size_t lHighWaterCount;  
    // The total bytes allocated at present:  
    size_t lTotalCount;  
} _CrtMemState;  
```  
  
 Bu yapı işaretçi hata ayıklama yığınını 's bağlantılı listesinin ilk (en yakın zamanda ayrılmış) bloğunda kaydeder. Ardından, iki dizide, her tür bir bellek kaç engelleme kaydeder (_NORMAL_BLOCK, `_CLIENT_BLOCK`, _FREE_BLOCK, vb.) listesini ve her blok türünde ayrılan bayt sayısı. Son olarak, bu noktaya kadar bir bütün olarak yığınında ayrılan bayt sayısı en yüksek sayıda ve şu anda ayrılan bayt sayısını kaydeder.  
  
 **Raporlama diğer CRT işlevleri**  
  
 Aşağıdaki işlevleri öbek içeriğini ve durum raporu ve bellek sızıntıları ve diğer sorunları saptamaya yardımcı olmak için bilgileri kullanın.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[_CrtMemCheckpoint](/cpp/c-runtime-library/reference/crtmemcheckpoint)|Yığın anlık kaydeder bir **_CrtMemState** uygulama tarafından sağlanan yapısı.|  
|[_CrtMemDifference](/cpp/c-runtime-library/reference/crtmemdifference)|İki bellek durumu yapıları karşılaştırır, üçüncü durumu yapısındaki aralarındaki farkı kaydeder ve iki durumlu farklı varsa TRUE değerini döndürür.|  
|[_CrtMemDumpStatistics](/cpp/c-runtime-library/reference/crtmemdumpstatistics)|Dökümleri bir verilen **_CrtMemState** yapısı. Yapısı, belirli bir süre veya iki anlık görüntüsü arasındaki farkı hata ayıklama yığınını durumunun anlık görüntü içerebilir.|  
|[_CrtMemDumpAllObjectsSince](/cpp/c-runtime-library/reference/crtmemdumpallobjectssince)|Belirli bir anlık görüntü öbek veya yürütme başından alındıktan sonra ayrılan tüm nesneler hakkındaki bilgileri dökümünü yapar. Bunu dökümleri her zaman bir **_clıent_block** bloğu biri kullanılarak yüklenmişse, uygulama tarafından sağlanan bir kanca işlevini çağırır **_CrtSetDumpClient**.|  
|[_CrtDumpMemoryLeaks](/cpp/c-runtime-library/reference/crtdumpmemoryleaks)|Tüm bellek program yürütme başladığından bu yana oluştu sızdırıyor ve bu durumda, tüm ayrılmış nesneleri dökümleri, belirler. Her zaman **_CrtDumpMemoryLeaks** dökümleri bir **_clıent_block** bloğu biri kullanılarak yüklenmişse, uygulama tarafından sağlanan bir kanca işlevini çağırır **_CrtSetDumpClient**.|  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
##  <a name="BKMK_Track_Heap_Allocation_Requests"></a>Yığın ayırma isteklerini izleme  
 Konumundaki kaynak dosya adı ve satır numarası yerini tam olarak belirtmekte rağmen bir assert ya da raporlama makrosu yürüten genellikle bir sorunun nedenini bulmak faydalıdır, aynı yığın ayırma işlevleri true olarak büyük olasılıkla uygun değildir. Bir uygulamanın mantığı ağacında birçok uygun noktalarda makroları eklenebilir, ancak bir ayırma genellikle birçok farklı yerlerden birçok farklı zamanlarda adlı özel bir yordama içinde kaçınma. Hangi satır kod hatalı bir ayırma oluşturulmayan soru genellikle olan ancak yerine hangisinin ayırmaları binlerce kod satırını tarafından yapılan hatalı ve neden oldu.  
  
 **Benzersiz ayırma isteği numaraları ve _crtBreakAlloc**  
  
 Yanlış gittiğini belirli öbek ayırma çağrısı tanımlamak için basit hata ayıklama yığınını her blok ile ilişkili benzersiz ayırma isteği numarası yararlanmak için yoldur. Bir blok hakkında bilgi döküm işlevleri biri tarafından bildirildiğinde bu ayırma isteği sayı ayraçları (örneğin, "{36}") içine alınır.  
  
 Yanlış ayrılmış bir blok ayırma isteği sayısını öğrendikten sonra bu sayı için geçirebilirsiniz [_CrtSetBreakAlloc](/cpp/c-runtime-library/reference/crtsetbreakalloc) bir kesme noktası oluşturmak için. Yürütme yalnızca blok ayırma önce çalışmamasına neden olur ve hangi yordam için hatalı çağrı sorumlu belirlemek için geri izlemeyi. Yeniden derlenmesi önlemek için hata ayıklayıcı aynı şeyi ayarlayarak gerçekleştirebilirsiniz **_crtBreakAlloc** ilgilendiğiniz ayırma isteği sayısı.  
  
 **Hata ayıklama sürümleri ayırma yordamları oluşturma**  
  
 Biraz daha karmaşık bir yaklaşım için karşılaştırılabilir kendi ayırma yordamları hata ayıklama sürümleri oluşturmaktır **_dbg** sürümleri [yığın ayırma işlevleri](../debugger/debug-versions-of-heap-allocation-functions.md). Sonra kaynak dosyasını ve satır numarası bağımsız değişkenleri aracılığıyla için temel alınan öbek ayırma yordamları geçirebilirsiniz ve hemen hatalı bir ayırma geldiği görmeye devam.  
  
 Örneğin, aşağıdakine benzer bir sık kullanılan yordamı uygulamanız bulunduğunu varsayın:  
  
```  
int addNewRecord(struct RecStruct * prevRecord,  
                 int recType, int recAccess)  
{  
    // ...code omitted through actual allocation...   
    if ((newRec = malloc(recSize)) == NULL)  
    // ... rest of routine omitted too ...   
}  
```  
  
 Bir üstbilgi dosyasında aşağıdaki gibi kod ekleyebilirsiniz:  
  
```  
#ifdef _DEBUG  
#define  addNewRecord(p, t, a) \  
            addNewRecord(p, t, a, __FILE__, __LINE__)  
#endif  
```  
  
 Ardından, bunu ayırma kaydı oluşturma yordamında aşağıdaki gibi değiştirebilirsiniz:  
  
```  
int addNewRecord(struct RecStruct *prevRecord,  
                int recType, int recAccess  
#ifdef _DEBUG  
               , const char *srcFile, int srcLine  
#endif  
    )  
{  
    /* ... code omitted through actual allocation ... */  
    if ((newRec = _malloc_dbg(recSize, _NORMAL_BLOCK,  
            srcFile, scrLine)) == NULL)  
    /* ... rest of routine omitted too ... */  
}  
```  
  
 Artık kaynak dosyanın adı ve satır numarası nerede `addNewRecord` çağrıldı hata ayıklama yığınında ayrılan her elde edilen bloğu depolanır ve bu blok incelenir zaman bildirilir.  
  
 ![Başa dön](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [içeriği](#BKMK_Contents)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)