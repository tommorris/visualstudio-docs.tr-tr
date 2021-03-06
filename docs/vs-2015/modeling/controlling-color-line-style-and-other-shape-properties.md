---
title: Renk, çizgi stili ve diğer Şekil özelliklerini denetleme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c06d0066-24aa-4c65-b91c-c2089b81ec8d
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 1722a3f8a5ff05589cfad987fff6448d44e96ec8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628556"
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>Renk, Çizgi Stili ve Diğer Şekil Özelliklerini Denetleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [denetleme renk, çizgi stili ve diğer Şekil özelliklerini](https://docs.microsoft.com/visualstudio/modeling/controlling-color-line-style-and-other-shape-properties).  
  
Renk 'olarak sunulabilir gibi' – bazı Şekil özelliklerini, diğer bir deyişle, şekle bir alan özelliğine bağlı. Başkalarının doğrudan denetlenmesi gerekir.  
  
## <a name="exposing-a-property"></a>Bir özelliği kullanıma sunma  
 Renk gibi bazı Şekil özelliklerini değeri alan özelliği olarak bağlanabilir.  
  
 DSL tanımındaki şekil, bağlayıcı veya diyagram sınıfı seçin. Kendi bağlam menüsünde **ekleme kullanıma sunulan**, istediğiniz gibi dolgu rengi özelliği seçin.  
  
 Şekil, program kodu veya bir kullanıcı olarak ayarlanmış bir alan özelliği artık sahiptir.  
  
## <a name="dynamically-updating-an-exposed-property"></a>Dinamik olarak sunulan bir özellik güncelleştiriliyor  
 Genellikle sunulan özelliği başka bir özellikte bağlı olmanız gerekir. Örneğin, belirli bir etki alanı özelliği olduğunda kırmızıya şekle sıfırdan isteyebilirsiniz. Bu bağımlılık olmak için oluşturun bir [kural](../modeling/rules-propagate-changes-within-the-model.md). Örneğin:  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
namespace ExampleNamespace  
{  
 // Attribute associates the rule with class:  
 [RuleOn(typeof(CarShape), FireTime = TimeToFire.TopLevelCommit)]  
 // The rule is a class derived from one of the abstract rules:  
 class CarShapeAddRule : AddRule  
 {  
 // Override the abstract method:  
 public override void ElementAdded(ElementAddedEventArgs e)  
 {  
 base.ElementAdded(e);  
 CarShape shape = e.ModelElement as CarShape;  
 Store store = shape.Store;  
 // Ignore this call if we're currently loading a model:  
 if (store.TransactionManager.CurrentTransaction.IsSerializing)   
  return;  
 Car car = shape.ModelElement as Car;  
 // Code here propagates change as required - for example:  
 shape.FillColor = car.Somebool ? System.Drawing.Color.Red : System.Drawing.Color.Green;   
 }  
}  
 // The rule must be registered:  
 public partial class ExampleDomainModel  
 {  
 protected override Type[] GetCustomDomainModelTypes()  
 {  
  List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
  types.Add(typeof(CarShapeAddRule));  
  // If you add more rules, list them here.   
  return types.ToArray();  
 }  
 }  
}  
```



