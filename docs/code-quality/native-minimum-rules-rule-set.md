---
title: Yerel Minimum Kurallar kural kümesi
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 2d898bc4-fba5-472e-8f09-b0c6b511c5a3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d037c06be1f0eb7acb3bad1c995679edab03730
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31927184"
---
# <a name="native-minimum-rules-rule-set"></a>Yerel Minimum Kurallar kural kümesi
Microsoft yerel Minimum kurallar olası güvenlik açıklarını ve uygulama çökme (Crash) dahil olmak üzere, yerel kodunuzda en kritik sorunlar odaklanır. Yerel projeleriniz için oluşturduğunuz herhangi bir özel kural kümesi içinde bu kural kümesi içermelidir.

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
|[C6522](../code-quality/c6522.md)|Boyutu geçersiz dize türü|
|[C6525](../code-quality/c6525.md)|Boyutu geçersiz dize ulaşılamaz konumu|
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