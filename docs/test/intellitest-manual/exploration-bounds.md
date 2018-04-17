---
title: Keşif sınırları | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Exploration bounds
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: f152f128fed04abee44ca8c57c89b9f1c2f12ae6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="exploration-bounds"></a>Keşif sınırları

**PexSettingsAttributeBase** ayarları sınırlarının nitelikleri için Özet temel sınıf. Bkz: [ayarları Waterfall](settings-waterfall.md) Intellitest ayarlarında genel bakış.

Bu ve türetilen özniteliklerini özelliklerini adlandırılmış kullanarak ayarları değiştirebilirsiniz:

```
[PexClass(MaxRuns = 10)]
public partial class FooTest {...}
```

* **Sınırların çözme kısıtlaması**
  * [MaxConstraintSolverTime](#maxconstraintsolvertime) -saniye sayısını [kısıtlaması Çözücü](input-generation.md#constraint-solver) izlenmesi yeni ve farklı yürütme yolu neden olacak girişleri bulmak vardır.
  * [MaxConstraintSolverMemory](#maxconstraintsolvermemory) -boyutunu megabayt cinsinden, [kısıtlaması Çözücü](input-generation.md#constraint-solver) girişleri bulmak için kullanabilirsiniz.<p />
* **Keşif yol sınırları**
  * [MaxBranches](#maxbranches) -tek yürütme yol boyunca izlenebilir dalları maksimum sayısı.
  * [MaxCalls](#maxcalls) -en fazla tek yürütme yolu sırasında yapılan çağrı sayısı.
  * [MaxStack](#maxstack) -yığın tek yürütme yolu sırasında her zaman en büyük boyutunu etkin çağrı çerçeve sayısı ölçülür.
  * [MaxConditions](#maxconditions) -tek yürütme yolu sırasında denetlenebilir girişleri üzerinden koşullar sayısı.<p />
* **Keşif sınırları**
  * [MaxRuns](#maxruns) -en fazla incelenmesi sırasında denenecek çalıştırır.
  * [MaxRunsWithoutNewTests](#maxrunswithoutnewtests) -sayısının gösterilmesini yeni bir test olmadan ardışık çalıştırır.
  * [MaxRunsWithUniquePaths](#maxrunswithuniquepaths) -en fazla incelenmesi sırasında denenecek benzersiz yürütme yollar ile çalışır.
  * [MaxExceptions](#maxexceptions) -tüm bulunan yürütme yollar bileşimi için bulunabilir özel durum sayısı.<p />
* **Test paketi kod oluşturma ayarları**
  * [TestExcludePathBoundsExceeded](#testexcludepathboundsexceeded) -olduğunda true, herhangi bir yol sınırlarının aşan yürütme yol ([MaxCalls](#maxcalls), [MaxBranches](#maxbranches), [MaxStack](#maxstack), [ MaxConditions](#maxconditions)) göz ardı edilir.
  * [TestEmissionFilter](#testemissionfilter) -hangi koşullar altında Intellitest testleri yayma gösterir.
  * [TestEmissionBranchHits](#testemissionbranchhits) -Intellitest yayar kaç testin denetler.

<a name="maxconstraintsolvertime"></a>
## <a name="maxconstraintsolvertime"></a>MaxConstraintSolverTime

Saniye sayısını [kısıtlaması Çözücü](input-generation.md#constraint-solver) ulaşmak yeni ve farklı yürütme yolu neden olacak girişleri hesaplamak vardır. Bu bir seçenektir, **PexSettingsAttributeBase** ve türetilmiş türler.

Daha derin bu Intellitest bir program yürütme yollarını inceler, daha karmaşık hale Intellitest akış denetimi ve veri akış programının derlemeler kısıtlaması sistemleri. Zaman sınırlaması bağlı olarak zaman bulan yeni yürütme yollar fazla veya az yapılacak Intellitest izin vermek için bu değeri ayarlayabilirsiniz.

Genellikle, bir zaman aşımı Intellitest bir çözüm yok. kısıtlama sistem için bir çözüm bulmak çalışıyor, ancak bu durum farkında değildir nedeni. Bunun en yaygın bir zaman aşımı için geçerli olduğundan, bu sınırı artırmak için anlamı olmayabilir.

<a name="maxconstraintsolvermemory"></a>
## <a name="maxconstraintsolvermemory"></a>MaxConstraintSolverMemory

Megabayt sayısı, [kısıtlaması Çözücü](input-generation.md#constraint-solver) ulaşmak yeni ve farklı yürütme yolu neden olacak girişleri hesaplamak vardır. Bu bir seçenektir, **PexSettingsAttributeBase** ve türetilmiş türler.

Daha derin Intellitest Intellitest akış denetimi ve veri akış programının derlemeler kısıtlaması sistemleri hale daha karmaşık bir program yürütme yollarını araştırır. Kullanılabilir bellek bilgisayarınızı bağlı olarak, daha karmaşık kısıtlaması sistemleri üstesinden gelmek Intellitest izin vermek için bu değer ayarlayabilirsiniz.

Genellikle, bir zaman aşımı Intellitest bir çözüm yok. kısıtlama sistem için bir çözüm bulmak çalışıyor, ancak bu durum farkında değildir nedeni. Bellek durumunun en yaygın neden olacağından, bu sınırı artırmak için anlamı olmayabilir.

<a name="maxbranches"></a>
## <a name="maxbranches"></a>MaxBranches

Tek Yürütme yol boyunca izlenebilir dalları maksimum sayısı.

Bağlı bu araştırması arkasında motivasyon sırasında Intellitest araştırır herhangi bir yürütme yol uzunluğu sınırlandırmaktır [giriş nesil](input-generation.md). Özellikle, programın sonsuz bir döngüde kalırsa yanıt veremez hale gelmesini Intellitest engeller.

Her koşullu ve koşulsuz dal yürütülen ve izlenen kod parametreli test girişler için dayanmayan dalları dahil olmak üzere bu sınır doğru sayılır.

Örneğin, aşağıdaki kodu 100 siparişi dallarda kullanır:

```
for (int i=0; i<100; i++) { }
```

<a name="maxcalls"></a>
## <a name="maxcalls"></a>MaxCalls

Tek yürütme yolu sırasında yapılan çağrı maksimum sayısı.

Bağlı bu araştırması arkasında motivasyon sırasında Intellitest araştırır herhangi bir yürütme yol uzunluğu sınırlandırmaktır [giriş nesil](input-generation.md). Özellikle, program Intellitest kurtaramazsınız bir yığın taşması neden olacağından kez sonsuz sayıda yöntemi yinelemeli olarak çağırırsa yanıt veremez hale gelmesini Intellitest engeller.

Yürütülen ve izlenen kod her çağrı (doğrudan, dolaylı, sanal, atlama) bu sınırında sayılır.

<a name="maxstack"></a>
## <a name="maxstack"></a>MaxStack

Yığın etkin çağrı çerçeveleri tarafından ölçülen bir tek yürütme yolu sırasında her zaman en büyük boyutu.

Bağlı bu araştırması arkasında amacı sırasında Intellitest araştırır herhangi bir yürütme yol yığın boyutu sınırı etmektir [giriş nesil](input-generation.md). Özellikle, Intellitest kurtaramazsınız bir yığın taşması neden olacağından tüm kullanılabilir yığın alanı kullanarak Intellitest engeller.

<a name="maxconditions"></a>
## <a name="maxconditions"></a>MaxConditions

Koşullar tek yürütme yolu sırasında denetlenebilir girişleri üzerinden emaximum sayısı.

Bağlı bu araştırması arkasında motivasyon sırasında Intellitest araştırır herhangi bir yürütme yol karmaşıklığını sınırlandırmaktır [giriş nesil](input-generation.md). Parametreli test girişler için bağlıdır her koşullu dal bu sınırında sayılır.

Örneğin, aşağıdaki kodu her yolunda n + 1 koşullar kullanır:

```
[PexMethod]
void ParameterizedTest(int n) 
{
     for (int i=0; i<n; i++) { // conditions are "0<n", "1<n", ..., "!(n<n)"
          ...
     }
     for (int i=0; i<100; i++) { // irrelevant for MaxConditions, since conditions do not depend on input
          ...
     }
}
```

<a name="maxruns"></a>
## <a name="maxruns"></a>MaxRuns

Bir test keşfi sırasında Intellitest deneyecek çalıştırmalarının TH emaximum sayısı.

Döngüler veya özyineleme içeren herhangi bir kod yürütme yolları sonsuz sayıda olabilir ve bu nedenle Intellitest sırasında sınırlı olması gerekiyor motivasyon bağlı bu araştırması arkasında olan [giriş nesil](input-generation.md). 

İki ayar **MaxRuns** ve **MaxRunsWithUniquePaths** gibi ilgili: 

* Intellitest çağıracaktır parametreli test yöntemi kadar **MaxRuns** süreleri farklı bir test girişleri ile.
* Yürütülen kod belirleyici ise, Intellitest farklı yürütme yolu her zaman alır. 
  Ancak, bazı koşullarda yürütülen kod izleyin ve bu da, daha önce farklı girişle denetlendiği bir yürütme yolu. 
* Intellitest bulduğu kaç tane benzersiz yürütme yolları sayar; Bu sayı sınırlıdır **MaxRunsWithUniquePaths** seçeneği.

<a name="maxrunswithoutnewtests"></a>
## <a name="maxrunswithoutnewtests"></a>MaxRunsWithoutNewTests

Üst sınırını gösterilmesini yeni bir test olmadan ardışık çalıştırır.

Intellitest genellikle birçok ilginç test girişleri kısa bir süre içinde bulabilirsiniz, ancak bir süre sonra dosyayı daha yeni girişleri test ve daha fazla birim testleri yayma bulamaz. Bu yapılandırma seçeneği bağımlı Intellitest yeni bir test yayma olmadan gerçekleştirebilir ardışık girişimlerine yerleştirir. Erişildiğinde, araştırması durdurulur. 

<a name="maxrunswithuniquepaths"></a>
## <a name="maxrunswithuniquepaths"></a>MaxRunsWithUniquePaths

Bir keşif sırasında Intellitest değerlendirir benzersiz yolları maksimum sayısı.

Döngüler veya özyineleme içeren herhangi bir kod yürütme yolları sonsuz sayıda olabilir ve bu nedenle Intellitest olmalıdır sırasında sınırlı motivasyon bağlı bu araştırması arkasında olan [giriş nesil](input-generation.md).

İki ayar **MaxRuns** ve **MaxRunsWithUniquePaths** gibi ilgili: 

* Intellitest çağıracaktır parametreli test yöntemi kadar **MaxRuns** süreleri farklı bir test girişleri ile.
* Yürütülen kod belirleyici ise, Intellitest farklı yürütme yolu her zaman alır. 
  Ancak, bazı koşullarda yürütülen kod izleyin ve bu da, daha önce farklı girişle denetlendiği bir yürütme yolu. 
* Intellitest bulduğu kaç tane benzersiz yürütme yolları sayar; Bu sayı sınırlıdır **MaxRunsWithUniquePaths** seçeneği.

<a name="maxexceptions"></a>
## <a name="maxexceptions"></a>MaxExceptions

Keşif durdurulamaz önce karşılaşılabilir özel durumlar maksimum sayısı.

Bağlı bu araştırması arkasında motivasyon çok sayıda hatayı içeren kodu incelenmesi önlemektir.
Intellitest kod içinde çok fazla hata bulursa, araştırması durdurulur.

<a name="testexcludepathboundsexceeded"></a>
## <a name="testexcludepathboundsexceeded"></a>TestExcludePathBoundsExceeded

Yapılandırılmış yolu sınırları aşan yürütme yolları [MaxCalls](#maxcalls), [MaxBranches](#maxbranches), [MaxStack](#maxstack), ve [MaxConditions](#maxconditions) göz ardı edilir.

Bağlı bu araştırması arkasında amacı ile (büyük olasılıkla) Sonlandırıcı olmayan testleri Dağıt etmektir. Intellitest gibi bağlı incelenmesi ulaştığında [MaxCalls](#maxcalls), [MaxBranches](#maxbranches), [MaxStack](#maxstack), veya [MaxConditions](#maxconditions), bunu kabul eder test Sonlandırıcı olmayan bir işlem olmaz ve bir yığın taşması daha sonra neden olmayacak olduğunu.
Bu tür test çalışmaları diğer test çerçeveleri ile ilgili sorunlara neden olabilir ve bu özniteliği, büyük olasılıkla Sonlandırıcı olmayan işlemler için test durumları ya da bir yığın taşması neden olacak test çalışmaları yayma Intellitest önlemek için bir yol sağlar.

<a name="testemissionfilter"></a>
## <a name="testemissionfilter"></a>TestEmissionFilter

Intellitest yayma sınama türlerini belirtir. Olası değerler şunlardır:

* **Tüm** -testleri dahil her şeyi için varsayım ihlalleri yayma.
* **FailuresAndIncreasedBranchHits** (varsayılan) - tüm benzersiz hataları için testleri yayma ve her bir test çalışması artırır kapsamı tarafından denetlenen [TestEmissionBranchHits](#testemissionbranchhits).
* **FailuresAndUniquePaths** - tüm hataları Intellitest bulur için testleri yayma ve ayrıca her test giriş için benzersiz yürütme yolu neden olur.
* **Hataları** -yalnızca hataları için testleri yayma.

<a name="testemissionbranchhits"></a>
## <a name="testemissionbranchhits"></a>TestEmissionBranchHits

Geçerli bağlı olarak [TestEmissionFilter](#testemissionfilter) önce kapsanmayan program dalında kapak zaman ayarı Intellitest yeni test çalışmalarını yayar.

**TestEmissionBranchHits** ayarı belirler Intellitest yalnızca bir dal hiç kapsamında dikkate almanız gereken varsa (**TestEmissionBranchHits = 1**), bir test, ya da iki kez (kapsamdaki **TestEmissionBranchHits = 2**) ve benzeri.

**TestEmissionBranchHits = 1** Intellitest ulaşmak tüm dalları kapsayan çok küçük test paketi oluşturur. Özellikle, bu test paketindeki ayrıca tüm temel blokları ve bu sınıra deyimleri ele alınacaktır. 

Bu seçenek için varsayılan değer **TestEmissionBranchHits = 2**, hangi de iyidir daha açıklayıcı bir test paketine oluşturur uygun gelecekteki regresyon hataları algılama için.

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
