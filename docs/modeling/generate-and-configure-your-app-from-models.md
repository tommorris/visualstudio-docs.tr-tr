---
title: "Oluşturmak ve uygulamanızı modeller aracılığıyla yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dc8f572-a09e-4d19-a92d-f1df383e728b
caps.latest.revision: "7"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.workload: multiple
ms.openlocfilehash: a08d7a94dcd512f650564a07a1e6784bffe8c45e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="generate-and-configure-your-app-from-models"></a>Uygulamanızı modeller aracılığıyla oluşturma ve yapılandırma
Oluşturmak veya bir modelden uygulamanızın parçalarını yapılandırın.
  
 Model gereksinimleri kodu daha doğrudan temsil eder. Uygulamanın davranışını doğrudan modelden türetme tarafından değiştirilen gereksinimleri çok daha hızlı ve güvenilir yapmaktan güncelleştirme yanıtlayabilir kodu. Bazı ilk iş türetmeyi kurmak için gerekli olmasa da bu yatırım gereksinimleri değişiklikler bekliyorsanız ya da ürün birkaç çeşidini yapmayı planlıyorsanız döndürülür.  
  
## <a name="generating-the-code-of-your-application-from-a-model"></a>Bir modelden uygulamanızın kod oluşturma  
 Metin şablonları kullanarak kod oluşturmanın en kolay yolu gerçekleşir. Aynı kodu oluşturabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözüm modeli tutun. Daha fazla bilgi için bkz.:  
  
-   [T4 Metin Şablonları Kullanarak Tasarım Zamanı Kodu Oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
-   [Etki Alanına Özgü Dilden Kod Oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)  
  
 Bu yöntem, artımlı olarak uygulamak kolaydır. Yalnızca belirli durumunuz için çalışan bir uygulama ile başlatın ve birkaç bazı bölümleri modelden farklı hale getirmek istediğiniz seçin. Metin şablonu (.tt) dosyaları olduklarında böylece bölümleri kaynak dosyalarını yeniden adlandırın. Bu noktada, uygulama önceden olduğu gibi çalışması için kaynak .cs dosyaları otomatik olarak şablon dosyalarından oluşturulur.  
  
 Ardından kodun bir parçası olması ve model okur ve kaynak dosyasının bu bölümü oluşturur bir metin şablonu ifadesi ile değiştirin. Modelin en az bir değer uygulamayı yeniden çalıştırın ve önceki gibi çalışır, özgün kaynak oluşturmanız gerekir. Farklı model değerlerini test ettikten sonra şablonu ifadeleri kodu başka bir bölümünü eklemek geçebilirsiniz.  
  
 Bu artımlı yöntem kod oluşturma genellikle düşük riskli bir yaklaşım anlamına gelir. Sonuçta elde edilen uygulamalar genellikle neredeyse elle yazılmış bir sürüm yanı sıra gerçekleştirin.  
  
 Ancak, varolan bir uygulama ile başlatırsanız, çok sayıda yeniden düzenleme model tarafından yönetilir ve böylece bağımsız olarak değiştirilebilir farklı davranışları ayırmak için gerekli olduğunu bulabilirsiniz. Projenizin maliyetini tahmin ederken uygulamanın bu yönünün değerlendirmenize öneririz.  
  
## <a name="configuring-your-application-from-a-model"></a>Bir Model uygulamanızdan yapılandırma  
 Çalışma zamanında uygulamanızın davranışını değiştirmek istiyorsanız, uygulama derlenmiş önce kaynak kodunu üretir kod oluşturma kullanamazsınız. Bunun yerine, uygulamanızın modeli okumak ve davranışını buna göre farklılık göstermesi için tasarlayabilirsiniz. Daha fazla bilgi için bkz.:  
  
-   [Nasıl yapılır: Program Kodunda Dosyadan Model Açma](../modeling/how-to-open-a-model-from-file-in-program-code.md)  
  
 Bu yöntem aynı zamanda bir artımlı olarak uygulanabilir, ancak daha fazla iş başında yok. Modeli okumak ve değerlerinin değişken parçaları için erişilebilir olmasını sağlayan bir çerçeve ayarlama kod yazmanız gerekir. Değişken bölümlerin genel yapılması, kod oluşturmaktan daha pahalıdır.  
  
 Genel Uygulama, genellikle kendi belirli ortaklarınıza daha az iyi gerçekleştirir. Performans önemliyse, Proje planınızı Bu risk değerlendirmesini içermelidir.  
  
## <a name="developing-a-derived-application"></a>Türetilen bir uygulama geliştirme  
 Aşağıdaki genel yönergeleri yararlı bulabilirsiniz.  
  
-   **Belirli başlayın, ardından genelleştirin.** Belirli bir sürümü, uygulamanızın ilk yazma. Bu sürüm, bir dizi koşula çalışması gerekir. Memnun kaldığınızda, BT'nin düzgün çalıştığından, bir modelden türetilen bazıları da yapabilirsiniz. Türetilmiş parçaları kademeli olarak genişletir.  
  
     Örneğin, belirli bir dizi Web sayfası bir modelde tanımlanan sayfaları sunan bir Web uygulaması tasarlamadan önce olan bir Web sitesi tasarlayın.  
  
-   **Değişken yönlerini model.** Ya da bir dağıtım ve başka arasında farklılık ya da zamanla gereksinimler değiştirmek yönleri tanımlar. Bir modelden türetilmiş yönleri şunlardır.  
  
     Örneğin, Web sayfaları ve arası bağlantılar, bunları değiştirir, ancak stili ve sayfaların biçimini her zaman aynı model bağlantıları açıklamalıdır ancak sayfaların biçimini açıklamak yok.  
  
-   **Sorunları ayırın.** Değişken yönleri bağımsız alanlara ayrılabilir, ayrı modelleri her alan için kullanın. ModelBus kullanarak, hem modelleri hem de aralarında kısıtlamaları etkileyen işlemler tanımlayabilirsiniz.  
  
     Örneğin, Web sayfalarını ve farklı bir model sayfaların düzenini tanımlamak için arasında gezinme tanımlamak için bir model kullanın.
  
-   **Çözüm gereksinim model.** Kullanıcı gereksinimlerini açıklar model tasarlayın. Bunun aksine, değişken yönlerini göre gösterimi uygulamasının Tasarım değil.  
  
     Örneğin, Web gezinti modeli, Web sayfalarını ve aralarındaki köprüleri temsil etmelidir. Web gezinti modeli HTML parçalarını veya uygulamanızdaki sınıfları temsil etmiyor.  
  
-   **Oluştur ya da yorumla?** Belirli bir dağıtım için gereksinimleri nadiren değişecekse program kodunu modelden oluşturun. Gereksinimleri sık sık değişebilir veya aynı dağıtımda birden fazla değişken içinde birlikte var, böylece okuyun ve bir modeli yorumlama uygulama yazma.  
  
     Bir dizi farklı ve ayrı ayrı yüklenmiş Web siteleri geliştirmek için Web sitesi modelinizi kullanırsanız, örneğin, daha sonra site kodunu modelden oluşturmanız gerekir. Ancak, model okuyan ve siteyi buna göre sunan bir Web sunucusu yazmak daha iyidir sonra her gün değişen bir siteyi denetlemek için modelinizin kullanın.  
  
-   **UML veya DSL?** UML'yi genişletmek için stereotipler kullanarak modelleme gösterimi oluşturmayı düşünün. Amaca uygun herhangi bir UML Diyagramı ise bir DSL tanımlayın. Ancak UML Standart semantiği çiğnemekten kaçının.  
  
     Örneğin, bir UML sınıf diyagramı kutuları ve okları koleksiyonudur; Bu gösterim teorik olarak herhangi bir şey tanımlayabilirsiniz. Ancak burada aslında bir dizi türleri tanımlamakta olduğunuz dışında sınıf diyagramını kullanmanızı önermiyoruz. Örneğin, Web sayfalarının farklı türlerini tanımlamak için sınıf diyagramları uyarlayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir etki alanına özgü dili kod oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)   
 [Nasıl yapılır: Program kodundaki dosyasından bir Model açın](../modeling/how-to-open-a-model-from-file-in-program-code.md)   
 [T4 Metin Şablonları Kullanarak Tasarım Zamanı Kodu Oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md)