---
title: "Etki alanına özgü diller hakkında | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language
ms.assetid: 29e5b6f2-ece4-4f3b-ab08-5f957418702f
caps.latest.revision: "26"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 7bdd5f6f9561e3479d173a1e182ffa07649bc776
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="about-domain-specific-languages"></a>Etki Alanına Özgü Diller Hakkında
Genel amaçlı bir dil C# veya UML gibi bir etki alanına özgü dil (DSL) belirli sorunu boşluk ya da etki alanı deyimlerinde ifade etmek için tasarlanmıştır.  
  
 Normal ifadeler ve SQL tanınmış DSL'ler içerir. Her DSL kendi kapsamı dışındadır fikirleri açıklayan işlemleri metin dizelerini veya bir veritabanı, ancak çok daha da kötüsü açıklamak için genel amaçlı bir dil çok iyidir. Tek tek sektörlerde kendi DSL'ler da vardır. Örneğin, telekomünikasyon sektörün dilleri telefon çağrısında durumları dizisi belirtin ve endüstri hava seyahat için yaygın olarak kullanılan DSL uçuş kayıtları tanımlamak için kullanılan standart bir çağrı açıklaması.  
  
 Projenizi ve işinizin DSL ile açıklanan kavramları özel kümeleriyle de ilgilidir. Örneğin, bu uygulamalardan birini için DSL tanımlayabilirsiniz:  
  
-   Bir Web sitesi gezinti yollarında planı.  
  
-   Bağlantı şemaları elektronik bileşenleri için.  
  
-   Taşıyıcı bantları ve bagaj işleme donanımını havaalanı için ağ.  
  
 DSL tasarlarken, tanımladığınız bir *etki alanı sınıfı* her etki alanında, bir Web sayfası, ampul veya havaalanı iade Masası gibi önemli kavramlar. Tanımladığınız *etki alanı ilişkilerini* köprü, kablo veya kavramları birbirine bağlamak için bir taşıyıcı bandı gibi.  
  
 Kullanıcıları, DSL oluşturmak *modeller.* Modelleri *örnekleri* DSL biri. Örneğin, bunlar belirli bir Web sitesi ya da belirli bir aygıt ya da belirli bir havaalanındaki sistemindeki işleme bagaj kablolama açıklanmaktadır.  
  
 Kullanıcılarınızın bir model diyagramı veya bir Windows formu olarak görüntüleyebilirsiniz. Modeller, XML olarak nasıl depolandığını olduğu de görüntülenebilir. DSL tanımlarken, her etki alanı sınıfı ve ilişki örnekleri kullanıcının ekranda görüntülenme tanımlayın. Tipik bir DSL simgeler veya oklarla bağlı dikdörtgenler koleksiyonu olarak görüntülenir.  
  
 Aşağıdaki şekilde grafiksel bir DSL küçük bir modeli gösterilmektedir:  
  
 ![Tudor Aile Ağacı Modeli](../modeling/media/tudor_familytreemodel.png "Tudor_FamilyTreeModel")  
  
## <a name="what-you-can-do-with-dsls"></a>DSL'ler ile yapabilecekleriniz  
 Program kodunu veya diğer yapıları oluşturmak için DSL, tipik bir uygulamasıdır. DSL tanımladığınızda, tanımlayabilirsiniz *metin şablonları* DSL modelinin okuyun ve metin dosyaları oluşturur.  
  
 Örneğin, bir havaalanındaki planı yapan ve yazılım bagaj, bazı planı açıklayın kullanıcı belgeleri yanı sıra işleme için parçası oluşturmak şablonları yazabilirsiniz.  
  
 DSL tanımlandığında, kendi bilgisayarlarına yükleyebilmek için diğer kullanıcılara dağıtabilirsiniz. DSL kullanıcılarının oluşturabilir ve düzenleyebilir modellerinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 Menü komutlarını da tanımlayabilirsiniz ve kullanıcıların Yardım diğer araçları DSL doğru kullanılır ve kullanıcıların yardımcı öğe şablonları yeni örnekleri oluşturmak sağlamaya yardımcı olmak için doğrulama kısıtlamaları DSL düzenleyin. Bir veya daha fazla DSL'ler kendi Araçlar ve diğer kayabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantıları tümleşik bir pakette olarak.  
  
 Genellikle, bir etki alanına özgü dil birkaç ürünleri için benzer bir kod yazmak bir geliştirme ekibi sahip olduğunda oluşturulur. Örneğin, bagaj işleme sistemlerini uzmanlaşmış bir şirket içinden bunlar bazı yüklemeler için kod oluşturabilirsiniz bagaj izleme DSL tanımlayabilirsiniz. Bunu anladım olduğunu müşterilerine tarafından buradan oluşturulan kodu güvenilirdir ve müşterilerin gereksinimleri değiştirirseniz, sistem'in hızlı bir şekilde güncelleştirilmiş DSL yararları şunlardır.  
  
 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]kendi grafik tasarımcı ve kendi diyagramı gösterimi sahip bir etki alanına özgü dil oluşturun ve her proje için uygun kaynak kodu oluşturmak için dil kullanmak olanak sağlar.  
  
## <a name="domain-specific-development"></a>Etki alanına özgü geliştirme  
 Etki alanına özgü geliştirme bir etki alanına özgü dil kullanarak sonra dil oluşturma ve uygulama geliştiricileri için dağıtma modellenebilir uygulamalarınızı bölümlerini belirleme işlemidir. Geliştiricilerin kendi uygulamalarına özel modelleri oluşturmak, kaynak kodu oluşturmak için modelleri kullanın ve uygulama geliştirmek için kaynak kodunu kullanın etki alanına özgü dil kullanın.  
  
## <a name="aspects-of-graphical-domain-specific-development"></a>Grafik etki alanına özgü geliştirme yönleri  
 Grafik bir etki alanına özgü dil aşağıdaki özellikleri şunları içermelidir:  
  
-   Gösterimi  
  
-   Etki alanı modeli  
  
-   Yapı oluşturma  
  
-   Serileştirme  
  
-   Visual Studio ile Tümleştirme  
  
### <a name="notation"></a>Gösterimi  
 Bir etki alanına özgü dil kolayca tanımlanabilir ve etki alanına özgü yapıları temsil etmek için genişletilmiş öğelerin makul küçük bir kümesini olması gerekir. Öğeleri temsil eder, Şekil ve bir grafik diyagram yüzeyinde öğeleri arasındaki ilişkileri gösteren bağlayıcıları, bir gösterim oluşur. İçinde [!INCLUDE[dsl](../modeling/includes/dsl_md.md)], şekiller genişletilmiş ve etki alanına özgü dil öğelerini göstermek için iyileştirilmiştir.  
  
### <a name="domain-model"></a>Etki alanı modeli  
 Bir etki alanına özgü dil öğeleri ve bunları tutarlı dilbilgisi arasındaki ilişkileri kümesini birleştirmeniz gerekir. Öğe ve ilişki birleşimlerini geçerli olup olmadığını tanımlamalısınız. Örneğin, programlama dilleri, genellikle ikinci sınıfından türetilmiş bir sınıf ve ilk sınıfından türetilen ikinci sınıfı döngüsel devralma engeller. Kısıtlamaları, iş mantığı ifade etmek için de kullanılabilir, örneğin, bir kişi, kendisine bağımlı olamaz. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]kısıtlamaları en etki alanına özgü dil gerektiren kısıtlamaları türlerini ifade etmek için kullanır.  
  
### <a name="artifact-generation"></a>Yapı oluşturma  
 Bir etki alanına özgü dil'ın ana amaçlarından biri, kaynak kodu, bir XML dosyası ya da başka bir kullanılabilir veri bir yapı oluşturmaktır. Genellikle, bir değişiklik modelinde yapı değişiklik anlamına gelir. Kullanabileceğiniz [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] yapıları oluşturmak ve model değiştirdiğinizde, bunları yeniden oluşturmak için.  
  
### <a name="serialization"></a>Serileştirme  
 Bir etki alanına özgü dil düzenlenemez, kaydedildi, kapalı, yeniden ve yönetilebilen bazı formunda kalıcı gerekir. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]tanımlama ve etki alanına özgü dil nasıl serileştirilmiş veya kalıcı özelleştirme olanak sağlayan bir XML biçimi kullanır.  
  
### <a name="integration-with-visual-studio"></a>Visual Studio ile Tümleştirme  
 Çünkü [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] içinde barındırılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], birçok genişletir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] windows ve denetimleri. Ayrıca menü komutları, araç kutusu öğelerini ve diğer öğeleri kullanıcı arabiriminin davranışını özelleştirmenizi sağlar.  
  
 Ayrıca, etki alanına özgü dil için bir Model veri yolu bağdaştırıcısı oluşturabilirsiniz. Bu bağdaştırıcı, başvuru bir model ve model ve erişebilir ve DSL örneği güncelleştirme kod yazmayı sağlar içinde öğelerin sağlar. Güçlü Model veri yolu mekanizmasını kullanarak, yazabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] birden çok modelleriyle çalışacak uzantıları. Aynı zamanda modelleriyle çalışacak bağımsız uygulamalar da yazabilirsiniz. Daha fazla bilgi için bkz: [Visual Studio Modelbus kullanarak modelleri tümleştirme](../modeling/integrating-models-by-using-visual-studio-modelbus.md).  
  
## <a name="benefits-of-domain-specific-development"></a>Etki alanına özgü geliştirme yararları  
 Bir etki alanına özgü dil aşağıdaki faydaları sağlayabilir:  
  
-   Sorun alanı tam olarak sığması yapılar içerir.  
  
     Genel amaçlı dillerinden farklı olarak, bir etki alanına özgü dil öğeleri ve doğrudan sorun alanı mantığı temsil eden ilişkiler oluşur. Örneğin, bir sigorta ilke uygulama ilkeleri ve talepler için öğeleri içermelidir. Bir etki alanına özgü dil, uygulama ve Bul ve mantığı hataları tasarlamak kolaylaştırır.  
  
-   Geliştiriciler olmayan ve genel tasarımı anlamak etki alanı bilmiyorsanız kişilerin olanak sağlar.  
  
     Grafik bir etki alanına özgü dil kullanarak, böylece geliştiriciler olmayan uygulama tasarımını kolayca anlayabileceği görsel bir etki alanı oluşturabilirsiniz.  
  
-   Son uygulama prototipi oluşturmak kolaylaştırır.  
  
     Geliştiriciler, istemcilere gösterebilir bir prototip uygulaması oluşturmak için kendi modeli oluşturur kodu kullanabilirsiniz.  
  
## <a name="the-process-of-domain-specific-development"></a>Etki alanına özgü geliştirme işlemi  
 Etki alanına özgü dil kullanan çoğu yazılım geliştirme ekipleri oluşturmak ve modellerini kullanmak için şu adımları izleyin:  
  
-   Takım etki alanından hiçbir zaman değişiklik bölümleri değişken bölümlerini ayırır.  
  
-   Geliştiriciler sabit bölümleri için kod yazma ve değişken bölümleri için uzantı noktaları bırakın.  
  
-   Sağlama yazılım geliştirici veya Mimarı etki alanı ve değişken bölümleri için uzantı noktaları sabit bölümlerinin tasarım desenleri içeren bir etki alanına özgü dil oluşturur.  
  
-   Sağlama yazılım geliştirici veya Mimarı etki alanına özgü dil takım üreten çeşitli uygulamalar geliştiricilerine dağıtır.  
  
-   Her geliştirici belirli bir uygulamaya uygulanan bir model oluşturur.