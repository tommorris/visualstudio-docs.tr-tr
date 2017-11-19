---
title: "MFC hata ayıklama teknikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AfxEnableMemoryTracking
- CMemoryState
- delayFreeMemDF
- checkAlwaysMemDF
- vs.debug.mfc
- vs.debug.objects.dump
- vs.debug.memory.dump
- allocMemDF
- afxMemDF
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugging [MFC]
ms.assetid: b154fc31-5e90-4734-8cbd-58dd9fe1f750
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 274cd182fa3b9eab23c151a4143c935c24f68fea
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="mfc-debugging-techniques"></a>MFC Hata Ayıklama Teknikleri
Bir MFC programı hata ayıklama, bu hata ayıklama teknikleri yararlı olabilir.  
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
 [AfxDebugBreak](#BKMK_AfxDebugBreak)  
  
 [TRACE makrosu](#BKMK_The_TRACE_macro)  
  
 [Bellek MFC'de sızıntılarını algılama](#BKMK_Memory_leak_detection_in_MFC)  
  
-   [Bellek ayırma izleme](#BKMK_Tracking_memory_allocations)  
  
-   [Bellek Tanılama'yı etkinleştirme](#BKMK_Enabling_memory_diagnostics)  
  
-   [Bellek anlık görüntüleri alma](#BKMK_Taking_memory_snapshots)  
  
-   [Bellek istatistiklerini görüntüleme](#BKMK_Viewing_memory_statistics)  
  
-   [Alma nesne dökümünü yapar](#BKMK_Taking_object_dumps)  
  
    -   [Bellek yorumlama dökümünü yapar](#BKMK_Interpreting_memory_dumps)  
  
    -   [Özelleştirme nesne dökümünü yapar](#BKMK_Customizing_object_dumps)  
  
     [MFC hata ayıklama yapı boyutunu azaltma](#BKMK_Reducing_the_size_of_an_MFC_Debug_build)  
  
    -   [Seçili modülleri için hata ayıklama bilgileri bir MFC uygulaması oluşturma](#BKMK_Building_an_MFC_app_with_debug_information_for_selected_modules)  
  
##  <a name="BKMK_AfxDebugBreak"></a>AfxDebugBreak  
 MFC sağlayan özel bir [AfxDebugBreak](http://msdn.microsoft.com/Library/c4cd79b9-9327-4db5-a9d6-c4004a92aa30) işlevi kaynak kodunda kesme noktaları kodlamak için:  
  
```  
AfxDebugBreak( );  
  
```  
  
 Intel platformlarda `AfxDebugBreak` hangi sonları kaynak kod çekirdek kodu yerine aşağıdaki kodu üretir:  
  
```  
_asm int 3  
```  
  
 Diğer platformlarda `AfxDebugBreak` yalnızca çağırır `DebugBreak`.  
  
 Kaldırdığınızdan emin olun `AfxDebugBreak` bir yayın oluşturduğunuzda deyimleri oluşturabilir veya kullanabilirsiniz `#ifdef _DEBUG` çevreleyen için.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_The_TRACE_macro"></a>TRACE makrosu  
 Hata ayıklayıcıda programınızdan iletileri görüntülemek için [çıktı penceresi](../ide/reference/output-window.md), kullanabileceğiniz [ATLTRACE](http://msdn.microsoft.com/Library/c796baa5-e2b9-4814-a27d-d800590b102e) makrosu ya da MFC [izleme](http://msdn.microsoft.com/Library/7b6f42d8-b55a-4bba-ab04-c46251778e6f) makrosu. Gibi [onaylar](../debugger/c-cpp-assertions.md), izleme makroları yalnızca programınızı hata ayıklama sürümü etkin olan ve yayın sürümünde derlendiğinde kaybolur.  
  
 Aşağıdaki örnekler kullanabileceğiniz yollardan bazılarını göstermek **izleme** makrosu. Gibi `printf`, **izleme** makrosu bağımsız değişken sayısı işleyebilir.  
  
```  
int x = 1;  
int y = 16;  
float z = 32.0;  
TRACE( "This is a TRACE statement\n" );  
  
TRACE( "The value of x is %d\n", x );  
  
TRACE( "x = %d and y = %d\n", x, y );  
  
TRACE( "x = %d and y = %x and z = %f\n", x, y, z );  
```  
  
 TRACE makrosu uygun şekilde char * hem wchar_t işleme\* parametreleri. Aşağıdaki örnekler, farklı türlerde dizesi parametreleri birlikte TRACE makrosu kullanımını göstermektedir.  
  
```  
TRACE( "This is a test of the TRACE macro that uses an ANSI string: %s %d\n", "The number is:", 2);  
  
TRACE( L"This is a test of the TRACE macro that uses a UNICODE string: %s %d\n", L"The number is:", 2);  
  
TRACE( _T("This is a test of the TRACE macro that uses a TCHAR string: %s %d\n"), _T("The number is:"), 2);  
  
```  
  
 Daha fazla bilgi için **izleme** makrosu, bkz: [tanılama Hizmetleri](/cpp/mfc/reference/diagnostic-services).  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Memory_leak_detection_in_MFC"></a>Bellek MFC'de sızıntılarını algılama  
 Ayrılmış olan, ancak hiçbir zaman serbest bellek algılamak için MFC sınıfları ve işlevleri sağlar.  
  
###  <a name="BKMK_Tracking_memory_allocations"></a>Bellek ayırma izleme  
 MFC içinde makrosu kullanabilirsiniz [DEBUG_NEW](http://msdn.microsoft.com/Library/9b379344-4093-4bec-a3eb-e0d8a63ada9d) yerine **yeni** bellek bulmanıza yardım etmek için işleci sızdırıyor. Programınız, hata ayıklama sürümünde `DEBUG_NEW` ayırdığı her nesne için dosya adı ve satır numarası izler. Program sürümünü derlediğinizde `DEBUG_NEW` basit bir çözümler **yeni** dosya adı ve satır numarası bilgilerini olmadan işlemi. Bu nedenle, hiçbir hızı cezası programınızın yayın sürümünü ücret ödersiniz.  
  
 Tüm programınızı kullanmak üzere yeniden yazmak istemiyorsanız `DEBUG_NEW` yerine **yeni**, Kaynak dosyalarınız bu makrosu tanımlayabilirsiniz:  
  
```  
#define new DEBUG_NEW  
```  
  
 Bunu yaptığınızda bir [nesne döküm](#BKMK_Taking_object_dumps), her nesne ile ayrılan `DEBUG_NEW` burada ayrıldı, dosya ve satır numarası gösterir bellek sızıntıları kaynakları belirlemenize olanak sağlar.  
  
 MFC çerçevesi hata ayıklama sürümü kullanan `DEBUG_NEW` otomatik olarak, ancak kodunuzu desteklemez. Avantajları istiyorsanız `DEBUG_NEW`, kullanmalısınız `DEBUG_NEW` açıkça veya **# yeni define** yukarıda gösterildiği gibi.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Enabling_memory_diagnostics"></a>Bellek Tanılama'yı etkinleştirme  
 Bellek Tanılama olanakları kullanabilmek için Tanılama izleme etkinleştirmeniz gerekir.  
  
 **Etkinleştirmek veya Bellek Tanılama'yı devre dışı bırakmak için**  
  
-   Genel bir işlevi çağırmak [AfxEnableMemoryTracking](http://msdn.microsoft.com/Library/0a40e0c4-855d-46e2-9577-a8f2346f47db) etkinleştirme veya tanılama bellek ayırıcısı devre dışı. Bellek Tanılama üzerinde varsayılan olarak hata ayıklama kitaplığı olduğundan, program yürütme hızını artırır ve tanılama çıktıları azaltan geçici olarak devre dışı bırakma bu işlevin genellikle kullanır.  
  
 **AfxMemDF ile özel bellek tanılama özellikleri seçmek için**  
  
-   Bellek Tanılama özellikleri üzerinde daha kesin denetim istiyorsanız, seçmeli olarak tek tek Bellek Tanılama özellikleri açma ve kapatma MFC genel değişkenin değeri olarak ayarlayarak kapatabilirsiniz [afxMemDF](http://msdn.microsoft.com/Library/cf117501-5446-4fce-81b3-f7194bc95086). Bu değişken numaralandırılmış türü tarafından belirtilen aşağıdaki değerlere sahip olabilir **afxMemDF**.  
  
    |Değer|Açıklama|  
    |-----------|-----------------|  
    |**allocMemDF**|Tanılama bellek ayırıcısı (varsayılan) açın.|  
    |**delayFreeMemDF**|Çağrılırken bellek boşaltma gecikme `delete` veya `free` program çıkar kadar. Bu, olası en fazla bellek miktarı ayırmak, program neden olur.|  
    |**checkAlwaysMemDF**|Çağrı [AfxCheckMemory](http://msdn.microsoft.com/Library/4644da71-7d14-41dc-adc0-ee9558fd7a28) bellek tahsis veya serbest her zaman.|  
  
     Bu değerlerin birleşimini mantıksal OR işlemi gerçekleştirerek aşağıda gösterildiği gibi kullanılabilir:  
  
    ```C++  
    afxMemDF = allocMemDF | delayFreeMemDF | checkAlwaysMemDF;  
    ```  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Taking_memory_snapshots"></a>Bellek anlık görüntüleri alma  
  
1.  Oluşturma bir [CMemoryState](http://msdn.microsoft.com/en-us/8fade6e9-c6fb-4b2a-8565-184a912d26d2) nesne ve çağrı [CMemoryState::Checkpoint](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__Checkpoint) üye işlevi. Bu ilk bellek anlık görüntü oluşturur.  
  
2.  Bellek ayırma ve kaldırma işlemlerini programınızı gerçekleştirdikten sonra başka birini oluşturmak `CMemoryState` nesne ve çağrı `Checkpoint` bu nesne için. Bellek kullanımı ikinci bir anlık görüntü alır.  
  
3.  Üçüncü oluşturma `CMemoryState` nesne ve çağrı kendi [CMemoryState::Difference](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__Difference) üye işlevi, önceki iki bağımsız değişken olarak sağladığını `CMemoryState` nesneleri. İki bellek durumları arasında bir fark ise `Difference` işlevi sıfır olmayan bir değer döndürür. Bu, bazı bellek blokları değil ayırması gösterir.  
  
     Bu örnek, kodu nasıl göründüğünü gösterir:  
  
    ```  
    // Declare the variables needed  
    #ifdef _DEBUG  
        CMemoryState oldMemState, newMemState, diffMemState;  
        oldMemState.Checkpoint();  
    #endif  
  
        // Do your memory allocations and deallocations.  
        CString s("This is a frame variable");  
        // The next object is a heap object.  
       CPerson* p = new CPerson( "Smith", "Alan", "581-0215" );  
  
    #ifdef _DEBUG  
        newMemState.Checkpoint();  
        if( diffMemState.Difference( oldMemState, newMemState ) )  
        {  
            TRACE( "Memory leaked!\n" );  
        }  
    #endif  
    ```  
  
     Bellek denetimi deyimleri tarafından köşeli parantez içindeki dikkat edin **#ifdef _DEBUG / #endif** yalnızca hata ayıklama sürümlerinde programınızı derlenen engeller.  
  
     Bellek sızıntısı var bildiğinize göre başka bir üye işlevini kullanabilirsiniz [CMemoryState::DumpStatistics](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpStatistics) yardımcı olacak bulun.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Viewing_memory_statistics"></a>Bellek istatistiklerini görüntüleme  
 [CMemoryState::Difference](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__Difference) işlevi iki bellek durumu nesnede arar ve yığın başlangıcını ve bitişini durumları arasında gelen serbest olmayan herhangi bir nesne algılar. Bellek anlık görüntüleri alınır ve bunları karşılaştırıldığında sonra kullanarak `CMemoryState::Difference`, çağırabilirsiniz [CMemoryState::DumpStatistics](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpStatistics) değil serbest nesneler hakkında bilgi almak için.  
  
 Aşağıdaki örnek göz önünde bulundurun:  
  
```  
if( diffMemState.Difference( oldMemState, newMemState ) )  
{  
   TRACE( "Memory leaked!\n" );  
   diffMemState.DumpStatistics();  
}  
```  
  
 Örneğindeki bir örnek dökümü şöyle görünür:  
  
```  
0 bytes in 0 Free Blocks  
22 bytes in 1 Object Blocks  
45 bytes in 4 Non-Object Blocks  
Largest number used: 67 bytes  
Total allocations: 67 bytes  
```  
  
 Ücretsiz taşlarıdır varsa, ayırmayı kaldırma Gecikmeli blokları `afxMemDF` ayarlandı `delayFreeMemDF`.  
  
 İkinci satırda gösterilen sıradan nesne blokları yığında ayrılmış kalır.  
  
 Olmayan nesne blokları içerecek dizileri ve yapıları ile ayrılmış `new`. Bu durumda, dört nesne olmayan blokları ve yığında ayrılan ancak değil serbest bırakıldı.  
  
 `Largest number used`herhangi bir zamanda program tarafından kullanılan en fazla bellek sağlar.  
  
 `Total allocations`Toplam program tarafından kullanılan bellek miktarını sağlar.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Taking_object_dumps"></a>Alma nesne dökümünü yapar  
 Bir MFC programında kullandığınız [CMemoryState::DumpAllObjectsSince](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpAllObjectsSince) değil serbest tüm nesneleri yığında açıklamasını dökümü. `DumpAllObjectsSince`tüm nesneler en son ayrılan dökümleri [CMemoryState::Checkpoint](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__Checkpoint). Öyle değilse `Checkpoint` çağrısı yerde harcanan `DumpAllObjectsSince` tüm nesneleri ve şu anda bellekte nonobjects dökümünü yapar.  
  
> [!NOTE]
>  MFC nesne dökme kullanabilmeniz için önce şunları yapmalısınız [Tanılama izleme etkinleştirmek](#BKMK_Enabling_Memory_Diagnostics).  
  
> [!NOTE]
>  MFC programınızı çıktığında, otomatik olarak tüm sızan nesneleri dökümleri, oluşturmanıza gerek olmayan şekilde dökümü kod bu noktada nesneleri.  
  
 Aşağıdaki kod, bellek sızıntısı için iki bellek durumları karşılaştırarak test eder ve bir sızıntısı algılanırsa, tüm nesneleri dökümünü yapar.  
  
```  
if( diffMemState.Difference( oldMemState, newMemState ) )  
{  
   TRACE( "Memory leaked!\n" );  
   diffMemState.DumpAllObjectsSince();  
}  
```  
  
 Döküm içeriğini şöyle görünür:  
  
```  
Dumping objects ->  
  
{5} strcore.cpp(80) : non-object block at $00A7521A, 9 bytes long  
{4} strcore.cpp(80) : non-object block at $00A751F8, 5 bytes long  
{3} strcore.cpp(80) : non-object block at $00A751D6, 6 bytes long  
{2} a CPerson at $51A4  
  
Last Name: Smith  
First Name: Alan  
Phone #: 581-0215  
  
{1} strcore.cpp(80) : non-object block at $00A7516E, 25 bytes long  
```  
  
 Çoğu satırların başında ayraç içinde numaralarını nesneleri tahsis düzeni belirtin. En son ayrılmış nesne en yüksek olan ve döküm üstünde görünür.  
  
 Bir nesne dökümü dışında en çok bilgi almak için kılabilirsiniz `Dump` üye işlevi herhangi `CObject`-nesne döküm özelleştirmek için nesne türetilmiş.  
  
 Genel değişkeni ayarlayarak, belirli bir bellek ayırma işleminde bir kesme noktası ayarlayabilirsiniz `_afxBreakAlloc` ayraçlar içinde numarasına. Program yeniden varsa bu ayırma gerçekleştiğinde hata ayıklayıcı yürütme çalışmamasına neden olur. Ardından, nasıl programınızı o noktaya var görmek için çağrı yığını da bakabilirsiniz.  
  
 C çalışma zamanı kitaplığı benzer bir işlevi olan [_CrtSetBreakAlloc](/cpp/c-runtime-library/reference/crtsetbreakalloc), C çalışma zamanı ayırmalarının kullanabilirsiniz.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
####  <a name="BKMK_Interpreting_memory_dumps"></a>Bellek yorumlama dökümünü yapar  
 Bu nesne döküm daha ayrıntılı bakın:  
  
```  
{5} strcore.cpp(80) : non-object block at $00A7521A, 9 bytes long  
{4} strcore.cpp(80) : non-object block at $00A751F8, 5 bytes long  
{3} strcore.cpp(80) : non-object block at $00A751D6, 6 bytes long  
{2} a CPerson at $51A4  
  
Last Name: Smith  
First Name: Alan  
Phone #: 581-0215  
  
{1} strcore.cpp(80) : non-object block at $00A7516E, 25 bytes long  
```  
  
 Bu döküm oluşturulan programın yalnızca iki açık ayırmaları vardı — bir yığını ve bir öbek üzerinde:  
  
```  
// Do your memory allocations and deallocations.  
CString s("This is a frame variable");  
// The next object is a heap object.  
CPerson* p = new CPerson( "Smith", "Alan", "581-0215" );  
```  
  
 `CPerson` Oluşturucusu işaretçileridir üç bağımsız değişken alan `char`, başlatmak için kullanılan `CString` üye değişkenleri. Bellek dökümü gördüğünüz `CPerson` üç nonobject blokları (3, 4 ve 5) yanı sıra nesnesi. Bu karakterleri tutun `CString` üye değişkenleri ve ne zaman silinmez `CPerson` nesne yıkıcı çağrılır.  
  
 Blok sayıdır 2 `CPerson` nesnesinin kendisi. `$51A4`Blok adresini temsil eder ve tarafından çıkış nesnesinin içeriğini arkasından `CPerson`::`Dump` çağrıldığında [DumpAllObjectsSince](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpAllObjectsSince).  
  
 Blok numarası 1 ile ilişkili olduğunu tahmin `CString` çerçeve değişkeni, sıra numarası ve çerçeve karakter sayısı ile eşleşen boyutu nedeniyle `CString` değişkeni. Çerçeve kapsam dışına çıktığında çerçevesi ayrılan değişkenleri otomatik olarak serbest.  
  
 **Çerçeve değişkenleri**  
  
 Genel olarak, size çerçeve değişkenleri kapsamının dışında olduğunuzda, bunlar otomatik olarak serbest çünkü çerçeve değişkenleri ile ilişkili yığın nesneler hususlara değil. Bellek Tanılama dökümleri dağınıklığı önlemek için aramalarınız getirin `Checkpoint` çerçeve değişkenleri kapsamı dışında olmasını sağlamak. Örneğin, aşağıda gösterildiği gibi önceki ayırma kod kapsam ayraç koyun:  
  
```  
oldMemState.Checkpoint();  
{  
    // Do your memory allocations and deallocations ...  
    CString s("This is a frame variable");  
    // The next object is a heap object.  
    CPerson* p = new CPerson( "Smith", "Alan", "581-0215" );  
}  
newMemState.Checkpoint();  
```  
  
 Kapsam köşeli parantez ile yerinde, bellek dökümü Bu örnek için aşağıdaki gibidir:  
  
```  
Dumping objects ->  
  
{5} strcore.cpp(80) : non-object block at $00A7521A, 9 bytes long  
{4} strcore.cpp(80) : non-object block at $00A751F8, 5 bytes long  
{3} strcore.cpp(80) : non-object block at $00A751D6, 6 bytes long  
{2} a CPerson at $51A4  
  
Last Name: Smith  
First Name: Alan  
Phone #: 581-0215  
```  
  
 **Nonobject ayırma**  
  
 Bazı ayırmaları nesnelerdir dikkat edin (gibi `CPerson`) ve nonobject ayırmaları bazılarıdır. "Nonobject ayırmaları" olan ayırmaları nesneleri öğesinden türetilmemiş için `CObject` veya ilkel C türleri gibi ayrılmasını `char`, `int`, veya `long`. Varsa **CObject -**türetilmiş sınıf iç arabellek için nesneleri nesne ve nonobject ayırmaları gösterecek gibi ek alan ayırır.  
  
 **Bellek sızıntılarını önleme**  
  
 Yukarıdaki kod bellek bloğu ile ilişkili fark `CString` çerçeve değişkeni otomatik olarak serbest ve bir bellek sızıntısı gösterilmez. Kural kapsamı ile ilişkili otomatik ayırmayı kaldırma çerçeve değişkenlerle ilişkili çoğu bellek sızıntıları ilgilenir.  
  
 Yığında ayrılmış nesneleri için ancak siz açıkça Bellek sızıntısını önlemek için nesnesini silmeniz gerekir. Önceki örnekte son bellek sızıntısı temizlemek için silme `CPerson` yığında gibi ayrılmış nesnesi:  
  
```  
{  
    // Do your memory allocations and deallocations.  
    CString s("This is a frame variable");  
    // The next object is a heap object.  
    CPerson* p = new CPerson( "Smith", "Alan", "581-0215" );  
    delete p;  
}  
```  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
####  <a name="BKMK_Customizing_object_dumps"></a>Özelleştirme nesne dökümünü yapar  
 Öğesinden bir sınıf türetin zaman [CObject](/cpp/mfc/reference/cobject-class), geçersiz kılabilirsiniz `Dump` kullandığınızda ek bilgi sağlamak için üye işlevi [DumpAllObjectsSince](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpAllObjectsSince) içindökümnesnelere[Çıktı penceresi](../ide/reference/output-window.md).  
  
 `Dump` İşlevi bir döküm bağlamına değişkenleri nesnenin üye metinsel gösterimini yazar ([CDumpContext](/cpp/mfc/reference/cdumpcontext-class)). Döküm bağlamı bir g/ç akışına benzer. Append işlecini kullanabilirsiniz (**<<**) veri göndermesini bir `CDumpContext`.  
  
 Kıldığınızda `Dump` işlevi, temel sınıf sürümü ilk çağrı `Dump` temel sınıf nesnesi içeriğini dökümü. Ardından bir metinsel ve her üye değişkeni türetilmiş sınıfınızın çıktı.  
  
 Bildirimi `Dump` işlevi şu şekilde görünür:  
  
```  
class CPerson : public CObject  
{  
public:  
#ifdef _DEBUG  
    virtual void Dump( CDumpContext& dc ) const;  
#endif  
  
    CString m_firstName;  
    CString m_lastName;  
    // And so on...  
};  
```  
  
 Bildirimi programınızı ayıklarken nesne dökme yalnızca anlamlı olduğundan `Dump` ile işlevi ayraçlı bir **#ifdef _DEBUG / #endif** bloğu.  
  
 Aşağıdaki örnekte, `Dump` işlev ilk çağrıları `Dump` işlevi için temel sınıfı. Ardından her üye değişkeni üyenin değeri yanı sıra kısa bir açıklamasını tanılama akışa yazar.  
  
```  
#ifdef _DEBUG  
void CPerson::Dump( CDumpContext& dc ) const  
{  
    // Call the base class function first.  
    CObject::Dump( dc );  
  
    // Now do the stuff for our specific class.  
    dc << "last name: " << m_lastName << "\n"  
        << "first name: " << m_firstName << "\n";  
}  
#endif  
```  
  
 Sağlamanız gerekir bir `CDumpContext` dump çıktısı nereye belirtmek için bağımsız değişken. MFC hata ayıklama sürümü önceden tanımlanmış bir sağlayan `CDumpContext` adlı nesne `afxDump` , hata ayıklayıcı için çıkış gönderir.  
  
```  
CPerson* pMyPerson = new CPerson;  
// Set some fields of the CPerson object.  
//...  
// Now dump the contents.  
#ifdef _DEBUG  
pMyPerson->Dump( afxDump );  
#endif  
```  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Reducing_the_size_of_an_MFC_Debug_build"></a>MFC hata ayıklama yapı boyutunu azaltma  
 Büyük bir MFC uygulaması için hata ayıklama bilgilerini disk alanının çok alabilir. Boyutunu azaltmak için aşağıdaki yordamlardan birini kullanabilirsiniz:  
  
1.  MFC kitaplıkları kullanarak yeniden [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](/cpp/build/reference/z7-zi-zi-debug-information-format) seçeneği, yerine **/Z7**. Bu seçenekler artıklık azaltma ve alan kaydetme tüm kitaplığı, hata ayıklama bilgilerini içeren bir tek bir program veritabanı (PDB) dosyası oluşturun.  
  
2.  MFC kitaplıkları hata ayıklama bilgisi olmadan yeniden (hiçbir [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](/cpp/build/reference/z7-zi-zi-debug-information-format) seçeneği). Bu durumda, hata ayıklama bilgileri eksikliği çoğu hata ayıklayıcı tesis içinde MFC kitaplık kodu kullanarak engeller, ancak MFC kitaplıkları zaten baştan sona ayıklandığını çünkü bu bir sorun olabilir.  
  
3.  Seçili modülleri için hata ayıklama bilgileri içeren kendi uygulamanızı yalnızca aşağıda açıklandığı gibi oluşturun.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Building_an_MFC_app_with_debug_information_for_selected_modules"></a>Seçili modülleri için hata ayıklama bilgileri bir MFC uygulaması oluşturma  
 MFC hata ayıklama kitaplıkları ile seçili modülleri oluşturma atlama kullanmanızı ve bu modüller diğer hata ayıklama tesislerde sağlar. Bu yordam hem bir hata ayıklama kullanır ve böylece aşağıdaki adımları (tam yayın derlemesi gerekli olduğunda yapmayı bir "tüm yeniden" gerekli yanı sıra) açıklanan değişiklikleri araya Visual C++ makefile modları bırakın.  
  
1.  Çözüm Gezgini'nde proje seçin.  
  
2.  Gelen **Görünüm** menüsünde, select **özellik sayfaları**.  
  
3.  İlk olarak, yeni bir proje yapılandırma oluşturacağız.  
  
    1.  İçinde  **\<Proje > özellik sayfaları** iletişim kutusu, tıklatın **Configuration Manager** düğmesi.  
  
    2.  İçinde [Yapılandırma Yöneticisi iletişim kutusu](http://msdn.microsoft.com/en-us/fa182dca-282e-4ae5-bf37-e155344ca18b), projenizin kılavuzda bulun. İçinde **yapılandırma** sütun, select  **\<yeni... >**.  
  
    3.  İçinde [yeni proje yapılandırma iletişim kutusu](http://msdn.microsoft.com/en-us/cca616dc-05a6-4fe3-bdc1-40c72a66f2be), "Kısmi Debug" gibi yeni yapılandırma için bir ad yazın **proje yapılandırma adı** kutusu.  
  
    4.  İçinde **kopyalama ayarlarından** listesinde, seçin **sürüm**.  
  
    5.  Tıklatın **Tamam** kapatmak için **yeni proje yapılandırması**iletişim kutusu.  
  
    6.  Kapat **Configuration Manager** iletişim kutusu.  
  
4.  Şimdi, tüm proje için seçenekleri ayarlayın.  
  
    1.  İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** klasöründe seçin **genel** kategorisi.  
  
    2.  Proje ayarları kılavuzunda genişletin **Proje Varsayılanları** (gerekiyorsa).  
  
    3.  Altında **Proje Varsayılanları**, bulma **kullanın, MFC**. Geçerli ayarı kılavuz sağ sütunda görüntülenir. Geçerli ayarını'ı tıklatın ve şekilde değiştirin **bir statik kitaplık kullanımı MFC'de**.  
  
    4.  Sol bölmesinde **özellikler sayfalarına** açık iletişim kutusunu **C/C++** klasörü ve select **önişlemci**. Özellikler kılavuzunda Bul **önişlemci tanımları** ve "NDEBUG" "_DEBUG" ile değiştirin.  
  
    5.  Sol bölmesinde **özellikler sayfalarına** açık iletişim kutusunu **bağlayıcı** klasörü ve select **giriş** kategorisi. Özellikler kılavuzunda Bul **ek bağımlılıklar**. İçinde **ek bağımlılıklar** ayarı "NAFXCWD. yazın LIB"ve"LIBCMT."  
  
    6.  Tıklatın **Tamam** yeni derleme seçenekleri kaydedip kapatmak için **özellik sayfaları** iletişim kutusu.  
  
5.  Gelen **yapı** menüsünde, select **yeniden**. Bu, modüllerden tüm hata ayıklama bilgileri kaldırır ancak MFC kitaplığını etkilemez.  
  
6.  Şimdi, hata ayıklama bilgilerini geri seçili modülleri uygulamanızda eklemeniz gerekir. Kesme noktalarını ayarlayın ve yalnızca hata ayıklama bilgileri ile derlenen modüllerde diğer hata ayıklayıcı işlevleri gerçekleştirmek unutmayın. Eklemek istediğiniz her proje dosya için hata ayıklama bilgileri, aşağıdaki adımları izleyin:  
  
    1.  Çözüm Gezgini'nde açık **kaynak dosyaları** klasörünün altında projenizin.  
  
    2.  Hata ayıklama bilgileri için ayarlamak istediğiniz dosyayı seçin.  
  
    3.  Gelen **Görünüm** menüsünde, select **özellik sayfaları**.  
  
    4.  İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma ayarlarını** klasörü, açık **C/C++** klasörünü seçip **genel** Kategori.  
  
    5.  Özellikler kılavuzunda Bul **hata ayıklama bilgileri biçimi.**  
  
    6.  Tıklatın **hata ayıklama bilgileri biçimi** ayarları ve istediğiniz seçeneği seçin (genellikle **/zi**) için hata ayıklama bilgileri.  
  
    7.  Uygulama Sihirbazı tarafından oluşturulan uygulama kullanmakta olduğunu veya önceden derlenmiş üstbilgiler, önceden derlenmiş üstbilgiler devre dışı bırakma veya diğer modüller derleme önce yeniden derleyin gerekir. Aksi takdirde, uyarı C4650 ve C2855 hata iletisi alırsınız. Değiştirerek önceden derlenmiş üst bilgiler devre dışı bırakabilir **Oluştur/Kullan önceden derlenmiş üstbilgiler** ayarı  **\<Proje > Özellikler** iletişim kutusu (**yapılandırma özellikleri**  klasörünü **C/C++** alt, **önceden derlenmiş üstbilgiler** kategori).  
  
7.  Gelen **yapı** menüsünde, select **yapı** eski proje dosyalarını yeniden oluşturmak için.  
  
 Alternatif yöntem bu konu başlığı altında açıklandığı gibi her dosya için ayrı seçenekler tanımlamak için bir dış derleme görevleri dosyası kullanabilirsiniz. Bu durumda, MFC hata ayıklama kitaplıklarıyla bağlamak için tanımlamanız gerekir [_DEBUG](/cpp/c-runtime-library/debug) her modül için bayrak. MFC sürüm kitaplıkları kullanmak istiyorsanız, NDEBUG tanımlamanız gerekir. Dış derleme görevleri dosyaları yazma ile ilgili daha fazla bilgi için bkz: [NMAKE başvurusu](/cpp/build/running-nmake).  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ hata ayıklama](../debugger/debugging-native-code.md)