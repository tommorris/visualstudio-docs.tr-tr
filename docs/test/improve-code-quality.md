---
title: "Kod kalitesini geliştirme | Microsoft Docs"
ms.custom: na
ms.date: 02/17/2017
ms.reviewer: na
ms.suite: na
ms.technology: vs-devops-test
ms.tgt_pltfrm: na
ms.topic: article
helpviewer_keywords:
- Visual Studio ALM
- team-based development
ms.assetid: 73baa961-c21f-43fe-bb92-3f59ae9b5945
caps.latest.revision: "39"
ms.author: douge
manager: douge
ms.openlocfilehash: 93847beaef971f9370d59a8c5c8ac9f3a59a0967
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="improve-code-quality"></a>Kod Kalitesini Geliştirme
Kod kalitesini nedir? Doğruluk, Bakım ve hatta şıklık harika bir kod oluşturmaya tüm dahil. Tanımladığınız ancak Visual Studio test araçları sizin ve ekibinizin geliştirmek ve kod mükemmel yüksek standartlarını sürdürebilmek için yardımcı olabilir.  
  
 **Gereksinimler**  
  
-   Bazı araçlar ve bu bölümde açıklanan özellikler yalnızca belirli Visual Studio sürümlerinde kullanılabilir — Visual Studio'da Evrensel kullanılabilir değil. Biz bu araçları ve özelliklerinin belgelerindeki belirli edition gereksinimleri listelenmiştir.  
  
## <a name="in-this-section"></a>Bu bölümde  
 Aşağıdaki tabloda, ortak görevler ve bu görevlerin nasıl başarıyla tamamlanıp hakkında daha fazla bilgi bağlantılarını açıklamaları bulabilirsiniz.  
  
|||  
|-|-|  
|[Kodunuza birim testi](../test/unit-test-your-code.md)|Test Gezgini, geliştirme uygulamada birim testleri tümleştirmeyi kolay hale getirir. Microsoft birim test çerçevesi veya birkaç üçüncü taraf ve açık kaynak çerçeveleri birini kullanabilirsiniz.|  
|[Birim testi Visual Studio ile canlı](../test/live-unit-testing.md)|Dinamik birim testi otomatik olarak birim testleri arka planda çalışır ve grafik Visual Studio Kod Düzenleyicisi'nde kod kapsamı ve test sonuçlarını görüntüler.|  
|[Uygulama kalitesini analiz etme](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)|Statik kod çözümleme araçları tasarım, kullanım, maintainablity ve stil sorunları c++'ta bulun ve yönetilen kod. Bu sorunların çoğunu standart sınama ortamında yeniden zor olan hatalarda neden olabilir.|  
|[Ölçüm karmaşıklığı ve yönetilen kod bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)|Kod ölçümleri, geliştirmekte olduğunuz daha iyi bir anlayış kod geliştiricilerin sağlayan yazılım ölçüleri kümesidir. Ölçümleri işlevleri ve sınıfları, işlevleri cyclomatic karmaşıklığını, sınıflar devralma derinliğini ve sınıflar arasında bağ miktarı için bir bakım dizini içerir.|  
  
## <a name="related-scenarios"></a>İlgili senaryolar  
 [Team Services ve TFS için DevOps genel bakış](https://www.visualstudio.com/docs/devops-alm-overview)  
 Visual Studio Team Foundation ve Visual Studio Team Services ile bilginiz yoksa, nasıl, bir takım geliştirme ortamında üretkenliği artırmak ve uygulama geliştirme ile ilişkili riskleri azaltmak için kullanabileceğiniz hakkında daha fazla bilgi edinebilirsiniz.  
  
 [Çözümleme ve mimarinin modelini oluşturma](../modeling/analyze-and-model-your-architecture.md)  
 Kullanabileceğiniz [!INCLUDE[vsPreExt](../test/includes/vspreext_md.md)] talepler ve yazılım tasarlama karmaşıklığını yönetmek için. [!INCLUDE[vsPreShort](../test/includes/vspreshort_md.md)]görsel olarak model hem şimdi var olduğundan ve gelecekte mevcut istediğiniz şekilde uygulamanızı sağlar. Oluşturmak ve fiziksel modelleri eşleme aynı zamanda, uygulamanızın mantıksal modelleri görselleştirmenize yardımcı olmak için diyagramları korumak; Bu, değiştirme, doğrulamak ve "tasarım altında" yazılımını çözümlemek sağlar  
  
 [Uygulamayı test etme](https://www.visualstudio.com/docs/test/overview)  
 Kullanabileceğiniz [!INCLUDE[vsPreShort](../test/includes/vspreshort_md.md)] ve [!INCLUDE[vsUltShort](../test/includes/vsultshort_md.md)] test yaşam döngüsü boyunca daha üretken olma olanağı. [!INCLUDE[vsPreShort](../test/includes/vspreshort_md.md)]veya [!INCLUDE[vsUltShort](../test/includes/vsultshort_md.md)] test çabanızı planlamanıza olanak tanır. Oluşturma, yönetme, düzenlemek ve elle ve otomatik çalıştırma testleri. Ayrıca, plana göre sınama ilerleme durumunuzu gözden geçirebilirsiniz.  
  
 [Uygulama PreEmptive tarafından koruması - Dotfuscator ile koruma](../ide/dotfuscator/index.md)  
 Güvenli ticari sırlar ve diğer fikri mülkiyet (IP) Yardım, korsanlık ve sahtekarlığın azaltmak için ücretsiz Dotfuscator Community Edition kullanın ve izinsiz ve yetkisiz hata ayıklama karşı koruyun.  Dotfuscator korur ve kaynak koduna ek programlama veya hatta erişim gerek kalmadan derlenmiş derlemeleri'ı sağlamlaştırma.
  
 [Uygulama oluşturma](https://www.visualstudio.com/docs/build/overview)  
 Kullanabileceğiniz [!INCLUDE[esprbuild](../test/includes/esprbuild_md.md)] oluşturup kodunuz için otomatik yapılarda yönetmek için. [!INCLUDE[esprbuild](../test/includes/esprbuild_md.md)]derlemeleri dağıtmak için açılan sunucuları oluşturmanızı sağlar. Ayrıca, yapı eğilimlerini analiz edebilirsiniz.  
  
 [Visual Studio Online veya Team Foundation Server kullanarak izleme iş](https://www.visualstudio.com/docs/work/overview)  
 Kullanabileceğiniz [!INCLUDE[vstsTfsLong](../test/includes/vststfslong_md.md)] planlamak ve bu işlemleri çevik işlem, resmi işlem ya da bir değişim kullanıp kullanmayacağınızı projelerinizi izlemek için. Projelerinizi planlama, plan karşı ilerleme durumunuzu izleme ve gerekli ayarlamaları tarafından riskleri azaltmak kötü beklenmeyen durumları önlemek ve projelerinizi maliyetini yönetin.
