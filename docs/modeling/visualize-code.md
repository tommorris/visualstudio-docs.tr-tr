---
title: "Kodu görselleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code, understanding
- code, visualizing
- code, exploring
ms.assetid: 0dd7d438-393a-4cd3-b417-9bf37379e1b0
caps.latest.revision: "47"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 0abc0bff93da0944ce7e413a83dafc47e375a8a2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="visualize-code"></a>Kodu görselleştirme
Var olan kodu anlamanıza ve uygulamanızı açıklamak yardımcı olmak için görselleştirme ve modelleme Visual Studio Araçları'nı kullanabilirsiniz. Bu, görsel olarak değişikliklerinizi kodu ve bu değişikliklerden kaynaklanan riskler ve iş değerlendirmek Yardım nasıl etkileyebileceğini öğrenin sağlar. Örneğin:  
  
-   Kodunuzu ilişkilerde anlamak için bu ilişkileri görsel olarak eşleyin.  
  
-   Sisteminizin mimariyi açıklamakta ve kod tasarımı ile tutarlı tutmak için bağımlılık diyagramları oluşturun ve bu diyagramları karşı kodu doğrulayın.  
  
-   Sınıf yapıları açıklamak için sınıf diyagramları oluşturun.  
  
 Bu araçlar, daha kolay proje ile ilgili kişilerle iletişim kurmanıza yardımcı. 
  
 Visual Studio hangi sürümlerinin her özelliğini desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?  
  
|||  
|-|-|  
|**Kod ve ilişkileri anlama:**<br /><br /> Özel kod parçalarını arasındaki ilişkileri eşleyin.<br /><br /> İlişkileri kodunuzda çözümün tamamı için genel bir bakış konusuna bakın.<br /><br /> **Not**: Visual Studio'nun bu sürümünde terimi *kod Haritası* yerine kullanılan *bağımlılık grafiğinin*.|-   [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)<br />-   [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)<br />-   [Kod Haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)<br />-   [Hata ayıklarken çağrı yığınında yöntemler eşleştirme](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)|  
|**Sınıf yapıları anlama:**<br /><br /> Bir projedeki sınıfların yapısını koddan sınıf diyagramları oluşturarak görselleştirin.|[Nasıl yapılır: sınıf diyagramlarını (Sınıf Tasarımcısı) projelerine ekleme](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)|  
|**Bu tasarım karşı kodu doğrulamak ve üst düzey sistem tasarımı açıklanmıştır:**<br /><br /> Üst düzey sistem tasarımı ve hedeflenen bağımlılıklarını bağımlılık diyagramları oluşturarak açıklanmaktadır. Koddaki bağımlılıklara tasarım ile tutarlı kalmasını emin olmak için bu tasarıma karşı kodu doğrulayın.|-   [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Bağımlılık diyagramları: başvuru](../modeling/layer-diagrams-reference.md)<br />-   [Bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md)<br />-   [Bağımlılık diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)|  
  
## <a name="external-resources"></a>Dış Kaynaklar  
  
|**Kategori**|**Bağlantılar**|  
|------------------|---------------|  
|**Forumları**|-   [Visual Studio Görselleştirme ve Modelleme Araçları](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio Görselleştirme ve modelleme SDK (DSL araçları)](http://go.microsoft.com/fwlink/?LinkId=184721)|  
|**Bloglar**|[Visual Studio ALM + Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=201340)|  
|**Teknik makaleler ve günlükleri**|[MSDN mimarisi Forumu](http://go.microsoft.com/fwlink/?LinkId=201343)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Senaryo: Görselleştirme ve modelleme kullanarak tasarımınızı değiştirme](../modeling/scenario-change-your-design-using-visualization-and-modeling.md)   
 [Çözümleme ve mimarinin modelini oluşturma](../modeling/analyze-and-model-your-architecture.md)   
 [Uygulama Mimarinizi modeli](../modeling/model-your-app-s-architecture.md)   
 [Geliştirme sürecinizde modelleri kullanma](../modeling/use-models-in-your-development-process.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
