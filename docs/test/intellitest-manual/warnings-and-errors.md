---
title: "Uyarıları ve hataları | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliTest, Warnings and errors
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 77f47c2d18b43c3ab08dac5fec6281892072ab36
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="warnings-and-errors"></a>Uyarıları ve hataları

## <a name="warnings-and-errors-by-category"></a>Uyarıları ve hataları kategoriye göre

* **Sınırları**
  * [MaxBranches aşıldı](#maxbranches-exceeded)
  * [MaxConstraintSolverTime aşıldı](#maxconstraintsolvertime-exceeded)
  * [MaxConditions aşıldı](#maxconditions-exceeded)
  * [MaxCalls aşıldı](#maxcalls-exceeded)
  * [MaxStack aşıldı](#maxstack-exceeded)
  * [MaxRuns aşıldı](#maxruns-exceeded)
  * [MaxRunsWithoutNewTests aşıldı](#maxrunswithoutnewtests-exceeded)<p />

* **Kısıtlama çözme**
  * [Çözüm Concretize olamaz](#cannot-concretize-solution)<p />

* **Etki alanları**
  * [Nesnesi oluşturmak için Yardım gerekiyor](#help-construct)
  * [Türlerini bulmak için Yardım gerekiyor](#help-types)
  * [Tahmin edilen kullanılabilir türü](#usable-type-guessed)<p />

* **Yürütme**
  * [Keşif sırasında beklenmeyen hata](#unexpected-exploration)
  * [TargetInvocationException](#targetinvocationexception)<p />

* **İzleme**
  * [Adlı uninstrumented yöntemi](#uninstrumented-method-called)
  * [Adlı dış yöntemi](#external-method-called)
  * [Adlı uninstrumentable yöntemi](#uninstrumentable-method-called)
  * [Test Edilebilirlik sorunu](#testability-issue)
  * [Sınırlama](#limitation)<p />

* **Yorumlayıcı**
  * [Gözlemlenen çağrısı uyuşmazlığı](#observed-call-mismatch)
  * [Statik alanda depolanan değer](#value-static-field)

<a name="maxbranches-exceeded"></a>
## <a name="maxbranches-exceeded"></a>MaxBranches aşıldı

Intellitest sınırlar sırasında araştırır herhangi bir yürütme yol uzunluğu [giriş nesil](input-generation.md). Bu özellik Intellitest program sonsuz bir döngüde gittiğinde, yanıt veremez hale gelmesini engeller.

Her koşullu ve koşulsuz dal yürütülen ve izlenen kod girişler için dayanmayan dalları dahil olmak üzere bu sınır doğru sayılan [parametreli birim testi](test-generation.md#parameterized-unit-testing).

Örneğin, aşağıdaki kodu 100 sırasına göre dalları kullanır:

```
for (int i=0; i<100; i++) { }
```

Düzenleyebileceğiniz **MaxBranches** seçeneği bir özniteliğin türetilen **PexSettingsAttributeBase**, gibi [PexClass](attribute-glossary.md#pexclass) veya [PexMethod](attribute-glossary.md#pexmethod) . Aşağıdaki örnek, etkili bir şekilde bu bağlı kaldırır:

```
[PexMethod(MaxBranches=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

Ayrıca ayarlayabilirsiniz **TestExcludePathBoundsExceeded** Intellitest bu sorunlarının üstesinden gelmek için nasıl genellikle bildirmek için seçeneği.

Test kodda kullandığınız [PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue) döngü koşul tarafından oluşturulan kısıtlamaları yoksaymak için:

```
for (int i=0; 
    PexSymbolicValue.Ignore(i<100); // IntelliTest will 'forget' about this path condition
    i++) 
{ }
```

<a name="maxconstraintsolvertime-exceeded"></a>
## <a name="maxconstraintsolvertime-exceeded"></a>MaxConstraintSolverTime aşıldı

Intellitest kullanan bir [kısıtlaması Çözücü](input-generation.md#constraint-solver) yeni test girişleri hesaplamak için. Kısıtlaması çözme olabilir çok zaman alan bir işlem Intellitest sınırları - özellikle yapılandırmanıza izin verir şekilde **MaxConstraintSolverTime**.

Birçok uygulama için daha iyi kapsamı önemli ölçüde zaman aşımı süresinin artırılması oluşturmayacaktır. Bunun nedeni, çoğu zaman aşımları çözüm sahip kısıtlaması sistemleri tarafından hatalardır ' dir. Ancak, Intellitest, zaman aşımı neden olacak tüm olası çözümleri çalışmadan tutarsız olup olmadığını belirlemek mümkün olmayabilir.

<a name="maxconditions-exceeded"></a>
## <a name="maxconditions-exceeded"></a>MaxConditions aşıldı

Intellitest sınırlar sırasında araştırır herhangi bir yürütme yol uzunluğu [giriş nesil](input-generation.md). Bu özellik Intellitest program sonsuz bir döngüde girdiğinde, yanıt veremez hale gelmesini engeller.

Girişler için bağlıdır her koşullu dal [parametreli birim testi](test-generation.md#parameterized-unit-testing) bu sınırında sayılır.

Örneğin, aşağıdaki kodu her yolunda tüketir **n + 1** koşullar:

```
[PexMethod]
void ParameterizedTest(int n) {
    // conditions are "0<n", "1<n", ..., "!(n<n)"
    for (int i=0; i<n; i++)
    { ... }

    // irrelevant for MaxConditions, since conditions do not depend on input
    for (int i=0; i<100; i++) 
    { ... }
}
```

Düzenleyebileceğiniz **MaxConditions** seçeneği bir özniteliğin türetilen **PexSettingsAttributeBase**, gibi [PexClass](attribute-glossary.md#pexclass) veya [PexMethod](attribute-glossary.md#pexmethod). Örneğin:

```
[PexMethod(MaxConditions=10000)]
void ParameterizedTest(int n) {
    // ...
}
```

Ayrıca ayarlayabilirsiniz **TestExcludePathBoundsExceeded** genellikle bu sorunlarının üstesinden gelmek nasıl Intellitest bildirmek için seçeneği.

Kullanabileceğiniz [PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue) döngü koşul tarafından oluşturulan kısıtlamaları yoksaymak için:

```
[PexMethod]
void ParameterizedTest(int n) {
    int nshadow = PexSymbolicValue.Ignore(n); // IntelliTest looses track of 'n'

    // irrevelant for MaxConditions, since nshadow is not related to input
    for (int i=0; i<nshadow; i++)  
    {...}
}
```

<a name="maxcalls-exceeded"></a>
## <a name="maxcalls-exceeded"></a>MaxCalls aşıldı

Intellitest sınırlar sırasında araştırır herhangi bir yürütme yol uzunluğu [giriş nesil](input-generation.md). Bu özellik Intellitest program sonsuz bir döngüye girer gittiğinde, yanıt veremez hale gelmesini engeller.

Her çağrı (doğrudan, dolaylı, sanal veya atlama) yürütülen ve izlenen kodu bu sınırında sayılır.

Düzenleyebileceğiniz **MaxCalls** seçeneği bir özniteliğin türetilen **PexSettingsAttributeBase**, gibi [PexClass](attribute-glossary.md#pexclass) veya [PexMethod](attribute-glossary.md#pexmethod). Aşağıdaki örnek, etkili bir şekilde bu bağlı kaldırır:

```
[PexMethod(MaxCalls=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

Ayrıca ayarlayabilirsiniz **TestExcludePathBoundsExceeded** genellikle bu sorunlarının üstesinden gelmek nasıl Intellitest bildirmek için seçeneği.

<a name="maxstack-exceeded"></a>
## <a name="maxstack-exceeded"></a>MaxStack aşıldı

Intellitest sınırlar sırasında araştırır herhangi bir yürütme yol çağrı yığınını boyutunu [giriş nesil](input-generation.md). Bu özellik, bir yığın taşması oluştuğunda sonlandırma Intellitest önler.

Düzenleyebileceğiniz **MaxStack** seçeneği bir özniteliğin türetilen **PexSettingsAttributeBase**, gibi [PexClass](attribute-glossary.md#pexclass) veya [PexMethod](attribute-glossary.md#pexmethod). Aşağıdaki örnek, etkili bir şekilde (önerilmez) bu bağlı kaldırır:

```
[PexMethod(MaxStack=int.MaxValue)]
public void MyTest(...) {
    // ....
}
```

Ayrıca ayarlayabilirsiniz **TestExcludePathBoundsExceeded** genellikle bu sorunlarının üstesinden gelmek nasıl Intellitest bildirmek için seçeneği.

<a name="maxruns-exceeded"></a>
## <a name="maxruns-exceeded"></a>MaxRuns aşıldı

Intellitest sırasında araştırır yürütme yolları sayısını sınırlar [giriş nesil](input-generation.md). Bu özellik, döngüler veya özyineleme program sahip olduğunda Intellitest sonlandırır sağlar.

Intellitest parametreli test belirli girişle her çalıştığında, yeni bir test çalışması yayar, durumda olmayabilir. Bkz: [TestEmissionFilter](exploration-bounds.md#testemissionfilter) daha fazla bilgi için.

Düzenleyebileceğiniz **MaxRuns** seçeneği bir özniteliğin türetilen **PexSettingsAttributeBase**, gibi [PexClass](attribute-glossary.md#pexclass) veya [PexMethod](attribute-glossary.md#pexmethod). Aşağıdaki örnek, etkili bir şekilde (önerilmez) bu bağlı kaldırır:

```
[PexMethod(MaxRuns=2000)]
public void MyTest(...) {
    // ....
}
```

<a name="maxrunswithoutnewtests-exceeded"></a>
## <a name="maxrunswithoutnewtests-exceeded"></a>MaxRunsWithoutNewTests aşıldı

Intellitest sırasında araştırır yürütme yolları sayısını sınırlar [giriş nesil](input-generation.md). Bu özellik, döngüler veya özyineleme program sahip olduğunda Intellitest sonlandırır sağlar.

Intellitest parametreli test belirli girişle her çalıştığında, yeni bir test çalışması yayar, durumda olmayabilir. Bkz: [TestEmissionFilter](exploration-bounds.md#testemissionfilter) daha fazla bilgi için.

Başlangıçta, genellikle bulur birçok ilginç test girişleri Intellitest olsa da, bunu bir süre sonra - daha fazla tüm testleri yayma değil -. Bu seçenek, ne kadar süreyle Intellitest başka bir ilgili test giriş bulmak denemeye devam yönetir.

Düzenleyebileceğiniz **MaxRunsWithoutNewTests** seçeneği bir özniteliğin türetilen **PexSettingsAttributeBase**, gibi [PexClass](attribute-glossary.md#pexclass) veya [PexMethod](attribute-glossary.md#pexmethod). Aşağıdaki örnek, etkili bir şekilde (önerilmez) bu bağlı kaldırır:

```
[PexMethod(MaxRunsWithoutNewTests=2000)]
public void MyTest(...) {
    // ....
}
```

<a name="cannot-concretize-solution"></a>
## <a name="cannot-concretize-solution"></a>Çözüm concretize olamaz

Bu hata genellikle daha önceki bir hata sonucu olur. Intellitest kullanan bir [kısıtlaması Çözücü](input-generation.md#constraint-solver) yeni test girişleri belirlemek için. Bazı durumlarda, tarafından önerilen girişleri test [kısıtlaması Çözücü](input-generation.md#constraint-solver) geçersizdir. Bu durum ortaya çıkabilir zaman:

* bazı kısıtlamalar bilinmiyor
* hatalar kullanıcı kodunda oluşmasına neden olan bir kullanıcı tarafından tanımlanan şekilde değerleri oluşturduysanız
* Bazı ilgili türleri (örneğin, COM sınıfları) Intellitest tarafından denetlenmeyen başlatma mantığına sahip

<a name="help-construct"></a>
## <a name="need-help-to-construct-object"></a>Nesnesi oluşturmak için Yardım gerekiyor

Intellitest [test girişleri oluşturur](input-generation.md), ve bazı girdi nesneleri alanlara sahip olabilir. Burada, özel bir alana sahip bir sınıfının bir örneğini oluşturmak Intellitest çalışır ve bu özel alan belirli bir değere sahip olduğunda ilginç bir program davranış gerçekleşir varsayar. 

Ancak, bu yansıma ile mümkün olmakla birlikte, Intellitest nesneleri rasgele alan değerleriyle üretmez. Bunun yerine, bu durumda, genel yöntemler bir sınıfın bir nesnesi oluşturun ve kendi özel alan istenen değere sahip olduğu bir duruma getirmek için nasıl kullanılacağı konusunda ipuçları sağlayan kullanıcıya kullanır.

Okuma [varolan sınıflarını örnekleme](input-generation.md#existing-classes) ilginç nesneleri oluşturmak Intellitest nasıl yardımcı olabileceğini öğrenin. 

<a name="help-types"></a>
## <a name="need-help-to-find-types"></a>Türlerini bulmak için Yardım gerekiyor

Intellitest [test girişleri oluşturur](input-generation.md) için herhangi bir .NET türü. Burada, Intellitest bir soyut sınıftan türeyen ya da bir Özet arabirimini uygulayan bir örneği oluşturmayı dener ve Intellitest kısıtlamaları karşılayan herhangi bir türde bilmez. 

Kısıtlamalarla eşleşen bir veya daha fazla türlerine göstererek Intellitest yardımcı olabilir. Genellikle, aşağıdaki öznitelikler birini yardımcı olur:

* **PexUseTypeAttribute**, belirli bir türe işaret eder.

  Örneğin, BT Intellitest raporları, "tüm türleri için atanabilir bilmez **System.Collections.IDictionary**", aşağıdaki ekleyerek yardımcı olabilir **PexUseTypeAttribute** test (veya donanımı sınıfı için):

  ```
  [PexMethod]
  [PexUseType(typeof(System.Collections.Hashtable))]
  public void MyTest(IDictionary[] dictionaries) { ... }
  ```

* **Bir derleme düzeyi özniteliği**

  ```
  [assembly: PexUseType(typeof(System.Collections.Hashtable))]
  ```

<a name="usable-type-guessed"></a>
## <a name="usable-type-guessed"></a>Tahmin edilen kullanılabilir türü

Intellitest [test girişleri oluşturur](input-generation.md) tüm .NET türleri için. Bir tür soyut veya arabirim olduğunda Intellitest türü belirli bir uygulama seçmeniz gerekir. Bu seçim yapmak için hangi tür mevcut bilmesi gerekir. 

Bu uyarı gösterildiğinde BT Intellitest başvurulan derlemelerin bazıları arama ve bir uygulama türü, ancak bulunan indiicates yazın ya da varsa daha uygun kullanılabilir türleri başka bir yerde kullanması gereken olup olmadığından emin değil. Intellitest yalnızca taahhüdü aranan bir türünü seçin.

Bu uyarı önlemek için Intellitest'ın türü seçimi kabul veya karşılık gelen ekleyerek diğer türleri kullanarak Intellitest yardımcı [PexUseType](attribute-glossary.md#pexusetype).

<a name="unexpected-exploration"></a>
## <a name="unexpected-failure-during-exploration"></a>Keşif sırasında beklenmeyen hata

Bir test keşfetme çalışırken beklenmeyen bir özel durum yakalandı.

Lütfen [bu bir hata rapor](#report-bug).

<a name="targetinvocationexception"></a>
## <a name="targetinvocationexception"></a>TargetInvocationException

Kullanıcı kodu özel durum oluştu. Yığın izleme inceleyin ve hatayı kodunuzda kaldırın.

<a name="uninstrumented-method-called"></a>
## <a name="uninstrumented-method-called"></a>Adlı uninstrumented yöntemi

Intellitest [test girişleri oluşturur](input-generation.md) program yürütme izleme tarafından. Böylece Intellitest davranışını izleyebilirsiniz ilgili kodu düzgün izlenmiş olan gereklidir.

İzleme eklenmiş kodu başka uninstrumented derlemede yöntemlerini çağırdığında bu uyarı görüntülenir. Her ikisi de etkileşimini keşfetmek için Intellitest istiyorsanız, diğer derleme (veya bazı bölümleri) işaretlemesini gerekir.

<a name="external-method-called"></a>
## <a name="external-method-called"></a>Adlı dış yöntemi

Intellitest [test girişleri oluşturur](input-generation.md) yürütme .NET uygulama izleme tarafından. Intellitest bir .NET dilinde yazılmaz kodu için anlamlı test girişleri oluşturulamıyor.

İzleme eklenmiş kodu Intellitest analiz edilemez bir yönetilmeyen, yerel yöntemi çağırdığında bu uyarı görüntülenir. Her ikisi de etkileşimini keşfetmek için Intellitest istiyorsanız, yönetilmeyen yöntemi mock gerekir.

<a name="uninstrumentable-method-called"></a>
## <a name="uninstrumentable-method-called"></a>Adlı uninstrumentable yöntemi

Intellitest [test girişleri oluşturur](input-generation.md) yürütme .NET uygulama izleme tarafından. Ancak, teknik nedenlerle Intellitest izleyemez, bazı yöntemler vardır. Örneğin, Intellitest statik Oluşturucu izleyemez.

İzleme eklenmiş kodu Intellitest izleyemez bir yöntem çağırdığında bu uyarı görüntülenir. 

<a name="testability-issue"></a>
## <a name="testability-issue"></a>Test Edilebilirlik sorunu

Intellitest [test girişleri oluşturur](input-generation.md) program yürütme izleme tarafından. Program belirleyici olduğunda ve ilgili davranışı test girişleri tarafından denetlenir ilgili test girişleri yalnızca oluşturabilirsiniz.

Test çalışması yürütme sırasında bir yöntem çağrıldı olduğundan ya da belirleyici olmayan şekilde davranır veya ortamı ile etkileşim bu uyarı görüntülenir. Örnekler yöntemlerini **System.Random** ve **System.IO.File**. Intellitest anlamlı test girişleri oluşturmak istiyorsanız, sınanabilirlik sorunlar Intellitest bayrakları yöntemleri mock gerekir.

<a name="limitation"></a>
## <a name="limitation"></a>Sınırlama

Intellitest [test girişleri oluşturur](input-generation.md) kullanarak bir [kısıtlaması Çözücü](input-generation.md#constraint-solver).
Ancak, kapsamı dışındaki bazı işlemler vardır [kısıtlaması Çözücü](input-generation.md#constraint-solver).
Şu anda bu içerir:

* (yalnızca bazı doğrusal aritmetik kayan nokta numarası desteklenir) en kayan nokta işlemleri
* kayan nokta sayıları ve tamsayılar arasında dönüştürme
* tüm işlemler **System.Decimal** türü

Yürütülen kod Intellitest yorumlanamıyor bir yöntemi çağırır veya bir işlem gerçekleştirir bu uyarı görüntülenir. 

<a name="observed-call-mismatch"></a>
## <a name="observed-call-mismatch"></a>Gözlemlenen çağrısı uyuşmazlığı

Intellitest [test girişleri oluşturur](input-generation.md) program yürütme izleme tarafından. Ancak, Intellitest tüm yönergeleri izlemek mümkün olmayabilir. Örneğin, yerel kod izleyemez ve değil izlenmiş olan kod izleyemez.

Intellitest kod izleyemez olduğunda, bu kodu için uygun olan test girişleri oluşturulamıyor.
Genellikle, Intellitest bu yöntem çağrısı kadar bir yöntem izleyemez olgu uyumlu değil. Ancak, bu uyarı nedeni:

* Intellitest uninstrumented yöntemine yapılan bir çağrı tarafından başlatılan biraz kod izlenen
* İzlenmiş olan bir yöntem olarak adlandırılan uninstrumented yöntemi
* Intellitest çağrıldı belgelenmiş yöntemini izler 

İç içe geçmiş Araçlı çağrısı ilgili test girişleri oluşturmak mümkün olmayabilir şekilde Intellitest uninstrumented Ara yöntemi ne yaptığını, bilmez.

<a name="value-static-field"></a>
## <a name="value-stored-in-static-field"></a>Statik alanda depolanan değer

Intellitest sistematik olarak belirleyebilir [ilgili test girişleri](input-generation.md) yalnızca zaman birim testi belirleyici; diğer bir deyişle, her zaman aynı test girişleri için aynı şekilde davranır. Özellikle, bu test test yeniden yürütmek için izin veren bir durumda sistem bırakmalısınız anlamına gelir.
İdeal olarak, birim testi herhangi bir genel durum değiştirmemeniz gerekir, ancak tüm etkileşim globals mocked.

Bu uyarı, statik bir alana değiştirildiğini gösterir; Bu, belirleyici olmayan biçimde davranır test yapabilir.

Bazı durumlarda, statik bir alana değiştirme kabul edilebilir:

* test girişleri değişikliği geri almak Kurulum veya temizleme kod zaman neden olur
* ne zaman alan yalnızca bir kez başlatılan ve değer daha sonra değişmez

<a name="report-bug"></a>

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
