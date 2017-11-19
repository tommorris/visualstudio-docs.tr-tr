---
title: "Bağımlılık diyagramları: Başvuru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.teamarch.layerdiagram.layerexplorer.artifactlink
- vs.teamarch.layerdiagram.layerexplorer.artifactlink.properties
- vs.teamarch.layerdiagram.diagram
- vs.teamarch.UMLModelExplorer.layerdiagram
- vs.teamarch.layerdiagram.layerexplorer
- vs.teamarch.layerdiagram.shapes.properties
- vs.teamarch.layerdiagram.toolbox
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: f26c986c-1e79-420e-b29a-a283e6d8a71d
caps.latest.revision: "33"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: ce4a203fd0843fd6b15bfbf85019e85032defbd6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="dependency-diagrams-reference"></a>Bağımlılık diyagramları: başvuru
Visual Studio'da kullanabileceğiniz bir *bağımlılık diyagramı* sisteminizin üst düzey, mantıksal mimarisini görselleştirmek için. Bir bağımlılık diyagramı fiziksel yapıları sisteminizde adlı mantıksal, soyut gruplar halinde düzenler *katmanları*. Bu katmanlar yapıları gerçekleştirir ana görevleri ya da sisteminizin ana bileşenlerini açıklar. Her katman daha ayrıntılı görevleri tanımlayan iç içe geçmiş katmanları de içerebilir.  
  
 Bu özellik, Visual Studio'nun hangi sürümleri desteklemek için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Katmanlar arasında hedeflenen veya var olan bağımlılıkları belirtebilirsiniz. Oklar temsil edilir, bu bağımlılıklar hangi katmanların kullanabilir veya şu anda diğer katmanları tarafından temsil edilen işlevselliği kullanmak gösterir. Sisteminiz farklı rolleri ve işlevleri açıklayan katmanlara düzenleyerek, bir bağımlılık diyagramı anlamak, yeniden ve kodunuzu bakımını kolaylaştırır yardımcı olabilir.  
  
 Aşağıdaki görevleri gerçekleştirmenize yardımcı olacak bir bağımlılık diyagramı kullanın:  
  
-   Sisteminizin varolan veya hedeflenen mantıksal mimarisi iletişim kurar.  
  
-   Mevcut kodunuzu ve hedeflenen mimari arasındaki çakışmaları keşfedin.  
  
-   Yeniden Düzenle, güncelleştirme ya da sisteminizi gelişmesi hedeflenen mimari üzerindeki değişikliklerin etkisini düşünün.  
  
-   Hedeflenen mimari geliştirme ve kodunuzu bakımı sırasında iade ile doğrulama içererek ve yapı işlemleri.  
  
 Bu konu, bir bağımlılık diyagramında kullanabileceğiniz öğeleri açıklar. Oluşturma ve bağımlılık diyagramlar çizin, bkz: hakkında daha ayrıntılı bilgi için [bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md). Katman desenleri hakkında daha fazla bilgi için ziyaret [desenleri ve uygulamalar site](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
## <a name="reading-dependency-diagrams"></a>Bağımlılık diyagramları okuma  
 ![Bağımlılık diyagramlarındaki öğelerin](../modeling/media/uml_layerrefreading.png "UML_LayerRefReading")  
  
 Aşağıdaki tabloda, bir bağımlılık diyagramında kullanabileceğiniz öğeleri açıklar.  
  
|**Şekil**|**Öğesi**|**Açıklama**|  
|---------------|-----------------|---------------------|  
|1.|**Katman**|Sisteminizdeki fiziksel yapıları mantıksal bir grubudur. Bu yapıtların ad alanları, projeler, sınıfları, yöntemleri vb. olabilir.<br /><br /> Bir katmana bağlı yapıları görmek için katman için kısayol menüsünü açın ve ardından **bağlantıları görüntüleme** açmak için **Katman Gezgini**.<br /><br /> Daha fazla bilgi için bkz: [Katman Gezgini](#Explorer).<br /><br /> -   **Namespace bağımlılıkları Yasak** -Bu katman ile ilişkilendirilmiş yapıların belirtilen ad alanında bulunan bağımlı olamaz belirtir.<br />-   **Ad alanları Yasak** -Bu katman ile ilişkilendirilmiş yapıların belirli ad alanlarına ait değil belirtir.<br />-   **Ad alanları gerekli** -Bu katman ile ilişkilendirilmiş yapıların belirtilen ad alanlarını birine ait olması gerektiğini belirtir.|  
|2|**Bağımlılık**|Bir katmanın işlevselliği kullanabileceğini gösterir başka bir katmanında ancak tersi geçerli değildir.<br /><br /> -   **Yön** -bağımlılığın yönünü belirtir.|  
|3|**Çift yönlü bağımlılık**|Bir katmanın işlevselliği kullanabileceğini gösterir başka bir katmanında ve tersi.<br /><br /> -   **Yön** -bağımlılığın yönünü belirtir.|  
|4|**Yorum**|Genel Notlar diyagramı veya diyagramındaki öğeler eklemek için kullanın.|  
|5|**Açıklama bağlantısı**|Diyagram üzerinde öğelerin açıklamaları bağlamak için kullanın.|  
  
##  <a name="Explorer"></a>Katman Gezgini  
 Çözümünüzdeki projeleri, sınıflar, ad alanları, proje dosyalarını ve diğer bölümleri yazılımınızı gibi her katman yapılara bağlayabilirsiniz. Bir katmana numarasını katmana bağlı yapıların sayısını gösterir. Bununla birlikte, bir katmandaki yapı sayısını okurken, aşağıdakileri unutmayın:  
  
-   Bir katman diğer yapıları içeren bir yapıya bağlanırsa, ancak katman doğrudan diğer yapılara bağlanmazsa, sayı yalnızca bağlı yapıyı içerir. Bununla birlikte, diğer yapılar katman doğrulanırken analiz için alınır.  
  
     Örneğin, bir katman tek bir ad alanına bağlanırsa, ad alanı sınıflar içerse bile, bağlı yapıların sayısı 1'dir. Katmanın ad alanındaki her bir sınıfa da bağlantıları bulunuyorsa, sayı bağlantılı sınıfları da içerecektir.  
  
-   Bir katman yapılarla bağlantılı diğer katmanları içeriyorsa, kapsayıcı katman da üzerindeki sayı bu yapıları içermese bile bu yapılara bağlıdır.  
  
 Bağlama katmanları ve yapıları hakkında daha fazla bilgi için bkz:  
  
-   [Bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md)  
  
-   [Kodunuz aracılığıyla bağımlılık diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)  
  
#### <a name="to-examine-the-linked-artifacts"></a>Bağlı yapıları incelemek için  
  
-   Bağımlılık diyagramdaki bir veya daha fazla katmanları için kısayol menüsünü açın ve ardından **bağlantıları görüntüleme**.  
  
     **Explorer katman** açar ve Seçili katmanlara bağlı yapıları gösterir. **Explorer katman** her yapı bağlantılarını özelliklerini gösteren bir sütun vardır.  
  
    > [!NOTE]
    >  Bu özelliklerin tümünü göremiyorsanız, genişletin **Katman Gezgini** penceresi.  
  
    |**Katman Gezgini'nde sütun**|**Açıklama**|  
    |----------------------------------|---------------------|  
    |**Kategorileri**|Sınıfı, ad alanı, kaynak dosya ve benzerleri gibi yapı türü|  
    |**Katman**|Yapıya katmanı|  
    |**Doğrulamayı destekler**|Varsa **doğru**, sonra da katman doğrulama işlemi projenin için veya öğeden olan bağımlılıklara doğrulayabilirsiniz.<br /><br /> Varsa **yanlış**, bağlantı katman doğrulama işlemine katılmayan sonra.<br /><br /> Daha fazla bilgi için bkz: [bağımlılık diyagramları: yönergeler](../modeling/layer-diagrams-guidelines.md).|  
    |**Tanımlayıcı**|Bağlı yapıya başvurusu|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulamanız için model oluşturma](../modeling/create-models-for-your-app.md)
