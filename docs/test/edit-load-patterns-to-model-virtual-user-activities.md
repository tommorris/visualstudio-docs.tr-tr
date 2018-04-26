---
title: Yük desenleri Visual Studio'da Test yük
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, load patterns
- load tests, scenarios
- load tests, virtual users
ms.assetid: 0ba0363b-7f50-4bde-a919-0e3bce7bc115
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: e9babedd5920f81dd4a0e2bc244acb21f0965d22
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="edit-load-patterns-to-model-virtual-user-activities"></a>Sanal kullanıcı etkinlikleri modellemek için yük desenlerini düzenleme

Bir yük testi sırasında sanal kullanıcı yükünü nasıl ayarlanır yük düzeni özelliklerini belirtin. Visual Studio üç yerleşik yük desenlerini sağlar: Sabit, adım ve hedef temelli. Yük düzeni seçin ve yük testi hedeflerinize uygun düzeylerine özelliklerini ayarlayın.

Yük düzeni, bir senaryo bileşenidir. Tanımlanmış yük düzenleriyle birlikte senaryolar bir yük testi oluşturur.

> [!NOTE]
> Tüm yük düzenleri, Visual Studio'nun oluşturduğu yük sanal kullanıcıların benzetilmiş bir yük var.

## <a name="load-patterns"></a>Yük desenleri

### <a name="constant"></a>Sabit

 Sabit yük düzeni yük testi sırasında değişmez bir kullanıcı yükünü belirtmek için kullanılır. Örneğin, bir Web uygulamasına duman testi çalıştırdığınızda, 10 kullanıcının açık ve sürekli bir yük ayarlamak isteyebilirsiniz.

#### <a name="constant-load-pattern-considerations"></a>Sabit yük düzeni değerlendirmeleri

 Bir sabit yük düzeni, bir yük testi çalıştırma sırasında aynı kullanıcı yükü çalıştırmak için kullanılır. Yüksek kullanıcı sayısı sahip bir sabit yük düzeni kullanma konusunda dikkatli olun; Bunu yaptığınızda, sunucu veya sunucularda yük testi başındaki aşırı veya belirtmeyi gerçekçi bir talep şekilde yerleştirebilirsiniz. Örneğin, bir giriş sayfası için bir istek ile başlayan bir Web testi yük testlerini içeren ve yük testi 1.000 kullanıcı sabit yükü ile ayarlama, yük testi giriş sayfasına ilk 1.000 isteği mümkün olduğunca hızlı gönderir. Bu, Web sitenizi gerçek gerçekçi bir benzetimi olmayabilir. Bunu azaltmak için kademeli olarak 1,000 kullanıcıya Yükselen bir adım yük düzeni kullanmayı deneyin veya yük testi çalıştırma ayarları bir Isınma Süresi belirtin. Isınma Süresi belirtilirse, yük testi otomatik olarak yük kademeli olarak Isınma süresi boyunca artacaktır. Daha fazla bilgi için bkz: [Senaryo Başlatma Gecikmelerini Yapılandırma](../test/configure-scenario-start-delays.md).

### <a name="step"></a>Adım

 Adım yük düzeni tanımlanmış maksimum kullanıcı yüklemesine kadar süresiyle artırır bir kullanıcı yükünü belirtmek için kullanılır. Belirttiğiniz Adımlama yükleri **ilk kullanıcı sayısı**, **maksimum kullanıcı sayısı**, **adım süresi (saniye)**, ve **adım kullanıcı sayısı**.

 Örneğin bir adım yük ile bir **ilk kullanıcı** sayısına, **maksimum kullanıcı sayısı** 100 **adım süresi (saniye)** 10 ve **adım kullanıcı sayısı** 1 / 1 artar 100 Kullanıcıya erişene kadar her 10 saniyede 1 ile başlayan bir kullanıcı yük düzeni oluşturur.

> [!NOTE]
> Toplam test süresi en fazla kullanıcı yükü kadar adım için gerekli olan zamandan daha kısa ise, test geçen süreden sonra durdurur ve en fazla kullanıcı sayısı hedefine ulaşmaz.


 Adım hedefini bir nokta sunucu ulaşana kadar yükünü artırmak için kullanabileceğiniz performans düşer önemli ölçüde burada. Yük arttıkça sunucu kaynakları tükendi sonunda çalıştırın. Adım yük Bu gerçekleştiğinde kullanıcı sayısını belirlemek için iyi bir yoludur. Adımlama yükü ile ayrıca yakından aracıların istenilen yükü oluşturabildiğinden emin olmak için aracı kaynakları izlemek vardır.

 Genellikle, farklı adım sürelerine sahip birkaç çalıştırma yürütmeniz gerekir ve sağlanan yük için iyi ölçümler alabilmesi adına, adım kullanıcı sayar. Sık sık kullanıcılar eklendikçe yükleri her adımı için bir başlangıç ani değişimi gösterir. Yükü o oranda tutmak ilk depodan sistem kurtarıldıktan sonra sistem performansını ölçmek sağlar.

#### <a name="step-load-pattern-considerations"></a>Adım yük düzeni değerlendirmeleri

 Adım yük düzeni, sunucu veya sunucularda yük kullanıcı yük arttıkça performansın nasıl değişeceğini görebileceğiniz şekilde yük testi olarak artırmak için kullanılabilir. Örneğin, sunucu veya sunucularda nasıl gerçekleştirmek görmek için kullanıcı yükü 2.000 kullanıcılara arttıkça, aşağıdaki özelliklere sahip bir adım yük düzeni kullanarak 10 saat yük testi çalıştırabilirsiniz:

-   İlk kullanıcı sayısı: 100

-   En fazla kullanıcı sayısı: 2.000

-   Adım Süresi (saniye): 1.800

-   Adım Rampa Süresi (saniye): 20

-   Adım kullanıcı sayısı: 100

 Kullanıcı, yük testi 30 dakika (1800 saniye olarak) bu ayarları 2.000 kullanıcılar en fazla ve 100, 200, 300 yükler. **Adım Rampa Süresi** özelliktir özel Bahsetme, Yeni Yük Testi Sihirbazı'nda seçim için kullanılabilir değil yalnızca bu özelliklerden biri olduğundan. Bu özelliği tek bir adımda artışın sonrakine (örneğin 100 200 kullanıcıya) artışın hemen yerine olanak tanır. Örnekte, kullanıcı yükü 20 saniye döneminde 100 ila 200'e yükseltilmiştir (artışı beş kullanıcıların her saniye). Daha fazla bilgi için bkz: [nasıl yapılır: Adım yük düzeni için Adım Rampa Süresi özelliğini belirtme](../test/how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern.md).

### <a name="goal-based"></a>Hedef tabanlı

 Hedef tabanlı yük düzeni adım düzeni benzer ancak Periyodik kullanıcı yükü ayarlamalarına karşı performans sayacı eşiklerine dayalı kullanıcı yükünü ayarlar. Hedefe dayalı yükler çeşitli farklı amaçlar için yararlıdır:

-   Aracılardan gelen çıkış en üst düzeye çıkarma: aracıları çıktısını en üst düzeye çıkarmak için aracı ölçüm sınırlama anahtar ölçmek. Genellikle, CPU olur. Ancak, bellek de olabilir.

-   Bazı hedef kaynak düzeyine ulaşmak, genellikle CPU, hedef sunucuda, ardından o düzeyde verimlilik ölçme. Bu çalışma çalıştırma karşılaştırmaları tutarlı bir sunucu üzerinde kaynak kullanımı düzeyini verilen sn'ye yapmanıza olanak sağlar.

-   Bir hedef üretilen iş düzeyi sunucuda ulaşmasını.

 Aşağıdaki tabloda, aşağıdaki özellik ayarları hedef tabanlı bir desenle bir örnek gösterilmektedir:

|Özellik grubu|Özellik|Değer|
|--------------------|--------------|-----------|
|Performans sayacı|Kategori|İşlemci|
|Performans sayacı|Bilgisayar|ContosoServer1|
|Performans sayacı|Sayaç|% İşlemci zamanı|
|Performans sayacı|Örnek|_Total|
|Performans sayacı için hedef aralığı|Üst uç|90|
|Performans sayacı için hedef aralığı|En düşük|70|
|Kullanıcı sayısı sınırı|İlk kullanıcı sayısı|1.|
|Kullanıcı sayısı sınırı|En fazla kullanıcı sayısı|100|
|Kullanıcı sayısı sınırı|En fazla kullanıcı sayısı azaltma|5|
|Kullanıcı sayısı sınırı|En fazla kullanıcı sayısını artırma|5|
|Kullanıcı sayısı sınırı|En az kullanıcı sayısı|1.|

 Bu ayarları neden **Yük Testi Çözümleyicisi** kullanıcı yükü 1 ile 100 arasında bir şekilde testi sırasında ayarlamak için **sayaç** için `% Processor Time` arasındagezinenWebServer01,`70%`ve `90%.`

 Her kullanıcı yük ayarlama boyutu tarafından belirlenir **maksimum kullanıcı sayısı artışı** ve **maksimum kullanıcı sayısı azaltma** ayarlar. Kullanıcı sayısı sınırları tarafından belirlenen **maksimum kullanıcı sayısı** ve **en az kullanıcı sayısı** özellikleri.

#### <a name="goal-based-load-pattern-considerations"></a>Hedef tabanlı yük düzeni konuları

 Hedef tabanlı yük düzeni sisteminizi destekleyebileceği kullanıcı sayısını belirlemek istediğinizde kullanışlıdır kaynak kullanımı belirli bir düzeyde erişmeden önce. Sisteminizde sınırlama kaynak (performans sorunu) tanımladığınızda bu seçenek en iyi şekilde çalışır.

 Örneğin, sınırlama sisteminizdeki, veritabanı sunucusundaki CPU kaynaktır ve veritabanı sunucusundaki CPU yaklaşık yüzde 75 meşgul olduğunda kaç kullanıcının desteklendiğini görmek istediğiniz bildiğiniz varsayalım. Yüzde 80'i ve yüzde 70 arasında değerin performans sayacı "% işlemci zamanı" tutma amacı olan bir hedef tabanlı yük düzeni kullanabilirsiniz.

 Dikkat edilmesi gereken tek şey, başka bir kaynağın sistemin verimliliğini sınırlama varsa ' dir. Bu tür kaynakları hiçbir zaman erişilmesi için hedef tabanlı yük düzeni tarafından belirtilen hedef neden olabilir. Ayrıca, kullanıcı yükü için belirtilen değer kadar artmaya devam edecektir **maksimum kullanıcı sayısı** ulaşıldı. Bu genellikle istenen yük değil, bu nedenle hedef tabanlı yük düzeni performans sayacında seçimi hakkında dikkatli olun.

## <a name="tasks"></a>Görevler

|Görevler|İlişkili Konular|
|-----------|-----------------------|
|**Yük testi için ilk yük düzeni belirtme:** Yeni Yük Testi Sihirbazı'nı kullanarak bir yük testi oluşturduğunuzda, bir yük düzeni seçin.|-   [Yük düzeni değiştirme](../test/edit-load-patterns-to-model-virtual-user-activities.md#EditingLoadPatternsChanging)|
|**Yük düzeni için yük testi düzenleme:** yük testlerini oluşturduktan sonra Yük Testi Düzenleyicisi'nde yük düzeni düzenleyebilirsiniz.|-   [Nasıl yapılır: Adım yük düzeni için Adım Rampa Süresi özelliğini belirtme](../test/how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern.md)|
|**Sanal kullanıcıların yük test senaryosu olup olmadığını belirten Web önbellek verilerini içermelidir:** değiştirebileceğiniz **yeni kullanıcı yüzdesi** yük testi, önbelleğe alma Web benzetim şeklinizi etkiler özelliği sanal kullanıcı için bir Web tarayıcısı tarafından gerçekleştirilmesi.|-   [Nasıl yapılır: Web önbellek verilerini kullanan sanal kullanıcıların yüzdesini belirtin](../test/how-to-specify-the-percentage-of-virtual-users-that-use-web-cache-data.md)|
|**Adım yük düzeni için Adım Rampa Süresi belirtme:** **Adım Rampa Süresi** özelliği tek bir adımda artışın sonrakine (örneğin 100 200 kullanıcıya) artışın hemen yerine izin verir.|-   [Nasıl yapılır: Adım yük düzeni için Adım Rampa Süresi özelliğini belirtme](../test/how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern.md)|

## <a name="changing-the-load-pattern"></a>Yük düzeni değiştirme

 Yük testi ile oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** test hedeflerinizi karşılayan düzeylere bir senaryoyla ilişkili yük düzeni özelliklerini değiştirmek için.

> [!NOTE]
> Yük testi senaryosu özellikleri ve açıklamalarının tam listesi için bkz: [yük testi senaryosu özellikleri](../test/load-test-scenario-properties.md).


 Bir yük düzeni etkin bir yük testi ve yeni kullanıcılar eklendiği oranı sırasında sanal kullanıcıların sayısını belirtir. Kullanılabilir üç düzenden seçebilirsiniz: adım düzeni, sabit ve hedef tabanlı. Daha fazla bilgi için bkz: [numarası, sanal kullanıcıları bir yük testi senaryosunda yük desenlerle belirten](../test/edit-load-patterns-to-model-virtual-user-activities.md).

> [!NOTE]
> Bir yük testi eklentisi kullanarak yükleme özelliklerini program aracılığıyla da değiştirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md).


### <a name="to-change-the-load-pattern"></a>Yük Düzeni değiştirmek için

1.  Bir yük testi açın.

2.  İçinde **Yük Testi Düzenleyicisi**, istediğiniz senaryo için yük düzeni seçin ve yük düzeni için düzenlemek için senaryoyu senaryolar klasöründe genişletin.

    > [!NOTE]
    > Yük testlerini, senaryo ağacında gösterildiği yük düzeni düğümü ifadesi yük oluştururken seçtiğiniz test yük profili yansıtır. Ya da olabilir **sabit yük profili** veya **Adım yük profili**.

3.  Tuşuna **F4** Özellikler penceresini görüntülemek için.

     **Yük düzeni** ve **parametreleri** kategorileri Özellikleri penceresinde görüntülenir.

4.  (İsteğe bağlı) Değişiklik **düzeni** özelliğinde **yük düzeni** kategorisi.

     İlgili seçimlerinizi **düzeni** özelliği **adım**, **sabit**, ve **hedefe dayalı**. Yük düzeni türleri hakkında daha fazla bilgi için bkz: [numarası, sanal kullanıcıları bir yük testi senaryosunda yük desenlerle belirten](../test/edit-load-patterns-to-model-virtual-user-activities.md).

5.  (İsteğe bağlı) İçinde **parametreleri** kategori değerlerini değiştirin.

    > [!NOTE]
    > İçin ayarlanan değerlerle **parametreleri** için seçtiğiniz değere göre farklılık **düzeni** özelliği.

6.  Özellikleri değiştirme bitirdikten sonra seçin **kaydetmek** üzerinde **dosya** menüsü. Ardından, yeni yük düzeni ile yük testlerini çalıştırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)
- [Nasıl yapılır: Web önbellek verilerini kullanan sanal kullanıcıların yüzdesini belirtin](../test/how-to-specify-the-percentage-of-virtual-users-that-use-web-cache-data.md)
- [Nasıl yapılır: Adım yük düzeni için Adım Rampa Süresi özelliğini belirtme](../test/how-to-specify-the-step-ramp-time-property-for-a-step-load-pattern.md)