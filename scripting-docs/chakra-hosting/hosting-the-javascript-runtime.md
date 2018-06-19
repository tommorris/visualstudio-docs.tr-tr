---
title: JavaScript çalışma zamanını barındırma | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ec744e-57cc-4ef5-8fe1-d2c27b946548
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2bf213bf262ede7642e05c66e424b860238dc57f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789269"
---
# <a name="hosting-the-javascript-runtime"></a>JavaScript Çalışma Zamanını Barındırma
JavaScript çalışma zamanı (JsRT) API'ları, masaüstü, Windows mağazası ve Windows işletim sistemi üzerinde çalışan sunucu tarafı uygulamaları'komut dosyası özellikleri de standartlara dayalı Chakra JavaScript altyapısını kullanarak uygulama eklemek için bir yol sağlar. Microsoft Edge ve Internet Explorer tarafından kullanılan. Bu API, Windows 10 ve Windows işletim sisteminin Internet Explorer sürüm 11.0 makinede yüklü olan herhangi bir sürümü kullanılabilir. Daha fazla bilgi için bkz: [başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md). Windows mağazası uygulamalarında JsRT kullanma hakkında daha fazla bilgi için bkz: [JsRT ve evrensel Windows platformu](#Windows).  
  
> [!NOTE]
>  Bu belge, JavaScript diliyle ilgili genel bir bilgiye sahip olunduğunu varsayar.  
  
## <a name="concepts"></a>Kavramlar  
 JsRT API'lerini kullanarak JavaScript motorunun nasıl barındırılacağını anlamak iki anahtar kavrama dayalıdır: çalışma zamanları ve yürütme bağlamları.  
  
 A *çalışma zamanı* eksiksiz bir JavaScript yürütme ortamı temsil eder. Oluşturulan her bir çalışma zamanı kendi yalıtılmış ve atık toplama yapılan yığınına ve varsayılan olarak kendi anlık (JIT) derleyicisi iş parçacığına ve atık toplayıcı (GC) iş parçacığına sahiptir. Bir *yürütme bağlamı* , genel kendi JavaScript nesne diğer tüm yürütme bağlamı farklı olan bir JavaScript ortamında temsil eder. Bir çalışma zamanı birden çok yürütme bağlamı içerebilir, böyle durumlarda tüm yürütme bağlamları çalışma zamanı ile ilişkilendirilen JIT derleyicisini ve GC iş parçacığını paylaşır.  
  
 Çalışma zamanları tek bir yürütme iş parçacığını temsil eder. Belirli bir iş parçacığında aynı anda yalnızca tek bir çalışma zamanı etkin olabilir ve bir çalışma zamanı yalnızca tek bir iş parçacığı üzerinde etkin olabilir. Bir çalışma zamanı, bir iş parçacığı üzerinde şu anda etkin değil şekilde çalışma zamanları olan iş parçacıklı, kiralama (yani olmayan herhangi bir JavaScript kodunu çalıştıran veya yapılan her çağrı ana bilgisayardan yanıt) etkin bir çalışma zamanı üzerinde zaten yüklü olmayan herhangi bir iş parçacığı üzerinde kullanılabilir.  
  
 Yürütme bağlamları belirli bir çalışma zamanına bağlıdır ve bu çalışma zamanı içinde kod çalıştırırlar. Çalışma zamanlarının aksine, bir iş parçacığında aynı anda birden çok yürütme bağlamı etkin olabilir. Bu nedenle bir konak, yürütme bağlamına çağrı yapabilir, o yürütme bağlamı konağa geri çağrı yapabilir ve konak başka bir yürütme bağlamına çağrı yapabilir.  
  
 ![Birden çok yürütme bağlamı](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting")  
  
 Bir ana bilgisayar ayrılmış ortamlarda, kod çalıştırmasına gerekmedikçe pratikte, tek yürütme bağlamı kullanılabilir. Benzer şekilde, bir konak aynı anda birden çok kod parçasını çalıştırmaya gerek duymadığı sürece tek bir çalışma zamanı yeterlidir.  
  
## <a name="memory-management"></a>Bellek yönetimi  
 JavaScript atık toplama yapılan bir dildir ve bu nedenle başka bir dilden JsRT API'lerle çalışırken dikkat edilmesi gereken birkaç nokta vardır.  
  
 Ana JavaScript atık toplayıcısı başvurular değerlere iki yerde yalnızca görebilirsiniz noktadır: kendi zamanının öbek ve yığını. Bu nedenle, başka bir JavaScript değerinde veya ana yığındaki bir yerel değişkende depolanan bir JavaScript değeri başvurusu, atık toplayıcı tarafından her zaman görülür. Ancak, konak veya sistem tarafından yönetilen yığınlar gibi başka konumlarda depolanan başvurular atık toplayıcısı tarafından görülmez ve konak tarafından hala kullanılmakta olan değerlerin zamanından önce toplanmasına neden olabilir.  
  
> [!IMPORTANT]
>  Bazı dil derleyicileri (örneğin Visual Studio C++ derleyicisi) mümkün olduğunda yerel değişkenleri iyileştirir. JavaScript değerlerine başvuran yerel değişkenlerin, bu değerleri canlı tutmaları için yığın üzerinde olduklarından emin olunmalıdır.  
  
 Eğer bir JavaScript değeri başvurusu atık toplayıcısına görünür olmayan bir konumda saklanacaksa konak, JsRT API'lerini kullanarak başvuruları el ile eklemeli ve kaldırmalıdır.  
  
## <a name="exception-handling"></a>Özel durum işleme  
 Betik yürütme sırasında bir JavaScript özel durumu oluştuğunda, bu özel durumu içeren çalışma zamanı özel duruma getirilir. Bir özel durumdayken, konak `JsErrorInExceptionState` API'sini kullanarak özel durumu alıp temizleyene kadar hiçbir kod çalıştırılamaz ve tüm API çağrıları `JsGetAndClearException` hata kodu ile başarısız olur. Konak çalışma zamanını özel durumundan temizlemeden bir JavaScript geri çağrısından dönerse, denetim JavaScript motoruna geçer geçmez JavaScript özel durumu yeniden oluşturulur. Bu aynı zamanda "çalışma zamanı özel durumuna ayarlayarak ve bir ana bilgisayar geri aramadan döndüren bir JavaScript özel durum" ana bilgisayar geri aramalar sağlar.  
  
 Bir konağın kendi iç özel durumlarını konak geri çağrıları arasında yaymasına izin verilmez; geri çağırma yöntemleri denetimi çalışma zamanına döndürmeden önce tüm konak özel durumlarını yakalamalıdır.  
  
## <a name="runtime-resource-usage"></a>Çalışma zamanı kaynak kullanımı  
 JsRT API'leri, çalışma zamanlarının kaynakları kullanma biçimini izlemek ve değiştirmek için birtakım yollar ortaya çıkarır. Bunlar genel olarak aşağıdaki kategorilere ayrılır:  
  
-   **İş parçacığı kullanımı**. Varsayılan olarak her çalışma zamanı, ayrılmış bir JIT derleyicisi iş parçacığı ve o iş parçacığına hizmet eden ayrılmış bir GC iş parçacığı oluşturur. Bir çalışma zamanı `JsRuntimeAttributeDisableBackgroundWork` bayrağı ile oluşturulursa JIT ve GC işleri, her biri için ayrı bir arka plan iş parçacığı yerine çalışma zamanı iş parçacığının kendisinde gerçekleştirilir. Bir konak, JIT ve GC işini uygun gördüğü şekilde zamanlayabilmesini sağlayan `JsCreateRuntime` çağrısına bir iş parçacığı hizmet geri çağrısı da sağlayabilir.  
  
-   **Bellek kullanımı**. Bir çalışma zamanının bellek kullanımını izlemek ve değiştirmek için birkaç yol vardır. Eğer çalışma zamanı uzun bir süre çalışacaksa konak, çalışma zamanını oluştururken `JsRuntimeAttributeEnableIdleProcessing` bayrağını belirtebilir ve ardından boş bir durumda olduğunda `JsIdle` yöntemini çağırabilir. Bu, motorun bazı bellek temizleme ve kayıt tutma işlemlerini boşta kalana kadar ertelemesini sağlar.  
  
     Konak, `JsSetRuntimeBeforeCollectCallback` yöntemini çağırarak atık toplama işlemlerini izleyebilir. Aynı zamanda `JsSetRuntimeMemoryAllocationCallback` yöntemini çağırarak yığın tarafından yapılan ayırmaları da izleyebilir. Yalnızca zamanının yığın daha fazla alan ayırmak üzere gerektiğinde bu API her JavaScript ayırmada geri çağırmaz unutmayın. Bellek ayırma geri çağırısı isteği reddedebilir; bu durumda bir atık toplama işlemi tetiklenir ve eğer kullanılabilir bellek yoksa çalışma zamanında yetersiz bellek hatası oluşturulur.  
  
     Ayrıca konak, bir çalışma zamanının kullanabileceği bellek miktarını sınırlamak için `JsSetRuntimeMemoryLimit` yöntemini çağırabilir. Bir çalışma zamanı sınıra ulaştığında, bir atık toplama işlemini tetikler ve eğer kullanılabilir bellek yoksa çalışma zamanı tarafından bir yetersiz bellek hatası oluşturulur.  
  
-   **Komut dosyası kesinti ve değerlendirme**. Konak, bir çalışma zamanındaki yürütmeyi sona erdirmek için `JsDisableRuntimeExecution` yöntemini çağırabilir. Bu çağrı herhangi bir zamanda herhangi bir iş parçacığından yapılabilir. Betik sonlandırma koda eklenen koruma noktalarına ulaşılmasına bağlı olduğundan bir betik tam o anda sonlandırılmayabilir, ancak kısa bir süre sonra sonlandırılacaktır. Varsayılan olarak, sonlandırma koruma noktaları üretilen koda kısıtlı miktarda yerleştirilir ve bu nedenle sonsuz döngü gibi her durumu kapsamayabilir. Çalışma zamanının `JsRuntimeAttributeAllowScriptInterrupt` bayrağı ile oluşturulması, genelde küçük bir performans yükü karşılığında çalışma zamanının sonsuz döngüler için ek denetimler eklemesini sağlar.  
  
     Eğer bir konak JIT derleyicisi tarafından yerel kod oluşturulmasını engellemek istiyorsa, `JsRuntimeAttributeDisableNativeCodeGeneration` bayrağını belirtebilir. Ayrıca bir konak `JsRuntimeAttributeDisableEval` bayrağını belirterek, betiklerin kendilerinin dinamik olarak betik çalıştırmalarını engelleyebilir.  
  
## <a name="debugging-and-profiling"></a>Hata Ayıklama ve Profil Oluşturma  
 JsRT API'leri Active Scripting teknolojisi aracılığıyla hata ayıklama ve profil oluşturmayı destekler.  
  
 Windows 10'dan başlayarak, Chakra JavaScript motoru eski altyapısı ve kenar altyapısını destekler ve JsRT ya da hedef (bkz [hedefleme kenar vs. Eski motorları](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md) Ayrıntılar için). Visual Studio'da bir komut dosyası hata ayıklama eski ve kenar altyapısı arasında farklı şekilde çalışır. Eski altyapısıyla konak sağlaması gerekir bir [Idebugapplication arabirimi](../winscript/reference/idebugapplication-interface.md) yükseltebilmeniz işaretçi bir [Iprocessdebugmanager arabirimi](../winscript/reference/iprocessdebugmanager-interface.md) örneği. Kenar altyapısı ile `IDebugApplication` kullanım dışıdır ve altyapısını etkinleştirir yerel ve üzerinden Visual Studio hata ayıklayıcısı hata ayıklama özellikleri uygulaması gerektirmeden komut Chakra `IDebugApplication` kullanıcıdan.  
  
 Komut dosyaları yürütme bağlamı içinde debuggable yapmak için daha az verimli kodu yürütme yöntemleri kullanmaya geçmek Chakra altyapısı vardır. Bu nedenle, hata ayıklanabilen kod genellikle hata ayıklanamayan koda göre daha yavaş çalışır. Sonuç olarak, eski altyapısıyla bir konak ya da bir yürütme bağlamı başlangıçtan itibaren sağlayarak hata ayıklamayı Başlat seçebilirsiniz `IDebugApplication` işaretçi Önden ile `JsCreateContext`, ya da hata ayıklama gerektiği kadar bekleyin ve ardından arama `JsStartDebugging`. Kenar altyapısı ile `JsCreateContext` artık geçen bir `IDebugApplication` parametresi ve sonuç olarak bir komut dosyası yalnızca sonra debuggable `JsStartDebugging` olarak adlandırılır. Visual Studio kullanarak hata ayıklama sırasında "Komut dosyası" hata ayıklayıcı seçeneği etkinleştirilmelidir.  
  
 Bir yürütme bağlamındaki JavaScript kodu için iki şekilde profil oluşturulabilir. Visual Studio profil oluşturucu (vsperf.exe) komut satırı Windows 8.1 ve sonraki sürümlerde /js anahtarıyla JavaScript kodunu çalıştırmak uygulamada hedefleyen bir raporu oluşturmak için kullanılabilir. Veya profil oluşturma işlemini kendisi gerçekleştirmek için konak, doğrudan `JsStartProfiling` ve `JsStopProfiling` yöntemlerini çağırabilir. Konak ayrıca çöp toplanan yığın durumu çağırarak inceleyebilirsiniz `JsEnumerateHeap`. JsRT içinde profil eski ve kenar altyapısı arasında aynı şekilde çalışır. Ancak, API profil JsRT (`JsStartProfiling`, `JsStopProfiling`, `JsEnumerateHeap`, ve `JsIsEnumeratingHeap`) Evrensel Windows uygulamaları için kullanılabilir değil.  
  
<a name="Windows"></a>   
## <a name="jsrt-and-the-universal-windows-platform"></a>JsRT ve evrensel Windows platformu  
 Karşılaştırması, bir evrensel Windows uygulaması için komut dosyası özellikleri eklemek için kullanabilirsiniz. Edge sırayla kenar Chakra altyapısı hedef karşılaştırması, hedef karşılaştırması kullanan bir evrensel Windows uygulaması gerekir. Daha fazla bilgi için bkz: [hedefleme kenar vs. Eski altyapıların](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md). Profil oluşturma ve yığın numaralandırma desteği dışında Evrensel Windows uygulamaları için tam JsRT API kullanılabilir (`JsStartProfiling`, `JsStopProfiling`, `JsEnumerateHeap`, ve `JsIsEnumeratingHeap` desteklenmez).  
  
 JsRT de yerel olarak erişmesi için komut dosyaları sağlar [Evrensel Windows Platformu (UWP) API](https://msdn.microsoft.com/en-us/library/windows/apps/br211377.aspx) API ad alanı kenar JsRT API aracılığıyla gösterme sonra `JsProjectWinRTNamespace`. Evrensel Windows uygulamaları planlanması gereken ad alanları, bir Klasik (Win32) Windows uygulamasında ek kurulum gerektirirken COM başlatılmış aracılığıyla etkinleştirilmesi pompa mekanizması gereksinimlerini temsilci `JsSetProjectionEnqueueCallback` olaylarını etkinleştirmek için ve zaman uyumsuz API'leri. Aşağıdaki Win32 örnek bir Uri'den içerik almak için bir http istemcisi oluşturmak için zaman uyumsuz UWP API'lerini kullanır:  
  
```cpp  
typedef struct _jsCall {  
    JsProjectionCallback jsCallback;  
    JsProjectionCallbackContext jsContext;  
    HANDLE event;  
} jsCall;  
  
// Set up delegated pumping mechanism; not necessary in UWP applications.  
jsCall outstandingCall = {};  
CoInitializeEx(nullptr, COINIT_MULTITHREADED);  
JsSetProjectionEnqueueCallback([](JsProjectionCallback jsCallback,   
JsProjectionCallbackContext jsContext, void *callbackState) {  
    jsCall* call = (jsCall*)callbackState;  
    call->jsCallback = jsCallback;  
    call->jsContext = jsContext;  
    SetEvent(call->event);  
    },  
&outstandingCall);  
HANDLE event = CreateEventEx(NULL, NULL, CREATE_EVENT_MANUAL_RESET, EVENT_ALL_ACCESS);  
outstandingCall.event = event;  
  
// Project necessary namespaces.  
JsProjectWinRTNamespace(L"Windows.Foundation");  
JsProjectWinRTNamespace(L"Windows.Web");  
  
// Get content from an Uri.  
JsRunScript(L"var uri = new Windows.Foundation.Uri(\"http://somedatasource.com\"); " \  
    L"var httpClient = new Windows.Web.Http.HttpClient();" \  
    L"httpClient.getStringAsync(uri).done(function (content) { " \  
    L"    // do something with the string content " \    
    L"}, onError); " \  
    L"function onError(reason) { " \  
    L"    // error handling " \        
    L"}",   
    currentSourceContext, L"", &result);  
  
// Wait for async call to come in and then execute; not necessary in UWP applications.  
WaitForSingleObjectEx(outstandingCall.event, 10000, FALSE) == WAIT_OBJECT_0;  
outstandingCall.jsCallback(outstandingCall.jsContext);  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript çalışma zamanı örnek uygulaması](http://go.microsoft.com/fwlink/p/?LinkID=306674&clcid=0x409)   
 [Başvuru (JavaScript çalışma zamanı)](../chakra-hosting/reference-javascript-runtime.md)   
 [JavaScript çalışma zamanı barındırma](../chakra-hosting/javascript-runtime-hosting.md)