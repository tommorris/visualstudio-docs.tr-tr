---
title: "Diyagramdaki bir arka plan görüntüsü ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 486ef0391f324ea355dd1ccdfc698c5c0394c1d8
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="setting-a-background-image-on-a-diagram"></a>Diyagram Üzerinde Arka Plan Görüntüsü Ayarlama
İçinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Görselleştirme ve modelleme SDK, ayarlayabileceğiniz arka plan görüntüsü oluşturulan Tasarımcısı için özel kod kullanarak.  
  
## <a name="setting-the-background-image"></a>Arka plan resmi ayarlama  
  
#### <a name="to-set-a-background-image-for-a-generated-designer"></a>Arka plan görüntüsü için oluşturulan bir tasarımcı ayarlamak için  
  
1.  Diyagramın arka planı olarak Dsl\Resources dizinine geçerli proje için kullanmak istediğiniz görüntü dosyasını kopyalayın.  
  
2.  İçinde **Çözüm Gezgini**, Dsl\Resources klasöre sağ tıklayın, fareyle **Ekle**ve ardından **varolan öğeyi**.  
  
3.  İçinde **varolan öğeyi Ekle** iletişim kutusunda, Dsl\Resources klasörüne gözatın.  
  
4.  İçinde **dosya türü** tıklatın **görüntü dosyaları**.  
  
5.  Dizine kopyalanan görüntü dosyasına tıklayın ve ardından **Ekle**.  
  
6.  DSL sağ tıklayın ve **özellikleri** Dsl proje özelliklerini açın.  
  
7.  Üzerinde **kaynakları** sekmesini tıklatın, **bu projenin varsayılan kaynak dosya içermiyor. Oluşturmak için burayı tıklatın.**  
  
8.  Görüntü dosyası resim sürükleyerek kaynak dosyasına eklemek **Çözüm Gezgini** kaynakları penceresine.  
  
9. Dosya menüsünü açın ve proje özelliklerini kaydetme seçeneğini tıklatın.  
  
10. Dsl\Properties\Resources.resx dosya var ve dosyanın Resources.Designer.cs altındaki sahip olduğunu doğrulayın.  
  
11. Resources.Designer.cs eksikse, Resources.resx dosyasını tıklatın, **Çözüm Gezgini**.  
  
12. İçinde **özellikleri** penceresindeki ayarlayın `Custom Tool` özelliğine `ResXFileCodeGenerator`.  
  
13. İçinde **Çözüm Gezgini**, Dsl projesine sağ tıklayın, fareyle **Ekle**, tıklatıp **yeni klasör**.  
  
14. Klasör adı **özel**.  
  
15. Özel klasöre sağ tıklayın, fareyle **Ekle**, tıklatıp **yeni öğe**.  
  
16. İçinde **Yeni Öğe Ekle** iletişim kutusunda **şablonları** tıklatın **kod dosyası**.  
  
17. İçinde **adı** kutusuna `BackgroundImage.cs`, tıklatıp **Ekle**.  
  
18. Ad alanı, şema sınıfı adı ve görüntü dosya kaynak adı ayarlama BackgroundImage.cs dosyasına aşağıdaki kodu kopyalayın.  
  
     "MyDiagramClass" Dsl\GeneratedCode\Diagrams.cs içinde tanımlanan diyagramı parçalı sınıf adını değiştirin. Bu gibi durumlarda, doğru ad alanı da Dsl\GeneratedCode\Diagrams.cs dosyasından alabilirsiniz.  
  
    ```  
    using System;  
    using Microsoft.VisualStudio.Modeling.Diagrams;  
  
    // Fix the namespace:  
    namespace Fabrikam.MyLanguage  
    {  
      // Fix the Diagram Class name - get it from GeneratedCode\Diagram.cs  
  
      public partial class Language29Diagram  
      {  
        protected override void InitializeInstanceResources()  
        {  
          // Fix the Resources namespace and the Image resource name:  
          ImageField backgroundField = new ImageField("background",  
              Fabrikam.MyLanguage.Properties.Resources.MyPicture);  
  
          backgroundField.DefaultFocusable = false;  
          backgroundField.DefaultSelectable = false;  
          backgroundField.DefaultVisibility = true;  
          backgroundField.DefaultUnscaled = false;  
  
          shapeFields.Add(backgroundField);  
  
          backgroundField.AnchoringBehavior  
            .SetTopAnchor(AnchoringBehavior.Edge.Top, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetLeftAnchor(AnchoringBehavior.Edge.Left, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetRightAnchor(AnchoringBehavior.Edge.Right, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetBottomAnchor(AnchoringBehavior.Edge.Bottom, 0.01);  
  
          base.InitializeInstanceResources();  
        }  
      }  
    }  
    ```  
  
     Program kodunu modeliyle özelleştirme hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şekiller ve bağlayıcılar tanımlama](../modeling/defining-shapes-and-connectors.md)   
 [Metin ve görüntü alanları özelleştirme](../modeling/customizing-text-and-image-fields.md)   
 [Gezinme ve bir modeli Program kodunda güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Etki Alanına Özgü Dili Özelleştirmek için Kod Yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
