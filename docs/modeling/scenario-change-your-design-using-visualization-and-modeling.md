---
title: 'Senaryo: Görselleştirme ve modelleme kullanarak tasarımınızı değiştirme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- code visualization [Visual Studio ALM]
- modeling software [Visual Studio ALM]
- software modeling [Visual Studio ALM]
- walkthroughs [Visual Studio ALM], visualizing code
- walkthrough [Visual Studio ALM], visualizing code
- walkthrough [Visual Studio ALM], modeling software
- walkthroughs [Visual Studio ALM], modeling software
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 829fd8ed601eae28d367e4b2f3de0a5c7b709985
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="scenario-change-your-design-using-visualization-and-modeling"></a>Senaryo: Görselleştirme ve modelleme kullanarak tasarımınızı değiştirme

Yazılım sisteminizin Görselleştirme ve modelleme Visual Studio araçları kullanarak tarafından Kullanıcıların ihtiyaçlarını karşıladığından emin olun.
Kod Haritaları, bağımlılık diyagramları ve sınıf diyagramlarına gibi araçları kullanın:

Visual Studio hangi sürümlerinin her aracı desteklediğini görmek için bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

- Kullanıcıların gereksinimleri ve iş süreçlerini açıklayın.

- Görselleştirme ve var olan kodu inceleyin.

- Varolan bir sistemde yapılan değişiklikleri açıklar.

- Sistem, gereksinimleri karşıladığını doğrulayın.

- Kodu tasarım ile tutarlı tutun.

Bu izlenecek yol:

- Yazılım projenizi Bu araçlar nasıl yararlanabilir açıklar.

- Bu araçları ne olursa olsun, geliştirme yaklaşım örnek bir senaryo ile kullanma gösterir.

Bu araçlar ve destekledikleri senaryoları hakkında daha fazla bilgi için bkz:

- [Çözümleme ve mimarinin modelini oluşturma](../modeling/analyze-and-model-your-architecture.md)

- [Kodu görselleştirme](../modeling/visualize-code.md)

## <a name="scenario-overview"></a>Senaryoya genel bakış

Bu senaryoda, iki hayali şirketin yazılım geliştirme yaşam döngüleri bölüm açıklanmaktadır: şimdi Yemeği ve bellek yayımlama. Şimdi Yemeği Seattle'da Web tabanlı bir paket teslim hizmeti sağlar. Müşteriler, Yemek Sipariş ve bunlar için Yemeği Şimdi Web sitesinde ödeme. Siparişler, ardından uygun yerel Restoran teslimat için gönderilir. Yayımlama bellek New York'taki şirket dışı ve Web birkaç işletmeler çalışır. Örneğin, müşterilerin restoran incelemeler burada nakledebilirsiniz bir Web sitesini çalıştırmak.

Bellek son şimdi Yemeği edinilen ve aşağıdaki değişiklikleri yapmak istiyor:

- Web sitelerinin Restoran gözden yetenekleri için şimdi Yemeği ekleyerek tümleştirin.

- Yemeği Now ödeme sistemini Lucerne sistemiyle değiştirin.

- Şimdi Yemeği hizmeti bölgesini genişletin.

Şimdi Yemeği SCRUM ve eXtreme programlama kullanır. Çok yüksek test kapsamı ve çok az desteklenmeyen kod sahiptirler. Bunlar küçük oluşturma ancak bir sistem ve işlevsellik artımlı olarak ekleme çalışma sürümleri tarafından riskleri en aza. Bunlar, kısa ve sık yinelemeler üzerinden kendi kodlarını geliştirin. Bu değişiklik güvenle çekirdeğin, kodu sık sık yeniden düzenleyin ve "Önden büyük tasarım" kaçının sağlar.

Bellek bazıları 40 yıldan daha eski olan sistemler, çok büyük ve karmaşık bir koleksiyonunu korur. Eski kod kapsamını ve karmaşıklığı nedeniyle değişiklikler yapma konusunda çok dikkatli oldukları. Bunlar, ayrıntılı çözümleri tasarlama ve tasarım ve geliştirme sırasında meydana gelen değişiklikleri belgelemek için tercih ederek daha ayrıntılı bir geliştirme süreci izleyin.

Her iki ekip modelleme diyagramları Kullanıcıların ihtiyaçlarını karşılayan sistemler geliştirmelerine yardımcı olması için Visual Studio kullanın. Team Foundation Server yanı sıra diğer araçları planlamak, düzenlemek ve işlerini yönetmek yardımcı olmak için kullanırlar.

Team Foundation Server hakkında daha fazla bilgi için bkz:

- [İş planlama ve izleme](#planning-and-tracking-work)

- [Sınama, doğrulama ve güncellenmiş kodu iade etme](#TestValidateCheckInCode)

## <a name="ModelingDiagramsTools"></a> Mimari ve modelleme diyagramları yazılım geliştirme rolleri

Aşağıdaki tabloda bu araçlar yazılım geliştirme yaşam döngüsü çoklu ve çeşitli aşamaları sırasında yürütebilirsiniz roller açıklanmaktadır:

||**Kullanıcı gereksinimlerini modelleme**|**İş Süreci Modelleme**|**Sistem Mimarisi ve tasarım**|**Kod Görselleştirme ve keşif**|**Doğrulama**|
|------|------------------------------------|-----------------------------------|--------------------------------------|------------------------------------------|----------------------|
|Etki alanına özgü dil (DSL) diyagramı|Evet|Evet|Evet|||
|Bağımlılık diyagramı, katman doğrulama|||Evet|Evet|Evet|
|Kod Haritası|||Evet|Evet|Evet|
|Sınıf Tasarımcısı (kod tabanlı)||||Evet||

Bağımlılık diyagramları çizmek için varolan bir çözümü veya yeni bir parçası olarak bir modelleme projesi oluşturmanız gerekir. Bu diyagramları modelleme projesinin içinde oluşturulmalıdır.
Bağımlılık diyagramlarındaki öğeleri modelleme projesinde bulunur, ancak ortak modelde depolanmaz. Kod haritaları ve koddan oluşturulan .NET sınıf diyagramları dışında modelleme projesine mevcut.

Bkz.

- [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)

- [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)

- [Nasıl Yapılır: Projelere Sınıf Diyagramları Ekleme (Sınıf Tasarımcısı)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)

- [Visual Studio için Modelleme SDK'sı - Etki Alanına Özgü Diller](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

Her iki ekip bağımlılık doğrulama kodu geliştirilme tasarım ile tutarlı olmasını sağlamak için de kullanır. Bkz.

- [Kodu tasarım ile tutarlı tutma](#ValidatingCode)

- [Mantıksal mimarisi açıklanmıştır: bağımlılık diyagramları](#DescribeLayers)

- [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)

> [!NOTE]
> Bazı Visual Studio sürümleri Görselleştirme ve modelleme için bağımlılık doğrulama ve kod haritalarını salt okunur sürümlerini destekler. Bu özellik, Visual Studio'nun hangi sürümleri desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="understand-and-communicate-information-about-the-system"></a>Anlama ve sistem hakkında bilgi iletişim

Gereksinimlerini veya bir yaklaşım ile uygun şekilde kullanabilmeniz için modelleme diyagramlarını, Visual Studio kullanarak hiçbir belirlenen sırada yoktur. Genellikle, takımlar modellerini tekrarlayarak ve sık sık proje boyunca yeniden ziyaret. Her diyagram anlamak, açıklar ve geliştirme sisteminde farklı yönlerini iletişim kurmanıza yardımcı olmak için belirli gücü sunar.

Şimdi Akşam Yemeği ve bellek birbiriyle ve proje Paydaşlar ile diyagramları ortak dil olarak kullanarak iletişim kurar. Örneğin, bu görevleri gerçekleştirmek için şimdi Yemeği diyagramları kullanır:

- Var olan kodu görselleştirin.

- Bellek ile yeni veya güncelleştirilmiş kullanıcı hikayeleri iletişim kurar.

- Yeni veya güncelleştirilmiş kullanıcı hikayeleri desteklemek için gereken değişiklikleri tanımlar.

Bu görevleri gerçekleştirmek için diyagramları bellek kullanır:

- Şimdi Yemeği iş süreci hakkında bilgi edinin.

- Sistemin tasarımını anlayın.

- Şimdi Yemeği ile yeni veya güncelleştirilmiş kullanıcı gereksinimleri ile iletişim kurun.

- Belge güncelleştirmeleri sisteme.

Takımlar planlama, yönetebilir ve işlerini daha kolay izlemek için diyagramları Team Foundation Server ile tümleşiktir. Örneğin, modelleri test durumları ve geliştirme görevleri tanımlamak ve işlerini tahmin etmek için kullanırlar. Bellek bağlantılar Team Foundation Server iş öğeleri model öğelerine ilerlemeyi izlemek ve sistem kullanıcıların gereksinimlerini karşıladığından emin olun. Tüm testler başarılı olduğunda kullanım örnekleri karşılandıktan görebilmeniz için örneğin, bunlar kullanım durumları test çalışması iş öğelerine bağlayın.

Takımlar yaptıkları değişiklikleri iade etmeden önce bağımlılık doğrulama ve otomatikleştirilmiş testleri içeren yapıları çalıştırarak kodu testleri ve tasarım karşı doğrulayın. Bu, güncelleştirilmiş kod değil tasarım ile çakışıyor ve daha önce çalışma işlevselliği bölün emin olmaya yardımcı olur.

### <a name="identify-changes-to-the-existing-system"></a>Varolan sistem değişiklikleri tanımlar

Şimdi Yemeği yeni gereksinimi toplantı maliyetini tahmin etmelisiniz. Bu, ne kadar bu değişiklik sisteminin diğer bölümleriyle kısmen etkileyecek bağlıdır. Bu anlamalarına yardımcı olmak için şimdi Yemeği geliştiriciler biri bu eşlemeleri ve diyagramları varolan koddan oluşturur:

|**Harita veya diyagramı**|**Gösterir**|
|------------------------|---------------|
|*Kod Haritası*<br /><br /> Bkz.<br /><br /> - [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)<br />- [Gözat ve kod haritalarını bunları yeniden düzenleme](../modeling/browse-and-rearrange-code-maps.md)<br />- [DGML dosyalarını düzenleyerek kod haritalarını özelleştirme](../modeling/customize-code-maps-by-editing-the-dgml-files.md)|Bağımlılıklar ve diğer ilişkiler kod.<br /><br /> Örneğin, şimdi Yemeği bütünleştirilmiş kod haritalarını genel bir bakış için derlemeler ve bağımlılıklarını gözden geçirerek başlayabilir. Bunlar ad alanları ve sınıflar bu derlemelerde keşfetmek için maps ayrıntılarına geçebilir.<br /><br /> Şimdi Yemeği belirli alanları ve diğer tür koddaki ilişkileri keşfetmek için maps de oluşturabilirsiniz. Çözüm Gezgini bulmak ve onları ilgilendiren ilişkileri ve alanları seçmek için kullanırlar.|
|*Kod tabanlı sınıf diyagramı*<br /><br /> Bkz: [nasıl yapılır: sınıf diyagramlarını (Sınıf Tasarımcısı) projelerine ekleme](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|Kodda varolan sınıfları|

 Örneğin, geliştiricinin kod Haritası oluşturur. Aynen yeni senaryodan etkilenecek alanlarına odaklanmak için kapsamı ayarlar. Bu alanlar seçilir ve haritada vurgulanmış:

 ![Namespace bağımlılık grafiğinin](../modeling/media/namespace_reviewsystem.png "Namespace_ReviewSystem")

 **Namespace kod Haritası**

 Geliştirici, kendi sınıfları, yöntemleri ve ilişkileri görmek için seçilen ad alanlarını genişletir:

 ![Genişletilmiş ad alanı bağımlılık grafiğinin](../modeling/media/dep_reviewsystem.png "Dep_ReviewSystem")

 **Genişletilmiş ad alanı kod Haritası görünür gruplar arası bağlantılar**

 Geliştirici etkilenen sınıflar ve yöntemler bulmak için kodu inceler. Bunları, üretme yaptığınız gibi her değişikliğin etkilerini görmek için her bir değişiklikten sonra kod eşler. Bkz: [kodu görselleştirme](../modeling/visualize-code.md).

 Bileşenler veya etkileşimler gibi sisteminin diğer bölümleriyle değişiklikleri açıklamak için takım panolara bu öğeleri çizin. Böylece ayrıntıları yakalanan, yönetilen ve her iki ekip tarafından anlaşılan Visual Studio'da ayrıca aşağıdaki diyagramlarda çizim:

|**Diyagramları**|**Açıklar**|
|------------------|-------------------|
|*Kod tabanlı sınıf diyagramı*<br /><br /> Bkz: [nasıl yapılır: sınıf diyagramlarını (Sınıf Tasarımcısı) projelerine ekleme](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|Varolan sınıfları kod.|

###  <a name="ValidatingCode"></a> Kodu tasarım ile tutarlı tutmak
 Şimdi Yemeği güncelleştirilmiş kod tasarım ile tutarlı kaldığından emin olmanız gerekir. Bunlar, sistemde işlevselliği katmanları tanımlamak, bunları ve ilişkilendirme çözümü yapıları bu katmanlara arasında izin verilen bağımlılıklarını belirt bağımlılık diyagramları oluşturun.

|**Diyagramı**|**Açıklar**|
|-----------------|-------------------|
|*Bağımlılık diyagramı*<br /><br /> Bkz.<br /><br /> - [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)<br />- [Bağımlılık diyagramları: başvuru](../modeling/layer-diagrams-reference.md)<br />- [Bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md)<br />- [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)|Kod mantıksal mimarisi.<br /><br /> Bir bağımlılık diyagram düzenler ve yapılar eşleyen bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şeklinde adlandırılan gruplara soyut çözüm *katmanları*. Bu katmanlar, roller, görevler veya bu yapıların sistemde gerçekleştirdiği işlevleri tanımlar.<br /><br /> Katman diyagramları sistemin amaçlanan tasarımını açıklayan ve tasarımda gelişen kod doğrulama için faydalıdır.<br /><br /> Katmanlar oluşturmak için Çözüm Gezgini'nde, kod haritalarını, sınıf görünümü ve Nesne Tarayıcısı öğeleri sürükleyin. Yeni Katmanlar çizmek için araç kutusu kullanın veya diyagram yüzeyine sağ tıklayın.<br /><br /> Var olan bağımlılıkları görüntülemek için katman diyagramı yüzeyine sağ tıklayın ve ardından **Bağımlılıklar Oluştur**. Hedeflenen bağımlılıklarını belirtmek için yeni bağımlılıkları çizin.|

 Örneğin, aşağıdaki bağımlılık diyagramda katmanları ve her bir katman ile ilişkili yapıları sayısı arasındaki bağımlılıkları açıklanmaktadır:

 ![Tümleşik ödeme sistemi bağımlılık diyagramı](../modeling/media/layer_integrated_dnlucerne.png "Layer_Integrated_DNLucerne")

 **Bağımlılık diyagramı**

Tasarım çakışıyor kod geliştirme sırasında meydana gelmediğinden emin olmak için bağımlılık doğrulamasını derlemeler takımlar kullanır, Team Foundation Build çalıştırılır. Bunlar ayrıca iade etme işlemlerini bağımlılık doğrulama gerektirecek şekilde özel bir MSBuild görev oluşturur. Doğrulama hataları toplamak için yapı raporlarını kullanırlar.

Bkz.

- [Derleme işlemi tanımlayın](http://msdn.microsoft.com/Library/61593e10-d24b-492f-b19a-af4d85abea6b)

- [Geçitli iade derleme süreci değişiklikleri doğrulamak için kullanın](http://msdn.microsoft.com/Library/9cfc8b9c-1023-40fd-8ab5-1b1bd9c172ec)

- [Derleme işlem şablonunu özelleştirme](http://msdn.microsoft.com/Library/b94c58f2-ae6f-4245-bedb-82cd114f6039)

### <a name="general-tips-for-creating-and-using-models"></a>Genel modelleri oluşturma ve kullanma ipuçları

- Çoğu diyagramları hatlarıyla düğümleri oluşur. Her diyagram türü için farklı türde düğümler ve satırları araç sağlar.

     Araç kutusu açmak için **Görünüm** menüsünde tıklatın **araç**.

- Bir düğüm oluşturmak için araç kutusu'ndan diyagrama sürükleyin. Belirli düğüm türleri, varolan düğümleri sürüklediğiniz gerekir. Örneğin, bir bileşen diyagramı üzerinde yeni bir bağlantı noktası var olan bir bileşen eklenmesi gerekir.

- Bir satır veya bir bağlantı oluşturmak için araç kutusunda uygun Aracı'nı tıklatın, kaynak düğümünü tıklatın ve sonra hedef düğümüne tıklayın. Bazı satırlar yalnızca belirli düğüm türleri arasında oluşturulabilir. İşaretçinin olası kaynak veya hedef taşıdığınızda, işaretçi bir bağlantı oluşturmak olup olmadığını gösterir.

### <a name="plan-and-track-work"></a>İşi planlayın ve izleyin

Planlamak, yönetmek ve iş daha kolay izlemek için visual Studio modelleme diyagramları Team Foundation Server ile tümleşiktir. Her iki ekip modelleri test durumları ve geliştirme görevleri tanımlamak ve işlerini tahmin etmek için kullanın. Bellek oluşturur ve bağlantıları Team Foundation Server iş öğeleri kullanım durumları veya bileşenleri gibi model öğelerine. Bu, bunları kendi ilerleme durumunu izleyin ve kendi iş geri kullanıcıların gereksinimlerini izleme yardımcı olur. Bu değişiklikleri bu gereksinimleri karşılamaya devam ettiğinden emin olun yardımcı olur.

Kendi iş ilerledikçe harcadıkları süre görevlerini üzerinde yansıtacak şekilde kendi iş öğelerini takımlar güncelleştirme. Ayrıca izleme ve raporlama aşağıdaki Team Foundation Server özelliklerini kullanarak işlerine durumu:

- Günlük *burndown raporları* Planlanmış iş beklenen süre içinde tamamlanır olup olmadığını gösterir. Bunlar, hatalar ilerlemesini izlemek için Team Foundation Server'dan benzer diğer raporlar oluşturur.

- Bir *yineleme çalışma sayfası* , Microsoft Excel izlemek ve üyeleri arasında iş yükünü dengelemek takım yardımcı olmak için kullanır. Bu çalışma Team Foundation Server'a bağlı ve düzenli ilerleme toplantıları sırasında tartışma odağı sağlar.

- A *geliştirme Pano* önemli proje bilgileri hakkında bilgi sahibi takım tutmak için Office proje kullanan.

Bkz.

- [Visual Studio Team Services veya Team Foundation Server kullanarak iş izleme](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503)

- [Grafikler, panolar ve Visual Studio ALM için raporlar](http://msdn.microsoft.com/Library/1f28ba6c-c5e5-46d3-9209-ede24ae78e48)

- [Biriktirme listesi ve Project'i kullanarak görev oluşturma](http://msdn.microsoft.com/Library/be5cef4f-755f-4ffe-8dd7-876d1e02c330)

### <a name="TestValidateCheckInCode"></a> Kodunuzu iade test ve doğrulama

Takımlar her bir görevi tamamlayın gibi Team Foundation sürüm denetimine kendi kodlarını ve bunlar unutursanız anımsatıcıları Team Foundation Server'dan alırsınız. Team Foundation Server kendi iadeler kabul etmeden önce takımları ve bağımlılık doğrulama kodu, test çalışmalarına ve tasarım karşı doğrulamak için birim testleri çalıştırın. Team Foundation Server derlemeleri, çalıştırmak için kullandıkları otomatik birim testleri ve düzenli olarak bağımlılık doğrulama. Bu kod aşağıdaki ölçütleri karşıladığından emin olun yardımcı olur:

- Bu çalışır.

- Daha önce çalışan kodu kesmez.

- Tasarım ile çakışmaz.

Şimdi Yemeği neredeyse tüm hala geçerli olduğundan, bellek yeniden otomatikleştirilmiş testleri büyük koleksiyonu vardır. Bellek Ayrıca bu testleri geliştirebilir ve yeni işlevsellikler içeren yeni bir tane ekleyebilirsiniz. Her ikisi de Visual Studio el ile testleri çalıştırmak için kullanın.

Kod tasarıma uyduğundan emin olmak için bağımlılık doğrulama dahil etmek için Team Foundation Yapı içinde takımlar yapılarına yapılandırın. Bir çakışma meydana gelirse, bir rapor ayrıntılarla oluşturulur.

Bkz.

- [Uygulamayı test etme](https://www.visualstudio.com/docs/test/overview)

- [Geliştirme sırasında sisteminizi doğrulama](../modeling/validate-your-system-during-development.md)

- [Sürüm denetimini kullanma](http://go.microsoft.com/fwlink/?LinkID=525605)

- [Derleme ve yayınlama](/vsts/build-release/index)

## <a name="update-the-system-using-visualization-and-modeling"></a>Sistem kullanarak Görselleştirme ve modelleme güncelleştir

Bellek ve şimdi Yemeği Ödeme sistemlerini tümleştirmeniz gerekir. Aşağıdaki bölümlerde, bu görevi gerçekleştirmek Visual Studio'da modelleme diyagramları yardımcı göster:

- [Var olan kodu görselleştirme: Kod eşlemeleri](#VisualizeCode)

- [Türler sözlüğü tanımlayın: sınıf diyagramları](#DefineClasses)

- [Mantıksal mimarisi açıklanmıştır: bağımlılık diyagramları](#DescribeLayers)

Bkz.

- [Kodu görselleştirme](../modeling/visualize-code.md)

- [Geliştirme sürecinizde modelleri kullanma](../modeling/use-models-in-your-development-process.md)

- [Uygulama mimarinizi modelleme](../modeling/model-your-app-s-architecture.md)

### <a name="VisualizeCode"></a> Var olan kodu görselleştirme: Kod eşlemeleri

Kod haritaları kodda mevcut organizasyon ve ilişkileri gösterir. Öğeleri temsil ettiği *düğümleri* haritaya ve ilişkileri temsil ettiği *bağlantılar*. Kod haritaları aşağıdaki tür görevleri gerçekleştirmenize yardımcı olabilir:

- Yabancı kodu keşfedin.

- Önerilen bir değişikliğin nerede ve nasıl var olan kodu etkilediğini anlayın.

- Karmaşıklık, doğal bağımlılıkları veya desenler alanlarının veya iyileştirmeden yararlanabilecek diğer alanları bulun.

Örneğin, şimdi Yemeği PaymentProcessing bileşeninin maliyetini tahmin etmelisiniz. Bu, ne kadar bu değişiklik sisteminin diğer bölümleriyle kısmen etkileyecek bağlıdır. Bu anlamalarına yardımcı olmak için şimdi Yemeği geliştiriciler birini koddan kod eşlemelerini oluşturur ve değişiklikten etkilenen alanları odağını ayarlar.

Aşağıdaki harita PaymentProcessing sınıfı ve seçili görünen diğer bölümleri şimdi Yemeği sistemi arasındaki bağımlılıkları gösterir:

![Bağımlılık grafiğinin şimdi Yemeği Ödeme sistemi için](../modeling/media/dep_dnpayment.png "Dep_DNPayment")

**Şimdi Yemeği Ödeme sistemi için kod Haritası**

Geliştirici PaymentProcessing sınıfı genişletme ve büyük olasılıkla etkilenen alanları görmek için üyelerini seçerek eşleme ele:

![PaymentProcessing ve bağımlılıkları içinde yer alan yöntemler](../modeling/media/depgraph_expandeddn.png "DepGraph_ExpandedDN")

**PaymentProcessing sınıfı ve bağımlılıklarını içinde yöntemleri**

Bunlar sınıfları, yöntemleri ve bağımlılıklarını incelemek bellek ödeme sistemi için aşağıdaki eşlemesi oluşturun. Takım bellek sistem diğer bölümleri şimdi Yemeği ile etkileşim kurmak için çalışma gerektirebilir görür:

![Bağımlılık grafiğinin bellek ödeme sistemi için](../modeling/media/depgraph_lucernepay.png "DepGraph_LucernePay")

**Kod Haritası bellek ödeme sistemi**

Her iki ekip iki sistemi tümleştirmek için gereken değişiklikleri belirlemek için birlikte çalışır. Bunlar, böylece güncelleştirmek daha kolay bazı kodları yeniden düzenlemeniz karar verin. PaymentApprover sınıfı DinnerNow.Business ad alanına taşır ve bazı yeni yöntemler gerektirir. İşlemleri işleyen şimdi Yemeği sınıflarının kendi ad olacaktır. Takımlar oluşturabilir ve iş öğeleri planlamak, düzenlemek ve işlerine izlemek için kullanabilirsiniz. Model öğelerine yararlı olduğu iş öğeleri bağlandıklarını.

Kod yeniden düzenledikten sonra takımlar güncelleştirilmiş yapısı ve ilişkileri görmek için yeni bir kod Haritası Oluştur:

![Bağımlılık grafiğinin yeniden düzenlenen koduyla](../modeling/media/depgraph_integrated.png "DepGraph_Integrated")

**Yeniden düzenlenen kodu içeren kod Haritası**

Bu haritada PaymentApprover sınıfı DinnerNow.Business ad alanında sunulmuştur ve bazı yeni yöntemler gösterir. Şimdi Yemeği işlem sınıflarının artık daha sonra bu kodla başa kolaylaştırır kendi PaymentSystem ad var.

#### <a name="creating-a-code-map"></a>Kod Haritası oluşturma

- Kaynak kodu hızlı bir genel bakış için bir kod haritası oluşturmak için aşağıdaki adımları izleyin:

     Üzerinde **mimarisi** menüsünde tıklatın **oluşturmak çözüm kod Haritası**.

     Hızlı bir genel bakış derlenmiş kod için boş bir kod Haritası oluşturma ve derleme veya ikili dosyaları harita yüzeyine sürükleyin.

- Belirli bir kod ya da çözüm öğeleri keşfetmek için Çözüm Gezgini öğeleri ve görselleştirmek için istediğiniz ilişkileri seçmek için kullanın. Ardından yeni bir harita oluşturmak veya mevcut bir haritayı seçili öğeleri Ekle. Bkz: [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md).

- Harita keşfetmenize yardımcı olmak için Düzen gerçekleştirmek istediğiniz görevlerin türlerini uygun şekilde yeniden düzenleyin.

     Örneğin, kodda katmanlama görselleştirmek için bir ağaç düzeni seçin. Bkz: [göz atın ve haritalar kod sıralama](../modeling/browse-and-rearrange-code-maps.md).

#### <a name="summary-strengths-of-code-maps"></a>Özeti: Kod haritaları gücü
 Kod haritaları yardımcı olur:

- Kuruluş ve varolan koddaki ilişkileri hakkında bilgi edinin.

- Önerilen bir değişiklikten etkilenen alanları tanımlayın.

- Karmaşıklık, desenleri, Katmanlar veya kod korumak, değiştirin ve yeniden daha kolay hale getirmek için artabileceğini diğer alanlarına alanlarının bulun.

#### <a name="relationship-to-other-diagrams"></a>Diğer Diyagramlarla İlişki

|**Diyagramı**|**Açıklar**|
|-----------------|-------------------|
|Bağımlılık diyagramı|Sistemin mantıksal mimarisi. Bağımlılık doğrulama kodu tasarım ile tutarlı kalmasını sağlamak için kullanın.<br /><br /> Varolan dependencys veya hedeflenen dependencys tanımlamanıza yardımcı olması için bir kod haritası oluşturmak ve ilgili öğeleri gruplayın. Bir bağımlılık diyagramı oluşturmak için bkz:<br /><br /> - [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)<br />- [Bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md)|
|Sınıf diyagramı (kod tabanlı)|Belirli bir proje kodunu varolan sınıflarda.<br /><br /> Görselleştirme ve mevcut bir sınıfın kodu değiştirmek için Sınıf Tasarımcısı kullanın.<br /><br /> Bkz: [nasıl yapılır: sınıf diyagramlarını (Sınıf Tasarımcısı) projelerine ekleme](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|

### <a name="DefineClasses"></a> Türler sözlüğü tanımlayın: sınıf diyagramları
 Sınıf diyagramları varlıklar, koşulları veya sistem ve ilişkilerini birbiriyle katılan kavramları tanımlayın. Örneğin, geliştirme sırasında bu diyagramları öznitelikleri ve bunların uygulama dili veya stil bağımsız olarak her sınıf için operations tanımlamak için kullanabilirsiniz.

 Açıklar ve İşlem Ödemesi kullanım örneğine katılan varlıklar ele bellek yardımcı olmak için aşağıdaki sınıf diyagramı çizim:

 ![Sınıf diyagramında Ödeme varlıkları işlemek](../modeling/media/uml_payentities.png "UML_PayEntities")

 **Sınıf diyagramında İşlem Ödemesi varlıkları**

 Bu diyagramda müşteri birçok siparişi ve siparişler için farklı yollar olabileceğini gösterir. BankAccount ve CreditCard ödeme devralır.

 Geliştirme sırasında bellek açıklar ve her sınıfın ayrıntılarını tartışmak için aşağıdaki sınıf diyagramı kullanır:

 ![Sınıf diyagramında Ödeme varlık ayrıntıları işlem](../modeling/media/uml_payment.png "UML_Payment")

 **Sınıf diyagramında İşlem ödeme ayrıntıları**

#### <a name="drawing-a-class-diagram"></a>Sınıf diyagramı çizme

Bir sınıf diyagramı aşağıdaki önemli özelliklere sahiptir:

- Sınıflar, arabirimler ve numaralandırmalar gibi türleri:

    - A *sınıfı* belirli yapısal veya davranışsal özellikleri paylaşan nesnelerin tanımıdır.

    - Bir *arabirimi* bir parçası olan bir nesne dışarıdan görünür davranışını tanımlar.

    - Bir *numaralandırma* değişmez değerler listesini içeren bir sınıflandırıcı değil.

- *Öznitelikleri* her örneği açıklayan belirli bir türdeki değerler bir *sınıflandırıcı*. Bir sınıflandırıcı türleri, bileşenleri, kullanım örnekleri ve hatta aktörler için genel bir addır.

- *İşlemleri* yöntemleri ya da bir sınıflandırıcı örneklerini gerçekleştirebilirsiniz işlevleri.

- Bir *ilişkilendirme* bazı türünden iki sınıflandırıcı arasındaki ilişkiyi gösterir.

    - Bir *toplama* sınıflandırıcı arasında paylaşılan bir sahiplik gösteren ilişkidir.

    - A *birleşim* sınıflandırıcı arasında bir tamsayı bölümü ilişki gösteren ilişkidir.

     Toplamaları veya birleşimleri göstermek için ayarlanmış **toplama** ilişkilendirme özelliği. **Paylaşılan** toplamaları gösterir ve **bileşik** bileşimleri gösterir.

- A *bağımlılık* bir sınıflandırıcı tanımını değiştirerek başka bir sınıflandırıcı tanımını değişebilir gösterir.

- A *Genelleştirme* belirli bir sınıflandırıcı genel bir sınıflandırıcı tanımından kendi tanımının bir parçası devralır gösterir. A *gerçekleştirme* bir sınıf işlemleri ve arabirim tarafından sunulan öznitelikleri uyguladığını gösterir.

     Bu ilişkileri oluşturmak için kullanmak **devralma** aracı. Alternatif olarak, bir gerçekleştirme olarak temsil edilebilir bir *Lolipop*.

- *Paketleri* sınıflandırıcı, ilişkileri, çizgileri, bileşenleri ve diğer paketleri gruplarıdır. *İçeri aktarma* ilişkileri gösteren bir paketin başka bir paketin tüm tanımları içerir.

Keşfetmek ve varolan sınıfları tartışmak için başlangıç noktası olarak Sınıf Tasarımcısı koddan sınıf diyagramları oluşturmak için kullanabilirsiniz.

- [Nasıl Yapılır: Projelere Sınıf Diyagramları Ekleme (Sınıf Tasarımcısı)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)

#### <a name="summary-strengths-of-class-diagrams"></a>Özeti: Sınıf diyagramları gücü
 Sınıf diyagramları tanımlamanıza yardımcı olur:

- Sık kullanılan terimler Kullanıcıların ihtiyaçlarını ve sisteme katılan varlıklar ele alınırken kullanılacak sözlüğü. Bkz: [Model kullanıcı gereksinimlerini](../modeling/model-user-requirements.md).

- Bölümleri, kendi uygulamadan bağımsız olarak bileşenleri gibi sistem tarafından kullanılan türleri. Bkz: [uygulama Mimarinizi Model](../modeling/model-your-app-s-architecture.md).

- Türleri arasındaki bağımlılıkları gibi ilişkiler. Örneğin, bir türü birden çok başka bir tür örnekleriyle ilişkili olabilir gösterebilir.

#### <a name="relationship-to-other-diagrams"></a>Diğer Diyagramlarla İlişki

|**Diyagramı**|**Açıklama**|
|-----------------|---------------------|
|Bağımlılık diyagramı|Sınıflara ilgili olarak sistemin mantıksal mimarisi tanımlayın.<br /><br /> Bağımlılık doğrulama kodu tasarım ile tutarlı kalmasını sağlamak için kullanın.<br /><br /> Bkz.<br /><br /> - [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)<br />- [Bağımlılık diyagramları: başvuru](../modeling/layer-diagrams-reference.md)<br />- [Bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md)<br />- [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)|
|Kod Haritası|Kuruluş ve varolan koddaki ilişkileri görselleştirin.<br /><br /> Sınıfları, ilişkilerini ve yöntemlerini tanımlamak için bu öğeleri gösteren bir kod Haritası oluşturun.<br /><br /> Bkz.<br /><br /> - [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)|

### <a name="DescribeLayers"></a> Mantıksal mimarisi açıklanmıştır: bağımlılık diyagramları
 Bağımlılık diyagramları çözümünüzdeki yapıları soyut gruplar halinde düzenleyerek bir sistem mantıksal mimarisini açıklar veya *katmanları*. Yapılar ad alanları, projeler, sınıfları, yöntemleri ve benzerleri gibi pek çok şey olabilir. Katmanlar temsil eder ve roller veya yapıları sistemde gerçekleştirdiği görevleri tanımlayın. Katman doğrulaması, yapı ve kod tasarımıyla tutarlı kalmasını sağlamak için iade etme işlemlerini de içerebilir.

 Kodu tasarım ile tutarlı tutmak için şimdi Yemeği ve bellek aşağıdaki bağımlılık diyagram geliştikçe kodlarını doğrulamak için kullanın:

 ![Tümleşik ödeme sistemi bağımlılık diyagramı](../modeling/media/layer_integrated_dnlucerne.png "Layer_Integrated_DNLucerne")

 **Yemeği Şimdi bellek ile tümleşik için bağımlılık diyagramı**

 Bu diyagramda katmanlarda karşılık gelen şimdi Yemeği ve bellek çözüm yapılarına bağlar. Örneğin, iş katmanı bağlantılarını DinnerNow.Business ad alanı ve üyeleri için artık PaymentApprover sınıfı içerir. Kaynak erişim katmanı bağlantılar DinnerNow.Data ad. Oklar veya *bağımlılıkları*, yalnızca iş katmanı kaynak erişim katmanındaki işlevselliği kullanabilirsiniz belirtin. Takımlar kendi kodlarını güncellerken gibi katman doğrulaması bunlar ortaya çıktığında çakışmaları catch ve derhal çözmesine takımlar yardımcı olmak için düzenli olarak gerçekleştirilir.

 Takımlar artımlı olarak tümleştirmek ve iki sistemlerini sınamak için birlikte çalışır. İlk PaymentProcessing uygulamasını ele önce PaymentApprover ve şimdi Yemeği kalanı başka bir işlemle başarılı bir şekilde çalıştığından emin olun.

 Aşağıdaki kod Haritası şimdi Yemeği ve PaymentApprover arasındaki yeni çağrıları gösterir:

 ![Güncelleştirilmiş bağımlılık grafiğinin tümleşik sistemiyle](../modeling/media/depgraph_intsystem.png "DepGraph_IntSystem")

 **Güncelleştirilmiş yöntem çağrılarını kod Haritası**

 Sistem beklendiği gibi çalıştığını onayladıktan sonra şimdi Yemeği PaymentProcessing kodunu açıklamalar. Katman doğrulama raporları temiz ve sonuçta elde edilen kod Haritası PaymentProcessing bağımlılığının bulunmadığını gösterir:

 ![Bağımlılık grafiğinin PaymentProcessing olmadan](../modeling/media/depgraph_nomore.png "DepGraph_NoMore")

 **Kod Haritası PaymentProcessing olmadan**

#### <a name="drawing-a-dependency-diagram"></a>Bir bağımlılık diyagramı çizme

Bir bağımlılık diyagramı aşağıdaki önemli özelliklere sahiptir:

- *Katmanlar* yapılarının mantıksal gruplar açıklanmaktadır.

- A *bağlantı* bir katman ve bir yapı arasındaki ilişkidir.

     Yapılardan katmanlar oluşturmak için Çözüm Gezgini'nde, kod haritalarını, sınıf görünümü ya da Nesne Tarayıcısı öğeleri sürükleyin. Yeni Katmanlar çizmek ve bunları yapılara bağlamak için araç kutusunu kullanın veya katmanları oluşturmak için diyagram yüzeyine sağ tıklayın ve ardından bu katmanlara öğeleri sürükleyin.

     Bir katmana numarasını katmana bağlı yapıların sayısını gösterir. Bu yapıtların ad alanları, projeler, sınıfları, yöntemleri vb. olabilir. Bir katmandaki yapı sayısını yorumlayabilir, aşağıdakileri unutmayın:

    - Bir katman diğer yapıları içeren bir yapıya bağlanırsa, ancak katman doğrudan diğer yapılara bağlanmazsa, sayı yalnızca bağlı yapıyı içerir. Bununla birlikte, diğer yapılar katman doğrulanırken analiz için alınır.

         Örneğin, bir katman tek bir ad alanına bağlanırsa, ad alanı sınıflar içerse bile, bağlı yapıların sayısı 1'dir. Katmanın ad alanındaki her bir sınıfa da bağlantıları bulunuyorsa, sayı bağlantılı sınıfları da içerecektir.

    - Bir katman yapılarla bağlantılı diğer katmanları içeriyorsa, kapsayıcı katman da üzerindeki sayı bu yapıları içermese bile bu yapılara bağlıdır.

     Bir katmana bağlı yapıları görmek için bağımlılık sağ tıklayın ve ardından **bağlantıları görüntüleme** açmak için **Katman Gezgini**.

- A *bağımlılık* bir katmanın işlevselliği kullanabileceğini gösterir başka bir katmanında ancak tersi geçerli değildir. A *çift yönlü bağımlılık* bir katmanın işlevselliği kullanabileceğini gösterir başka bir katmanında ve tersi.

     Var olan bağımlılıkları bağımlılık diyagramı görüntülemek için diyagram yüzeyine sağ tıklayın ve ardından **Bağımlılıklar Oluştur**. Hedeflenen bağımlılıklarını tanımlamak için yenilerini çizin.

Bkz.

- [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)

- [Bağımlılık Diyagramları: Başvuru](../modeling/layer-diagrams-reference.md)

- [Bağımlılık Diyagramları: Yönergeler](../modeling/layer-diagrams-guidelines.md)

- [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)

#### <a name="summary-strengths-of-dependency-diagrams"></a>Özet: Bağımlılık Şemalarının Gücü

Bağımlılık diyagramları yardımcı olur:

- İşlevselliği göre sistem yapılarının mantıksal mimarisini tanımlar.

- Kod geliştirme altında belirtilen tasarıma uyduğundan emin olun.

#### <a name="relationship-to-other-diagrams"></a>Diğer Diyagramlarla İlişki

|**Diyagramı**|**Açıklama**|
|-----------------|---------------------|
|Kod Haritası|Kuruluş ve varolan koddaki ilişkileri görselleştirin.<br /><br /> Katmanlar oluşturmak için bir kod Haritası Oluştur ve olası Katmanlar olarak harita üzerinde öğeleri grubu. Grupları eşlemesinden bağımlılık diyagrama sürükleyin.<br /><br /> Bkz.<br /><br /> - [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)<br />- [Gözat ve kod haritalarını bunları yeniden düzenleme](../modeling/browse-and-rearrange-code-maps.md)|

## <a name="external-resources"></a>Dış Kaynaklar

|**Kategori**|**Bağlantılar**|
|------------------|---------------|
|**Forumları**|- [Visual Studio Görselleştirme ve Modelleme Araçları](http://go.microsoft.com/fwlink/?LinkId=184720)<br />- [Visual Studio Görselleştirme ve modelleme SDK (DSL araçları)](http://go.microsoft.com/fwlink/?LinkId=184721)|

## <a name="see-also"></a>Ayrıca bkz.

- [Kodu görselleştirme](../modeling/visualize-code.md)
- [Geliştirme sürecinizde modelleri kullanma](../modeling/use-models-in-your-development-process.md)
- [Çevik Geliştirme modelleri kullanma](http://msdn.microsoft.com/592ac27c-3d3e-454a-9c38-b76658ed137f)
- [Geliştirme sırasında sisteminizi doğrulama](../modeling/validate-your-system-during-development.md)
