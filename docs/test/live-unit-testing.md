---
title: Visual Studio'da Test dinamik birim
ms.date: 2017-03-07
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: 577ebebec7de0599675f60d764dec52d0d8babd6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="live-unit-testing-with-visual-studio-2017"></a>Dinamik birim ile Visual Studio 2017 testi

Uygulama geliştirme gibi canlı birim testi otomatik olarak tüm etkilenen birim testleri arka planda çalışır ve sonuçları ve kod kapsamı Canlı gerçek zamanlı Visual Studio IDE'de sunar. Kodunuzu değiştirirken, Canlı birim testi geri bildirim değişikliklerinizi varolan testleri nasıl etkilediği sağlar ve yeni kod, olup eklediğiniz bir veya daha fazla var olan testleri tarafından ele alınmıştır. Bu hafifçe hata düzeltmeleri yapma veya yeni özellikler eklemek gibi birim testleri yazmak için anımsatır.

> [!NOTE]
> Dinamik birim testi .NET Core veya Enterprise Edition, Visual Studio 2017 .NET Framework'teki hedef C# ve Visual Basic projeleri için kullanılabilir.

Birim testi Canlı testleriniz için kullandığınızda, birim testi canlı verileri testlerinizi durumu hakkında devam eder. Kalıcı veri kullanma yeteneğini canlı, sınamaları çalışırken dinamik olarak kod değişikliklere yanıt üst düzey performans sağlamak birim testi sağlar.
 
## <a name="supported-test-frameworks"></a>Desteklenen test çerçeveler
Aşağıdaki tabloda listelenen üç popüler birim test çerçevelerini ile canlı birim testi çalışır. Ve çerçeveleri bağdaştırıcıları desteklenen minimum sürümü tabloda de listelenir. Birim testi çerçevelerini NuGet.org tüm kullanılabilir.
 
<table> 
<tr>
   <th>Test çerçevesi</th>
   <th>Visual Studio bağdaştırıcısı en düşük sürüm</th>
   <th>Framework en düşük sürüm</th>
</tr>
<tr>
   <td>xUnit.net</td>
   <td> xunit.Runner.VisualStudio sürüm 2.2.0-beta3-build1187</td>
   <td>xunit 1.9.2</td> 
</tr>
<tr>
   <td>NUnit</td>
   <td>NUnit3TestAdapter sürüm 3.5.1</td>  
   <td>NUnit sürüm 3.5.0</td>
</tr>
<tr>
   <td>MSTest</td>
   <td>MSTest.TestAdapter 1.1.4-preview</td>
   <td>MSTest.TestFramework 1.0.5-preview</td>
</tr>
</table>

Eski varsa mstest'i başvurduğunuzdan test projeleri dayalı `Microsoft.VisualStudio.QualityTools.UnitTestFramework` ve daha yeni mstest'i NuGet paketleri, Visual Studio 2017 sürüm 15.4 yükseltme taşımak istemiyorsanız. 

Bazı durumlarda, açıkça Canlı çalışması birim testi için sırayla Çözümdeki projeler tarafından başvurulan NuGet paketlerini geri yüklemek gerekebilir. Açık bir yapı çözümü yaparak ya da bunu yapabilirsiniz (seçin **yapı**, **çözümü yeniden derle** en üst düzey Visual Studio menüsünde) veya çözümde paketleri geri (sağ tıklayın Çözüm ve select **NuGet paketleri geri**) yaşam birim testi etkinleştirmeden önce. 

#   <a name="configuring-live-unit-testing"></a>Dinamik birim testi yapılandırma

Birim testi Canlı seçerek yapılandırabileceğiniz **Araçları**, **seçenekleri** en üst düzey Visual Studio menü ve ardından seçme **Canlı birim testi** sol bölmesinde **Seçenekleri** iletişim. Birim testi dinamik yapılandırma seçenekleri iletişim kutusunda aşağıdaki şekilde gösterilmiştir.

  ![Görüntü](./media/lut-options.png)

Yapılandırılabilir seçeneklerin şunları içerir:

- Bir çözüm yerleşik ve hata ayıklaması olup Canlı birim testi duraklatır
 
- Sistemin pil gücü belirtilen eşiğin altına düştüğünde olup Canlı birim testi duraklatır.
- Bir çözümü açtığınızda olup Canlı birim testi otomatik olarak çalıştırılır.
- Kalıcı veri depolanacağı dizin.   
   **Kalıcı verileri Sil** düğmesi tüm kalıcı veri silmenize olanak sağlar. Bu, birim testi Canlı hangi kalıcı veri bozuldu öneren öngörülemeyen veya beklenmeyen şekilde davrandığından durumunda faydalı olur.   
- Daha sonra bir test çalışması zaman aşımına uğruyor aralığı; Varsayılan değer 30 saniyedir. 
- En yüksek Canlı birim testi oluşturur test işlem sayısı. 
- En fazla Canlı birim testi işler bellek miktarı kullanabilir.
- Canlı birim testi için yazılan bilgilerin düzeyini **çıkış** penceresi.   
   Seçenekleriniz günlüğünü (**hiçbiri**), hata iletileri yalnızca (**hata**), hata ve bilgilendirici iletileri (**bilgisi**, varsayılan), ya da tüm ayrıntıları (**Verbose** ).

Ayrıca, dinamik birim testi içinde ayrıntılı çıktı görüntüleyebilirsiniz **çıkış** değerini "1" adlı bir kullanıcı düzeyinde ortam değişkenine atayarak penceresi `VS_UTE_DIAGNOSTICS` ve Visual Studio'yu yeniden başlatmayı. 

Ayrıntılı MSBuild günlük iletilerden birim testi canlı bir dosyaya yakalamak için `LiveUnitTesting_BuildLog` günlük içerecek şekilde dosyasının adı için kullanıcı düzeyinde ortam değişkeni.

Birim testi Canlı etkinleştirildikten sonra (sonraki bölüme bakın [başlatma, duraklatma ve canlı birim testi durdurma](#starting-pausing-and-stopping-live-unit-testing), da açabilirsiniz **seçenekleri** seçerek iletişim **Test**, **Canlı birim testi**, **seçenekleri**.

## <a name="starting-pausing-and-stopping-live-unit-testing"></a>Başlatma, duraklatma ve canlı birim testi durdurma

Birim testi Canlı seçerek etkinleştirmeniz **Test**, **Canlı birim testi**, **Başlat** en üst düzey Visual Studio menüsünde. Birim testi Canlı etkinleştirildiğinde, kullanılabilir seçenekler **Canlı birim testi** tek bir öğe menüsünden değişikliği **Başlat**, **duraklatma**, **Durdur**, ve **temiz sıfırlama**.

> [!NOTE]
> Birim testi projesi içermeyen bir çözümde Canlı birim testi başlatırsanız **duraklatma**, **durdurmak**, ve **sıfırlama temiz** seçenekler görünür **Canlı Birim test** menü ancak dinamik birim testi başlatılmaz. **Çıkış** penceresi başlar, "desteklenen test bağdaştırıcısı yok... Bu çözüm tarafından başvurulan" bir ileti görüntülenir  

Herhangi bir zamanda geçici olarak duraklatmak veya tamamen Canlı birim testi durdurun. Yeniden düzenleme ortasında olan ve testlerinizi biraz kırılır biliyorsanız, örneğin, bunu isteyebilirsiniz. Üç menü seçenekleri şunlardır:

- **Duraklatma**, hangi geçici olarak askıya Canlı birim testi. 
 
    Birim testi Canlı duraklatıldığında kapsamı görselleştirme Düzenleyicisi'nde görüntülenmez, ancak toplanan tüm veriler korunur. Birim testi Canlı sürdürmek için seçin **devam** Canlı birim testi menüsünde. Dinamik birim testi duraklatıldı ve karakterleri uygun şekilde güncelleştirir, yapılan tüm düzenlemeleri ile Yakala için gerekli olan iş yok. 

- **Durdur**, Canlı birim testi tamamen durdurmak için. Dinamik birim testi toplanmış tüm verileri atar.

- **Temiz sıfırlama**, Canlı birim testi durdurur, siler kalıcı veriler ve canlı birim testi yeniden başlatır.

- **Seçenekler**, açan **seçenekleri** iletişim açıklanan [yapılandırma Canlı birim testi](#configuring-live-unit-testing) bölümü.
 
##  <a name="viewing-coverage-visualization-in-the-editor-as-you-type"></a>Siz yazarken kapsamı görselleştirme düzenleyicisinde görüntüleme

Etkinleştirildikten sonra birim testi dinamik güncelleştirmeler her kodu yazdığınız olup olmadığını göstermek için Visual Studio düzenleyicisinde kod satırı birim testleri ve bunu kapsamak testleri olup geçirme tarafından ele alınmıştır.  Aşağıdaki şekilde geçirme hem testleri gibi testler tarafından kapsanmayan kod satırlarını başarısız kod satırları gösterir. Yeşil "✓" ile donatılmış satırları yalnızca testleri geçirerek ele alınmıştır, bir veya daha fazla başarısız testleri tarafından kapsanan "x" kırmızı ile donatılmış satırlar ve mavi "➖" ile donatılmış satırları herhangi bir test tarafından ele alınmamaktadır.

  ![Görüntü](./media/lut-codewindow.png)

Kod düzenleyicisinde kod değiştirirken kapsamı görselleştirme hemen güncelleştirilmesi birim testi dinamik. Düzenlemeleri işlenirken görselleştirme değişikliklerin veri yuvarlak bir süreölçer ekleyerek güncel olmadığını göstermek için başarısız olan, geçirme aşağıda görüntü ve aşağıdaki şekilde gösterildiği gibi semboller kapsanmayan.

  ![Görüntü](./media/lut-codeupdating.png)
 
## <a name="getting-information-on-successful-or-failed-tests"></a>Başarılı veya başarısız testleri hakkında bilgi alma

Kod penceresinde başarılı veya başarısız simgenin üzerine gelerek, o satırdaki kaç testin devreyi görebilirsiniz. Simgesine tıklayın, aşağıdaki şekilde gösterildiği gibi tek tek testlerin durumunu görebilirsiniz:
 
  ![Görüntü](./media/lut-failedinfo.png) 

Sağlama adları ve test sonucu, araç ipucu sağlar ek olarak, testleri yeniden çalıştırarak yanı hata ayıklayıcı kullanarak test kümesini çalıştırın. Bir veya daha fazla testleri ipucunda seçerseniz, çalıştırmak veya yalnızca bu testleri hata ayıklama. Bu kod penceresi ayrılmak zorunda kalmadan testlerinizi ayıklamanızı sağlar. Hata ayıklayıcı yürütüldüğünde, zaten ayarladınız, kesme Gözlemleme ek olarak hata ayıklama sırasında program yürütme duraklatır bir [ `Assert` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert) beklenmeyen bir sonuç döndürür yöntemi. 

Başarısız bir test ipucunda üzerine geldiğinizde, bu hata hakkında ek bilgi sağlamak için aşağıdaki resimde gösterildiği gibi genişletir. Başarısız test ipucunda çift tıklarsanız, doğrudan gidebilirsiniz.

  ![Görüntü](./media/lut-failedmsg.png) 

Başarısız test gittiğinizde birim testi Canlı görsel olarak da (yeşil "✓" ile birlikte yarı-tam beaker tarafından gösterilen), başarılı olan testler başarısız yöntemi imzada gösterir (kırmızı birlikte yarı-tam beaker "🞩"), veya değil Canlı birim testi (yarı-tam beaker mavi "➖" ile birlikte) katılan. Olmayan test yöntemleri bir simge ile donatılmış değil. Aşağıdaki şekilde yöntemleri tüm dört türü gösterilmektedir.
 
  ![Görüntü](media/lut-testsource.png)
 
## <a name="diagnosing-and-correcting-test-failures"></a>Tanılama ve test hataları düzeltme

Başarısız testten kolayca hata ayıklama için ürün kodu, düzenlemeler ve uygulamanızı geliştirme devam edebilirsiniz. Canlı birim testi arka planda çalıştığından, durdurma ve birim testi Canlı hata ayıklama sırasında yeniden başlatma gerekmez düzenleyin ve döngü devam edin.

Örneğin, önceki çizimde gösterilen test hatasının alfabetik olmayan karakterler dönüş test yöntemi yanlış varsayılır nedeni `true` için geçirildiğinde <xref:System.Char.IsLower%2A?displayProperty=fullName> yöntemi. Biz test yöntemi düzeltmek sonra tüm testlerden geçtiğini bulun. Biz bunu yaparken, biz duraklatmak ya da Canlı birim testi durdurmak zorunda değildir.

## <a name="live-unit-testing-and-test-explorer"></a>Birim testi canlı ve Explorer test etme

Normalde, **Test Gezgini** çalıştırmak, hata ayıklama ve test sonuçlarını analiz sağlayan arabirim sağlar. Dinamik birim testi tümleşir **Test Gezgini**. Birim testi Canlı etkin değil veya durdurulursa, **Test Gezgini** birim testleri son bir test çalıştırıldığı zaman durumunu görüntüler. Kaynak kod değişikliklerini testleri yeniden çalıştırın gerektirir. Birim testi Canlı etkinleştirildiğinde, buna karşılık, birim durumunu içinde testleri **Test Gezgini** anında güncelleştirilir. Artık, birim testleri açıkça çalıştırmanız gerekir. 

> [!NOTE]
> Açabilirsiniz **Test Gezgini** seçerek **Test**, **Windows**, **Test Gezgini** en üst düzey Visual Studio menüsünde.  

Fark edebilirsiniz **Test Gezgini** bazı testleri soluk penceresi. Örneğin, etkinleştirdiğinizde Canlı birim testi önceden kaydedilmiş bir proje açtıktan sonra **Test Gezgini** penceresi soluk başarısız test dışındaki tüm giden aşağıdaki şekilde gösterildiği gibi. Bu durumda, Canlı birim testi başarısız test yeniden ancak başarılı testleri yeniden değil, Canlı birim testi 's kalıcı yaptığınızdan veri en son başarıyla testler bu yana hiçbir değişiklik olduğunu gösterir.

  ![Görüntü](media/lut-test-explorer.png)

Seçerek soluk görünür tüm testleri çalıştırabilirsiniz **tümünü Çalıştır** veya **çalıştırmak** gelen seçenekleri **Test Gezgini** menüsünde veya bir veya daha fazla sınama seçerek**Test Gezgini** menüsünde sağ tıklayıp seçerek **seçili Testleri Çalıştır** veya **seçili Testlerde Hata Ayıkla** açılan menüsünden. Testleri çalıştırırken, bunlar yukarı üst Kabarcık.

Canlı otomatik olarak çalıştırarak ve test sonuçlarını güncelleştirme ve açıkça çalışan testleri birim testi arasındaki bazı farklar vardır **Test Gezgini**. Bu farklılıklar şunlardır:

- İzleme eklenmiş ikili dosyalar çalıştırılır Canlı birim testi çalıştırma veya Test Gezgini penceresi testlerden hata ayıklama normal ikili dosyaları, çalışır. 
- Dinamik birim testi testleri çalıştırmak için yeni bir uygulama etki alanı oluşturmaz, ancak bunun yerine varsayılan etki alanından testleri çalıştırır. Testleri çalıştırmak **Test Gezgini** penceresi, yeni bir uygulama etki alanı oluşturun.
- Dinamik birim testi testleri sıralı olarak her test derlemesi içinde çalıştırır. Birden çok testlerden çalıştırırsanız **Test Gezgini** penceresi ve **paralel Testleri Çalıştır** düğme seçildiğinde, testler paralel olarak.

## <a name="live-unit-testing-and-large-solutions"></a>Birim testi ve büyük çözümlerde Canlı

Çözümünüzü kalıcı veri yok ve canlı birim testi başlattığınızda 10 veya daha fazla proje varsa veya seçtiğinizde **Test**, **Canlı birim testi**, **sıfırlama temiz** Visual Studio üst düzey Visual Studio menüsünden seçeneği büyük projeler testlerinde çok sayıda dinamik yürütme performansı önemli ölçüde etkileyebilir uyarmak için aşağıdaki iletişim kutusunu görüntüler. Seçerseniz **Tamam**, Canlı birim testi, Çözümdeki tüm metinleri yürütür. Seçerseniz **iptal**, yürütülecek testleri seçebilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için aşağıdaki bölümde bkz [dahil ve hariç projeleri ve test yöntemleri](#including-and-excluding-test-projects-and-test-methods).  

 ![Büyük projeler için dinamik birim testi iletişim](media/lut-large-project.png)

## <a name="including-and-excluding-test-projects-and-test-methods"></a>Dahil ve hariç projeleri test ve test yöntemleri

Çok sayıda test projeleri, çözümleri için ne projeleri ve birim testine canlı bir projede tek tek yöntemleri katılmak kontrol edebilirsiniz. Örneğin, test projeleri yüzlerce bir çözüm varsa, birim testine Canlı katılmayı test projeleri hedeflenen kümesini seçebilirsiniz. Dışarıda bırakmak istediğiniz ayrı ayrı test veya bir dahil etmek veya hariç çoğu testleri istediğinizi proje ya da çözüm, tüm testler hariç tutmak isteyip istemediğinizi bağlı olarak bunu yapmak için çeşitli yöntemler vardır. Dinamik birim testi dahil etme/hariç tutma durumu kullanıcı ayarı olarak kaydeder ve bir çözüm açılamaz ve kapandığında hatırlıyor. 

**Proje ya da çözüm tüm testleri hariç**

Birim testleri bağımsız projeleri seçmek için birim testi Canlı başlatıldıktan sonra aşağıdakileri yapın:

1.  Çözüm Gezgini'ndeki çözüme sağ tıklayın ve seçin **Canlı testleri**, **hariç** çözümün tamamında dışlanacak.
1.  Seçin ve testlerine dahil etmek istediğiniz her test projesi sağ tıklayın **Canlı testleri**, **INCLUDE**.

**Kod Düzenleyicisi penceresinden tek tek testlerin hariç**

Kod Düzenleyicisi penceresinde, dahil etmek veya hariç ayrı ayrı test yöntemleri kullanabilirsiniz. Kod Düzenleyicisi penceresinde test yönteminin imzasını sağ tıklatın ve seçin **Canlı testleri**, **dahil [seçili yöntemi]**, **Canlı testleri**,  **[Seçilen yöntemi] hariç**, veya **Canlı testleri**, **hariç tüm ancak [seçili yöntemi]**, burada "Seçili yöntemi" kodda seçili yöntemin adı. penceresini açın. 

**Testleri program aracılığıyla hariç** 

Uygulayabileceğiniz <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> program aracılığıyla yöntemleri, sınıfları ve yapıları Canlı birim testi içinde kendi kapsamı Raporlama dışında tutulacak özniteliği.

Aşağıdaki öznitelikler, Canlı birim testi yöntemleri ayrı ayrı dışlamak için de kullanabilirsiniz:

- XUnit için: `[Trait("Category", "SkipWhenLiveUnitTesting")]`
- NUnit için: `[Category("SkipWhenLiveUnitTesting")]`
- Mstest'i için: `[TestCategory("SkipWhenLiveUnitTesting")]` 
 
## <a name="see-also"></a>Ayrıca bkz.

[Test Araçları kod](https://www.visualstudio.com/vs/testing-tools/)   
[Dinamik birim testi blogu](https://go.microsoft.com/fwlink/?linkid=842514)   
[Birim testi SSS Canlı](live-unit-testing-faq.md)    
[Kanal 9 Video: Dinamik birim Visual Studio 2017 testi](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T105)

