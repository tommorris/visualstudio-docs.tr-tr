---
title: "Renk, çizgi stili ve diğer şekil özellikleri denetleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5903c6cc79e637514b75c9e44cb4cbe5c0342ee7
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>Renk, Çizgi Stili ve Diğer Şekil Özelliklerini Denetleme
Renk 'olarak verilebilen gibi' - bazı şekil özellikleri başka bir deyişle, etki alanına bağlı bir özellik şeklin için. Başkalarının doğrudan denetlenmesi gerekir.  
  
## <a name="exposing-a-property"></a>Bir özellik gösterme  
 Bazı şekil özellikleri renk gibi bir etki alanı özellik değerine bağlanabilir.  
  
 DSL tanımı'nda bir şekil, bağlayıcı veya diyagramı sınıfı seçin. Kendi bağlam menüsünde seçin **eklemek açığa**ve ardından istediğiniz dolgu rengi gibi bir özellik seçin.  
  
 Şeklin şimdi program kodundaki veya bir kullanıcı olarak ayarlayabilirsiniz bir etki alanı özelliğine sahiptir.  
  
## <a name="dynamically-updating-an-exposed-property"></a>Dinamik olarak sunulan bir özelliği güncelleniyor  
 Genellikle, sunulan özelliği başka bir özellikte bağımlı hale getirmek istediğiniz. Örneğin, belirli bir etki alanı özelliği olduğunda kırmızı açmak için bir şekli sıfırdan isteyebilirsiniz. Bu bağımlılık yapmak için Oluştur bir [kuralı](../modeling/rules-propagate-changes-within-the-model.md). Örneğin:  
  
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