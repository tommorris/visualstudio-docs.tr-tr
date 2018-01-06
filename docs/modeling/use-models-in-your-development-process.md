---
title: "Geliştirme sürecinizde modelleri kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords: UML, using models
ms.assetid: a33ac8fc-4ba0-4850-b71b-014dc8674e54
caps.latest.revision: "29"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.workload: multiple
ms.openlocfilehash: 4a93b60cfac2bbc727fbc2a7b4054c4e7b8e3dce
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="use-models-in-your-development-process"></a>Geliştirme sürecinizde modelleri kullanma
Visual Studio'da anlamak ve bir sistem, uygulama veya bileşen değiştirmenize yardımcı olmak için bir model kullanabilirsiniz. Bir model sisteminizin çalıştığı world görselleştirme, kullanıcıların ihtiyaçlarını açıklamak, sisteminizin mimarisiyle tanımlamak, kodu çözümlemenize ve kodunuzun gereksinimleri karşıladığından emin olun yardımcı olabilir. Bkz: [kanal 9 Video: modelleme mimarisine artırmak](http://go.microsoft.com/fwlink/?LinkID=252078).  
  
 Visual Studio hangi sürümlerinin her türde bir model desteklediğini görmek için bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="how-to-use-models"></a>Modelleri kullanma  
 Modelleri çeşitli şekillerde yardımcı olabilir:  
  
-   Modelleme diyagramları çizim, gereksinimler, mimari ve üst düzey tasarımı ilgili kavramları açıklamak yardımcı olur. Daha fazla bilgi için bkz: [Model kullanıcı gereksinimlerini](../modeling/model-user-requirements.md).  
  
-   Modeller ile çalışmak gereksinimlerdeki tutarsızlıkları kullanıma yardımcı olabilir.  
  
-   Modeller ile iletişim kurarken önemli kavramları iletişim yardımcı değerinden muğlak doğal dili. Daha fazla bilgi için bkz: [uygulama Mimarinizi Model](../modeling/model-your-app-s-architecture.md).  
  
-   Modeller, kod veya veritabanı şemaları ve belgeler gibi diğer yapılarını oluşturmak için bazen kullanabilirsiniz. Örneğin, modelleme bileşenlerinin [!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)] bir modelden oluşturulur.  Daha fazla bilgi için bkz: [oluştur ve uygulamanızı modeller aracılığıyla yapılandırma](../modeling/generate-and-configure-your-app-from-models.md).  
  
 Çok çeşitli işlemlerden aşırı yüksek Çevik seremoni modellerinde kullanabilirsiniz.  
  
### <a name="use-models-to-reduce-ambiguity"></a>Belirsizliği azaltmak için modelleri kullanın  
 Model oluşturma dili doğal dil az belirsizdir ve genellikle yazılım geliştirme sırasında gereken fikirleri ifade etmek için tasarlanmıştır.  
  
 Projeniz Çevik uygulamaları takip küçük bir ekibe sahipse, kullanıcı hikayeleri açıklığa kavuşturmak amacıyla modelleri kullanabilirsiniz. Müşterinin gereksinimlerine hakkında ile tartışmalara bir model oluşturma yararlı soruları çok daha hızlı ve ani veya prototip kod yazma daha geniş bir alan, ürün arasında oluşturabilir.  
  
 Projenizi büyük ve dünya farklı kısımlarını takımlar içeriyorsa, gereksinimleri ve mimariyi düz metin olarak yapabileceğiniz çok daha etkili iletişim yardımcı olmak için modelleri kullanabilirsiniz.  
  
 Her iki durumda da neredeyse her zaman bir model oluşturma tutarsızlıklar ve belirsizlikleri önemli bir azalmayla sonuçlanır. Farklı Paydaşlar sık sistem çalıştığı iş dünyanın farklı anlayışları, ve farklı geliştiriciler sık sisteminin nasıl çalıştığı, farklı anlayışları sahiptir. Bir modeli kullanarak bir tartışma odağı olarak genellikle bu farklılıkları gösterir. Bir model tutarsızlıkları azaltmak için nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [Model kullanıcı gereksinimlerini](../modeling/model-user-requirements.md).  
  
### <a name="use-models-with-other-artifacts"></a>Modelleri diğer yapılar ile kullanma  
 Bir model tek başına bir gereksinimler belirtimi veya bir mimari değil. Bunlardan bazı yönlerini daha net bir şekilde ifade etmek için bir araç olan, ancak yazılım tasarımı sırasında gerekli tüm kavramlar ifade edilebilir. Modelleri bu nedenle iletişimin OneNote sayfalarını veya paragrafları gibi başka bir şekilde birlikte kullanılmalıdır, Microsoft Office belgeleri, iş öğelerini [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)], ya da proje yer duvarında Yapışkan Notlar. Son öğenin dışında tüm bu nesne türleri için model öğelerini bölümleri bağlanabilir.  
  
 Normalde modeller ile birlikte kullanılan diğer yönlerini belirtimi arasında şunlar yer alır. Ölçek ve stil projenizin bağlı olarak birkaç bu yönlerinin kullanın veya herhangi bir hiç kullanmamak:  
  
-   Kullanıcı hikayeleri. Kullanıcı hikayesi kullanıcıları ve projenin yineleme birinde teslim edilecek sistemin davranışı durumunun diğer Paydaşlar ile açıklanan kısa bir açıklamasıdır. "Müşteri yapabilirsiniz..." tipik kullanıcı hikayesi başlar Kullanıcı hikayesi kullanım örnekleri grubunu getirebilir veya önceden geliştirilmiş kullanım durumlarının uzantıları tanımlayabilirsiniz. Tanımlama veya kullanım örneklerini genişletme kullanıcı hikayesinin daha anlaşılır yardımcı olun.  
  
-   Değişiklik istekleri. Bir değişiklik isteğini daha resmi projesinde, kullanıcı hikayesi Çevik projesinde çok benzer. Çevik yaklaşım önceki yinelemelerde geliştirilmiş olan için tüm gereksinimleri değiştikçe değerlendirir.  
  
-   Kullanım örneği açıklaması. Kullanım örneği, bir kullanıcının belirli bir hedefe ulaşmak için kullanıcının sistem ile etkileşimde bulunan bir yolunu temsil eder. Tam açıklama hedef, ana ve alternatif dizileri olayları ve olağanüstü sonuçları içerir. Kullanım örneği diyagramı özetlemek ve kullanım örneklerini genel bir bakış sağlayan yardımcı olur.  
  
-   Senaryoları. Bir senaryodur nasıl sistem, kullanıcılar ve diğer sistemler değeri katılımcılara sunmak için birlikte çalışan gösteren olayların sırası oldukça ayrıntılı bir açıklaması. Kullanıcı arabiriminin slide show ya da kullanıcı arabiriminin bir prototip sürebilir. Bir kullanım örneği veya kullanım örnekleri dizisini açıklayabilirsiniz.  
  
-   Sözlük. Projenin gereksinimler sözlüğü, müşterilerin kendi world ele kelimeleri açıklar. Kullanıcı arabirimi ve gereksinimler modeli de bu koşulları kullanmanız gerekir. Sınıf diyagramında Bu terimlerin birçoğu arasındaki ilişkileri açıklanmasına yardımcı olabilir. Sözlük ve diyagramları oluşturma yalnızca kullanıcılar ve geliştiriciler arasında anlamaları azaltır, ancak ayrıca neredeyse her zaman farklı iş Paydaşlar arasındaki yanlış anlamaları kullanıma sunar.  
  
-   İş kuralları. Birçok iş kuralları ilişkilendirmeler ve öznitelikler gereksinimleri sınıf modelindeki değişmez kısıtlamalar ve sıralı diyagramlar kısıtlamalar olarak ifade edilebilir.  
  
-   Üst düzey tasarımı. Başlıca parçaları ve onların birlikte nasıl uyduğunu açıklar. Bileşen, dizi ve arabirim diyagramları üst düzey tasarımı önemli bir parçasıdır.  
  
-   Tasarım desenleri. Tasarımın sistem farklı bölümleri arasında paylaşılan kurallarını açıklar.  
  
-   Sınama belirtimleri. Test betikler ve test kodu için tasarımlar, sınama adımları dizisini açıklamak üzere etkinlik ve sıralı diyagramlar iyi kullanımını yapabilirsiniz. Böylece gereksinimleri değiştiğinde bunlar kolayca değiştirilebilir sistem testleri gereksinimler modeli açısından ifade edilmelidir.  
  
-   Proje planı. Proje planı veya biriktirme listesi her özelliğin teslim zaman tanımlar. Her bir özelliğin ne durumları ve uygulayan veya genişletir iş kurallarını kullanmak belirterek tanımlayabilirsiniz. Doğrudan planında ya da iş kuralları ve kullanım örnekleri için başvurabilir veya ayrı bir belge bir özellikler kümesi tanımlayabilir ve planda özellik başlıklarını kullanın.  
  
### <a name="use-models-in-iteration-planning"></a>Yineleme Planlama modelleri kullanma  
 Tüm projeleri, ölçek ve kuruluşun farklı olmasına rağmen tipik bir proje yinelemelerini altı ve iki hafta arasında bir dizi olarak planlanmaktadır. Sonraki yinelemelerden planları ve kapsamını ayarlamak için kullanılacak Erken yinelemeler görüşleri izin vermek için yeteri kadar yineleme planlama önemlidir.  
  
 Aşağıdaki öneriler yinelemeli projesinde modelleme faydaları hayata geçirmek yardımcı olmak yararlı bulabilirsiniz.  
  
#### <a name="sharpen-focus-as-each-iteration-approaches"></a>Her yineleme yaklaşımlar Odağı Keskinleştirme  
 Her yineleme yaklaşımı olarak modelleri yinelemenin sonunda teslim edilecek nedir tanımlamaya yardımcı olmak için kullanın.  
  
-   Erken yinelemeler ayrıntılı her şeyi model yok. İlk yinelemede kullanıcı sözlüğündeki ana öğeler için bir sınıf diyagramı oluşturmak, önemli kullanım örneklerini diyagramı ve ana bileşenlerini diyagramı çizin. Ayrıntı daha sonra projede değişir olduğundan bunları ince ayrıntılarıyla tanımlamaz. Özellikler veya kullanıcı hikayelerini listesini oluşturmak için bu modelde tanımlanmış terimleri kullanın. Yaklaşık proje boyunca tahmini iş yükünü dengelemek için yinelemelere özellikler atayın. Daha sonra projede bu atamaları değiştirecek.  
  
-   En önemli kullanım örneklerini Basitleştirilmiş sürümleri erken yineleme uygulamak deneyin. Genişletme olanlar sonraki yinelemelerde kullanım. Bu yaklaşım gereksinimlerinde bir kusur veya hakkında herhangi bir şey yapmak için çok geç proje mimarisinde keşfetme riskini azaltmaya yardımcı olur.  
  
-   Her yineleme sonuna yakın gereksinimleri veya sonraki yinelemede geliştirilen kullanıcı hikayelerini ayrıntılı olarak tanımlamak için gereksinimler Atölyesi tutun. Kullanıcılar ve geliştiriciler ve sistem sınayıcılar yanı sıra önceliklerini, karar verebilirsiniz iş Paydaşlar davet edin. 2 haftalık yineleme için gereksinimleri tanımlamak üç saat izin verir.  
  
-   Atölye amacı, sonraki yinelemeye ucu tarafından elde kabul herkese içindir. Modelleri araçlardan biri gereksinimleri belirlemenize yardımcı olması için kullanın. Yineleme Biriktirme Atölye çıktısını listesidir: geliştirme listesini diğer bir deyişle, görevlerinin [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] ve test paketleri [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)].  
  
-   Geliştirme görevleri için tahminleri belirlemek yalnızca gereksinim duyduğunuz kadar duymanıza gereksinimleri Atölye içinde tasarımı tartışın. Aksi takdirde kullanıcıların doğrudan deneyebileceği sistem davranışını tartışmaya tutun. Gereksinimler modelini mimari modelden ayrı tutun.  
  
-   Yedeğin Paydaşlar genellikle sizden biraz kılavuzluk ile UML diyagramlarını anlama herhangi bir sorun vardır.  
  
#### <a name="link-model-to-work-items"></a>İş öğeleri için bağlantı modeli  
 Gereksinimler Atölyesi sonra gereksinimler modeli ayrıntılarını özenli ve modeli geliştirme görevlerine bağlayın. Bu iş öğelerini bağlantılandırarak yapmak [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] model öğelerine.
  
 İş öğeleri için herhangi bir öğe bağlayabilirsiniz, ancak en yararlı öğeler aşağıdaki gibidir:  
  
-   İş kurallarını veya hizmet gereksinimlerinin kalitesini açıklayan yorumlar. Daha fazla bilgi için bkz: [Model kullanıcı gereksinimlerini](../modeling/model-user-requirements.md).  
  
#### <a name="link-model-to-tests"></a>Testleri bağlantı modeli  
 Kabul testleri tasarım kılavuzu için gereksinimler modeli kullanın. Bu testler eşzamanlı olarak geliştirme iş oluşturun.  
  
 Bu teknik hakkında daha fazla bilgi için bkz: [model aracılığıyla test geliştirme](../modeling/develop-tests-from-a-model.md).  
  
#### <a name="estimate-remaining-work"></a>Kalan işi tahmin etme  
 Gereksinimler modeli, her bir yineleme boyutuna göre proje toplam boyutunu tahmin yardımcı olabilir. Sayısı ve karmaşıklığı kullanım örnekleri ve sınıfların değerlendiriliyor gerekir geliştirme iş tahmin etmenize yardımcı olabilir. Ne zaman ilk birkaç yineleme kapsanan gereksinimler karşılaştırması tamamladınız ve gereksinimlerini karşılamak için hala yaklaşık bir maliyet ölçüsü ve rest projenin kapsamını verebilirsiniz.  
  
 Her yineleme sonuna yakın gelecek yinelemeler için gereksinimlerin atamasını gözden geçirin. Kullanım örneği diyagramı içindeki bir alt sistemi olarak her bir yineleme sonunda yazılım durumunu göstermek için yararlı olabilir. Tartışmalara kullanım örnekleri taşıyın ve kullanım örneği uzantıları bu alt sistemleri birinden diğerine.  
  
## <a name="levels-of-abstraction"></a>Soyutlama düzeyleri  
 Modelleri soyutlama yazılım ile ilgili olarak bir dizi vardır. En somut modeller doğrudan program kodunu gösterir ve en soyut modeller olabilir ya da koddaki temsil edilmeyen iş kavramlarını temsil eder.  
  
 Bir model birçok türdeki diyagram görüntülenebilir. Modelleri ve diyagramları hakkında daha fazla bilgi için bkz: [uygulamanız için model oluşturma](../modeling/create-models-for-your-app.md).  
  
 Farklı türlerdeki diyagram soyutlama farklı düzeylerde tasarım açıklamak için yararlıdır. Çoğu diyagram türlerinin birden fazla düzeyde yararlıdır. Bu tablo her diyagram türünün nasıl kullanılabileceğini gösterir.  
  
|Tasarım düzeyi|Diyagram türleri|  
|------------------|-------------------|  
|İş işlemi<br /><br /> İçinde sisteminizi kullanılacak bağlamı anlamak kullanıcıların ondan gerekenler anlamanıza yardımcı olur.|-Kavramsal sınıf diyagramları iş işlemi içinde kullanılan iş kavramlarını açıklar.|  
|Kullanıcı gereksinimleri<br /><br /> Kullanıcıların sisteminizden gerekenler tanımı.|-İş kuralları ve Hizmet gereksinimlerinin kalitesi ayrı belgelerde açıklanabilir.|  
|Üst düzey tasarım<br /><br /> Sistem genel yapısını: ana bileşenler ve onların birlikte nasıl eşleştiği.|-Bağımlılık diyagramları sistemin bölümler halinde nasıl yapılandırıldığını açıklar. Program kodunu mimariye uyduğundan emin olmak için bağımlılık diyagramları karşı doğrulayabilirsiniz.|  
|Kod çözümleme<br /><br /> Diyagramları koddan oluşturulabilir.|-Bağımlılık diyagramları sınıflar arasındaki bağımlılıkları gösterir. Güncelleştirilmiş kod bir bağımlılık diyagramına karşı doğrulanabilir.<br />-Sınıf diyagramları kodda sınıfları gösterir.|  
  
## <a name="external-resources"></a>Dış Kaynaklar  
  
|**Kategori**|**Bağlantılar**|  
|------------------|---------------|  
|**Videolar**|![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [MSDN nasıl yapmak ı videolar: oluşturma ve kullanma UML modellerini ve diyagramları (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkId=214460)<br /><br /> ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Visual Studio 2010 ile UML](http://go.microsoft.com/fwlink/?LinkID=201106)<br /><br /> ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo") [MSDN nasıl yapmak ı serisi: UML araçları ve genişletilebilirlik (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkID=214467)|  
|**Forumları**|-   [Visual Studio Görselleştirme ve Modelleme Araçları](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio Görselleştirme ve modelleme SDK (DSL araçları)](http://go.microsoft.com/fwlink/?LinkId=184721)|  
|**Bloglar**|[Visual Studio ALM + Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=201340)|  
|**Teknik makaleler ve günlükleri**|[MSDN Mimari Merkezi](http://go.microsoft.com/fwlink/?LinkId=201343)<br /><br /> [Visual Studio Mimari Araç Kullanımı Kılavuzu](../modeling/visual-studio-architecture-tooling-guidance.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çevik Geliştirme modelleri kullanma](http://msdn.microsoft.com/en-us/592ac27c-3d3e-454a-9c38-b76658ed137f)   
 [Uygulamanız için model oluşturma](../modeling/create-models-for-your-app.md)   
 [Kullanıcı gereksinimlerini modelleme](../modeling/model-user-requirements.md)   
 [Uygulama Mimarinizi modeli](../modeling/model-your-app-s-architecture.md)   
 [Model aracılığıyla test geliştirme](../modeling/develop-tests-from-a-model.md)   
 [Modelleme çözümünüzün yapısını oluşturma](../modeling/structure-your-modeling-solution.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
