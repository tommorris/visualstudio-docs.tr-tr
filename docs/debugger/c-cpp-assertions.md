---
title: "C/C++ onayları | Microsoft Docs"
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
- debugging [MFC], assertions
- results, checking
- result checking
- Call Stack window, assertion failures
- debugging [C++], assertions
- VERIFY macro
- assertions, side effects
- assertions
- ASSERT macro
- errors [C++], catching with assertions
- testing, error conditions with assertion statements
- _DEBUG macro
- Assertion Failed dialog box
- failures, finding locations
ms.assetid: 2d7b0121-71aa-414b-bbb6-ede1093d0bfc
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46ea417ccd8b4dbecd0c6584699e9f2e98330d69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="cc-assertions"></a>C/C++ Onayları
Bir onay deyimi programınızdaki bir noktada doğru olması için beklediğiniz bir koşulu belirtir. Bu koşul doğru değilse, onaylama işlemi başarısız olursa, yürütme programınızın kesildiği ve [onaylama başarısız iletişim kutusu](../debugger/assertion-failed-dialog-box.md) görüntülenir.  
  
 Visual C++ üzerinde aşağıdaki yapıları dayalı onaylama deyimleri destekler:  
  
-   MFC programları için MFC onaylar.  
  
-   [ATLASSERT](http://msdn.microsoft.com/Library/98e3e0fc-77e2-499b-a6f6-b17a21c6fbd3) ATL kullanan programlar  
  
-   C çalışma zamanı kitaplığı kullanan programlar için CRT onaylar.  
  
-   ANSI [assert işlevi](/cpp/c-runtime-library/reference/assert-macro-assert-wassert) diğer C/C++ programları için.  
  
 Onaylar mantığı hatalarını yakalama, bir işlem sonuçlarını denetleyin ve işlenen hata koşulları sınamak için kullanabilirsiniz.  
  
##  <a name="BKMK_In_this_topic"></a>Bu konudaki  
 [Onaylar nasıl çalışır](#BKMK_How_assertions_work)  
  
 [Hata ayıklama ve yayın derlemeleri onaylar](#BKMK_Assertions_in_Debug_and_Release_builds)  
  
 [Onaylar kullanarak yan etkileri](#BKMK_Side_effects_of_using_assertions)  
  
 [CRT onaylar](#BKMK_CRT_assertions)  
  
 [MFC onaylar](#BKMK_MFC_assertions)  
  
-   [MFC assert_valıd ve CObject::AssertValid](#BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid)  
  
-   [AssertValid sınırlamaları](#BKMK_Limitations_of_AssertValid)  
  
 [Onaylar kullanma](#BKMK_Using_assertions)  
  
-   [Mantık hataları yakalama](#BKMK_Catching_logic_errors)  
  
-   [Sonuçları denetleniyor](#BKMK_Checking_results_)  
  
-   [İşlenmemiş bulma hataları](#BKMK_Testing_error_conditions_)  
  
##  <a name="BKMK_How_assertions_work"></a>Onaylar nasıl çalışır  
 Hata ayıklayıcı bir MFC veya C çalışma zamanı kitaplığı onaylama nedeniyle durdurur, kaynak olup olmadığını sonra hata ayıklayıcı onaylama meydana geldiği kaynak dosyası noktaya gider. Onaylama ileti görünür [çıktı penceresi](../ide/reference/output-window.md) ve **onaylama başarısız** iletişim kutusu. Onaylama iletisinde kopyalama **çıkış** gelecekte başvurmak üzere kaydetmek istiyorsanız, bir metin penceresi penceresine. **Çıkış** penceresi diğer hata iletilerini de içerebilir. Onaylama işlemi hatasına neden ipuçları sağladıkları için bu iletiler dikkatlice inceleyin.  
  
 Onaylar, geliştirme sırasında hatalar algılamak için kullanın. Bir kural olarak, bir onaylama her varsayım için kullanın. Örneğin, bir bağımsız değişken NULL olmayan olduğunu varsayarsak, bir onaylama Bu varsayım sınamak için kullanın.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Assertions_in_Debug_and_Release_builds"></a>Hata ayıklama ve yayın derlemeleri onaylar  
 Onaylama deyimleri yalnızca derleme `_DEBUG` tanımlanır. Aksi takdirde derleyici onaylar null deyimleri değerlendirir. Bu nedenle, onaylama deyimleri zorunlu tuttukları olmamasıdır veya performans maliyeti son sürüm programınıza ve kullanmaktan kaçının izin `#ifdef` yönergeleri.  
  
##  <a name="BKMK_Side_effects_of_using_assertions"></a>Onaylar kullanarak yan etkileri  
 Kodunuzu onaylar eklediğinizde onaylar yan etkileri sahip olmadığından emin olun. Örneğin, değiştirir aşağıdaki onaylama göz önünde bulundurun `nM` değeri:  
  
```  
ASSERT(nM++ > 0); // Don't do this!  
  
```  
  
 Çünkü `ASSERT` ifadesi, programınızı yayın sürümü değerlendirilmez `nM` hata ayıklama ve yayın sürümlerinde farklı değerlere sahip olur. MFC içinde bu sorundan kaçınmak için kullanabileceğiniz [doğrula](http://msdn.microsoft.com/Library/3e1ab4ee-cbc7-4290-a777-c92f42ce7b96) makrosu yerine `ASSERT`.  `VERIFY`tüm sürümlerinde ifadeyi hesaplar, ancak yayın sürümü sonucunda denetlemez.  
  
 Bir işlev değerlendirme olabileceğinden işlev çağrılarını onaylama deyimlerinde kullanırken özellikle dikkatli olun beklenmeyen yan etkiler.  
  
```  
ASSERT ( myFnctn(0)==1 ) // unsafe if myFnctn has side effects  
VERIFY ( myFnctn(0)==1 ) // safe  
```  
  
 `VERIFY`çağrıları `myFnctn` hata ayıklama ve yayın sürümlerinde, bu nedenle, kullanmak için kabul edilebilir. Ancak, kullanarak `VERIFY` yayın sürümü gereksiz işlev çağrısında yükü getirir.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_CRT_assertions"></a>CRT onaylar  
 CRTDBG. H üstbilgi dosyası tanımlar [_ASSERT ve _ASSERTE makroları](/cpp/c-runtime-library/reference/assert-asserte-assert-expr-macros) onaylama işlemi denetimi.  
  
|Makrosu|Sonuç|  
|-----------|------------|  
|`_ASSERT`|Belirtilen ifade, FALSE hesaplanırsa dosya adını ve satır numarasını `_ASSERT`.|`_ASSERTE`|  
|`_ASSERTE`|Aynı `_ASSERT`, artı uygulanan ifade dize gösterimi.|  
  
 `_ASSERTE`FALSE dönüştü sürülen ifade bildirmesi nedeniyle daha güçlü bir özelliktir. Bu kaynak koduna başvuran olmadan sorunu tanımlamak için yeterli olabilir. Ancak, hata ayıklama sürümü, uygulamanızın kullanılarak uygulanan her bir ifadenin bir dize sabitine içerecek `_ASSERTE`. Birçok kullanırsanız `_ASSERTE` makroları, bu dizesi ifadeleri ele önemli miktarda bellek. Bir sorun için kanıtlar kullanırsanız `_ASSERT` bellekten tasarruf etmek.  
  
 Zaman `_DEBUG` tanımlanan `_ASSERTE` makrosu şu şekilde tanımlanır:  
  
```  
#define _ASSERTE(expr) \  
   do { \  
      if (!(expr) && (1 == _CrtDbgReport( \  
         _CRT_ASSERT, __FILE__, __LINE__, #expr))) \  
         _CrtDbgBreak(); \  
   } while (0)  
```  
  
 Onaylanan ifadesi, FALSE hesaplanırsa [_CrtDbgReport](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw) (varsayılan olarak bir ileti iletişim kutusunu kullanarak) onaylama hatası rapor için çağrılır. Seçerseniz **yeniden deneme** iletisi iletişim kutusunda `_CrtDbgReport` 1 döndürür ve `_CrtDbgBreak` hata ayıklayıcı aracılığıyla çağırır `DebugBreak`.  
  
### <a name="checking-for-heap-corruption"></a>Yığın bozulması denetleniyor  
 Aşağıdaki örnek kullanır [_CrtCheckMemory](/cpp/c-runtime-library/reference/crtcheckmemory) öbek bozulma olup olmadığını denetleyin:  
  
```  
_ASSERTE(_CrtCheckMemory());  
```  
  
### <a name="checking-pointer-validity"></a>İşaretçi geçerlilik denetimi  
 Aşağıdaki örnek kullanır [_crtısvalidpointer](/cpp/c-runtime-library/reference/crtisvalidpointer) verilen bellek aralığı okuma veya yazma için geçerli olduğu doğrulanamadı.  
  
```  
_ASSERTE(_CrtIsValidPointer( address, size, TRUE );  
```  
  
 Aşağıdaki örnek kullanır [_crtısvalidheappointer](/cpp/c-runtime-library/reference/crtisvalidheappointer) yerel yığın bellekte bir işaretçi işaret doğrulamak için (öbek oluşturulan ve C çalışma zamanı kitaplığı bu örneği tarafından yönetilen — DLL Kitaplığı örneğini olabilir ve Bu nedenle, kendi yığın, uygulama yığın dışında). Bu onay yalnızca null yakalar değil veya out-of-bounds de statik değişkenler, yığın değişkenleri ve başka bir yerel olmayan bellek işaretçiler ancak adresleri.  
  
```  
_ASSERTE(_CrtIsValidPointer( myData );  
```  
  
### <a name="checking-a-memory-block"></a>Bir bellek bloğu denetleniyor  
 Aşağıdaki örnek kullanır [_crtısmemoryblock](/cpp/c-runtime-library/reference/crtismemoryblock) bir bellek bloğu içinde yerel yığın olduğunu ve geçerli blok türü sahip olduğunu doğrulamak için.  
  
```  
_ASSERTE(_CrtIsMemoryBlock (myData, size, &requestNumber, &filename, &linenumber));  
```  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_MFC_assertions"></a>MFC onaylar  
 MFC tanımlar [ASSERT](http://msdn.microsoft.com/Library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) onaylama işlemi denetimi makrosu. Ayrıca tanımlar `MFC ASSERT_VALID` ve `CObject::AssertValid` iç durumunu denetleme yöntemleri bir `CObject`-türetilmiş bir nesne içermelidir.  
  
 Varsa MFC bağımsız değişkeni `ASSERT` makrosu değerlendirir sıfır veya yanlış makrosu program yürütme durdurur ve kullanıcıyı uyarır, aksi halde, yürütme devam eder.  
  
 Bir onaylama işlemi, kaynak dosyasının adını ve onaylama satır sayısı bir ileti iletişim kutusu gösterir başarısız olduğunda. Yeniden deneme iletişim kutusunda seçerseniz kutusunda yapılan bir çağrı [AfxDebugBreak](http://msdn.microsoft.com/Library/c4cd79b9-9327-4db5-a9d6-c4004a92aa30) ayıklayıcıya gönder yürütme neden olur. Bu noktada, çağrı yığınını incelemek ve diğer hata ayıklayıcı tesis onaylama neden başarısız olduğunu belirlemek için kullanın. Etkinleştirdiyseniz [sadece zamanında hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md)ve hata ayıklayıcısı zaten çalışmadığı, iletişim kutusunun hata ayıklayıcı başlatabilirsiniz.  
  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `ASSERT` bir işlevin dönüş değerini denetlemek için:  
  
```  
int x = SomeFunc(y);  
ASSERT(x >= 0);   //  Assertion fails if x is negative  
```  
  
 ASSERT ile kullanabileceğiniz [Iskindof](/cpp/mfc/reference/cobject-class.md#CObject__IsKindOf) işlevi tür işlev bağımsız değişkenleri denetlemesini sağlamak için:  
  
```  
ASSERT( pObject1->IsKindOf( RUNTIME_CLASS( CPerson ) ) );  
```  
  
 `ASSERT` Makrosu yayın sürümü hiçbir kodu oluşturur. Yayın sürümü ifadesinde değerlendirmek gereksinim duyarsanız kullanın [doğrula](http://msdn.microsoft.com/Library/3e1ab4ee-cbc7-4290-a777-c92f42ce7b96) makrosu ASSERT yerine.  
  
###  <a name="BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid"></a>MFC assert_valıd ve CObject::AssertValid  
 [CObject::AssertValid](/cpp/mfc/reference/cobject-class.md#CObject__AssertValid) yöntemi sağlar çalışma zamanı nesne iç durumunu denetler. Geçersiz kılma gerekmez ancak `AssertValid` , sınıfından türetilen zaman `CObject`, bunu yaparak, sınıfınızın daha güvenilir yapabilirsiniz. `AssertValid`onaylar tüm geçerli değerler içerdiğinden emin doğrulamak için nesnenin üye değişkenleri gerçekleştirmeniz gerekir. Örneğin, işaretçi üye değişkenleri NULL olmayan denetlemelisiniz.  
  
 Aşağıdaki örnek bildirmek nasıl gösterir bir `AssertValid` işlevi:  
  
```  
class CPerson : public CObject  
{  
protected:  
    CString m_strName;  
    float   m_salary;  
public:  
#ifdef _DEBUG  
    // Override  
    virtual void AssertValid() const;  
#endif  
    // ...  
};  
  
```  
  
 Kıldığınızda `AssertValid`, temel sınıf sürümü çağrı `AssertValid` kendi denetimleri gerçekleştirmeden önce. Ardından ASSERT makrosu türetilmiş sınıfınıza benzersiz üye denetlemek için aşağıda gösterildiği gibi kullanın:  
  
```  
#ifdef _DEBUG  
void CPerson::AssertValid() const  
{  
    // Call inherited AssertValid first.  
    CObject::AssertValid();  
  
    // Check CPerson members...  
    // Must have a name.  
    ASSERT( !m_strName.IsEmpty());  
    // Must have an income.  
    ASSERT( m_salary > 0 );  
}  
#endif  
  
```  
  
 Üye değişkenleri hiçbirini nesneleri depolarsanız, kullanabileceğiniz `ASSERT_VALID` iç geçerliliği test etmek için makrosu (kendi sınıfları geçersiz kılarsanız `AssertValid`).  
  
 Örneğin, bir sınıf göz önünde bulundurun `CMyData`, depolayan bir [CObList](/cpp/mfc/reference/coblist-class) üye değişkenlerini birinde. `CObList` Değişkeni `m_DataList`, koleksiyonu depolar `CPerson` nesneleri. Kısaltılmış bir bildirimi `CMyData` şöyle görünür:  
  
```  
class CMyData : public CObject  
{  
    // Constructor and other members ...  
    protected:  
        CObList* m_pDataList;  
    // Other declarations ...  
    public:  
#ifdef _DEBUG  
        // Override:  
        virtual void AssertValid( ) const;  
#endif  
    // And so on ...  
};  
  
```  
  
 `AssertValid` Geçersiz kılması `CMyData` şöyle görünür:  
  
```  
#ifdef _DEBUG  
void CMyData::AssertValid( ) const  
{  
    // Call inherited AssertValid.  
    CObject::AssertValid( );  
    // Check validity of CMyData members.  
    ASSERT_VALID( m_pDataList );  
    // ...  
}  
#endif  
  
```  
  
 `CMyData`kullanan `AssertValid` kendi veri üyesi depolanan nesneler geçerliliğini sınamak için bir mekanizma. Geçersiz kılma `AssertValid` , `CMyData` çağırır `ASSERT_VALID` makrosu kendi m_pDataList üye değişkeni için.  
  
 Geçerlilik testleri değil durdurmak bu düzeyde çünkü sınıfı `CObList` ayrıca geçersiz kılar `AssertValid`. Bu geçersiz kılma ek geçerlilik listesinin iç durumunu sınama gerçekleştirir. Bu nedenle, geçerlilik test üzerinde bir `CMyData` nesne müşteri adayları saklı iç durumları için ek geçerlilik testleri için `CObList` liste nesnesi.  
  
 Daha fazla bazı çalışmak için geçerlilik testleri ekleyebilirsiniz `CPerson` listesinde de depolanan nesneler. Bir sınıf türetin `CPersonList` gelen `CObList` ve geçersiz kılma `AssertValid`. Geçersiz kılma seçeneğinde, çağırırdı `CObject::AssertValid` ve liste yineleme çağırma `AssertValid` her `CPerson` listede depolanan nesnesi. `CPerson` Bu konunun başındaki zaten gösterilen sınıfı geçersiz kılan `AssertValid`.  
  
 Hata ayıklama için derlerken güçlü bir mekanizmadır. Daha sonra bu sürüm için yapılandırdığınızda, mekanizması otomatik olarak kapatılır.  
  
###  <a name="BKMK_Limitations_of_AssertValid"></a>AssertValid sınırlamaları  
 Tetiklenen onaylama nesne kesinlikle bozuk ve yürütme durdurulacak gösterir. Ancak, onaylama işlemi eksikliği yalnızca herhangi bir sorun bulundu, ancak nesne iyi olması garanti edilmemiştir gösterir.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Using_assertions"></a>Onaylar kullanma  
  
###  <a name="BKMK_Catching_logic_errors"></a>Mantık hataları yakalama  
 Bir onaylama programınızı mantığı göre doğru olmalıdır bir koşul ayarlayabilirsiniz. Bir mantık hatası oluşmadığı sürece onaylama bir etkisi yoktur.  
  
 Örneğin, bir kapsayıcı ve değişken gaz molecules benzetimi varsayalım `numMols` molecules toplam sayısını temsil eder. Bu sayı olamaz sıfırdan küçük böyle bir MFC onaylama deyimi içerebilir şekilde:  
  
```  
ASSERT(numMols >= 0);  
  
```  
  
 Ya da böyle bir CRT onaylama şunlar olabilir:  
  
```  
_ASSERT(numMols >= 0);  
```  
  
 Programınız düzgün çalışıyorsa bu deyimleri hiçbir şey yapmayın. Bir mantık hatası neden olursa `numMols` değerinden küçük olması için sıfır ancak, onaylama işlemi, programın yürütülmesini durdurur ve görüntüler [onaylama başarısız iletişim kutusu](../debugger/assertion-failed-dialog-box.md).  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Checking_results_"></a>Sonuçları denetleniyor  
 Onaylar sonuçlarını hızlı bir görsel denetleme belirgin olmayan işlemleri test etmek için değerlidir.  
  
 Örneğin, değişkeni güncelleştirmeleri aşağıdaki kodu göz önünde bulundurun `iMols` gösterdiği bağlantılı listesinin içeriğine göre `mols`:  
  
```  
/* This code assumes that type has overloaded the != operator  
 with const char *   
It also assumes that H2O is somewhere in that linked list.   
Otherwise we'll get an access violation... */  
while (mols->type != "H2O")  
{  
 iMols += mols->num;  
 mols = mols->next;  
}  
ASSERT(iMols<=numMols); // MFC version  
_ASSERT(iMols<=numMols); // CRT version  
```  
  
 Sayılan molecules sayısı tarafından `iMols` her zaman molecules, toplam sayısı küçük veya buna eşit olmalıdır `numMols`. Döngü Visual İnceleme için bu koşul sınamak için kullanılan bir onaylama deyimi döngüden sonra bu mutlaka durumda olacağından emin göstermez.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Testing_error_conditions_"></a>İşlenmemiş bulma hataları  
 Onaylar, burada hataları işlenen bir noktada hata koşulları için kodunuzu test etmek için kullanabilirsiniz. Aşağıdaki örnekte, bir grafik yordam bir hata kodu veya başarı için sıfır değerini döndürür.  
  
```  
myErr = myGraphRoutine(a, b);  
  
/* Code to handle errors and  
   reset myErr if successful */  
  
ASSERT(!myErr); -- MFC version  
_ASSERT(!myErr); -- CRT version  
```  
  
 Hata işleme kodu düzgün şekilde çalışıyorsa, hata işleneceğini ve `myErr` onaylama ulaşılmadan önce sıfır sıfırlama. Varsa `myErr` sahip başka bir değer, onaylama işlemi başarısız olursa, program durur ve [onaylama başarısız iletişim kutusu](../debugger/assertion-failed-dialog-box.md) görüntülenir.  
  
 Onaylama deyimleri hata işleme kodu yerine ancak değildir. Aşağıdaki örnek, son sürümde kodda sorunlara yol açabilecek bir onaylama deyimi gösterir:  
  
```  
myErr = myGraphRoutine(a, b);  
  
/* No Code to handle errors */  
  
ASSERT(!myErr); // Don't do this!  
_ASSERT(!myErr); // Don't do this, either!  
```  
  
 Bu kod hata durumu işlemek için onaylama deyimi kullanır. Sonuç olarak, herhangi bir hata kodu döndürdü tarafından `myGraphRoutine` son sürümde kodda işlenmemiş.  
  
 [Bu konudaki](#BKMK_In_this_topic)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)   
 [Yönetilen koddaki onaylar](../debugger/assertions-in-managed-code.md)