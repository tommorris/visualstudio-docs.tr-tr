---
title: "Şekiller ve bağlayıcılar modeli yansıtacak şekilde güncelleştirme | Microsoft Docs"
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
ms.openlocfilehash: 2f192b1bc65d9040ea6ae4fa1278e053398425c7
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="updating-shapes-and-connectors-to-reflect-the-model"></a>Modeli Yansıtacak Şekilleri ve Bağlayıcıları Güncelleştirme
Bir etki alanına özgü dilde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], temel alınan model durumunu yansıtacak bir şekli görünümünü yapabilirsiniz.  
  
 Bu konuda kod örnekleri eklenmelidir bir `.cs` dosyasını, `Dsl` projesi. Bu deyimler her bir dosyadaki gerekir:  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
```  
  
## <a name="set-shape-map-properties-to-control-the-visibility-of-a-decorator"></a>Bir oluşturma öğesi görünürlüğünü denetlemek için Şekil eşleme özelliklerini ayarlama  
 Şekil ve etki alanı sınıf arasında eşleme DSL tanımında yapılandırarak program kod yazmadan bir oluşturma öğesi görünürlüğünü kontrol edebilirsiniz. Daha fazla bilgi için bkz: [bir etki alanına özgü dil tanımlamak nasıl](../modeling/how-to-define-a-domain-specific-language.md).
  
## <a name="expose-the-color-and-style-of-a-shape-as-properties"></a>Bir şekli bir tarzını ve rengini özellikleri olarak kullanıma sunma  
 Shape sınıfı DSL tanımı'nda sağ tıklayın, fareyle **eklemek kullanıma sunulan**, ardından öğelerden birini gibi **dolgu rengi**.  
  
 Şeklin şimdi program kodundaki veya bir kullanıcı olarak ayarlayabilirsiniz bir etki alanı özelliğine sahiptir. Örneğin, bir komut veya kural program kodunda ayarlamak için yazabilirsiniz:  
  
 `shape.FillColor = System.Drawing.Color.Red;`  
  
 Özellik değişkeni program denetimindeki yalnızca ve kullanıcı tarafından yapmak istiyorsanız, yeni etki alanı özelliği gibi seçin **dolgu rengi** DSL tanımı diyagramdaki. Daha sonra Özellikler penceresinde ayarlayın **olan gözatılamaz** için `false` veya ayarlayın **UI salt okunur olduğundan** için `true`.  
  
## <a name="define-change-rules-to-make-color-style-or-location-depend-on-model-element-properties"></a>Değişiklik renk, stil veya model öğesi özelliklerini bağımlı konumu yapmak için kurallar tanımlar  
 Model diğer bölümlerini bağımlı şekli görünümünü güncelleştirme kurallar tanımlayabilirsiniz. Örneğin, model öğesi özelliklerini bağımlı kendi şeklinin rengi güncelleştiren bir model öğesi üzerinde bir değişiklik kural tanımlayabilirsiniz. Değişiklik kuralları hakkında daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).  
  
 Undo komutu gerçekleştirildiğinde kuralları çünkü deposunda saklanır özellikleri yalnızca güncelleştirmek için kuralları kullanmanız gerekir. Bu şeklin görünürlüğünü ve boyutu gibi grafik bazı özellikleri içermez. Bu şeklin özelliklerini güncelleştirmek için bkz: [olmayan deposu grafik güncelleştirme özelliklerini](#OnAssociatedProperty).  
  
 Aşağıdaki örnek, oluşturduğunuz varsayılır `FillColor` önceki bölümde açıklandığı gibi bir etki alanı özelliği olarak.  
  
```csharp  
[RuleOn(typeof(ExampleElement))]  
  class ExampleElementPropertyRule : ChangeRule  
  {  
    public override void ElementPropertyChanged(ElementPropertyChangedEventArgs e)  
    {  
      base.ElementPropertyChanged(e);  
      ExampleElement element = e.ModelElement as ExampleElement;  
      // The rule is called for every property that is updated.  
      // Therefore, verify which property changed:  
      if (e.DomainProperty.Id == ExampleElement.NameDomainPropertyId)  
      {  
        // There is usually only one shape:  
        foreach (PresentationElement pel in PresentationViewsSubject.GetPresentation(element))  
        {  
          ExampleShape shape = pel as ExampleShape;  
          // Replace this with a useful condition:  
          shape.FillColor = element.Name.EndsWith("3")   
                     ? System.Drawing.Color.Red : System.Drawing.Color.Green;  
        }  
      }  
    }  
  }  
  // The rule must be registered:  
  public partial class OnAssociatedPropertyExptDomainModel  
  {  
    protected override Type[] GetCustomDomainModelTypes()  
    {  
      List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
      types.Add(typeof(ExampleElementPropertyRule));  
      // If you add more rules, list them here.   
      return types.ToArray();  
    }  
  }  
  
```  
  
## <a name="use-onchildconfigured-to-initialize-a-shapes-properties"></a>Şeklin özellikleri başlatmak için OnChildConfigured kullanın  
 İlk çalıştırıldığında bir şekli özelliklerini ayarlamak için oluşturulan, geçersiz kılma `OnChildConfigured()` diyagramı sınıfınızın kısmi tanımında. Diyagram sınıfı DSL tanımında belirtilir ve oluşturulan kod **Dsl\Generated Code\Diagram.cs**. Örneğin:  
  
```csharp  
partial class MyLanguageDiagram  
{  
  protected override void OnChildConfigured(ShapeElement child, bool childWasPlaced, bool createdDuringViewFixup)  
  {  
    base.OnChildConfigured(child, childWasPlaced, createdDuringViewFixup);  
    ExampleShape shape = child as ExampleShape;  
    if (shape != null)   
    {  
      if (!createdDuringViewFixup) return; // Ignore load from file.  
      ExampleElement element = shape.ModelElement as ExampleElement;  
      // Replace with a useful condition:  
      shape.FillColor = element.Name.EndsWith("3")   
          ? System.Drawing.Color.Red : System.Drawing.Color.Green;  
    }  
    // else deal with other types of shapes and connectors.  
  }  
}  
  
```  
  
 Bu yöntem, hem etki alanı özellikleri ve şeklin boyutunu gibi deposu olmayan özellikler için kullanılabilir.  
  
##  <a name="OnAssociatedProperty"></a>Diğer bir şekli özelliklerini güncelleştirmek için AssociateValueWith() kullanın  
 Şeklin gölge ya da bir bağlayıcı ok stilini sahip olup olmadığı gibi bazı özellikler için özellik bir etki alanı özelliği olarak gösterme yerleşik bir yöntem yoktur.  Bu tür özellikleri için değişiklikler hareket sistemi denetiminde değildir. Bu nedenle, bunları güncelleştirmek uygun değil kullanıcı Undo komutu gerçekleştirdiğinde kuralları çağrılmaz kurallarını kullanarak.  
  
 Bunun yerine, gibi özellikleri kullanarak güncelleştirebileceğinizi <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.OnAssociatedPropertyChanged%2A>. Aşağıdaki örnekte, bir bağlayıcı ok stilini ilişkisinde, bağlayıcı görüntüler bir etki alanı özellik değeri tarafından denetlenir:  
  
```  
public partial class ArrowConnector // My connector class.   
{  
   /// <summary>  
    /// Called whenever a registered property changes in the associated model element.  
    /// </summary>  
    /// <param name="e"></param>  
    protected override void OnAssociatedPropertyChanged(VisualStudio.Modeling.Diagrams.PropertyChangedEventArgs e)  
    {  
      base.OnAssociatedPropertyChanged(e);  
      // Can be called for any property change. Therefore,  
      // Verify that this is the property we're interested in:  
      if ("IsDirected".Equals(e.PropertyName))  
      {  
        if (e.NewValue.Equals(true))  
        { // Update the shape's built-in Decorator feature:  
          this.DecoratorTo = LinkDecorator.DecoratorEmptyArrow;  
        }  
        else  
        {  
          this.DecoratorTo = null; // No arrowhead.  
        }  
      }  
    }  
    // OnAssociatedPropertyChanged is called only for properties  
    // that have been registered using AssociateValueWith().  
    // InitializeResources is a convenient place to call this.  
    // This method is invoked only once per class, even though  
    // it is an instance method.   
    protected override void InitializeResources(StyleSet classStyleSet)  
    {  
      base.InitializeResources(classStyleSet);  
      AssociateValueWith(this.Store, Wire.IsDirectedDomainPropertyId);  
      // Add other properties here.  
    }  
}  
  
```  
  
 `AssociateValueWith()`kaydetmek istediğiniz her bir etki alanı özellik için bir kez çağrılmalıdır. Bunu çağrıldıktan sonra belirtilen özellik değişiklikleri çağıracak `OnAssociatedPropertyChanged()` , özelliğin model öğesi sunan şekilleri içinde.  
  
 Bu çağrı gerekli değildir `AssociateValueWith()` her örneği için. InitializeResources örnek yöntemi olsa da, her shape sınıfı için yalnızca bir kez çağrılır.
