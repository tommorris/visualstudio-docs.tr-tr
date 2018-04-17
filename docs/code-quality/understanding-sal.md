---
title: SAL anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: a94d6907-55f2-4874-9571-51d52d6edcfd
author: mikeblome
ms.author: mblome
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: deb1825bb514afec4db3bf705ac787aadb88cc11
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="understanding-sal"></a>SAL'ı Anlama
Microsoft kaynak kodu ek açıklama dili (SAL), bir işlev parametreleri, bunlarla ilgili kolaylaştırır varsayımları ve tamamlandığında kolaylaştıran garanti nasıl kullandığını tanımlamak için kullanabileceğiniz ek açıklamaları kümesi sağlar. Ek açıklamalar üstbilgi dosyasında tanımlanan `<sal.h>`. C++ için Visual Studio Kod Analizi SAL ek açıklamaları işlevleri çözümlemesini değiştirmek için kullanır. Windows Sürücü Geliştirme için SAL 2.0 hakkında daha fazla bilgi için bkz: [SAL 2.0 ek açıklamalar için Windows sürücülerini](http://go.microsoft.com/fwlink/?LinkId=250979).  
  
 Yerel olarak, C ve C++ amacını ve invariance tutarlı bir şekilde express geliştiriciler için yalnızca sınırlı yollar sağlar. SAL ek açıklamaları kullanılarak işlevlerinizi daha ayrıntılı tanımlayabilir, böylece bunları kullanan geliştiriciler nasıl kullanıldığını daha iyi anlayabilirsiniz.  
  
## <a name="what-is-sal-and-why-should-you-use-it"></a>SAL nedir ve neden kullanmalısınız?  
 Kısacası, SAL kodunuzu denetimi derleyici izin vermek için bir ucuz yoludur.  
  
### <a name="sal-makes-code-more-valuable"></a>SAL kod daha yararlı hale getirir  
 SAL insanlar hem kod çözümleme araçları, kod tasarımınızın daha anlaşılır hale yardımcı olabilir. C çalışma zamanı işlevi gösterir Bu örneği göz önünde bulundurun `memcpy`:  
  
```cpp  
  
void * memcpy(  
   void *dest,   
   const void *src,   
   size_t count  
);  
  
```  
  
 Bu işlev yaptığı anlayabilirim? Bir işlev uygulanmadı ya da adlı program doğruluğundan emin olmak için belirli özellikleri korunmalıdır. Yalnızca bir örnekte gibi bir bildirimi bakarak, bunların ne olduğunu bilmiyorsanız. SAL ek açıklamalar olmadan, belge veya kod açıklamaları yararlanmayı gerekir. İçin MSDN belgelerine işte `memcpy` diyor:  
  
> "Kopya taşınmaya src bayt sayısı. Kaynak ve hedef çakışırsa, memcpy davranışını tanımlanmamıştır. Memmove çakışan bölgeler işlemek için kullanır.   
> **Güvenlik Notu:** boyutu veya daha büyük kaynak arabelleği hedef arabelleği aynı olduğundan emin olun. Daha fazla bilgi için önleme arabellek taşmasına neden bakın."  
  
 Belgeler birkaç kodunuzu program doğruluğundan emin olmak için belirli özellikleri korumak sahip önerdiğinde BITS bilgi içermektedir:  
  
-   `memcpy` kopya `count` hedef arabelleği kaynak arabellekteki bayt.  
  
-   Hedef arabellek en az kaynak arabelleği kadar büyük olmalıdır.  
  
 Ancak, derleyici belge veya resmi olmayan yorumlar okunamıyor. İki arabelleğini arasında bir ilişki olduğunu bilmiyor ve `count`, ve bu da etkin bir ilişki hakkında tahmin edilemez. SAL, aşağıda gösterildiği gibi özellikleri ve işlev uygulaması hakkında daha fazla netlik sağlayabilir:  
  
```cpp  
  
void * memcpy(  
   _Out_writes_bytes_all_(count) void *dest,   
   _In_reads_bytes_(count) const void *src,   
   size_t count  
);  
```  
  
 Bu ek açıklamalar MSDN belgelerindeki bilgilerine benzer, ancak daha kısa ve anlam desenler izleyen dikkat edin. Bu kodu okurken, bu işlevin özelliklerine ve arabellek taşması güvenlik sorunlarını önlemek nasıl hızlı bir şekilde anlayabilirsiniz. Bile daha iyi SAL sağlar anlamsal desenleri verimliliği ve potansiyel hataları erken bulgu otomatik kod çözümleme araçları verimliliğini artırabilir. Birisi bu buggy uygulaması, yazar düşünün `wmemcpy`:  
  
```cpp  
  
wchar_t * wmemcpy(  
   _Out_writes_all_(count) wchar_t *dest,   
   _In_reads_(count) const wchar_t *src,   
   size_t count)  
{  
   size_t i;  
   for (i = 0; i <= count; i++) { // BUG: off-by-one error  
      dest[i] = src[i];  
   }  
   return dest;  
}  
  
```  
  
 Bu uygulama bir ortak kapalı tek hata içeriyor. Neyse ki, SAL arabellek boyutu ek açıklama kod yazar dahil — tek başına Bu işlev çözümleyerek hatayı kod analizi aracı catch.  
  
### <a name="sal-basics"></a>SAL temelleri  
 SAL dört temel tür kullanım deseniyle tarafından kategorilere parametreleri tanımlar.  
  
|Kategori|Parametre ek açıklaması|Açıklama|  
|--------------|--------------------------|-----------------|  
|**Giriş olarak adlandırılan için işlevi**|`_In_`|Veriler, çağrılan işlev geçirilir ve salt okunur olarak kabul edilir.|  
|**Giriş işlevini çağırdı ve çağırana çıkış**|`_Inout_`|Kullanılabilir veri işlevdeki geçirilir ve potansiyel olarak değiştirilebilir.|  
|**Arayan çıkışı**|`_Out_`|Çağıran, yalnızca yazmak çağrılan işlev alan sağlar. Çağrılan işlev, bu alana veri yazar.|  
|**Arayan işaretçisine çıktısı**|`_Outptr_`|Gibi **çağırana çıktı**. Çağrılan işlev tarafından döndürülen değer gösteren bir işaretçidir.|  
  
 Bu dört temel ek açıklamalar daha açık olarak çeşitli şekillerde yapılabilir. Varsayılan olarak, ek açıklama işaretçisi parametreleri gerekli olduğu varsayılır; NULL olmayan olmalıdır başarılı olması işlev için. En yaygın kullanılan değişim temel ek açıklamaları işaretçi parametresi isteğe bağlı olduğunu gösterir; NULL ise, işlev yine çalışmasını yaparken de başarılı olabilir.  
  
 Bu tablo, gerekli ve isteğe bağlı parametreleri arasında ayrım gösterilmektedir:  
  
||Parametreler gereklidir|Parametreler isteğe bağlıdır|  
|-|-----------------------------|-----------------------------|  
|**Giriş olarak adlandırılan için işlevi**|`_In_`|`_In_opt_`|  
|**Giriş işlevini çağırdı ve çağırana çıkış**|`_Inout_`|`_Inout_opt_`|  
|**Arayan çıkışı**|`_Out_`|`_Out_opt_`|  
|**Arayan işaretçisine çıktısı**|`_Outptr_`|`_Outptr_opt_`|  
  
 Bu ek açıklamalar olası başlatılmamış değerler tanımlamaya yardımcı olmak ve geçersiz bir null işaretçi resmi ve doğru bir şekilde kullanır. Gerekli parametre için NULL geçirme kilitlenmeye neden olabilir veya döndürülecek bir "başarısız" hata kodu neden olabilir. Her iki durumda da, işini yaparak işlevi başarılı olamaz.  
  
## <a name="sal-examples"></a>SAL örnekleri  
 Bu bölümde, kod örnekleri için temel SAL ek açıklamaları gösterilmiştir.  
  
### <a name="using-the-visual-studio-code-analysis-tool-to-find-defects"></a>Hataları bulmak için Visual Studio kod analizi aracı kullanma  
 Örneklerde, Visual Studio kod analizi aracı, kod hatalarını bulmak için SAL ek açıklamaları ile birlikte kullanılır. Bunun nasıl yapılacağını burada verilmiştir.  
  
##### <a name="to-use-visual-studio-code-analysis-tools-and-sal"></a>Visual Studio kod çözümleme araçları ve SAL kullanmak için  
  
1.  Visual Studio'da SAL ek açıklamaları içeren bir C++ projesi açın.  
  
2.  Menü çubuğunda seçin **yapı**, **çalıştırmak Kod Analizi çözüm üzerinde**.  
  
     _In göz önünde bulundurun\_ bu bölümdeki örnek. Kod çözümleme üzerinde çalıştırıyorsanız, bu uyarı görüntülenir:  
  
    > **C6387 Geçersiz parametre değeri**   
    > 'pInt', '0' olabilir: Bu belirtimine 'InCallee' işlevi için uymaz.  
  
### <a name="example-the-in-annotation"></a>Örnek: _In\_ ek açıklaması  
 `_In_` Ek açıklama gösterir:  
  
-   Parametre geçerli olmalıdır ve değiştirilmeyecek.  
  
-   İşlevi yalnızca tek öğe arabelleğinden okur.  
  
-   Arayan arabellek sağlar ve başlatmanız gerekir.  
  
-   `_In_` "salt okunur" belirtir. Sık karşılaşılan hata uygulamaktır `_In_` olması gereken bir parametre `_Inout_` ek açıklama yerine.  
  
-   `_In_` ancak Çözümleyicisi işaretçi olmayan skalerler'tarafından göz ardı izin verilir.  
  
```cpp  
void InCallee(_In_ int *pInt)  
{  
   int i = *pInt;  
}  
  
void GoodInCaller()  
{  
   int *pInt = new int;  
   *pInt = 5;  
  
   InCallee(pInt);  
   delete pInt;     
}  
  
void BadInCaller()  
{  
   int *pInt = NULL;  
   InCallee(pInt); // pInt should not be NULL  
}  
  
```  
  
 Visual Studio Kod Analizi göre bu örnekte kullanırsanız, başlatılmış bir arabellek için Null olmayan işaretçi arayanlar geçtiğini doğruladığı `pInt`. Bu durumda, `pInt` işaretçisi NULL olamaz.  
  
### <a name="example-the-inopt-annotation"></a>Örnek: _In_opt\_ ek açıklaması  
 `_In_opt_` aynı `_In_`, giriş parametresinin NULL olmasına izin ve işlevi bu nedenle, denetlemelisiniz dışında.  
  
```cpp  
  
void GoodInOptCallee(_In_opt_ int *pInt)  
{  
   if(pInt != NULL) {  
      int i = *pInt;  
   }  
}  
  
void BadInOptCallee(_In_opt_ int *pInt)  
{  
   int i = *pInt; // Dereferencing NULL pointer 'pInt'  
}  
  
void InOptCaller()  
{  
   int *pInt = NULL;  
   GoodInOptCallee(pInt);  
   BadInOptCallee(pInt);  
}  
  
```  
  
 Visual Studio Kod Analizi arabellek erişim izni vermeden önce işlevi NULL denetler doğrular.  
  
### <a name="example-the-out-annotation"></a>Örnek: _bant\_ ek açıklaması  
 `_Out_` bir öğe arabellek işaret eden bir NULL olmayan işaretçi geçirilen ve öğe işlevi başlatır yaygın bir senaryo destekler. Arayan çağırmadan önce arabellek başlatmak zorunda değildir; Çağrılan işlev döndürdüğü önce başlatmak taahhüt eder.  
  
```cpp  
  
void GoodOutCallee(_Out_ int *pInt)  
{  
   *pInt = 5;  
}  
  
void BadOutCallee(_Out_ int *pInt)  
{  
   // Did not initialize pInt buffer before returning!  
}  
  
void OutCaller()  
{  
   int *pInt = new int;  
   GoodOutCallee(pInt);  
   BadOutCallee(pInt);  
   delete pInt;  
}  
  
```  
  
 Visual Studio kod analizi aracı doğrular çağıran bir arabellek için NULL olmayan işaretçi geçirir `pInt` ve onu döndürmeden önce arabellek işlevi tarafından başlatılır.  
  
### <a name="example-the-outopt-annotation"></a>Örnek: _Out_opt\_ ek açıklaması  
 `_Out_opt_` aynı `_Out_`, parametre NULL olmasına izin ve işlevi bu nedenle, denetlemelisiniz dışında.  
  
```cpp  
  
void GoodOutOptCallee(_Out_opt_ int *pInt)  
{  
   if (pInt != NULL) {  
      *pInt = 5;  
   }  
}  
  
void BadOutOptCallee(_Out_opt_ int *pInt)  
{  
   *pInt = 5; // Dereferencing NULL pointer 'pInt'  
}  
  
void OutOptCaller()  
{  
   int *pInt = NULL;  
   GoodOutOptCallee(pInt);  
   BadOutOptCallee(pInt);  
}  
  
```  
  
 Visual Studio Kod Analizi doğrular bu işlev, önce NULL denetler `pInt` başvuru yapıldı ve `pInt` döndürdüğü önce arabellek işlevi tarafından başlatılır NULL değil.  
  
### <a name="example-the-inout-annotation"></a>Örnek: _Inout\_ ek açıklaması  
 `_Inout_` işlev tarafından değiştirilebilir bir işaretçi parametresi açıklama eklemek için kullanılır. İşaretçinin çağırmadan önce geçerli başlatılmış veri işaret etmelidir ve onu değişse bile, geçerli bir değer getirisi hala olmalıdır. Ek açıklamanın işlevi serbestçe okuma ve tek öğeli arabellek yazma belirtir. Arayan arabellek sağlar ve başlatmanız gerekir.  
  
> [!NOTE]
>  Gibi `_Out_`, `_Inout_` değiştirilebilir değerine uygulamanız gerekir.  
  
```cpp  
  
void InOutCallee(_Inout_ int *pInt)  
{  
   int i = *pInt;  
   *pInt = 6;  
}  
  
void InOutCaller()  
{  
   int *pInt = new int;  
   *pInt = 5;  
   InOutCallee(pInt);  
   delete pInt;  
}  
  
void BadInOutCaller()  
{  
   int *pInt = NULL;  
   InOutCallee(pInt); // 'pInt' should not be NULL  
}  
  
```  
  
 Visual Studio Kod Analizi doğrular başlatılmış bir arabellek için NULL olmayan işaretçi arayanlar geçtiğini `pInt`ve iade önce `pInt` hala NULL değilse ve arabellek başlatıldı.  
  
### <a name="example-the-inoutopt-annotation"></a>Örnek: _Inout_opt\_ ek açıklaması  
 `_Inout_opt_` aynı `_Inout_`, giriş parametresinin NULL olmasına izin ve işlevi bu nedenle, denetlemelisiniz dışında.  
  
```cpp  
  
void GoodInOutOptCallee(_Inout_opt_ int *pInt)  
{  
   if(pInt != NULL) {  
      int i = *pInt;  
      *pInt = 6;  
   }  
}  
  
void BadInOutOptCallee(_Inout_opt_ int *pInt)  
{  
   int i = *pInt; // Dereferencing NULL pointer 'pInt'  
   *pInt = 6;  
}  
  
void InOutOptCaller()  
{  
   int *pInt = NULL;  
   GoodInOutOptCallee(pInt);  
   BadInOutOptCallee(pInt);  
}  
  
```  
  
 Visual Studio Kod Analizi doğrular arabellek erişim izni vermeden önce ve bu işlev için NULL denetler `pInt` döndürdüğü önce arabellek işlevi tarafından başlatılır NULL değil.  
  
### <a name="example-the-outptr-annotation"></a>Örnek: _Outptr\_ ek açıklaması  
 `_Outptr_` bir işaretçi döndürmek için amaçlanan bir parametre öğesine açıklama eklemek için kullanılır.  Parametre NULL olmamalıdır ve çağrılan işlev NULL olmayan işaretçi döndürür ve bu işaretçiyi başlatılmış veri noktaları.  
  
```cpp  
  
void GoodOutPtrCallee(_Outptr_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 5;  
  
   *pInt = pInt2;  
}  
  
void BadOutPtrCallee(_Outptr_ int **pInt)  
{  
   int *pInt2 = new int;  
   // Did not initialize pInt buffer before returning!  
   *pInt = pInt2;  
}  
  
void OutPtrCaller()  
{  
   int *pInt = NULL;  
   GoodOutPtrCallee(&pInt);  
   BadOutPtrCallee(&pInt);  
}  
  
```  
  
 Visual Studio Kod Analizi doğrular çağıran bir NULL olmayan işaretçi geçtiğini `*pInt`, ve bunu döndürmeden önce arabellek işlevi tarafından başlatılır.  
  
### <a name="example-the-outptropt-annotation"></a>Örnek: _Outptr_opt\_ ek açıklaması  
 `_Outptr_opt_` aynı `_Outptr_`, isteğe bağlı bir parametredir dışında — çağıran parametresi için bir NULL işaretçinin geçirebilirsiniz.  
  
```cpp  
  
void GoodOutPtrOptCallee(_Outptr_opt_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 6;  
  
   if(pInt != NULL) {  
      *pInt = pInt2;  
   }  
}  
  
void BadOutPtrOptCallee(_Outptr_opt_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 6;  
   *pInt = pInt2; // Dereferencing NULL pointer 'pInt'  
}  
  
void OutPtrOptCaller()  
{  
   int **ppInt = NULL;  
   GoodOutPtrOptCallee(ppInt);  
   BadOutPtrOptCallee(ppInt);  
}  
  
```  
  
 Visual Studio Kod Analizi doğrular bu işlev, önce NULL denetler `*pInt` başvuru yapıldı ve onu döndürmeden önce arabellek işlevi tarafından başlatılır.  
  
### <a name="example-the-success-annotation-in-combination-with-out"></a>Örnek: _Success\_ _bant ile birlikte ek açıklaması\_  
 Ek açıklamalar çoğu nesne için uygulanabilir.  Özellikle, tüm işlevi açıklama ekleyebilirsiniz.  Bir işlevin en belirgin özellikleri, başarılı başarısız veya olduğunu biridir. Ancak bir arabellek boyutuna arasındaki ilişkiyi gibi C/C++ işlevi başarı veya başarısızlık express olamaz. Kullanarak `_Success_` ek açıklama, bir işlev için hangi başarının neye benzediğini söyleyebilirsiniz.  Parametre `_Success_` ek açıklama true olduğunda işlevi başarılı olduğunu belirten bir ifade değil. İfade ek açıklama ayrıştırıcı işleyebilir herhangi bir şey olabilir. İşlev döndükten sonra ek açıklamalar etkilerini yalnızca işlevi başarılı olduğunda geçerlidir. Bu örnekte gösterilir nasıl `_Success_` etkileşimde `_Out_` doğru şey yapmak için. Anahtar sözcüğünü kullanabilirsiniz `return` dönüş değerini temsil etmek için.  
  
```cpp  
  
_Success_(return != false) // Can also be stated as _Success_(return)  
bool GetValue(_Out_ int *pInt, bool flag)  
{  
   if(flag) {  
      *pInt = 5;  
      return true;  
   } else {  
      return false;  
   }  
}  
  
```  
  
 `_Out_` Ek açıklama çağıran bir arabellek için NULL olmayan işaretçi geçirir Visual Studio kod doğrulamak için çözümleme neden `pInt`, ve bunu döndürmeden önce arabellek işlevi tarafından başlatılır.  
  
## <a name="sal-best-practice"></a>SAL en iyi uygulama  
  
### <a name="adding-annotations-to-existing-code"></a>Ek açıklamalar için var olan kod ekleme  
 SAL, güvenlik ve güvenilirlik kodunuzun geliştirmenize yardımcı olabilir güçlü bir teknolojidir. SAL öğrendikten sonra yeni yetenek günlük iş uygulayabilirsiniz. Yeni kod içinde Tasarım SAL tabanlı özellikleri kullanabilirsiniz; eski kod içinde ek açıklama artımlı olarak ekleyin ve böylece güncelleştirdiğiniz her sefer avantajlarını artırmak.  
  
 Microsoft ortak üst bilgileri zaten açıklama eklendi. Bu nedenle, projelerinizde, önce yaprak düğümü işlevlerini ve çoğu elde etmek için Win32 API çağrısı işlevlerini ek açıklama olmasını öneririz.  
  
### <a name="when-do-i-annotate"></a>Ne zaman ı açıklama?  
 Bazı yönergeler şunlardır:  
  
-   Tüm işaretçi parametreleri açıklama.  
  
-   Böylece Kod Analizi arabellek ve işaretçi güvenliği sağlamak değer aralığı ek açıklamaları açıklama.  
  
-   Kilitleme kuralları ve kilitleme yan etkileri açıklama. Daha fazla bilgi için bkz: [kilitlenme davranışını yorumlama](../code-quality/annotating-locking-behavior.md).  
  
-   Sürücü özellikleri ve diğer etki alanına özgü özellikleri açıklama.  
  
 Veya, hedefi Temizle boyunca yapmak ve ek açıklamaları yapılmış denetlemek kolaylaştırmak için tüm parametreleri açıklama ekleyebilirsiniz.  
  
## <a name="related-resources"></a>İlgili Kaynaklar  
 [Kod çözümleme ekip blogu](http://go.microsoft.com/fwlink/p/?LinkId=251197)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ kod hatalarını azaltmak için SAL ek açıklamalarını kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [İşlev parametrelerini ve dönüş değerlerini açıklama](../code-quality/annotating-function-parameters-and-return-values.md)   
 [İşlev davranışını yorumlama](../code-quality/annotating-function-behavior.md)   
 [Yapıları ve sınıfları yorumlama](../code-quality/annotating-structs-and-classes.md)   
 [Kilitlenme davranışını yorumlama](../code-quality/annotating-locking-behavior.md)   
 [Açıklamanın ne zaman ve nereye uygulanacağını belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [En iyi yöntemler ve örnekler](../code-quality/best-practices-and-examples-sal.md)