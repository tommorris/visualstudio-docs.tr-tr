---
title: "Uygulamanızı &#39; model s mimarisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: UML, modeling architecture
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ce471f2229744c9ee72f16a3b784f9e09823375d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="model-your-app39s-architecture"></a>Uygulamanızı &#39; model s mimarisi
Yazılım sistem veya uygulama kullanıcılarınızın karşıladığından emin olmak için gereken, Visual Studio'da modelleri genel yapısı, açıklaması ve yazılımı sistem veya uygulama davranışını bir parçası olarak oluşturabilirsiniz. Modelleri kullanarak tasarım boyunca kullanılan desenleri de tanımlayabilirsiniz. Bu modeller var olan mimarisi anlamak, değişiklikleri ele ve, ilkenizin amacını açıkça iletişim yardımcı olur.  
  
 Bu özellik, Visual Studio'nun hangi sürümleri desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Doğal dil açıklamasında ortaya belirsizlikleri azaltmak ve siz ve arkadaşlarınız tasarım görselleştirmek ve Alternatif tasarımlar tartışmak için yardımcı olmak için bir model amacı budur. Bir model, diğer belge ve tartışmaları ile birlikte kullanılmalıdır. Tek başına bir model mimarisinin tam bir belirtimini göstermiyor.  
  
> [!NOTE]
>  Bu konu içinde "Sistem" geliştirdiğiniz yazılım anlamına gelir. Büyük bir koleksiyon birçok yazılım ve donanım bileşeni veya tek bir uygulama ya da bir uygulamanın parçası olabilir.  
  
 Bir sistem mimarisi iki alana ayrılabilir:  
  
-   [Üst düzey tasarımı](#Structure). Bu, ana bileşenler ve her gereksinimi karşılamak için birbirleriyle nasıl etkileşim kurduklarını açıklar. Sistem büyük olursa, her bileşenin daha küçük bileşenlerden nasıl oluştuğunu gösteren kendi üst düzey tasarımı olabilir.  
  
-   [Tasarım desenleri](#Patterns) ve bileşenlerin tasarımları boyunca kullanılan kuralları. Bir programlama hedefini sağlamak için belirli bir yaklaşım bir deseni açıklar. Bir tasarım boyunca aynı desenleri kullanarak, ekibiniz değişiklik yapmadan ve yeni bir yazılım geliştirme maliyetini azaltabilir.  
  
##  <a name="Structure"></a>Üst düzey tasarımı  
 Üst düzey tasarımı, sisteminize ve tasarım hedeflerinize ulaşmak için birbirleriyle nasıl etkileşim kurduklarını ana bileşenlerini açıklar. Aşağıdaki listede etkinlikleri, mutlaka belirli bir sırada ancak üst düzey tasarımı geliştirirken ilgilidir.  
  
 Var olan kodu güncelleştiriyorsanız başlıca bileşenleri açıklayarak başlayabilirsiniz. Kullanıcı gereksinimlerinde yapılacak değişiklikler anlamak ve eklediğinizde veya değiştirdiğinizde bileşenler arasındaki etkileşimler emin olun. Yeni bir sistem geliştiriyorsanız, kullanıcıların ihtiyaçlarını ana özelliklerini anlayarak başlayın. Ana kullanım örnekleri için etkileşim dizileri keşfedin ve bileşen tasarım dizilere birleştirin.  
  
 Her durumda, farklı etkinlikleri paralel geliştirmek ve kod geliştirmeye yardımcı olur ve erken bir aşamada sınar. Başka birine başlamadan önce bu yönlerden birini tamamlamaya çalışırken kaçının. Genellikle, yazma ve kodu test ederken gereksinimleri ve sistemi tasarlamak için en iyi yolu Anlayışınızı değiştirir. Bu nedenle, anlama ve gereksinimlerin ve tasarımınızın ana özelliklerini kodlama başlamalısınız. Projenin sonraki yinelemelerden ayrıntıları doldurun.  
  
-   [Gereksinimleri anlama](#Requirements). Başlangıç herhangi tasarım Kullanıcıların ihtiyaçlarını NET bir anlayış noktasıdır.  
  
-   [Mimari desenler](#BigDecisions). Çekirdek teknolojiler ve sistem mimari öğeleri hakkında yaptığınız seçimler.  
  
-   Veri modeli, bileşenleri ve arabirimleri. Bileşenleri arasında geçirilen ve bileşenler içinde depolanan bilgileri açıklamak için sınıf diyagramları çizebilirsiniz.  
  
##  <a name="Requirements"></a>Gereksinimleri anlama  
 Tam bir uygulamanın üst düzey tasarımı gereksinimler modeli veya diğer kullanıcıların ihtiyaçlarını açıklaması ile birlikte en verimli şekilde geliştirilmiştir. Gereksinimleri modelleri hakkında daha fazla bilgi için bkz: [Model kullanıcı gereksinimlerini](../modeling/model-user-requirements.md).  
  
 Geliştirdiğiniz sistem daha büyük bir sistem bileşenidir, bir kısmı veya tümü gereksinimlerinizi programlama arabirimleri gerçekleştirilen.  
  
 Gereksinimler modeli Bu önemli bilgi parçalarını sağlar:  
  
-   Arabirimleri sağlanır. İnsan kullanıcılara veya diğer yazılım bileşenleri olup sağlanan arabirimi Hizmetleri veya sistemin veya bileşenin kendi kullanıcılara sağlamanız gerekir işlemleri listeler.  
  
-   Gerekli arabirimleri. Gerekli bir arabirim hizmet veya sistem veya bileşenin kullanabileceği işlemleri listeler. Bazı durumlarda, tüm hizmetlerin kendi sisteminin bir parçası tasarlamanız mümkün olacaktır. Diğer durumlarda, özellikle birçok yapılandırmada diğer bileşenlerle birlikte bir bileşen tanımlıyorsanız gereken arabirim dış etkenler tarafından ayarlanır.  
  
-   Hizmet gereksinimlerinin kalitesi. Performans, güvenlik, sağlamlık ve diğer hedefleri ve sistemin karşılaması gereken kısıtlamalar.  
  
 Kişiler veya diğer yazılım bileşenleri olup gereksinimler modeli açısından bakıldığında, sisteminizin kullanıcılarının yazılır. Sisteminizin iç işleyişi hiçbir şey bildikleri. Bunun aksine, bir mimari modelde hedefiniz iç işleyişi açıklamak ve kullanıcıların nasıl karşıladıklarından göstermek için gereken ' dir.  
  
 Gereksinimleri ve mimari modelleri ayrı tutmak yararlıdır çünkü gereksinimleri kullanıcılarla tartışmak kolaylaştırır. Ayrıca, tasarımı yeniden düzenlemeniz ve gereksinimleri değişmeden tutarken alternatif mimarileri göz önünde bulundurun yardımcı olur.  
  
 Gereksinimler veya bir mimari modeli yerleştirileceği ayrıntı miktarını ve proje boyutu ölçeği ve dağıtım ekibi bağlıdır. Kısa bir projedeki küçük bir ekip iş kavramları ve bazı tasarım desenleri sınıf diyagramı tasarlamaktan daha başka geçebilir; içinde birden fazla bölgeye dağıtılmış büyük bir proje önemli ölçüde daha fazla ayrıntı gerekir.  
  
##  <a name="BigDecisions"></a>Mimari desenleri  
 Geliştirme içinde bir ana teknolojileri ve tasarım bağlı öğeleri seçmeniz gerekir. Bu seçenekler hale getirilmesi gereken alanlar şunlardır:  
  
-   Bir veritabanı ve dosya sistemi ve ağa bağlı bir uygulama ve bir Web istemcisi arasında seçim arasında seçim gibi teknoloji seçimleri temel vb. kullanın.  
  
-   Windows Workflow Foundation veya ADO.NET Entity Framework arasında bir seçim gibi çerçeveleri seçenekleri.  
  
-   Örneğin bir kurumsal hizmet veri yolu veya noktadan noktaya kanal arasında tümleştirme yöntemi seçenekleri.  
  
 Bu seçenekler sık ölçek ve esneklik gibi hizmet gereksinimlerinin kalitesi tarafından belirlenir ve ayrıntılı gereksinimler bilinmeden önce yapılabilir. Büyük bir sistemde, donanım ve yazılım yapılandırmasını kesinlikle birbiriyle ilişkilidir.  
  
 Yaptığınız seçimleri kullanın ve Mimari modeli yorumlama nasıl etkiler. XML dosyalarını temel alan bir sistemde, ilişkilendirmeleri XPath kullanmak çapraz işaret ediyor olabilir ancak örneğin, bir veritabanı kullanan bir sistemde, sınıf diyagramında ilişkilendirmeleri ilişkileri veya veritabanındaki yabancı anahtarlar gösterebilir. Dağıtılmış bir sistemde, sıralı diyagram iletilerinde kablo üzerindeki iletileri gösterebilir; kendi içinde bulunan bir uygulamada işlev çağrılarını temsil edebilir.  
  
##  <a name="Patterns"></a>Tasarım desenleri  
 Bir tasarım deseni belirli bir yazılım sistem farklı kısımlarını yinelenen bir özellikle durumuyla tasarlamak nasıl ana hattı ' dir. Tekdüzen bir yaklaşım projede kabul ederek, tasarımın maliyetini azaltabilir, kullanıcı arabiriminde tutarlılığı sağlamak ve maliyetini anlama ve kodunu değiştirme.  
  
 Bazı genel tasarım desenleri gözlemci gibi bilinen ve yaygın olarak uygulanabilir. Ayrıca, yalnızca projenize uygulanabilir desenleri vardır. Örneğin, bir Web satış sisteminde olacaktır koddaki çeşitli işlemleri değişiklikler Müşteri'nin siparişe burada yapılır. Sipariş durumunu doğru şekilde her aşamada görüntülendiğinden emin olmak için tüm bu işlemler veritabanını güncelleştirmek için belirli bir protokol izlemeniz gerekir.  
  
 Yazılım mimarisi iş parçası olan desenleri olması gerektiğini belirlemek için tasarım boyunca benimsenen. Yeni desenleri ve varolan desenleri geliştirmeler Proje ilerledikçe bulunan genellikle devam eden bir görev olmasıdır. Böylece her önemli tasarım desenleri erken aşamada çalışma geliştirme planı düzenlemek yararlıdır.  
  
 Çoğu tasarım desenleri kısmen framework kodunda. Desen parçası belirli sınıfları ve veritabanı doğru işlendiğini sağlar bir veritabanı erişim katmanı gibi bileşenleri kullanmak Geliştirici isteyerek azaltılabilir.  
  
 Bir tasarım deseni bir belgede açıklanır ve genellikle aşağıdaki bölümleri içerir:  
  
-   Adı.  
  
-   Geçerli olduğu bağlam açıklaması. Hangi kriterleri bu deseni uygularken geliştirici olmanız gerekir?  
  
-   Çözdüğü sorunu kısa bir açıklama.  
  
-   Başlıca parçaları ve ilişkilerini modeli. Bu, sınıflar veya bileşenler ve ilişkileri ve aralarındaki bağımlılıkları olan arabirimler olabilir. Öğeleri genellikle iki kategoriye ayrılır:  
  
-   Adlandırma kuralları.  
  
-   Nasıl düzeni sorununu çözer açıklaması.  
  
-   Geliştiriciler benimsemeye olabilir Çeşitlemeler açıklaması.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kodu görselleştirme](../modeling/visualize-code.md)   
 [Kullanıcı gereksinimlerini modelleme](../modeling/model-user-requirements.md)   
 [Model aracılığıyla test geliştirme](../modeling/develop-tests-from-a-model.md)   
 [Geliştirme sürecinizde modelleri kullanma](../modeling/use-models-in-your-development-process.md)