---
title: "Visual Studio statik kod analizi kullanarak UWP uygulamaları C++ kod kalitesini çözümleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.propertypages.native.express
ms.assetid: c5355e43-a37c-4686-a969-18e3dfc59a9c
caps.latest.revision: "13"
ms.author: douge
manager: douge
ms.openlocfilehash: c4c49f910615e1e181fe66feab3dce5bb3c90002
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="analyze-c-code-quality-of-uwp-apps-using-visual-studio-static-code-analysis"></a>Visual Studio statik kod analizi kullanarak UWP uygulamaları C++ kod kalitesini çözümleme
![Windows ve Windows Phone için geçerlidir](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Kod çözümleme aracı Visual Studio express sürümleri de kodunuz sık karşılaşılan sorunları kümesi ve iyi bir programlama uygulama ihlalleri için inceler. Kod çözümleme geçerli olan, ancak hala siz veya kodunuzu kullanan diğer kişiler için sorunlarına neden olabilir belirli kod düzenleri arar çünkü kod analizi uyarıları derleyici hataları ve Uyarıları farklılık gösterir. Kod çözümleme kodunuzda sınama aracılığıyla bulmak zordur kusurları da bulabilirsiniz. Kod çözümleme aracı geliştirme sürecinde düzenli aralıklarla çalışan tamamlanan uygulama kalitesini geliştirebilirsiniz.  
  
> [!NOTE]
>  Visual Studio Ultimate, Visual Studio Premium ve Visual Studio Professional, kod çözümleme araçları tam işlevselliğini kullanabilirsiniz. Bkz: [kod çözümleme araçları ile uygulama kalitesini analiz etme](http://msdn.microsoft.com/library/dd264897.aspx) MSDN Kitaplığı'nda.  
  
## <a name="in-this-topic"></a>Bu konuda  
 Hakkında bilgi alabilirsiniz:  
  
 [Çalışan kod çözümleme](../test/analyze-cpp-code-quality-of-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Run)  
  
 [Çözümleme ve Kod Analizi uyarıları çözümleme](../test/analyze-cpp-code-quality-of-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Analyze)  
  
 [Kod çözümleme uyarıları gizleme](../test/analyze-cpp-code-quality-of-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Suppress)  
  
 [Arama ve kod çözümleme sonuçlarını filtreleme](../test/analyze-cpp-code-quality-of-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Search)  
  
 [C++ Kod Analizi uyarıları](../test/analyze-cpp-code-quality-of-store-apps-using-visual-studio-static-code-analysis.md#Warnings)  
  
##  <a name="BKMK_Run"></a>Çalışan kod çözümleme  
 Visual Studio çözümünüzü Kod Analizi çalıştırmak için:  
  
-   Üzerinde **yapı** menüsünde seçin **çalıştırmak Kod Analizi çözüm üzerinde**.  
  
 Kod çözümleme her zaman otomatik olarak çalıştırmak için bir proje oluşturun:  
  
1.  Çözüm Gezgini'nde proje adına seçin ve ardından **özellikleri**.  
  
2.  Proje özellik sayfası seçin **Kod Analizi** ve ardından **derlemede C/C++ için Kod Analizi etkinleştir**.  
  
 Çözüm derlenir ve Kod Analizi çalıştırır. Sonuçları Kod Analizi penceresinde görüntülenir.  
  
 ![Kod çözümleme penceresi](../test/media/ca_cpp_collapsed.png "CA_CPP_Collapsed")  
  
##  <a name="BKMK_Analyze"></a>Çözümleme ve Kod Analizi uyarıları çözümleme  
 Belirli bir uyarı çözümlemek için Kod Analizi penceresinde uyarıyı başlığını seçin. Sorun hakkında ayrıntılı bilgileri görüntülemek için uyarı genişletir. Mümkün olduğunda, kod analizi için uyarı öncülük satır numarası ve analiz mantığı görüntüler.  
  
 ![Kod çözümleme uyarısı Genişletilmiş](../test/media/ca_cpp_expanded_callout.png "CA_CPP_Expanded_Callout")  
  
 Bir uyarı genişlettiğinizde, uyarıya neden olan kod satırlarını Visual Studio Kod Düzenleyicisi'nde vurgulanır.  
  
 ![Vurgulanan kaynak kodu](../test/media/ca_cpp_sourceline.png "CA_CPP_SourceLine")  
  
 Sorun anladıktan sonra kodunuzda çözebilirsiniz. Ardından uyarı artık Kod Analizi penceresinde görüntülenir ve yeni uyarılar gerçekleşti, düzeltme henüz emin olmak için Kod Analizi yeniden çalıştırın.  
  
> [!TIP]
>  Kod çözümleme Kod Analizi penceresinden yeniden çalıştırabilirsiniz. Seçin **Çözümle** düğmesine tıklayın ve ardından analiz kapsamını seçin. Analiz çözümün tamamında veya seçili bir proje üzerinde yeniden çalıştırabilirsiniz.  
  
##  <a name="BKMK_Suppress"></a>Kod çözümleme uyarıları gizleme  
 Kod çözümleme uyarısı düzeltme değil zaman karar verebilirsiniz zamanlar vardır. Uyarı çözümleme sorunu kodunuzu herhangi bir gerçek uygulaması içinde çıkabilecek olasılık ile ilgili çok fazla değiştirilemeyen gerektirir karar verebilirsiniz. Veya uyarıda kullanılan analiz belirli bağlam için uygun olduğunu düşünüyorsanız. Kod Analizi penceresinde artık görünecekleri bireysel uyarıları gizleyebilirsiniz.  
  
 Bir uyarıyı gizlemek için:  
  
1.  Ayrıntılı bilgi görüntülenmiyorsa uyarı başlığı genişletin.  
  
2.  Seçin **Eylemler** uyarı sonundaki bağlantı.  
  
3.  Tercih **bastırmak ileti** ve ardından **içinde kaynak**.  
  
 Bir ileti gizleme ekler `#pragma(warning:` *WarningId* `)` kod satırı için uyarı gizler.  
  
##  <a name="BKMK_Search"></a>Arama ve kod çözümleme sonuçlarını filtreleme  
 Uyarı iletilerini uzun listeler arayabilir ve birden çok proje çözümü uyarıları filtreleyebilirsiniz.  
  
 ![Arama ve Kod Analizi penceresi filtre](../test/media/ca_searchfilter.png "CA_SearchFilter")  
  
##  <a name="Warnings"></a>C++ Kod Analizi uyarıları  
 Kod çözümleme C++ kodu için aşağıdaki uyarıları başlatır:  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[C6001](../code-quality/c6001.md)|Başlatılmamış bellek kullanma|  
|[C6011](../code-quality/c6011.md)|Null işaretçinin başvurusunun kaldırılmasının|  
|[C6029](../code-quality/c6029.md)|Unchecked değeri kullanımı|  
|[C6053](../code-quality/c6053.md)|Çağrısından sıfır sonlandırma|  
|[C6059](../code-quality/c6059.md)|Hatalı birleştirme|  
|[C6063](../code-quality/c6063.md)|İşlev biçimlendirmek için dize bağımsız değişkeni eksik|  
|[C6064](../code-quality/c6064.md)|İşlev biçimlendirmek için tamsayı bağımsız değişkeni eksik|  
|[C6066](../code-quality/c6066.md)|İşlev biçimlendirmek için işaretçi bağımsız değişkeni eksik|  
|[C6067](../code-quality/c6067.md)|İşlev biçimlendirmek için dize işaretçi bağımsız değişkeni eksik|  
|[C6101](../code-quality/c6101.md)|Başlatılmamış bellek döndürme|  
|[C6200](../code-quality/c6200.md)|Dizin arabellek üst sınırını aşıyor|  
|[C6201](../code-quality/c6201.md)|Dizin yığını arabellek üst sınırını aşıyor|  
|[C6270](../code-quality/c6270.md)|İşlev biçimlendirmek için Float bağımsız değişkeni eksik|  
|[C6271](../code-quality/c6271.md)|İşlev biçimlendirmek için ek bağımsız değişken|  
|[C6272](../code-quality/c6272.md)|İşlev biçimlendirmek için bağımsız değişken Float|  
|[C6273](../code-quality/c6273.md)|Tamsayı olmayan Argumen işlevi biçimlendirmek için|  
|[C6274](../code-quality/c6274.md)|İşlev biçimlendirmek için karakter olmayan bağımsız değişken|  
|[C6276](../code-quality/c6276.md)|Geçersiz dize atama|  
|[C6277](../code-quality/c6277.md)|Geçersiz CreateProcess arama|  
|[C6284](../code-quality/c6284.md)|İşlev biçimlendirmek için geçersiz nesne değişkeni|  
|[C6290](../code-quality/c6290.md)|Bitwise Not mantıksal- ve önceliği|  
|[C6291](../code-quality/c6291.md)|Bitwise Not mantıksal- veya önceliği|  
|[C6302](../code-quality/c6302.md)|İşlev biçimlendirmek için geçersiz bir karakter dizesi bağımsız değişkeni|  
|[C6303](../code-quality/c6303.md)|İşlev biçimlendirmek için geçersiz geniş karakter dizesi bağımsız değişkeni|  
|[C6305](../code-quality/c6305.md)|Eşleşmeyen boyutunu ve sayısını kullan|  
|[C6306](../code-quality/c6306.md)|Yanlış değişken bağımsız değişken işlev çağrısı|  
|[C6328](../code-quality/c6328.md)|Olası bağımsız değişkeni tür uyuşmazlığı|  
|[C6385](../code-quality/c6385.md)|Okuma taşması|  
|[C6386](../code-quality/c6386.md)|Taşma yazma|  
|[C6387](../code-quality/c6387.md)|Geçersiz parametre değeri|  
|[C6500](../code-quality/c6500.md)|Geçersiz öznitelik özelliği|  
|[C6501](../code-quality/c6501.md)|Çakışan öznitelik özellik değerleri|  
|[C6503](../code-quality/c6503.md)|Başvuruları Null olamaz|  
|[C6504](../code-quality/c6504.md)|İşaretçi null|  
|[C6505](../code-quality/c6505.md)|Void üzerinde Pages'in|  
|[C6506](../code-quality/c6506.md)|İşaretçi olmayan veya dizi arabellek boyutu|  
|[C6507](http://msdn.microsoft.com/en-us/18f88cd1-d035-4403-a6a4-12dd0affcf21)|Konumundaki null uyuşmazlığı sıfır başvuru|  
|[C6508](../code-quality/c6508.md)|Yazma erişimi sabiti|  
|[C6509](../code-quality/c6509.md)|Önkoşul üzerinde kullanılan dönüş|  
|[C6510](../code-quality/c6510.md)|Null işaretçinin olmayan üzerinde sonlandırıldı|  
|[C6511](../code-quality/c6511.md)|Pages'in olmalıdır Evet veya Hayır|  
|[C6513](../code-quality/c6513.md)|Arabellek boyutu olmadan öğesi boyutu|  
|[C6514](../code-quality/c6514.md)|Dizi boyutu arabellek boyutunu aşıyor|  
|[C6515](../code-quality/c6515.md)|İşaretçi olmayan arabellek boyutu|  
|[C6516](../code-quality/c6516.md)|Hiçbir öznitelik özellikleri|  
|[C6517](../code-quality/c6517.md)|Okunabilir olmayan arabellek geçerli boyutu|  
|[C6518](../code-quality/c6518.md)|Yazılabilir olmayan arabellek yazılabilir boyutu|  
|[C6519](http://msdn.microsoft.com/en-us/2b6326b0-0539-4d26-8fb1-720114933232)|Geçersiz ek açıklama: 'NeedsRelease' özelliğinin değeri olmalıdır Evet veya Hayır|  
|[C6521](http://msdn.microsoft.com/en-us/e98d0ae3-6f13-47b2-9a15-15d4055af9ef)|Boyutu geçersiz dize başvuru|  
|[C6522](../code-quality/c6522.md)|Boyutu geçersiz dize türü|  
|[C6523](http://msdn.microsoft.com/en-us/11397a31-b224-46b0-afb7-d49ca576a3bb)|Geçersiz boyutu dizesi parametresi|  
|[C6525](../code-quality/c6525.md)|Boyutu geçersiz dize ulaşılamaz konumu|  
|[C6526](http://msdn.microsoft.com/en-us/59c590c7-0098-4166-a1ac-87f324596002)|Boyutu geçersiz dize arabellek türü|  
|[C6527](../code-quality/c6527.md)|Geçersiz ek açıklama: 'NeedsRelease' özelliğinin türü void değerlerine kullanılamaz|  
|[C6530](../code-quality/c6530.md)|Tanınmayan biçim dizesi stili|  
|[C6540](../code-quality/c6540.md)|Bu işlev özniteliği ek açıklamalarını kullanımını tüm mevcut __declspec açıklamalarıyla geçersiz kılar|  
|[C6551](../code-quality/c6551.md)|Geçersiz boyut belirtimi: ifadesi değil parsable|  
|[C6552](../code-quality/c6552.md)|Geçersiz Deref = veya Notref =: ifadesi değil parsable|  
|[C6701](../code-quality/c6701.md)|Değer geçerli bir Evet/Hayır/olabilir değeri değil|  
|[C6702](../code-quality/c6702.md)|Değer bir dize değeri değil|  
|[C6703](../code-quality/c6703.md)|Değer bir sayı değil|  
|[C6704](../code-quality/c6704.md)|Beklenmeyen ek açıklama ifade hatası|  
|[C6705](../code-quality/c6705.md)|Beklenen sayıda bağımsız değişken ek açıklama için gerçek ek açıklama için bağımsız değişken sayısı eşleşmiyor|  
|[C6706](../code-quality/c6706.md)|Ek açıklama için beklenmeyen bir ek açıklamanın hata|  
|[C28021](../code-quality/c28021.md)|Açıklama parametresi bir işaretçi olmalıdır|  
|[C28182](../code-quality/c28182.md)|BOŞ işaretçi başvurusunun kaldırılmasının. Başka bir işaretçi yaptığınız gibi bir işaretçi aynı NULL değer içeriyor.|  
|[C28202](../code-quality/c28202.md)|Statik olmayan üye geçersiz başvuru|  
|[C28203](../code-quality/c28203.md)|Sınıf üyesine başvuru belirsiz.|  
|[C28205](../code-quality/c28205.md)|_Success\_ veya _On_failure\_ geçersiz bir bağlamda kullanılır|  
|[C28206](../code-quality/c28206.md)|İşlenen noktaları için yapı sol, Kullan '->'|  
|[C28207](../code-quality/c28207.md)|Sol işleneni yapı, kullanın '.'|  
|[C28210](../code-quality/c28210.md)|Ek açıklamalar __on_failure bağlamının açık öncesi bağlamda olmamalıdır|  
|[C28211](../code-quality/c28211.md)|Statik içerik adı SAL_context için bekleniyor|  
|[C28212](../code-quality/c28212.md)|İşaretçi ifade eklenti için bekleniyor|  
|[C28213](../code-quality/c28213.md)|_Use_decl_annotations\_ ek açıklama, başvuru, değişiklik yapmadan önce bir bildirim için kullanılmalıdır.|  
|[C28214](../code-quality/c28214.md)|Öznitelik parametre adları p1... olmalıdır p9|  
|[C28215](../code-quality/c28215.md)|Typefix bir typefix zaten olan bir parametre için uygulanamaz|  
|[C28216](../code-quality/c28216.md)|CheckReturn ek açıklama yalnızca Sonkoşullar belirli bir işlev parametresi için geçerlidir.|  
|[C28217](../code-quality/c28217.md)|İşlevi için dosya bulunan ek açıklama için parametre sayısı eşleşmiyor|  
|[C28218](../code-quality/c28218.md)|İşlev paramteer için dosya bulunan ek açıklamanın parametresi eşleşmiyor|  
|[C28219](../code-quality/c28219.md)|Numaralandırma üyesi için ek açıklama ek açıklamanın parametresinde bekleniyordu.|  
|[C28220](../code-quality/c28220.md)|Tamsayı ifade eklenti için ek açıklama parametresinde bekleniyordu.|  
|[C28221](../code-quality/c28221.md)|Ek açıklamanın parametresinin beklenen dize ifadesi|  
|[C28222](../code-quality/c28222.md)|__yes, \__hayır, veya \__maybe eklenti için bekleniyor|  
|[C28223](../code-quality/c28223.md)|Beklenen belirteç/tanımlayıcı ek bilgi için bulamadı parametresi|  
|[C28224](../code-quality/c28224.md)|Ek açıklama parametreleri gerektirir|  
|[C28225](../code-quality/c28225.md)|Gerekli Parametreler doğru sayıda açıklama içinde bulunamadı|  
|[C28226](../code-quality/c28226.md)|Ek açıklama ayrıca PrimOp (bildiriminde geçerli) olamaz|  
|[C28227](../code-quality/c28227.md)|Ek açıklama bir PrimOp da olamaz (önceki bildirimi bakın)|  
|[C28228](../code-quality/c28228.md)|Ek açıklama parametresi: türü ek açıklamalar kullanamaz|  
|[C28229](../code-quality/c28229.md)|Ek açıklama parametreleri desteklemez|  
|[C28230](../code-quality/c28230.md)|Parametre hiç üye türü.|  
|[C28231](../code-quality/c28231.md)|Ek açıklama yalnızca dizisinde geçerlidir|  
|[C28232](../code-quality/c28232.md)|önceden, post veya hiçbir ek açıklama uygulanmamış deref|  
|[C28233](../code-quality/c28233.md)|önceden, gönderme veya bir blok uygulanan deref|  
|[C28234](../code-quality/c28234.md)|ifade __at geçerli işlevi için geçerli değildir|  
|[C28235](../code-quality/c28235.md)|İşlev açıklamanın tek başına olamaz|  
|[C28236](../code-quality/c28236.md)|Ek açıklamanın bir ifadede kullanılamaz|  
|[C28237](../code-quality/c28237.md)|Ek açıklamayı parametresi artık desteklenmiyor|  
|[C28238](../code-quality/c28238.md)|Ek açıklamanın parametresi üzerinde birden fazla değer, stringValue ve LongDeğer sahip. Paramn kullanmak xxx =|  
|[C28239](../code-quality/c28239.md)|Ek açıklamanın parametresi üzerinde hem değer, stringValue veya LongDeğer sahiptir; ve paramn = xxx. Yalnızca paramn kullanmak xxx =|  
|[C28240](../code-quality/c28240.md)|Ek açıklamanın parametresindeki param2 ancak hiçbir param1 sahiptir|  
|[C28241](../code-quality/c28241.md)|Ek açıklamanın parametresindeki işlevi için tanınmıyor|  
|[C28243](../code-quality/c28243.md)|İşlev parametresi üzerinde daha gerektirir açıklama gerçek tür izin verdiğinden ek açıklamanın dereferences|  
|[C28245](../code-quality/c28245.md)|Ek açıklamanın işlevi için bir üye-işlev olmayan üzerinde 'this' açıklama ekler|  
|[C28246](../code-quality/c28246.md)|İşlevi için parametre ek açıklama parametresinin türü eşleşmiyor.|  
|[C28250](../code-quality/c28250.md)|İşlevi için tutarsız ek açıklama: önceki örneği hatalı.|  
|[C28251](../code-quality/c28251.md)|İşlevi için tutarsız ek açıklama: Bu örnek bir hata vardır.|  
|[C28252](../code-quality/c28252.md)|İşlevi için tutarsız ek açıklama: Bu örneğinde parametresine sahip başka bir ek açıklamaları.|  
|[C28253](../code-quality/c28253.md)|İşlevi için tutarsız ek açıklama: Bu örneğinde parametresine sahip başka bir ek açıklamaları.|  
|[C28254](../code-quality/c28254.md)|Ek açıklamalar dynamic_cast <> (') desteklenmiyor|  
|[C28262](../code-quality/c28262.md)|Ek açıklamanın bir sözdizimi hatası ek açıklama için işlevi bulundu|  
|[C28263](../code-quality/c28263.md)|İç eklenti için koşullu bir ek açıklamanın bir sözdizimi hatası bulundu|  
|[C28264](http://msdn.microsoft.com/en-us/bf6ea983-a06e-4752-a042-747a7dbf338c)|Sonuç listeleri değerleri olmalıdır.|  
|[C28267](../code-quality/c28267.md)|Ek açıklamalar bir sözdizimi hatası ek açıklama işlevinde bulunamadı.|  
|[C28272](../code-quality/c28272.md)|Ek açıklamanın işlevi için incelerken parametresi işlev bildirimi ile tutarsız|  
|[C28273](../code-quality/c28273.md)|İşlevi için ipuçları işlevi bildirimi ile tutarsız|  
|[C28275](../code-quality/c28275.md)|_Macro_value parametresi\_ null|  
|[C28279](../code-quality/c28279.md)|Simge için bir 'başlamak' bir eşleşen 'end ' bulundu|  
|[C28280](../code-quality/c28280.md)|Simge için bir 'end' bir eşleşen olmadan 'başlamak' bulundu|  
|[C28282](../code-quality/c28282.md)|Biçim dizeleri önkoşulları içinde olmalıdır|  
|[C28285](../code-quality/c28285.md)|İşlev, parametre sözdizimi hatası|  
|[C28286](../code-quality/c28286.md)|İşlev, son yakınında sözdizimi hatası|  
|[C28287](../code-quality/c28287.md)|İşlev, söz dizimi hatası sürü_müne\_() ek açıklama (tanınmayan parametre adı)|  
|[C28288](../code-quality/c28288.md)|İşlev, söz dizimi hatası sürü_müne\_() ek açıklama (geçersiz parametre adı)|  
|[C28289](../code-quality/c28289.md)|İşlevi için: ReadableTo veya WritableTo bir parametre olarak bir sınırı spec yoktu|  
|[C28290](../code-quality/c28290.md)|ek açıklamanın işlevi için parametre gerçek sayısından daha fazla Externals içerir|  
|[C28291](../code-quality/c28291.md)|POST null/notnull adresindeki deref düzeyi 0'dır işlevi için anlamsız.|  
|[C28300](../code-quality/c28300.md)|Uyumsuz türlerin operatöre ifade işlenenleri|  
|[C28301](../code-quality/c28301.md)|İşlevin ilk bildirimi için hiçbir ek açıklamalar.|  
|[C28302](../code-quality/c28302.md)|Bir ek _Deref\_ işleci ek açıklamayı bulundu.|  
|[C28303](../code-quality/c28303.md)|Belirsiz _Deref\_ işleci ek açıklamayı bulundu.|  
|[C28304](../code-quality/c28304.md)|Yanlış yerleştirilmiş _Notref\_ işleci belirtecine uygulanan bulundu.|  
|[C28305](../code-quality/c28305.md)|Bir belirteç ayrıştırılırken bir hata bulundu.|  
|[C28350](../code-quality/c28350.md)|Ek açıklamanın koşullu kullanılamaz bir durumda açıklar.|  
|[C28351](../code-quality/c28351.md)|Ek açıklamanın dinamik bir değer (bir değişken) koşulunda burada kullanılamaz açıklar.|
