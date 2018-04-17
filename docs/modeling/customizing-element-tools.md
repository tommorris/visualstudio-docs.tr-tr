---
title: Öğe araçları özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 96fe1bf1667cb9a00ad81301738b5eb3c93e1114
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="customizing-element-tools"></a>Öğe Araçlarını Özelleştirme
Bazı DSL tanımları, tek bir kavram öğeleri grubu olarak temsil eder. Örneğin, bir bileşenin sabit bir dizi bağlantı noktası olan bir model oluşturursanız, her zaman kendi üst bileşeni ile aynı zamanda oluşturulması için bağlantı noktalarını istiyorsunuz. Bu nedenle, öğelerin yerine tek bir grup oluşturur, böylece öğesi oluşturma aracı özelleştirmeniz gerekir. Bunu başarmak için öğe oluşturma Aracı nasıl başlatılır özelleştirebilirsiniz.  
  
 Ayrıca, aracı diyagramı veya bir öğenin üzerine sürüklendiğinde olanlar geçersiz kılabilirsiniz.  
  
## <a name="customizing-the-content-of-an-element-tool"></a>Bir öğe aracı içeriğini özelleştirme  
 Her öğe aracı örneği depolayan bir <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype> (EGP), seri duruma getirilmiş sürüm bir veya daha fazla model öğelerini ve bağlantıları içerir. Varsayılan olarak, bir öğenin aracı EGP için Aracı'nı belirtin sınıfının bir örneğini içerir. Bu geçersiz kılarak değiştirme *YourLanguage*`ToolboxHelper.CreateElementToolPrototype`. DSL paketi yüklendiğinde, bu yöntem çağrılır.  
  
 Yönteminin bir parametresi DSL tanımında belirtilen sınıfın kimliğidir. İlgilendiğiniz sınıfı ile yöntemi çağrıldığında, EGP ekstra öğeler ekleyebilirsiniz.  
  
 EGP bağlı öğeleri bir ana öğe bağlantılardan katıştırma eklemeniz gerekir. Referans bağlantıları de içerir.  
  
 Aşağıdaki örnek, bir ana öğesi ve iki katıştırılmış öğeleri oluşturur. Ana sınıf Direnci denir ve Terminal adlı öğe için iki katıştırma ilişkileri vardır. Katıştırma rolü özellikleri Terminal1 ve Terminal2 olarak adlandırılır ve hem 1..1 çokluğu sahiptir.  
  
```  
using Microsoft.VisualStudio.Modeling; ...    
public partial class CircuitDiagramToolboxHelper  
{  
  protected override ElementGroupPrototype    CreateElementToolPrototype(Store store, Guid domainClassId)  
  {  
    // A case for each tool to customize:    
    if (domainClassId == Resistor.DomainClassId)  
    {  
      // Set up the prototype elements and links:  
      Resistor resistor = new Resistor(store);  
      resistor.Terminal1 = new Terminal(store);   
      resistor.Terminal2 = new Terminal(store);  
      resistor.Terminal1.Name = "T1"; // embedding  
      resistor.Terminal2.Name = "T2"; // embedding  
      // We could also set up reference links.  
  
      // Create an element group prototype for the toolbox:  
      ElementGroup egp = new ElementGroup(store.DefaultPartition);  
      egp.AddGraph(resistor, true);  
      // We do not have to explicitly include embedded children.  
      return egp.CreatePrototype();  
    }  
    // Element tools for other classes:  
    else  
      return base.CreateElementToolPrototype(store, domainClassId);  
  }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğe Oluşturma ve Hareketini Özelleştirme](../modeling/customizing-element-creation-and-movement.md)