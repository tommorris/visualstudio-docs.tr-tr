---
title: Test Gezgini ile birim testleri çalıştırma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.unittesting.testexplorer.overview
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 1c3cf206b952ebf8879045bcdc2881c2d2f4cc0c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="run-unit-tests-with-test-explorer"></a>Test Gezgini ile birim testleri çalıştırma

Kullanım **Test Gezgini** Visual Studio ya da üçüncü taraf birim testi projelerini birim testleri çalıştırmak için. Aynı zamanda **Test Gezgini** testleri kategoriler halinde gruplandırabilirsiniz, test listesini filtrelemek ve oluşturmak, kaydetme ve çalma testleri çalıştırmak için. Testleri hata ayıklama ve test performans ve kod kapsamı analiz edin.

Visual Studio hem yönetilen hem de yerel kod için Microsoft birim test çerçevelerini içerir. Ancak, **Test Gezgini** herhangi bir birimi bir Test Gezgini bağdaştırıcısı uyguladı test çerçevesi de çalıştırabilirsiniz. Üçüncü şahıs birim test çerçevelerini yükleme hakkında daha fazla bilgi için bkz: [üçüncü taraf birim test çerçevelerini yükleme](../test/install-third-party-unit-test-frameworks.md)

**Test Gezgini** testleri bir çözümde birden çok test proje ve üretim kodu projeleri parçası olan test sınıfları'ndan çalıştırabilirsiniz. Test projeleri farklı birim test çerçevelerini kullanabilirsiniz. .NET Framework için test altındaki kodun yazıldığında test projesinin Ayrıca, hedef kod dilini bağımsız olarak .NET Framework hedefler herhangi bir dilde yazılabilir. Yerel C/C++ kod projeleri, C++ birim test çerçevesi kullanılarak test edilebilir. Daha fazla bilgi için bkz: [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md).

## <a name="run-tests-in-test-explorer"></a>Test Gezgini testleri çalıştırma

Test projesi derlerken, testleri Test Gezgini'nde görünür. Test Gezgini görünür durumda değilse, seçin **Test** Visual Studio menüsünde, **Windows**ve ardından **Test Gezgini**.

![Birim Test Gezgini](../test/media/ute_failedpassednotrunsummary.png "UTE_FailedPassedNotRunSummary")

Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları varsayılan gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve  **Testler değil**. Test Gezgini testlerinizi grupları şekilde değiştirebilirsiniz.

Bulma, düzenleme ve testleri Test Gezgini araç çubuğundan çalışan işin çoğunu gerçekleştirebilirsiniz.

![Test Gezgini araç çubuğundan testler](../test/media/ute_toolbar.png "UTE_ToolBar")

### <a name="run-tests"></a>Testleri çalıştırma

Bir grup veya seçtiğiniz testleri kümesi tüm testleri Çözümdeki tüm testleri çalıştırın. Aşağıdakilerden birini yapın:

- Bir çözümde tüm testleri çalıştırmak için tercih **tümünü Çalıştır**.

- Bir varsayılan grubundaki tüm testleri çalıştırmak için tercih **Çalıştır...**  ve grubun menüsünde'i seçin.

- Seçilen test bağlam menüsünü açın ve ardından çalıştırmak istediğiniz tek tek testlerin seçin **seçili Testleri Çalıştır**.

- Tek tek testlerin herhangi bir sırayla çalıştırmak engelleyen bağımlılık varsa, paralel test yürütmesi ile Aç ![UTE&#95;parallelicon&#45;küçük](../test/media/ute_parallelicon-small.png "UTE_parallelicon küçük") iki durumlu düğme araç çubuğunda. Bu, tüm testleri çalıştırmak için geçen süre önemli ölçüde azaltabilir.

Test Gezgini penceresinin üst geçişi/hata çubuğu Testleri Çalıştır animasyon eklenir. Tüm testleri geçirilen ya da herhangi bir test başarısız olursa kırmızı kapatır testi sonuç geçişi/hata çubuğu yeşil olur.

### <a name="run-tests-after-every-build"></a>Her yapıdan sonra testleri çalıştırma

|||
|-|-|
|![Derleme sonrası çalıştırın](../test/media/ute_runafterbuild_btn.png)|Her yerel yapıdan sonra birim testleri çalıştırmak için tercih **Test** standart menüsünde ve ardından **çalıştırmak sonra yapı testleri** Test Gezgini araç çubuğunda.|

## <a name="view-test-results"></a>Test sonuçlarını görüntüleme

Test Gezgini çalıştırmak, yazma ve testleri yeniden çalıştırmak gibi sonuçları gruplar halinde görüntülenir. **başarısız testler**, **testleri geçti**, **atlandı testleri** ve **çalışmıyor Testleri**. Test Gezgini görüntüler altındaki ayrıntılar bölmesini test özetini çalıştırın.

### <a name="view-test-details"></a>Test ayrıntıları görüntüle

Bir test ayrıntılarını görüntülemek için test'i seçin.

![Test yürütme ayrıntıları](../test/media/ute_testdetails.png "UTE_TestDetails")

Test Ayrıntılar bölmesinde aşağıdaki bilgileri görüntüler:

- Kaynak dosya adı ve test yöntemi satır sayısı.

- Test durumu.

- Test yöntemi sürdüğü geçen süre.

Sınama başarısız olursa, Ayrıntılar bölmesinde de görüntüler:

- Test için birim test çerçevesi tarafından döndürülen ileti.

- Yığın izleme testi başarısız zaman.

### <a name="view-the-source-code-of-a-test-method"></a>Bir test yönteminin kaynak kodu görüntüleme

 Visual Studio Düzenleyicisinde test yöntemi için kaynak kodunu görüntülemek için test seçin ve ardından **açık Test** bağlam menüsünde (klavye: **F12**).

## <a name="group-and-filter-the-test-list"></a>Grup ve test listesini filtreleme

Test Gezgini testlerinizi önceden tanımlanmış kategoriler halinde gruplandırabilirsiniz olanak sağlar. Test Gezgini let çalıştırdığınız çoğu birim test çerçevelerini kendi kategorileri ve testlerinizi gruplamak için kategori/değer çiftleri tanımlayın. Eşleşen dizeler karşı test özellikleri tarafından testleri listesi filtre uygulayabilirsiniz.

### <a name="group-tests-in-the-test-list"></a>Test listesi grup testlerinde

 Seçin yanındaki aşağı oka testleri düzenlenir yöntemini değiştirmek için **Group By** düğmesini ![Test Gezgini grubu düğmesini](../test/media/ute_groupby_btn.png "UTE_GroupBy_btn") ve yeni bir grup seçin ölçütleri.

 ![Test Gezgini'nda kategoriye göre testleri grup](../test/media/ute_groupbycategory.png "UTE_GroupByCategory")

### <a name="test-explorer-groups"></a>Test Gezgini grupları

|Grup|Açıklama|
|-----------|-----------------|
|**Süre**|Test grupları göre yürütme süresini: **hızlı**, **orta**, ve **yavaş**.|
|**Sonucu**|Testleri yürütme sonuçları göre gruplandırır: **başarısız testler**, **atlandı testleri**, **testleri geçti**.|
|**Özellikleri**|Belirlediğiniz kategori/değer çiftleri test grubu. Ayırdedici nitelik kategorileri ve değerleri belirtmek için sözdizimi birim test çerçevesi tarafından tanımlanır.|
|**Project**|Projeleri adıyla test grubu.|

### <a name="group-by-traits"></a>Nitelikler göre gruplandırmak

 Bir ayırdedici nitelik genellikle bir kategori ad/değer çifti adıdır, ancak tek bir kategori olabilir. Test yöntemi olarak birim testi çerçevesi tarafından tanımlanan yöntemler nitelikler atanabilir. Birim testi çerçevesi ayırdedici nitelik kategorileri tanımlayabilir. Kendi kategori ad/değer çiftleri tanımlamak için ayırdedici nitelik kategoriler değerleri ekleyebilirsiniz. Ayırdedici nitelik kategorileri ve değerleri belirtmek için sözdizimi birim test çerçevesi tarafından tanımlanır.

 **Yönetilen kod için Framework sınama Microsoft biriminde özellikleri**

 Microsoft birim test çerçevesi yönetilen uygulamalar için de ayırdedici nitelik adı tanımla / değer çiftini bir <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute> özniteliği. Test çerçevesi aynı zamanda bu önceden tanımlanmış özellikleri içerir:

|Ayırdedici nitelik|Açıklama|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.OwnerAttribute>|Sahiplik kategorisi birim test çerçevesi tarafından tanımlanır ve bir dize değeri sahibinin sağlamanızı gerektirir.|
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>|Öncelik kategori birim test çerçevesi tarafından tanımlanır ve öncelik tamsayı değerini sağlamanızı gerektirir.|
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute>|TestCategory öznitelik, bir değer içermeyen bir kategori sağlamanıza izin verir. TestCategory özniteliği tarafından tanımlanan bir kategori TestProperty özniteliği kategorisini de olabilir.|
|<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>|TestProperty özniteliği ayırdedici nitelik kategori/değer çifti tanımlamanızı sağlar.|

 **C++ için Microsoft birim testi çerçevesi nitelikler** bkz [C++ için Microsoft birim testi çerçevesi kullanmayı](how-to-use-microsoft-test-framework-for-cpp.md).

### <a name="search-and-filter-the-test-list"></a>Arama ve filtre test listesi

Test Gezgini filtreleri test yöntemleri, görüntüleme ve çalıştırma projelerinizde sınırlamak için kullanabilirsiniz.

Bir dizede Test Gezgini arama kutusuna yazın ve ENTER seçin, yalnızca tam adları dizeyi içeren testleri görüntülemek için test listesi filtrelenir.

Farklı bir ölçüte göre filtre uygulamak için:

1. Arama kutusunun sağındaki açılan listesini açın.

2. Yeni bir ölçütü seçin.

3. Filtre değeri tırnak işaretleri arasında girin.

![Test Gezgini testlerinde filtre](../test/media/ute_filtertestlist.png "UTE_FilterTestList")

> [!NOTE]
> Aramalar büyük küçük harfe duyarlı ve herhangi bir kısmını ölçütleri değeri için belirtilen dize eşleşmesi.

|Niteleyici|Açıklama|
|---------------|-----------------|
|**Ayırdedici nitelik**|Ayırdedici nitelik kategori ve değeri için eşleşme arar. Ayırdedici nitelik kategorileri ve değerleri belirlemek için söz dizimi birim test çerçevesi tarafından tanımlanır.|
|**Project**|Eşleşme için test proje adları arar.|
|**Hata iletisi**|Kullanıcı tanımlı hata iletilerinin tarafından geri döndürülen başarısız aramaları için eşleşen onaylar.|
|**Dosya yolu**|Test kaynak dosyaların tam dosya adı için eşleşen arar.|
|**Tam adı**|Test ad alanları, sınıflar ve yöntemler tam dosya adı için eşleşen arar.|
|**Output**|Standart çıkış (stdout) veya standart hata (stderr) için yazılmış kullanıcı tanımlı hata iletilerinin arar. Çıktı iletileri belirlemek için söz dizimi birim test çerçevesi tarafından tanımlanır.|
|**Sonucu**|Test Gezgini kategori adları eşleştirmeleri arar: **başarısız testler**, **atlandı testleri**, **testleri geçti**.|

Bir filtre sonuçlarını kümesini dışarıda bırakmak için aşağıdaki sözdizimini kullanın:

```
FilterName:"Criteria" -FilterName:"SubsetCriteria"
```

Örneğin, `FullName:"MyClass" - FullName:"PerfTest"` "PerfTest" adında da dahil testler dışındaki kullanıcıların adı "MyClass" dahil tüm testleri döndürür.

## <a name="create-custom-playlists"></a>Özel çalma listeleri oluşturma

 Oluşturun ve çalıştırın veya bir grup olarak görüntülemek istediğiniz testleri listesini kaydedin. Bir çalma listesi seçtiğinizde, listedeki testler görüntülenir Test Gezgini. Bir test birden fazla çalma listesine ekleyin ve varsayılan seçtiğinizde projenizdeki tüm testleri kullanılabilir **tüm testleri** çalma listesi.

 ![Bir çalma listesi seçin](../test/media/ute_playlist.png "UTE_Playlist")

 **Bir çalma listesi oluşturmak için**, bir veya daha fazla testleri Test Explorer'da seçin. Bağlam menüsünde seçin **eklemek için çalma**, **NewPlaylist**. Ad ve belirttiğiniz konuma sahip dosyayı kaydedin **yeni çalma listesi oluştur** iletişim kutusu.

 **Testleri çalma listesine eklemek için**, bir veya daha fazla testleri Test Explorer'da seçin. Bağlam menüsünde seçin **eklemek için çalma**ve ardından sınamaları eklemek istediğiniz çalma listesi seçin.

 **Bir çalma listesi açmak için**, Test, Visual Studio menüsünde çalma listesi seçin ve son kullanılan çalma listesinden seçin veya çalma çalma konumunu ve adını belirtmek için Aç'ı seçin.

 Tek tek testlerin herhangi bir sırayla çalıştırmak engelleyen bağımlılık varsa, paralel test yürütmesi ile Aç ![UTE&#95;parallelicon&#45;küçük](../test/media/ute_parallelicon-small.png "UTE_parallelicon küçük") iki durumlu düğme araç çubuğunda. Bu, tüm testleri çalıştırmak için geçen süre önemli ölçüde azaltabilir.

## <a name="debug-and-analyze-unit-tests"></a>Hata ayıklama ve birim testleri çözümleme

### <a name="debug-unit-tests"></a>Birim testleri hata ayıklama

Test Gezgini, testleriniz için hata ayıklama oturumu başlatmak için kullanabilirsiniz. Kodunuz Visual Studio hata ayıklayıcısı ile sorunsuz bir şekilde Adımlama, İleri ve geri birim testleri ve test altındaki proje arasında alır. Hata ayıklama başlatmak için:

1. Visual Studio Düzenleyicisi'nde hata ayıklamak istediğiniz bir veya daha fazla test yöntemler bir kesme noktası ayarlayın.

    > [!NOTE]
    > Test yöntemleri herhangi bir sırada çalıştığından hata ayıklamak istediğiniz tüm test yöntemler kesme noktalarını ayarlayın.

2. Test Gezgini test yöntemleri seçin ve ardından **seçili Testlerde Hata Ayıkla** bağlam menüsünde.

 Hata ayıklayıcı hakkında daha fazla bilgi için bkz: [Visual Studio'da hata ayıklamayı](../debugger/debugging-in-visual-studio.md).

### <a name="diagnose-test-method-performance-issues"></a>Test yöntemi performans sorunlarını tanılamanıza

 Test yöntemi çok fazla zaman ayırdığınız neden tanılamak için Test Gezgini'nde yöntemi seçin ve ardından bağlam menüsünden profilini seçin. Bkz: [performans Gezgini](../profiling/performance-explorer.md).

### <a name="analyze-unit-test-code-coverage"></a>Birim testi kod kapsamını çözümleme

Visual Studio kod kapsamı aracını kullanarak, birim testleri tarafından gerçekten sınanan ürün kodunuzu miktarını belirleyebilir. Kod kapsamı seçili testleri ya da bir çözümde tüm testleri çalıştırabilirsiniz.

Bir çözümde test yöntemleri için kod kapsamı çalıştırmak için:

1. Seçin **testleri** Visual Studio menüsünde ve ardından **kod kapsamını çözümleme**.

2. Alt menüsünden aşağıdaki komutlardan birini seçin:

    - **Seçili testleri** Test Gezgini'nde seçtiğiniz test yöntemleri çalıştırır.

    - **Tüm testler** Çözümdeki tüm test yöntemlerini çalıştırır.

Kod Kapsamı Sonuçları penceresi satır, işlev, sınıf, ad alanı ve modülü tarafından kullanılabilecek ürün kod bloklarını yüzdesini görüntüler.

Daha fazla bilgi için bkz: [kullanarak kod kapsamı belirleme ne kadar kodun için test](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

## <a name="test-shortcuts"></a>Test kısayolları

Testleri çalıştırılabilir **Test Gezgini**, Kod düzenleyicisinde test üzerinde sağ tıklatıp seçerek **testi**, varsayılan kullanarak veya [Test Gezgini kısayolları](../ide/default-keyboard-shortcuts-in-visual-studio.md#bkmk_testexplorerGLOBAL) içinde Visual Studio. Bazı kısayollar içerik tabanlı. Bu, çalıştırmak veya imlecinizi Kod Düzenleyicisi'nde olduğu dayanarak testleri hata ayıklama anlamına gelir. İmlecinizi bir test yöntemi içinde ise, yöntemi çalışır sınayın. İmlecinizi sınıf düzeyinde ise, o sınıfta tüm testleri çalıştırın. Bu ad alanı düzeyinde de aynıdır.

|Sık kullanılan komutlar| Klavye Kısayolları|
|--------------|------------------------|
|TestExplorer.DebugAllTestsInContext|Ctrl+R, Ctrl+T|
|TestExplorer.RunAllTestsInContext|Ctrl+R, T|

> [!NOTE]
> Testleri yalnızca soyut sınıflarda tanımlanır ve değil örneği için bir Özet sınıfta bir test çalıştırılamıyor. Soyut sınıflar testleri çalıştırmak için soyut sınıftan türeyen bir sınıf oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
- [64 bitlik bir işlem olarak birim testi çalıştırma](../test/run-a-unit-test-as-a-64-bit-process.md)
