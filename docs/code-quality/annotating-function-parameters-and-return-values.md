---
title: İşlev Parametrelerini ve Dönüş Değerlerini Açıklama
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- _Outptr_opt_result_bytebuffer_to_
- _Inout_updates_all_opt_
- _Post_equal_to_
- _Outptr_opt_result_maybenull_
- _Out_writes_bytes_all_
- _Out_writes_all_opt_
- _In_opt_
- _Outptr_
- _Outptr_result_maybenull_
- _Outref_result_bytebuffer_all_maybenull_
- _Inout_updates_opt_z_
- _Inout_updates_z_
- _Out_writes_
- _Out_writes_to_ptr_opt_z_
- _In_reads_to_ptr_opt_
- _Ret_writes_to_maybenull_
- _Outref_result_maybenull_
- _Ret_writes_bytes_
- _Outptr_result_bytebuffer_
- _Out_writes_opt_
- _Inout_updates_bytes_opt_
- _In_z_
- _Inout_updates_to_
- _Ret_maybenull_
- _Ret_writes_bytes_to_
- _Ret_z_
- _COM_Outptr_
- _Ret_maybenull_z_
- _Out_opt_
- _In_reads_opt_z_
- _Outptr_result_bytebuffer_to_
- _Ret_notnull_
- _COM_Outptr_opt_result_maybenull_
- _Inout_updates_to_opt_
- _Inout_updates_
- _Outptr_opt_result_buffer_
- _Outptr_result_buffer_to_
- _Out_writes_to_ptr_opt_
- _Out_writes_bytes_all_opt_
- _Inout_updates_all_
- _Deref_inout_range_
- _Ret_writes_
- _Out_writes_z_
- _Ret_writes_to_
- _Out_writes_to_ptr_z_
- _Out_writes_bytes_to_opt_
- _In_reads_or_z_
- _Inout_updates_bytes_to_
- _In_reads_z_
- _In_opt_z_
- _Outref_result_buffer_maybenull_
- _Ret_range_
- _COM_Outptr_opt_
- _Ouptr_opt_result_maybenull_z_
- _In_reads_opt_
- _Inout_
- _Field_range_
- _Ret_writes_z_
- _Out_writes_to_
- _Out_writes_to_ptr_
- _Inout_opt_z_
- _Outref_
- _Deref_out_range_
- _Outref_result_buffer_
- _Outref_result_buffer_to_
- _Outref_result_bytebuffer_to_maybenull_
- _In_reads_bytes_
- _Outptr_opt_result_buffer_to_
- _Outref_result_buffer_all_
- _Out_writes_bytes_to_
- _Result_zeroonfailure_
- _In_reads_bytes_opt_
- _Outref_result_buffer_to_maybenull_
- _Outref_result_bytebuffer_all_
- _Outref_result_buffer_all_maybenull_
- _Ret_writes_maybenull_z_
- _In_range_
- _Inout_updates_bytes_all_opt_
- _Outref_result_bytebuffer_to_
- _Inout_updates_bytes_to_opt_
- _Pre_equal_to_
- _Ret_writes_bytes_maybenull_
- _COM_Outptr_result_maybenull_
- _Ret_writes_maybenull_
- _Out_writes_bytes_
- _Outptr_opt_
- _Out_writes_opt_z_
- _Outref_result_nullonfailure_
- _Outptr_opt_result_z_
- _Inout_opt_
- _Deref_in_range_
- _Outptr_result_z_
- _In_reads_to_ptr_opt_z_
- _Struct_size_bytes_
- _Outptr_result_nullonfailure_
- _In_
- _Inout_updates_bytes_
- _In_reads_to_ptr_z_
- _Ret_writes_bytes_to_maybenull
- _Outptr_opt_result_nullonfailure_
- _In_reads_to_ptr_
- _Outptr_result_buffer_
- _Out_
- _Outref_result_bytebuffer_maybenull_
- _Outptr_result_maybenull_z_
- _In_reads_
- _Inout_updates_opt_
- _Out_writes_to_opt_
- _Outptr_opt_result_bytebuffer_
- _Out_writes_all_
- _Out_range_
- _Inout_updates_bytes_all_
- _Inout_z_
- _Outref_result_bytebuffer_
- _Result_nullonfailure_
- _Ret_null_
ms.assetid: 82826a3d-0c81-421c-8ffe-4072555dca3a
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: a06a987dc94ac4f3eb71d047ba33d410d7391a91
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="annotating-function-parameters-and-return-values"></a>İşlev Parametrelerini ve Dönüş Değerlerini Açıklama
Bu makalede tipik ek açıklamaları kullanımları basit işlev parametreleri — skalerler ve yapılar ve sınıflar işaretçileri — ve çoğu arabellek.  Bu makalede ayrıca ek açıklamalar için ortak kullanım desenlerini gösterilmektedir. İşlevler ilişkili ek açıklama için bkz: [işlev davranışını yorumlama](../code-quality/annotating-function-behavior.md)

## <a name="pointer-parameters"></a>İşaretçi parametreleri
 İşaretçi parametresi açıklama, aşağıdaki tablodaki ek açıklamalar için işaretçi null ise Çözümleyicisi bir hata bildirir.  Bu işaretçileri ve için işaret herhangi bir veri öğesini geçerlidir.

 **Ek açıklamalar ve açıklamaları**

-   `_In_`

     Skalerler, yapıları, yapıları işaretçiler ve benzeri giriş parametreleri açıklama ekler.  Açıkça basit skalerler üzerinde kullanılabilir.  Parametre öncesi durumunda geçerli olması gerekir ve değiştirilmeyecek.

-   `_Out_`

     Skalerler, yapıları, yapıları işaretçiler ve benzeri çıkış parametreleri açıklama ekler.  Bu değer döndüremez bir nesne için geçerli değildir — Örneğin, değeri tarafından geçirilen bir skaler.  Parametre öncesi durumunda geçerli olması gerekmez, ancak sonrası durumunda geçerli olması gerekir.

-   `_Inout_`

     İşlev tarafından değiştirilen bir parametre açıklama ekler.  Hem ön durumu hem de sonrası durumu geçerli olmalı, ancak önce ve sonra aramayı farklı değerlere sahip olduğu varsayılır. Değiştirilebilir bir değere uygulamanız gerekir.

-   `_In_z_`

     Giriş olarak kullanılan null ile sonlandırılmış bir dize için bir işaretçi.  Dize öncesi durumda geçerli olmalıdır.  Türevleri `PSTR`, hangi zaten doğru ek açıklamalarına sahip, tercih edilir.

-   `_Inout_z_`

     Değiştirilecek bir null olarak sonlandırılan bir karakter dizisi için bir işaretçi.  Bunu önce ve çağrısından sonra geçerli olmalıdır, ancak değer değiştirilmiş kabul edilir.  Null Sonlandırıcı taşınmış olabilir, ancak yalnızca özgün null Sonlandırıcı kadar öğeleri erişilebilir.

-   `_In_reads_(s)`

     `_In_reads_bytes_(s)`

     Bir işaretçi bir dizi işlev tarafından okunur.  Dizi boyutudur `s` öğeleri, her biri olmalıdır geçerli.

     `_bytes_` Değişken öğeleri yerine bayt cinsinden boyutu sağlar. Yalnızca boyutu öğeleri olarak ifade edilemeyecek bunu kullanın.  Örneğin, `char` dizeleri kullandığınız `_bytes_` yalnızca bir benzer, çalışmazsa varyantı kullanır `wchar_t` gerekir.

-   `_In_reads_z_(s)`

     Sonlandırılmış ve bilinen bir boyuta sahip bir dizi için bir işaretçi. Öğeler null Sonlandırıcı kadar — veya `s` null Sonlandırıcı ise — öncesi durumunda geçerli olması gerekir.  Bayt cinsinden boyutu biliniyorsa ölçeklendirme `s` öğesi boyutuna göre.

-   `_In_reads_or_z_(s)`

     Bilinen bir boyut veya her ikisi de null ile sonlandırılmış olduğundan veya bir dizi için bir işaretçi. Öğeler null Sonlandırıcı kadar — veya `s` null Sonlandırıcı ise — öncesi durumunda geçerli olması gerekir.  Bayt cinsinden boyutu biliniyorsa ölçeklendirme `s` öğesi boyutuna göre.  (İçin kullanılan `strn` ailesi.)

-   `_Out_writes_(s)`

     `_Out_writes_bytes_(s)`

     Bir dizi için bir işaretçi `s` işlevi tarafından yazılmış öğeler (Sorum bayt cinsinden).  Dizi öğeleri öncesi durumunda geçerli olması gerekmez ve sonrası durumunda geçerli olan öğe sayısı belirtilmedi.  Parametre türü hakkında ek açıklamalar varsa, bunlar sonrası durumunda uygulanır. Örneğin, aşağıdaki kodu göz önünde bulundurun.

     `typedef _Null_terminated_ wchar_t *PWSTR; void MyStringCopy(_Out_writes_ (size) PWSTR p1,    _In_ size_t size,    _In_ PWSTR p2);`

     Bu örnekte, çağıran bir arabellek sağlar `size` için öğeleri `p1`.  `MyStringCopy` Bu öğelerin bazıları geçerli hale getirir. Daha da önemlisi, `_Null_terminated_` ek açıklamayı `PWSTR` anlamına `p1` sonrası null ile sonlandırılmış durumda.  Bu şekilde, geçerli öğe sayısını hala iyi tanımlanmış, ancak belirli öğe sayısını gerekli değildir.

     `_bytes_` Değişken öğeleri yerine bayt cinsinden boyutu sağlar. Yalnızca boyutu öğeleri olarak ifade edilemeyecek bunu kullanın.  Örneğin, `char` dizeleri kullandığınız `_bytes_` yalnızca bir benzer, çalışmazsa varyantı kullanır `wchar_t` gerekir.

-   `_Out_writes_z_(s)`

     Bir dizi için bir işaretçi `s` öğeleri.  Öğeleri öncesi durumunda geçerli olması gerekmez.  Sonrası durumda null Sonlandırıcı aracılığıyla öğeleri — hangi bulunmalıdır — geçerli olmalıdır.  Bayt cinsinden boyutu biliniyorsa ölçeklendirme `s` öğesi boyutuna göre.

-   `_Inout_updates_(s)`

     `_Inout_updates_bytes_(s)`

     Hem okunur ve işlevinde yazılan bir dizi için bir işaretçi.  Boyutu olan `s` öğeleri ve öncesi durumu ve sonrası durumu geçerli.

     `_bytes_` Değişken öğeleri yerine bayt cinsinden boyutu sağlar. Yalnızca boyutu öğeleri olarak ifade edilemeyecek bunu kullanın.  Örneğin, `char` dizeleri kullandığınız `_bytes_` yalnızca bir benzer, çalışmazsa varyantı kullanır `wchar_t` gerekir.

-   `_Inout_updates_z_(s)`

     Sonlandırılmış ve bilinen bir boyuta sahip bir dizi için bir işaretçi. Öğeleri null Sonlandırıcı aracılığıyla — hangi bulunmalıdır — hem ön durumu hem de sonrası durumu geçerli olmalıdır.  Değerin sonrası durumda öncesi durumda değerinden farklı olduğu kabul edilir; Bu null Sonlandırıcı konumunu içerir. Bayt cinsinden boyutu biliniyorsa ölçeklendirme `s` öğesi boyutuna göre.

-   `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     Bir dizi için bir işaretçi `s` öğeleri.  Öğeleri öncesi durumunda geçerli olması gerekmez.  Sonrası durumdaki yukarı öğelerine `c`- th öğesi geçerli olmalıdır.  Bayt cinsinden boyutu biliniyorsa ölçeklendirme `s` ve `c` öğesi boyutu ya da kullanım `_bytes_` olarak tanımlanan değişken:

     `_Out_writes_to_(_Old_(s), _Old_(s))    _Out_writes_bytes_to_(_Old_(s), _Old_(s))`

     Diğer bir deyişle, arabellekteki kadar var. her öğenin `s` öncesi ve sonrası durumundaki geçerli durumda.  Örneğin:

     `void *memcpy(_Out_writes_bytes_all_(s) char *p1,    _In_reads_bytes_(s) char *p2,    _In_ int s); void * wordcpy(_Out_writes_all_(s) DWORD *p1,     _In_reads_(s) DWORD *p2,    _In_ int s);`

-   `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     Hem okunur ve işlev tarafından yazılmış bir dizi için bir işaretçi.  Boyutu olan `s` öğeleri, her biri olmalıdır geçerli öncesi durumunda, ve `c` öğeleri olmalıdır geçerli sonrası durumda.

     `_bytes_` Değişken öğeleri yerine bayt cinsinden boyutu sağlar. Yalnızca boyutu öğeleri olarak ifade edilemeyecek bunu kullanın.  Örneğin, `char` dizeleri kullandığınız `_bytes_` yalnızca bir benzer, çalışmazsa varyantı kullanır `wchar_t` gerekir.

-   `_Inout_updates_z_(s)`

     Sonlandırılmış ve bilinen bir boyuta sahip bir dizi için bir işaretçi. Öğeleri null Sonlandırıcı aracılığıyla — hangi bulunmalıdır — hem ön durumu hem de sonrası durumu geçerli olmalıdır.  Değerin sonrası durumda öncesi durumda değerinden farklı olduğu kabul edilir; Bu null Sonlandırıcı konumunu içerir. Bayt cinsinden boyutu biliniyorsa ölçeklendirme `s` öğesi boyutuna göre.

-   `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     Bir dizi için bir işaretçi `s` öğeleri.  Öğeleri öncesi durumunda geçerli olması gerekmez.  Sonrası durumdaki yukarı öğelerine `c`- th öğesi geçerli olmalıdır.  Bayt cinsinden boyutu biliniyorsa ölçeklendirme `s` ve `c` öğesi boyutu ya da kullanım `_bytes_` olarak tanımlanan değişken:

     `_Out_writes_to_(_Old_(s), _Old_(s))    _Out_writes_bytes_to_(_Old_(s), _Old_(s))`

     Diğer bir deyişle, arabellekteki kadar var. her öğenin `s` öncesi ve sonrası durumundaki geçerli durumda.  Örneğin:

     `void *memcpy(_Out_writes_bytes_all_(s) char *p1,    _In_reads_bytes_(s) char *p2,    _In_ int s); void * wordcpy(_Out_writes_all_(s) DWORD *p1,     _In_reads_(s) DWORD *p2,    _In_ int s);`

-   `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     Hem okunur ve işlev tarafından yazılmış bir dizi için bir işaretçi.  Boyutu olan `s` öğeleri, her biri olmalıdır geçerli öncesi durumunda, ve `c` öğeleri olmalıdır geçerli sonrası durumda.

     `_bytes_` Değişken öğeleri yerine bayt cinsinden boyutu sağlar. Yalnızca boyutu öğeleri olarak ifade edilemeyecek bunu kullanın.  Örneğin, `char` dizeleri kullandığınız `_bytes_` yalnızca bir benzer, çalışmazsa varyantı kullanır `wchar_t` gerekir.

-   `_Inout_updates_all_(s)`

     `_Inout_updates_bytes_all_(s)`

     Hem okunur ve boyutu işlevi tarafından yazılmış bir dizi için bir işaretçi `s` öğeleri. Eşdeğer olarak tanımlanan:

     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`

     Diğer bir deyişle, arabellekteki kadar var. her öğenin `s` öncesi öncesi durumuna ve sonrası durumu geçerli bir durumda.

     `_bytes_` Değişken öğeleri yerine bayt cinsinden boyutu sağlar. Yalnızca boyutu öğeleri olarak ifade edilemeyecek bunu kullanın.  Örneğin, `char` dizeleri kullandığınız `_bytes_` yalnızca bir benzer, çalışmazsa varyantı kullanır `wchar_t` gerekir.

-   `_In_reads_to_ptr_(p)`

     Kendisi için bir dizi için bir işaretçi ifade `p`  -  `_Curr_` (diğer bir deyişle, `p` eksi `_Curr_`) standart uygun dili tarafından tanımlanır.  Öncesinde öğelerine `p` öncesi durumunda geçerli olması gerekir.

-   `_In_reads_to_ptr_z_(p)`

     Sonlandırılmış bir dizi kendisi için bir işaretçi ifade `p`  -  `_Curr_` (diğer bir deyişle, `p` eksi `_Curr_`) standart uygun dili tarafından tanımlanır.  Öncesinde öğelerine `p` öncesi durumunda geçerli olması gerekir.

-   `_Out_writes_to_ptr_(p)`

     Kendisi için bir dizi için bir işaretçi ifade `p`  -  `_Curr_` (diğer bir deyişle, `p` eksi `_Curr_`) standart uygun dili tarafından tanımlanır.  Öncesinde öğelerine `p` öncesi durumunda geçerli olması gerekmez ve sonrası durumunda geçerli olması gerekir.

-   `_Out_writes_to_ptr_z_(p)`

     Sonlandırılmış bir dizi kendisi için bir işaretçi ifade `p`  -  `_Curr_` (diğer bir deyişle, `p` eksi `_Curr_`) standart uygun dili tarafından tanımlanır.  Öncesinde öğelerine `p` öncesi durumunda geçerli olması gerekmez ve sonrası durumunda geçerli olması gerekir.

## <a name="optional-pointer-parameters"></a>İsteğe bağlı işaretçisi parametreleri
 Ne zaman bir işaretçi parametresi ek açıklama içerir `_opt_`, parametre null olabileceğini gösterir. Aksi durumda, ek açıklama içermeyen sürümüyle aynı gerçekleştirir `_opt_`. Bir listesi aşağıdadır `_opt_` işaretçi parametresi ek açıklamaları çeşitlemelerini:

||||
|-|-|-|
|`_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`|`_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`|`_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`|

## <a name="output-pointer-parameters"></a>Çıkış işaretçi parametreleri
 Çıkış işaretçi parametreleri null şahit parametresi ve işaret için konum belirsizliğini ortadan kaldırmak için özel gösterimi gerektirir.

 **Ek açıklamalar ve açıklamaları**

-   `_Outptr_`

     Parametresi null olamaz ve sonrası durumu işaret için konum null olamaz ve geçerli olmalıdır.

-   `_Outptr_opt_`

     Parametre null olabilir, ancak sonrası durumu işaret için konum null olamaz ve geçerli olmalıdır.

-   `_Outptr_result_maybenull_`

     Parametresi null olamaz ve sonrası durumda işaret için konumu null olabilir.

-   `_Outptr_opt_result_maybenull_`

     Parametre null olabilir ve sonrası durumda işaret için konumu null olabilir.

 Aşağıdaki tabloda, ek alt dizeler daha fazla ek açıklamanın anlamını nitelemek için ek açıklama adı eklenir.  Çeşitli alt dizeler olan `_z`, `_COM_`, `_buffer_`, `_bytebuffer_`, ve `_to_`.

> [!IMPORTANT]
>  Yorumlama arabirimi COM ise, bu açıklamalarının COM formu kullanın. COM ek açıklama herhangi bir tür arabirimi ile kullanmayın.

 **Ek açıklamalar ve açıklamaları**

-   `_Outptr_result_z_`

     `_Outptr_opt_result_z_`

     `_Outptr_result_maybenull_z_`

     `_Ouptr_opt_result_maybenull_z_`

     Döndürülen işaretçiyle `_Null_terminated_` ek açıklama.

-   `_COM_Outptr_`

     `_COM_Outptr_opt_`

     `_COM_Outptr_result_maybenull_`

     `_COM_Outptr_opt_result_maybenull_`

     Döndürülen işaretçi COM semantiği varsa ve bu nedenle taşıyan bir `_On_failure_` döndürülen işaretçisi null sonrası koşul.

-   `_Outptr_result_buffer_(s)`

     `_Outptr_result_bytebuffer_(s)`

     `_Outptr_opt_result_buffer_(s)`

     `_Outptr_opt_result_bytebuffer_(s)`

     Döndürülen işaretçinin işaret geçerli arabellek boyutunu `s` öğeleri veya bayt.

-   `_Outptr_result_buffer_to_(s, c)`

     `_Outptr_result_bytebuffer_to_(s, c)`

     `_Outptr_opt_result_buffer_to_(s,c)`

     `_Outptr_opt_result_bytebuffer_to_(s,c)`

     Döndürülen işaretçinin işaret arabellek boyutunu `s` öğeleri veya biri bayt ilk `c` geçerlidir.

 Belirli arabirimi kuralları çıkış parametreleri hatada nullified olduğunu varsayın.  COM kod dışında açıkça aşağıdaki tabloda formlarında tercih edilir.  COM kodu için önceki bölümde listelenen karşılık gelen COM formları kullanın.

 **Ek açıklamalar ve açıklamaları**

-   `_Result_nullonfailure_`

     Diğer ek açıklamaları değiştirir. Sonuç işlevi başarısız olursa null olarak ayarlanır.

-   `_Result_zeroonfailure_`

     Diğer ek açıklamaları değiştirir. İşlev başarısız olursa sonucu sıfır olarak ayarlanır.

-   `_Outptr_result_nullonfailure_`

     İşlev başarısız olursa döndürülen işaretçi işlevi başarılı olursa geçerli bir arabellek veya null işaret eder. Bu ek açıklama yönelik isteğe bağlı olmayan bir parametre değil.

-   `_Outptr_opt_result_nullonfailure_`

     İşlev başarısız olursa döndürülen işaretçi işlevi başarılı olursa geçerli bir arabellek veya null işaret eder. Bu ek açıklama için isteğe bağlı bir parametredir.

-   `_Outref_result_nullonfailure_`

     İşlev başarısız olursa döndürülen işaretçi işlevi başarılı olursa geçerli bir arabellek veya null işaret eder. Bu ek açıklama yönelik bir başvuru parametre değil.

## <a name="output-reference-parameters"></a>Çıkış başvuru parametreleri
 Bir ortak başvuru parametresi için çıkış parametreleri kullanılır.  Basit çıkış başvuru parametreleri için — örneğin, `int&`—`_Out_` doğru semantiği sağlar.  Ancak, ne zaman çıkış değerini bir işaretçidir — örneğin `int *&`— eşdeğer işaretçi ek açıklamaları ister `_Outptr_ int **` doğru semantiğini sağlaması gerekmez.  İşaretçi türleri için çıkış başvuru parametreleri semantiği yönelik olarak kısaca ifade etmek için bu bileşik ek açıklamaları kullanın:

 **Ek açıklamalar ve açıklamaları**

-   `_Outref_`

     Sonuç sonrası durumda geçerli olmalıdır ve null olamaz.

-   `_Outref_result_maybenull_`

     Sonuç sonrası durumunda geçerli olması gerekir, ancak sonrası durumda null olabilir.

-   `_Outref_result_buffer_(s)`

     Sonuç sonrası durumda geçerli olmalıdır ve null olamaz. Noktaları için geçerli arabellek boyutunu `s` öğeleri.

-   `_Outref_result_bytebuffer_(s)`

     Sonuç sonrası durumda geçerli olmalıdır ve null olamaz. Noktaları için geçerli arabellek boyutunu `s` bayt sayısı.

-   `_Outref_result_buffer_to_(s, c)`

     Sonuç sonrası durumda geçerli olmalıdır ve null olamaz. İşaret arabelleği için `s` biri öğeleri ilk `c` geçerlidir.

-   `_Outref_result_bytebuffer_to_(s, c)`

     Sonuç sonrası durumda geçerli olmalıdır ve null olamaz. İşaret arabelleği için `s` hangi baytını ilk `c` geçerlidir.

-   `_Outref_result_buffer_all_(s)`

     Sonuç sonrası durumda geçerli olmalıdır ve null olamaz. Noktaları için geçerli arabellek boyutunu `s` geçerli öğeleri.

-   `_Outref_result_bytebuffer_all_(s)`

     Sonuç sonrası durumda geçerli olmalıdır ve null olamaz. İşaret geçerli arabelleği `s` geçerli öğelerinin bayt.

-   `_Outref_result_buffer_maybenull_(s)`

     Sonuç sonrası durumunda geçerli olması gerekir, ancak sonrası durumda null olabilir. Noktaları için geçerli arabellek boyutunu `s` öğeleri.

-   `_Outref_result_bytebuffer_maybenull_(s)`

     Sonuç sonrası durumunda geçerli olması gerekir, ancak sonrası durumda null olabilir. Noktaları için geçerli arabellek boyutunu `s` bayt sayısı.

-   `_Outref_result_buffer_to_maybenull_(s, c)`

     Sonuç sonrası durumunda geçerli olması gerekir, ancak sonrası durumda null olabilir. İşaret arabelleği için `s` biri öğeleri ilk `c` geçerlidir.

-   `_Outref_result_bytebuffer_to_maybenull_(s,c)`

     Sonuç sonrası durumunda geçerli olması gerekir, ancak post durumda null olabilir. İşaret arabelleği için `s` hangi baytını ilk `c` geçerlidir.

-   `_Outref_result_buffer_all_maybenull_(s)`

     Sonuç sonrası durumunda geçerli olması gerekir, ancak post durumda null olabilir. Noktaları için geçerli arabellek boyutunu `s` geçerli öğeleri.

-   `_Outref_result_bytebuffer_all_maybenull_(s)`

     Sonuç sonrası durumunda geçerli olması gerekir, ancak post durumda null olabilir. İşaret geçerli arabelleği `s` geçerli öğelerinin bayt.

## <a name="return-values"></a>Dönüş Değerleri
 Bir işlevin dönüş değeri benzer bir `_Out_` parametresi ancak farklı de-reference düzeyinde ve sonucu işaretçisine kavramı göz önünde bulundurmanız gereken yok.  Aşağıdaki ek açıklamalar için dönüş değerini açıklamalı nesnesidir — bir skaler, yapı işaretçi ya da bir arabellek için bir işaretçi. Bu ek açıklamalar ilgili olarak aynı semantiklerine sahip `_Out_` ek açıklama.

|||
|-|-|
|`_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`|`_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`|

## <a name="other-common-annotations"></a>Ortak diğer ek açıklamaları
 **Ek açıklamalar ve açıklamaları**

-   `_In_range_(low, hi)`

     `_Out_range_(low, hi)`

     `_Ret_range_(low, hi)`

     `_Deref_in_range_(low, hi)`

     `_Deref_out_range_(low, hi)`

     `_Deref_inout_range_(low, hi)`

     `_Field_range_(low, hi)`

     Parametresi, alan veya sonuç gelen (dahil) aralığında olan `low` için `hi`.  Eşdeğer `_Satisfies_(_Curr_ >= low && _Curr_ <= hi)` uygun önceden durum veya sonrası durum koşul birlikte açıklamalı nesneye uygulanır.

    > [!IMPORTANT]
    >  "İçinde" ve "dış", semantiği adlarını içerse de `_In_` ve `_Out_` yapmak **değil** bu ek açıklamalar için geçerlidir.

-   `_Pre_equal_to_(expr)`

     `_Post_equal_to_(expr)`

     Ek açıklama değeri tam olduğundan `expr`.  Eşdeğer `_Satisfies_(_Curr_ == expr)` uygun önceden durum veya sonrası durum koşul birlikte açıklamalı nesneye uygulanır.

-   `_Struct_size_bytes_(size)`

     Bir yapı ya da sınıf bildirimi geçerlidir.  Bu tür geçerli bir nesne tarafından verilen bayt sayısı ile bildirilen türü büyük olabileceğini gösterir `size`.  Örneğin:

     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`

     Arabellek boyutunu bayt cinsinden parametresinin `pM` türü `MyStruct *` sonra olacak şekilde gerçekleştirilir:

     `min(pM->nSize, sizeof(MyStruct))`

## <a name="related-resources"></a>İlgili Kaynaklar
 [Kod çözümleme ekip blogu](http://go.microsoft.com/fwlink/?LinkId=251197)

## <a name="see-also"></a>Ayrıca Bkz.
 [C/C++ kod hatalarını azaltmak için SAL ek açıklamalarını kullanma](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md) [SAL anlama](../code-quality/understanding-sal.md) [işlev davranışını yorumlama](../code-quality/annotating-function-behavior.md) [yapıları ve sınıfları yorumlama](../code-quality/annotating-structs-and-classes.md) [ Kilitlenme davranışını yorumlama](../code-quality/annotating-locking-behavior.md) [açıklamanın ne zaman ve nereye uygulanacağını belirtme](../code-quality/specifying-when-and-where-an-annotation-applies.md) [iç işlevler](../code-quality/intrinsic-functions.md) [en iyi yöntemler ve örnekler](../code-quality/best-practices-and-examples-sal.md)