---
title: "Model kullanıcı gereksinimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- requirements
- stories
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0ffbfd6da8abb0063ed16d7956bcec97626c9666
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="model-user-requirements"></a>Kullanıcı gereksinimlerini modelleme
Etkinlikler ve bölümü hakkında diyagramlar çizerek kullanıcıların gereksinimlerini anlamak, ele almaktadır ve visual Studio yardımcı olur, sisteminizi hedeflerine ulaşması yardımcı oynadığı. Gereksinimler modeli her biri kullanıcıların ihtiyaçlarını farklı bir açısını odaklanır bu diyagramları kümesidir. Video gösterimi için bkz: [iş etki alanını modelleme](http://channel9.msdn.com/posts/clinted/UML-with-VS-2010-Part-3-Modeling-the-Business-Domain/).  
  
 Visual Studio hangi sürümlerinin her türde bir model desteklediğini görmek için bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Gereksinimler modeli yardımcı olur:  
  
-   İç tasarımından ayrı olarak sistemin dış davranışı odaklanır.  
  
-   Kullanıcıların açıklar ve Paydaşlar ile doğal dilde daha az belirsizlik gerekiyor.  
  
-   Tutarlı bir kullanıcı, geliştiriciler ve sınayıcılar tarafından kullanılan terimler sözlüğü tanımlar.  
  
-   Boşluklar ve tutarsızlıkları azaltın.  
  
-   Gereksinim değişikliklerine yanıt vermek için gereken çalışmayı azaltır.  
  
-   Özellikler geliştirilecek sipariş planlayın.  
  
-   Modeller, testler ve gereksinimler arasında NET bir ilişki yaparak sistem sınamaları için temel olarak kullanın. Gereksinimleri değiştiğinde, bu ilişki testleri doğru şekilde güncelleştirmenize yardımcı olur. Bu sistem yeni gereksinimleri karşıladığından emin olmanızı sağlar.  
  
 Kullanıcıları veya onların temsilcileriyle olan tartışmalara odaklanmak için kullanırsanız ve her bir yineleme başında yeniden ziyaret gereksinimler modeli en büyük avantajı sağlar. Kod yazmadan önce ayrıntılı olarak tamamlamanız gerekmez. Kısmen çalışan bir uygulama, çok Basitleştirilmiş olsa bile, genellikle en cazip kullanıcılarla gereksinimlerinin tartışma temelini oluşturur. Model bu tartışmalara sonuçları özetlemek için etkili bir yoldur. Daha fazla bilgi için bkz: [geliştirme sürecinizde modelleri kullanma](../modeling/use-models-in-your-development-process.md).  
  
> [!NOTE]
>  Bu konular boyunca "Sistem" Sistem veya geliştirdiğiniz uygulama anlamına gelir. Birçok yazılım ve donanım bileşenleri büyük koleksiyonu olabilir; veya tek bir uygulama; veya daha büyük bir sistem içinde bir yazılım bileşeni. Her durumda, bir kullanıcı arabirimi ya da API aracılığıyla sisteminizi dışında görünür davranışı gereksinimler modeli açıklar.  
  
## <a name="common-tasks"></a>Ortak Görevler  
 Kullanıcıların gereksinimlerini birkaç farklı görünümlerini oluşturabilirsiniz.  Her görünüm belirli türde bilgi sağlar.  Bu görünümler oluşturduğunuzda, sık birinden diğerine taşımak en iyisidir. Herhangi bir görüntüden başlatabilirsiniz.  
  
|Diyagram veya belge|Bu gereksinimler modelinde açıklar|Bölüm|  
|-------------------------|-----------------------------------------------|-------------|  
|Kavramsal sınıf diyagramı|Gereksinimleri tanımlamak için kullanılan türler sözlüğü; görünen türler sistemin arabirimi.||  
|Ek belgeler veya iş öğeleri|Performans, güvenlik, kullanılabilirlik ve güvenilirlik ölçütleri.|[Hizmet gereksinimlerinin kalitesini açıklayan](#QoSRequirements)|  
|Ek belgeler veya iş öğeleri|Sınırlamalar ve kurallar için belirli bir özel olmayan kullanım örneği|[İş kurallarını gösterme](#BusinessRules)|  
  
 Diyagram türlerinin çoğu diğer amaçlar için kullanılabilir dikkat edin. Diyagram türlerine genel bakış için bkz: [uygulamanız için model oluşturma](../modeling/create-models-for-your-app.md).
  
##  <a name="BusinessRules"></a>İş kurallarını gösterme  
 Bir iş kuralı belirli kullanım örneği ile ilişkili değil ve sistem genelinde uyulması bir gereksinimdir.  
  
 Birçok iş kavramsal sınıflar arasındaki ilişkileri kısıtlamalar kurallardır. Bu yazma *statik ** iş kuralları* kavramsal sınıf diyagramında ilgili sınıflarla ilişkilendirilmiş açıklamalar olarak. Örneğin:  
  
 ![Düzen sınıfına eklenmiş AÇIKLAMADAKİ kural. ] (../modeling/media/uml_reqmcd2.png "UML_ReqmCD2")  
  
 *Dinamik iş kurallarını* izin verilen olaylar dizisi sınırlayın. Örneğin, bir kullanıcı, sisteminizdeki diğer işlemleri gerçekleştirmeden önce oturum açması gerektiğini göstermek için bir dizi veya etkinlik diyagramını kullanın.  
  
 Bununla birlikte, birçok dinamik kural daha etkili ve genel olarak statik kurallarla değiştirerek belirtilebilir. Örneğin, kavramsal sınıf modelinde bir sınıf için bir Boole öznitelikte ' oturum ' ekleyebilirsiniz. Kullanım örneği günlüğüne Sonkoşul olarak oturum ekleyin ve diğer kullanım örnekleri çoğu önkoşulu olarak eklemek. Bu yaklaşım, tüm olası olaylar dizisi birleşimlerini tanımlamaktan kaçının olanak tanır. Yeni kullanım örnekleri modele eklemek gerektiğinde, aynı zamanda daha esnektir.  
  
 Buradaki seçiminiz gereksinimleri nasıl tanımladığınız hakkında olduğuna ve bu nasıl, gereksinimleri ve program kodunda uyguladığınızdan bağımsız olduğuna dikkat edin.  
  
 Aşağıdaki konularda daha fazla bilgi sağlar:  
  
|Hakkında bilgi almak için|Oku|  
|--------------------|----------|  
|İş kurallarına uyduğundan kod nasıl geliştirilir|[Uygulama mimarinizi modelleme](../modeling/model-your-app-s-architecture.md)|  
  
##  <a name="QoSRequirements"></a>Hizmet gereksinimlerinin kalitesini açıklayan  
 Hizmet kalitesi gereksinimleri birkaç kategorisi vardır. Bunlar aşağıdakileri içerir:  
  
-   Performans  
  
-   Güvenlik  
  
-   Kullanılabilirlik  
  
-   Güvenilirlik  
  
-   Sağlamlık  
  
 Bu gereksinimleri bazılarını belirli kullanım durumları açıklamasında ekleyebilirsiniz. Diğer gereksinimler kullanım örneklerine özgü olmayan ve ayrı bir belge en verimli şekilde yazılır. Şunları yapabilirsiniz, gereksinimler modeli tarafından tanımlanan sözlük uyması kullanışlıdır. Aşağıdaki örnekte, gereksinim olarak kullanılan ana sözcüklerin aktörler, kullanım örnekleri ve önceki çizimlerde sınıflarda başlıklarını olduğuna dikkat edin:  
  
 Bir müşteri yemek sıralama sırasında bir restoran menü öğesi silerse, bu menü öğesine başvuran herhangi bir sırada öğesini kırmızı olarak görüntülenir.  
  
 Aşağıdaki konularda daha fazla bilgi sağlar:  
  
|Hakkında bilgi almak için|Oku|  
|--------------------|----------|  
|Hizmet gereksinimlerinin kalitesini kaydetme hakkında daha ayrıntılı bilgi|[Servis kalitesi gereksinimleri tanımlamak için yönergeler](http://msdn.microsoft.com/en-us/9677a437-c2cb-4ac4-8c2d-4e3350005f06)|  
|Hizmet gereksinimlerinin kalitesini aynılarını kod nasıl geliştirilir|[Uygulama mimarinizi modelleme](../modeling/model-your-app-s-architecture.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Geliştirme sürecinizde modelleri kullanma](../modeling/use-models-in-your-development-process.md)   
 [Uygulama mimarinizi modelleme](../modeling/model-your-app-s-architecture.md)   
