---
title: IDataObject nesnesinden UML model öğelerini alma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML API, copy and paste
ms.assetid: e0b9cec8-3b93-4a24-8bd3-3e086501d387
caps.latest.revision: 20
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: a69a6f20fdccdce9d8795c68bf0a70c74604428b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693398"
---
# <a name="get-uml-model-elements-from-idataobject"></a>IDataObject nesnesinden UML model öğelerini alma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [alma UML model öğelerini bilgisine](https://docs.microsoft.com/visualstudio/modeling/get-uml-model-elements-from-idataobject).  
  
Kullanıcı öğeleri herhangi bir kaynaktan diyagram üzerine sürüklediğinde, sürüklenen öğeler içinde kodlanır bir `System.Windows.Forms.IDataObject`. Kodlama, kaynak nesnenin türüne bağlıdır. Aşağıdaki parçası, kaynak UML diyagram olduğunda öğelerin nasıl alındığını gösterir.  
  
> [!NOTE]
>  UML modeller üzerinde yapmak zorunda işlemlerin çoğunu türleri kullanarak gerçekleştirilebilir derlemede tanımlanan **Microsoft.VisualStudio.Uml.Interfaces** ve  **Microsoft.VisualStudio.ArchitectureTools.Extensibility**. Ancak bu amaç için UML modelleme araçları uygulamasının parçaları olan bazı sınıfları kullanmanız gerekir. Örneğin, `ShapeElement` bu parçada UML aynı değil `IShape`. UML model ve diyagramlarının tutarsız bir duruma koymanın riskini azaltmak için bu durumlar dışında bu uygulama sınıfları üzerinde yöntemleri kullanmaktan kaçınmak en iyisidir istisnası yoktur.  
  
## <a name="code-sample"></a>Kod örneği  
 Projenize aşağıdaki başvurmalıdır [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)] derlemeler:  
  
 **Microsoft.VisualStudio.Modeling.Sdk. [sürüm]**  
  
 **Microsoft.VisualStudio.Modeling.Sdk.Diagrams. [sürüm]**  
  
 **System.Windows.Forms**  
  
```  
using Microsoft.VisualStudio.Modeling;    
  // for ElementGroupPrototype  
using Microsoft.VisualStudio.Modeling.Diagrams;    
  // for ShapeElement, DiagramDragEventArgs, DiagramPointEventArgs  
…   
  /// <summary>  
  /// Retrieves UML IElements from drag arguments.  
  /// Works for drags from UML diagrams.  
  /// </summary>  
  private IEnumerable<IElement> GetModelElementsFromDragEvent  
                  (DiagramDragEventArgs dragEvent)  
  {  
     //ElementGroupPrototype is the container for  
     //dragged and copied elements and toolbox items.  
     ElementGroupPrototype prototype =  
        dragEvent.Data.  
        GetData(typeof(ElementGroupPrototype))  
                     as ElementGroupPrototype;  
     // Locate the originals in the implementation store.  
     IElementDirectory implementationDirectory =   
        dragEvent.DiagramClientView.Diagram.Store.ElementDirectory;  
  
     return  prototype.ProtoElements.Select(  
       prototypeElement =>   
       {  
          ModelElement element = implementationDirectory  
                .FindElement(prototypeElement.ElementId);  
          ShapeElement shapeElement = element as ShapeElement;  
          if (shapeElement != null)  
          {   
            // Dragged from a diagram.  
            return shapeElement.ModelElement as IElement;  
          }  
          else  
          {   
            // Dragged from UML Model Explorer.  
            return element as IElement;  
          }  
        });  
    }  
```  
  
 Hakkında daha fazla bilgi için `ElementGroupPrototype` ve `Store` , UML modelleme araçlarının uygulandığı durumunda, bkz: [Visual Studio - etki alanına özgü diller için modelleme SDK](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UML API ile programlama](../modeling/programming-with-the-uml-api.md)   
 [Modelleme Diyagramında Menü komutu tanımlama](../modeling/define-a-menu-command-on-a-modeling-diagram.md)



