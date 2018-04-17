---
title: Etki alanı özellik değeri değişiklik işleyicileri Visual Studio'da | Microsoft Docs
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, overriding event handlers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 627855fdcad1528d5a80290a5fa0866abf328041
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="domain-property-value-change-handlers"></a>Etki alanı özellik değeri değişiklik işleyicileri

İçinde bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir etki alanı özellik değeri değiştiğinde, etki alanına özgü dil `OnValueChanging()` ve `OnValueChanged()` yöntemleri, etki alanı özelliği işleyicisinde çağrılır. Değişiklik yanıt vermek için bu yöntemleri geçersiz kılabilirsiniz.

## <a name="override-the-property-handler-methods"></a>Özellik işleyicisi yöntemlerini geçersiz kılın

Her bir etki alanı, etki alanına özgü dil özelliğinin, ana etki alanı sınıfı içinde iç içe bir sınıf tarafından işlenir. Biçim adını izleyen *PropertyName*PropertyHandler. Bu özellik işleyici sınıfını dosyasındaki inceleyebilirsiniz **Dsl\Generated Code\DomainClasses.cs**. Sınıfında, `OnValueChanging()` değer değişikliklerini hemen önce çağrılır ve `OnValueChanged()` hemen değeri değiştikten sonra çağrılır.

Örneğin, adlı bir etki alanı sınıf olduğunu varsayalım `Comment` adlı bir dize etki alanı özelliği olan `Text` ve adlı bir tamsayı özelliği `TextLengthCount`. Neden `TextLengthCount` her zaman uzunluğu içerecek şekilde `Text` dize Dsl projesinde ayrı bir dosyada aşağıdaki kodu yazabilirsiniz:

```csharp
// Domain Class "Comment":
public partial class Comment
{
  // Domain Property "Text":
  partial class TextPropertyHandler
  {
    protected override void OnValueChanging(CommentBase element, string oldValue, string newValue)
    {
      base.OnValueChanging(element, oldValue, newValue);

      // To update values outside the Store, write code here.

      // Let the transaction manager handle undo:
      Store store = element.Store;
      if (store.InUndoRedoOrRollback || store.InSerializationTransaction) return;

      // Update values in the Store:
      this.TextLengthCount = newValue.Length;
    }
  }
}
```

Aşağıdaki noktaları özelliği işleyicileri hakkında dikkat edin:

-   Özellik işleyici yöntemleri, kullanıcı bir etki alanı özelliği için değişiklik yaptığında, hem program kodunu özelliği için farklı bir değer atandığında denir.

-   Gerçekte yalnızca değeri değiştiğinde yöntemleri denir. Program kodunda geçerli değerine eşit bir değer atarsa işleyici çağrılır değil.

-   Hesaplanan ve özel depolama etki alanı özellikleri T:System.Windows.PropertyChangedCallback ve OnValueChanging yöntemleri gerekmez.

-   Yeni değer değiştirmek için değişiklik işleyici kullanamaz. Örneğin belirli bir aralık değeri kısıtlamak, tanımlamak Bunu yapmak istiyorsanız, bir `ChangeRule`.

-   Bir ilişkinin bir rolü temsil eden bir özellik için bir değişiklik işleyici ekleyemezsiniz. Bunun yerine, tanımlayan bir `AddRule` ve `DeleteRule` ilişki sınıfı üzerinde. Bu kurallar bağlantıları oluşturulduğunda veya değiştirilen tetiklenir. Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).

### <a name="changes-in-and-out-of-the-store"></a>Mağazada değişiklikleri

Özellik işleyici yöntemleri değişiklik başlatılan işlem içinde denir. Bu nedenle, yeni bir işlem açmadan deposunda daha fazla değişiklik yapabilirsiniz. Değişikliklerinizi ek işleyici aramasına neden.

Bir işlem geri alınamaz, geri alınmış ya da, geri, değişiklik yapmamalısınız Mağazası'nda, diğer bir deyişle, model öğelerini, ilişkileri, şekil, bağlayıcılar diyagramları veya özelliklerini değiştirir.

Model dosyadan yüklendiğinde Ayrıca, genellikle değerleri güncelleştirmek değil.

Modelde değişiklikler, bu nedenle böyle bir test tarafından korunmalıdır:

```csharp
if (!store.InUndoRedoOrRollback && !store. InSerializationTransaction)
{
   this.TextLength = ...; // in-store changes
}
```

Bunun aksine, özellik işleyicinizi değişiklikleri mağaza dışına yayılırsa, örneğin, bir dosya, veritabanı veya depolama olmayan değişkenleri sonra her zaman kullanıcı geri çalıştırdığında dış değerler güncelleştirilir, böylece bu değişiklik veya gerekir Yinele.

### <a name="cancel-a-change"></a>Bir değişiklik iptal et

Bir değişiklik engellemek istiyorsanız, geçerli işlem geri alabilirsiniz. Örneğin, bir özellik belirli bir aralık içinde kaldığından emin olmak isteyebilirsiniz.

```csharp
if (newValue > 10)
{
   store.TransactionManager.CurrentTransaction.Rollback();
   System.Windows.Forms.MessageBox.Show("Value must be less than 10");
}
```

### <a name="alternative-technique-calculated-properties"></a>Alternatif yöntem: hesaplanan özellikleri

Önceki örnekte, bir etki alanı özelliğinden değerlere yaymak için OnValueChanged()'ın nasıl kullanılabileceğini gösterir. Her bir özellik depolanan değeri var.

Bunun yerine, bir hesaplanmış özellik olarak türetilen özellik tanımlama düşünebilirsiniz. Durum, özellik kendi hiçbir depolama alanına sahip ve tanımlıyor değeri gerekli olduğunda işlevi değerlendirilir. Daha fazla bilgi için bkz: [hesaplanan ve özel depolama özellikleri](../modeling/calculated-and-custom-storage-properties.md).

Önceki örnekte yerine, ayarlayabilirsiniz **türü** alanını `TextLengthCount` olmasını **hesaplanan** DSL tanımında. Kendi içermediği **almak** bu etki alanı özelliği için yöntem. **Almak** yöntemi geçerli uzunluğu döndürebildiği `Text` dize.

Ancak, olası bir dezavantajı hesaplanan özellikleri, değer, bir performans sorununu sunabilir kullanıldığı her sefer ifade değerlendirilir olur. Ayrıca, hiçbir OnValueChanging() ve yoktur OnValueChanged() hesaplanan bir özellik.

### <a name="alternative-technique-change-rules"></a>Alternatif yöntem: kuralları Değiştir

Bir ChangeRule tanımlarsanız, içinde bir özelliğin değerini değiştirir bir işlem sonunda yürütülür.  Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).

Bir işlemde birkaç değişiklik yaptıysanız, tüm tamamlandığı zaman ChangeRule yürütür. Karşıtlık, OnValue... tarafından yöntemleri, bazı değişiklikler gerçekleştirilmemiş zaman çalıştırılır. Ne istediğinize bağlı olarak, bu bir ChangeRule daha uygun hale getirebilirsiniz.

Bir ChangeRule, belirli bir aralık içinde tutmak için özelliğin yeni değeri ayarlamak için de kullanabilirsiniz.

> [!WARNING]
> Kural deposu içeriği değişiklikler yaparsa, diğer kuralları ve özellik işleyicileri tetiklenen. Bir kural, tetiklenen özellik değişirse tekrar çağrılır. Sonsuz tetikleyen kural tanımlarınızı yol açmamasını emin olmanız gerekir.

```csharp
using Microsoft.VisualStudio.Modeling;
...
// Change rule on the domain class Comment:
[RuleOn(typeof(Comment), FireTime = TimeToFire.TopLevelCommit)]
class MyCommentTrimRule : ChangeRule
{
  public override void
    ElementPropertyChanged(ElementPropertyChangedEventArgs e)
  {
    base.ElementPropertyChanged(e);
    Comment comment = e.ModelElement as Comment;

    if (comment.Text.StartsWith(" ") || comment.Text.EndsWith(" "))
      comment.Text = comment.Text.Trim();
    // If changed, rule will trigger again.
  }
}

// Register the rule:
public partial class MyDomainModel
{
 protected override Type[] GetCustomDomainModelTypes()
 { return new Type[] { typeof(MyCommentTrimRule) };
 }
}
```

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, bir etki alanı özelliğin özellik işleyicisi geçersiz kılar ve bir özellik için kullanıcıyı uyarır `ExampleElement` etki alanı sınıfı değişti.

### <a name="code"></a>Kod

```csharp
using DslModeling = global::Microsoft.VisualStudio.Modeling;
using DslDesign = global::Microsoft.VisualStudio.Modeling.Design;

namespace msft.FieldChangeSample
{
  public partial class ExampleElement
  {
    internal sealed partial class NamePropertyHandler
    {
      protected override void OnValueChanged(ExampleElement element,
         string oldValue, string newValue)
      {
        if (!this.Store.InUndoRedoOrRollback)
        {
           // make in-store changes here...
        }
        // This part is called even in undo:
        System.Windows.Forms.MessageBox.Show("Value Has Changed");
        base.OnValueChanged(element, oldValue, newValue);
      }
    }
  }
}
```