---
title: "Visual Basic'te uyarıları yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors [Visual Basic], warnings
- run-time errors, warnings
- warnings, configuring
ms.assetid: 99cf4781-bd4d-47b4-91b9-217933509f82
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4df81a0d5f6faee7a272abd13ca6e046681b045d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="configuring-warnings-in-visual-basic"></a>Visual Basic'teki Uyarıları Yapılandırma
[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Derleyici uyarıları çalışma zamanı hataları neden olabilir kodu hakkında bir dizi içerir. Temizleyici, daha hızlı ve daha az hataları ile daha iyi bir kod yazmak için bu bilgileri kullanabilirsiniz. Derleyici örneğin veya kullanıcı atanmamış nesne değişkeni, dönüş değeri ayarı olmadan bir işlevden dönüş üyesi çağırma girişiminde bulunduğunda bir uyarı üretir yürütme bir `Try` bloğu özel durumları yakalamak için mantığı hatalı.  
  
 Bazen, kullanıcı elinizdeki yerine olası hatalar bekleme üzerinde odaklanabilmeniz derleyici kullanıcı adına ek mantığı sağlar. Önceki sürümlerinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], `Option Strict` ek mantık sınırlamak için kullanılan, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] derleyici sağlar. Uyarıları yapılandırma bireysel uyarıları düzeyinde daha ayrıntılı bir şekilde bu mantığı sınırlamanıza olanak sağlar.  
  
 Projenizi özelleştirebilir ve bazı uyarılar değil ilgili diğer uyarılara hataları içine kapatma sırasında uygulamanıza etkinleştirmek isteyebilirsiniz. Bu sayfa, bireysel uyarıları açıp kapatabilirsiniz açıklanmaktadır.  
  
## <a name="turning-warnings-off-and-on"></a>Uyarılar ve kapatma  
 Uyarıları yapılandırmak için iki farklı yolu vardır: bunları yapılandırabilirsiniz kullanarak **Proje Tasarımcısı**, veya kullanabilirsiniz **/warnaserror** ve **/nowarn** derleyici seçenekleri .  
  
 **Derleme** sekmesinde **Proje Tasarımcısı** sayfası uyarıları açıp kapatabilirsiniz sağlar. Seçin **tüm uyarıları devre dışı** tüm uyarıları devre dışı bırakmak için onay kutusunu işaretleyin; seçin **tüm uyarıları hata olarak değerlendir** tüm uyarıları hata olarak değerlendirmek için. Tek tek bazı uyarılar hata veya uyarı kapatılabilir görüntülenen tablosundaki istenen şekilde.  
  
 Zaman **Option Strict** ayarlanır **kapalı**, **Option Strict** uyarıları olamaz kabul diğer bağımsız olarak ilgili. Zaman **Option Strict** ayarlanır **üzerinde**, ilişkili uyarıları hata olarak kabul edilir, Hayır ne durumlarını önemli değildir. Zaman **Option Strict** ayarlanır **özel** belirterek `/optionstrict:custom` komut satırı derleyicisini içinde **Option Strict** uyarıları açılıp kapatılabilecek bağımsız olarak.  
  
 **/Warnaserror** derleyici komut satırı seçeneği de uyarıları hata olarak kabul edilip edilmeyeceğini belirlemek için kullanılabilir. Virgülle ayrılmış listesini hangi uyarıların hata veya uyarı kullanarak ele alınması gerektiğini belirtmek için bu seçeneği ekleyebileceğiniz + veya -. Aşağıdaki tabloda olası seçeneklerin ayrıntıları verilmiştir.  
  
|Komut satırı seçeneği|Belirler|  
|--------------------------|---------------|  
|`/warnaserror+`|Tüm uyarıları hata olarak işle|  
|`/warnsaserror`-|Uyarıları hata olarak olarak görmeyin. Bu varsayılandır.|  
|`/warnaserror+:<warning list``>`|Belirli uyarıları, virgülle ayrılmış listesini r hata kodu numarasına göre listelenen hata olarak kabul eder.|  
|`/warnaserror-:<warning list>`|Belirli uyarıları, virgülle ayrılmış listesini hata kodu numarasına göre listelenen hata olarak ele değil.|  
|`/nowarn`|Uyarıları bildirmez.|  
|`/nowarn:<warning list>`|Belirtilen uyarılar, virgülle ayrılmış listesini hata kodu numarasına göre listelenen rapor etmez.|  
  
 Uyarı listesi belirli uyarıları açmak veya kapatmak için komut satırı seçenekleriyle kullanılabilir hata olarak ele alınması gerektiğini uyarıların hata kimliği numaralarını içerir. Uyarı listesi geçersiz bir sayı içeriyorsa, bir hata bildirilir.  
  
## <a name="examples"></a>Örnekler  
 Komut satırı bağımsız değişkenleri örnekleri bu tablo her bağımsız yaptığı açıklar.  
  
|Bağımsız Değişken|Açıklama|  
|--------------|-----------------|  
|`vbc /warnaserror`|Tüm uyarıların hata sayılması gerektiğini belirtir.|  
|`vbc /warnaserror:42024`|Bu uyarı belirtir 42024 hata olarak kabul.|  
|`vbc /warnaserror:42024,42025`|Uyarılar 42024 ve 42025 hata olarak kabul edileceğini belirtir.|  
|`vbc /nowarn`|Uyarı bildirilen olduğunu belirtir.|  
|`vbc /nowarn:42024`|Bu uyarı belirtir 42024 bildirilmedi.|  
|`vbc /nowarn:42024,42025`|Uyarılar 42024 ve 42025 bildirilmedi belirtir.|  
  
## <a name="types-of-warnings"></a>Uyarı türleri  
 Hata ele isteyebilirsiniz uyarıların listesi aşağıda verilmiştir.  
  
### <a name="implicit-conversion-warning"></a>Örtük dönüştürme uyarı  
 İçin oluşturulan örtük dönüşüm örnekleri. Bunlar bir dize için geçerli bir sayısal tür gelen örtük dönüşümler kullanırken içermez `&` işleci. Yeni projeler kapatmak için varsayılan.  
  
 KİMLİĞİ: 42016  
  
### <a name="late-bound-method-invocation-and-overload-resolution-warning"></a>Yöntem çağırma ve aşırı yükleme çözümü uyarı geç bağlama  
 İçin oluşturulan örnekleri olarak geç bağlama. Yeni projeler kapatmak için varsayılan.  
  
 KİMLİĞİ: 42017  
  
### <a name="operands-of-type-object-warnings"></a>Türü nesne uyarıları işlenenleri  
 Oluşturulan türündeki işlenenler `Object` hatayla oluşturmak ortaya `Option Strict On`. Yeni projeler üzerinde için varsayılan.  
  
 Kimliği: 42018 ve 42019  
  
### <a name="declarations-require-as-clause-warnings"></a>'As' yan tümcesi uyarı bildirimleri gerektirir  
 Değişken, işlev veya özellik bildirimi eksik zaman oluşturulan bir `As` yan tümcesi, bir hata ile oluşturulan `Option Strict On`. Atanmış bir türleri olmadığı değişkenleri kabul türü `Object`. Yeni projeler üzerinde için varsayılan.  
  
 Kimliği: 42020 (değişken bildirimi), 42021 (işlev bildirimi) ve 42022 (özellik bildirimi).  
  
### <a name="possible-null-reference-exception-warnings"></a>Olası Null başvuru özel durumu uyarıları  
 Bir değişkene bir değer atanan önce kullanıldığında oluşturulur. Yeni projeler üzerinde için varsayılan.  
  
 KİMLİĞİ: 42104, 42030  
  
### <a name="unused-local-variable-warning"></a>Kullanılmayan yerel değişken uyarı  
 Yerel bir değişken bildirilmiş ancak hiçbir zaman başvurulan oluşturulur. Varsayılan açıktır.  
  
 KİMLİĞİ: 42024  
  
### <a name="access-of-shared-member-through-instance-variable-warning"></a>Örnek değişken uyarı aracılığıyla paylaşılan üye erişimi  
 Örneğinden paylaşılan bir üyeye erişme yan etkileri olabilir veya bir örnek değişkeni paylaşılan bir üyeye erişme ve sağ taraftaki ifade değil ya da bir parametre olarak geçirilen zaman oluşturulur. Yeni projeler üzerinde için varsayılan.  
  
 KİMLİĞİ: 42025  
  
### <a name="recursive-operator-or-property-access-warnings"></a>Özyinelemeli işleci veya özellik erişim uyarılar  
 Bir yordam gövdesi aynı işleci veya içinde tanımlanan özelliğini kullandığında oluşturulur. Yeni projeler üzerinde için varsayılan.  
  
 Kimliği: 42004 (işleç), 42026 (özellik)  
  
### <a name="function-or-operator-without-return-value-warning"></a>İşlev veya dönüş değeri uyarmadan işleci  
 İşlev veya işleci belirtilen dönüş değeri olmadığında oluşturulur. Bu atlama içeren bir `Set` örtük yerel değişkene işlevi aynı ada sahip. Yeni projeler üzerinde için varsayılan.  
  
 Kimliği: 42105 (işlev), 42016 (işleç)  
  
### <a name="overloads-modifier-used-in-a-module-warning"></a>Bir modülü uyarı kullanılan aşırı değiştiricisi  
 Oluşturulan `Overloads` kullanılan bir `Module`. Yeni projeler üzerinde için varsayılan.  
  
 KİMLİĞİ: 42028  
  
### <a name="duplicate-or-overlapping-catch-blocks-warnings"></a>Yinelenen veya örtüşen Catch blokları uyarıları  
 Oluşturulan bir `Catch` bloğu diğer ilişkisi nedeniyle hiçbir zaman ulaşıldığında `Catch` tanımlanmış engeller. Yeni projeler üzerinde için varsayılan.  
  
 KİMLİĞİ: 42029, 42031  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata türleri](/dotnet/visual-basic/programming-guide/language-features/error-types)   
 [Try... Catch... Finally ifadesi](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [/ nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn)   
 [/ warnaserror (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/warnaserror)   
 [Derle sayfası, Proje Tasarımcısı (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Varsayılan olarak kapalı olan derleyici uyarıları](/cpp/preprocessor/compiler-warnings-that-are-off-by-default)