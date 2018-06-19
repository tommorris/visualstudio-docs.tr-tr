---
title: Değişiklikleri Modelin İçinde Yayan Kurallar
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, programming domain models
- Domain-Specific Language, rules
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7b97151ba98a4d854802d96205aefa59fbbdbfac
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952765"
---
# <a name="rules-propagate-changes-within-the-model"></a>Değişiklikleri Modelin İçinde Yayan Kurallar
Bir değişiklik bir öğeden başka bir Görselleştirme ve modelleme SDK (VMSDK) yaymak için bir depolama kural oluşturabilirsiniz. Herhangi bir öğeye deposunda bir değişiklik meydana geldiğinde kuralları genellikle en dıştaki işlem tamamlandığında, yürütülecek zamanlanır. Farklı bir öğe ekleme veya silme gibi olaylar, farklı türleri için kuralı türü vardır. Öğeleri, şekiller veya diyagramları belirli türleri için kurallar ekleyebilirsiniz. Birçok yerleşik özellikleri kuralları tarafından tanımlanır: Örneğin, kuralları model değiştiğinde bir diyagram güncelleştirildiğinden emin olun. Kendi kurallarınızı ekleyerek, etki alanına özgü dil özelleştirebilirsiniz.

 Mağaza kuralları store - diğer bir deyişle, içinde değişiklikleri yayılıyor model öğelerini, ilişkileri, şekiller veya bağlayıcılar ve kendi etki alanı değişiklikleri özellikleri için özellikle yararlıdır. Kullanıcı geri alma veya yineleme komutlarını verdiğinde kuralları çalıştırmayın. Bunun yerine, İşlem Yöneticisi deposu içeriği doğru duruma geri yüklenir emin olur. Mağaza dışında bir kaynağa değişiklikleri yaymak depolamak olayları kullanın. Daha fazla bilgi için bkz: [olay işleyicileri yayılması değişiklikleri dışında modeli](../modeling/event-handlers-propagate-changes-outside-the-model.md).

 Örneğin, kullanıcı (veya kodunuzu) yeni bir öğe türü ExampleDomainClass oluşturduğunda, başka bir tür ek bir öğe başka bir modelin parçası oluşturduğunuz belirlemek istediğinizi varsayalım. Bir AddRule yazma ve ExampleDomainClass ile ilişkilendirin. Kod ek öğe oluşturmak için kuralda yazarsınız.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Microsoft.VisualStudio.Modeling;

namespace ExampleNamespace
{
 // Attribute associates the rule with a domain class:
 [RuleOn(typeof(ExampleDomainClass), FireTime=TimeToFire.TopLevelCommit)]
 // The rule is a class derived from one of the abstract rules:
 class MyAddRule : AddRule
 {
  // Override the abstract method:
  public override void ElementAdded(ElementAddedEventArgs e)
  {
    base.ElementAdded(e);
    ExampleDomainClass element = e.ModelElement;
    Store store = element.Store;
    // Ignore this call if we're currently loading a model:
    if (store.TransactionManager.CurrentTransaction.IsSerializing)
       return;

    // Code here propagates change as required - for example:
      AnotherDomainClass echo = new AnotherDomainClass(element.Partition);
      echo.Name = element.Name;
      echo.Parent = element.Parent;
    }
  }
 // The rule must be registered:
 public partial class ExampleDomainModel
 {
   protected override Type[] GetCustomDomainModelTypes()
   {
     List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());
     types.Add(typeof(MyAddRule));
     // If you add more rules, list them here.
     return types.ToArray();
   }
 }
}

```

> [!NOTE]
>  Bir kural kodu deposu içinde öğeleri durumunu yalnızca değiştirmeniz gerekir; diğer bir deyişle, kural yalnızca model öğelerini, ilişkileri, şekil, bağlayıcılar, diyagramları veya özelliklerini değiştirmeniz gerekir. Mağaza dışında bir kaynağa değişiklikleri yaymak istiyorsanız, olayları depolamak tanımlayın. Daha fazla bilgi için bkz: [olay işleyicileri yayılması değişiklikleri dışında modeli](../modeling/event-handlers-propagate-changes-outside-the-model.md)

### <a name="to-define-a-rule"></a>Bir kural tanımlamak için

1.  Bir sınıf ile önek olarak kural tanımlayın `RuleOn` özniteliği. Öznitelik kural biri etki alanı sınıfları, ilişkileri veya diyagramı öğeleri ile ilişkilendirir. Kural soyut bu sınıfın her örneği için uygulanır.

2.  Kural tarafından döndürülen kümesi ekleyerek kaydetmek `GetCustomDomainModelTypes()` etki alanı modeli sınıfınızda.

3.  Soyut kural sınıflarının birinden kural sınıf türetin ve yürütme yöntemi kodunu yazın.

 Aşağıdaki bölümlerde daha ayrıntılı adımları açıklanmaktadır.

### <a name="to-define-a-rule-on-a-domain-class"></a>Bir etki alanı sınıf üzerinde bir kural tanımlamak için

-   Özel kod dosyasındaki bir sınıf tanımlama ve önüne <xref:Microsoft.VisualStudio.Modeling.RuleOnAttribute> özniteliği:

    ```
    [RuleOn(typeof(ExampleElement),
         // Usual value - but required, because it is not the default:
         FireTime = TimeToFire.TopLevelCommit)]
    class MyRule ...

    ```

-   İlk parametre konu türü, bir etki alanı sınıfı, etki alanı ilişkisinin, şekil, bağlayıcı veya diyagramı olabilir. Genellikle, kuralları etki alanı sınıflar ve ilişkiler için geçerlidir.

     `FireTime` Genellikle `TopLevelCommit`. Bu işlemin tüm birincil değişiklikler yalnızca yaptıktan sonra kural yürütülen sağlar. Değişiklikten hemen sonra kural yürütür satır içi alternatifleri olan; ve kural (hangi dıştaki olmayabilir) geçerli işlem sonunda yürütür LocalCommit. Kuyrukta sıralama etkilemek için bir kural önceliğini de ayarlayabilirsiniz, ancak ihtiyaç duyduğunuz sonuç elde güvenilir olmayan bir yöntem budur.

-   Konu türü olarak soyut bir sınıf belirtebilirsiniz.

-   Kural, konu sınıfın tüm örnekleri için geçerlidir.

-   İçin varsayılan değer `FireTime` TimeToFire.TopLevelCommit değil. Bu, en dıştaki işlem tamamlandığında yürütülecek kural neden olur. TimeToFire.Inline alternatiftir. Bu kural yakında tetikleme olayından sonra yürütülecek neden olur.

### <a name="to-register-the-rule"></a>Kuralı kaydetmek için

-   Tarafından döndürülen türlerinin listesi kuralı sınıfınıza ekleyin `GetCustomDomainModelTypes` etki alanı modelinizdeki:

    ```
    public partial class ExampleDomainModel
     {
       protected override Type[] GetCustomDomainModelTypes()
       {
         List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());
         types.Add(typeof(MyAddRule));
         // If you add more rules, list them here.
         return types.ToArray();
       }
     }

    ```

-   Etki alanı modeli sınıfı adından emin değilseniz, dosyanın içinde Ara **Dsl\GeneratedCode\DomainModel.cs**

-   Özel kod dosyasında DSL projenizdeki bu kodu yazın.

### <a name="to-write-the-code-of-the-rule"></a>Kural kod yazma

-   Kural sınıfı aşağıdaki temel sınıflarının birinden türetilen:

    |Taban sınıfı|Tetikleyici|
    |----------------|-------------|
    |<xref:Microsoft.VisualStudio.Modeling.AddRule>|Bir öğe, bağlantı veya şekil eklenir.<br /><br /> Yeni öğeler yanı sıra yeni ilişkiler algılamak için bunu kullanın.|
    |<xref:Microsoft.VisualStudio.Modeling.ChangeRule>|Bir etki alanı özellik değeri değiştirildi. Yöntem bağımsız değişkeninin eski ve yeni değerleri sağlar.<br /><br /> Şekiller için bu kural tetiklenir olduğunda yerleşik `AbsoluteBounds` şekli taşınırsa özellik değişikliği.<br /><br /> Çoğu durumda, geçersiz kılmak daha kullanışlı `OnValueChanged` veya `OnValueChanging` özelliği işleyicisi. Bu yöntemler, hemen önce ve sonra değişiklik denir. Bunun aksine, kural, genellikle işlem sonunda çalışır. Daha fazla bilgi için bkz: [etki alanı özellik değeri değişiklik işleyicileri](../modeling/domain-property-value-change-handlers.md). **Not:** bir bağlantı oluşturulduğunda veya silindiğinde bu kural tetiklenmez. Bunun yerine, yazma bir `AddRule` ve `DeleteRule` etki alanı ilişki.|
    |<xref:Microsoft.VisualStudio.Modeling.DeletingRule>|Bir öğe veya bağlantı silinmek üzere olduğunda tetiklenir. ModelElement.IsDeleting özelliği işlemin sonuna kadar geçerlidir.|
    |<xref:Microsoft.VisualStudio.Modeling.DeleteRule>|Bir öğe veya bağlantı silindiğinde gerçekleştirilir. Kural DeletingRules dahil olmak üzere diğer tüm kurallar çalıştırılıncaya sonra yürütülür. ModelElement.IsDeleting false olur ve ModelElement.IsDeleted doğrudur. Bir sonraki geri alma için izin vermek için öğe gerçekte bellekten kaldırılmaz, ancak Store.ElementDirectory kaldırılır.|
    |<xref:Microsoft.VisualStudio.Modeling.MoveRule>|Bir öğenin bir depoya bölümünden taşınır.<br /><br /> (Bu bir şekil grafik konuma ilişkili olmadığını dikkat edin.)|
    |<xref:Microsoft.VisualStudio.Modeling.RolePlayerChangeRule>|Bu kural, yalnızca etki alanı ilişkileri için geçerlidir. Bir model öğesi ya da bir bağlantı sonuna açıkça atarsanız tetiklenir.|
    |<xref:Microsoft.VisualStudio.Modeling.RolePlayerPositionChangeRule>|Bağlantılar için veya bir öğeden sıralama MoveBefore veya MoveToIndex yöntemlerini bir bağlantıyı kullanarak değiştirildiğinde tetiklendi.|
    |<xref:Microsoft.VisualStudio.Modeling.TransactionBeginningRule>|Bir işlem oluşturulurken yürütüldü.|
    |<xref:Microsoft.VisualStudio.Modeling.TransactionCommittingRule>|İşlem hakkında kabul edilebilmesi için olduğunda yürütülür.|
    |<xref:Microsoft.VisualStudio.Modeling.TransactionRollingBackRule>|İşlem hakkında geri alınması için olduğunda yürütülür.|

-   Her sınıf, geçersiz bir yöntem vardır. Tür `override` bulması için sınıfınızda. Bu yöntem parametresinin değiştiriliyor öğeyi tanımlar.

 Aşağıdaki noktaları kuralları hakkında dikkat edin:

1.  Bir değişiklik kümesini birçok kuralları tetikleyebilir. Genellikle, en dıştaki işlem tamamlandığında kuralları çalıştırılır. Bunlar, belirtilmeyen bir sırada yürütülür.

2.  Bir kural, bir işlem içinde her zaman yürütülür. Bu nedenle, değişiklik yapmak için yeni bir işlem oluşturmak zorunda değildir.

3.  Kurallar, bir işlem geri alındı veya geri alma veya yineleme işlemleri gerçekleştirildiğinde yürütülmez. Bu işlemler deposunun tüm içeriği önceki durumuna geri sıfırlayın. Kuralınız deposunu dışında bir şey durumu değişirse, bu nedenle, onu synchronism deposuyla içinde içerik tutabilirsiniz değil. Durum deposunu dışında güncelleştirmek için olayları kullanmak en iyisidir. Daha fazla bilgi için bkz: [olay işleyicileri yayılması değişiklikleri dışında modeli](../modeling/event-handlers-propagate-changes-outside-the-model.md).

4.  Bir model dosyasından yüklediğinde bazı kurallar yürütülür. Yükleme veya kaydetme sürüyor olup olmadığını belirlemek için `store.TransactionManager.CurrentTransaction.IsSerializing`.

5.  Daha fazla kural Tetikleyicileri kuralınız kodunu oluşturur, bunlar tetikleme listesinin sonuna eklenir ve işlem tamamlanmadan önce yürütülür. DeletedRules diğer tüm kurallardan sonra yürütülür. Bir kural, bir işlemde her değişiklik için bir kez birçok kez çalıştırabilirsiniz.

6.  Bilgi alıp kuralları geçirmek için bilgisinde saklayabilirsiniz `TransactionContext`. İşlem sırasında korunur bir sözlük budur. İşlem sona erdiğinde atıldı. Her kural olay değişkenlerinde erişimi sağlar. Kuralları tahmin edilebilir bir sırada yürütülmez unutmayın.

7.  Diğer alternatifleri düşünüldükten sonra kuralları kullanın. Örneğin, bir özellik değeri değiştiğinde güncelleştirmek istiyorsanız, hesaplanan bir özellik kullanmayı düşünün. Boyutunu veya konumunu bir şekli sınırlamak istiyorsanız, kullanmak bir `BoundsRule`. Özellik değerinde bir değişiklik yanıt vermek istiyorsanız, ekleyin bir `OnValueChanged` özelliğine işleyici. Daha fazla bilgi için bkz: [yanıtlama ve yayılıyor değişiklikleri](../modeling/responding-to-and-propagating-changes.md).

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, iki öğe bağlamak için bir etki alanı ilişkisinin örneği oluşturulduğunda bir özellik güncelleştirir. Program kodunda bağlantı oluşturursa yalnızca kullanıcı bir bağlantı bir diyagram üzerinde aynı zamanda oluşturduğunda, kuralı tetiklenir.

 Bu örneği test etmek için Görev akışı çözüm şablonu kullanarak bir DSL oluşturmak ve Dsl proje dosyasında aşağıdaki kodu ekleyin. Yapı çözümü çalıştırın ve hata ayıklama projesinde örnek dosyasını açın. Açıklama bağlantısı, bir açıklama şekli ve akış öğesi arasında çizin. Rapor kendisine bağlı en son öğesindeki açıklama metni değiştirir.

 Uygulamada, her AddRule için genellikle bir DeleteRule yazarsınız.

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Microsoft.VisualStudio.Modeling;

namespace Company.TaskRuleExample
{

  [RuleOn(typeof(CommentReferencesSubjects))]
  public class RoleRule : AddRule
  {

    public override void ElementAdded(ElementAddedEventArgs e)
    {
      base.ElementAdded(e);
      CommentReferencesSubjects link = e.ModelElement as CommentReferencesSubjects;
      Comment comment = link.Comment;
      FlowElement subject = link.Subject;
      Transaction current = link.Store.TransactionManager.CurrentTransaction;
      // Don't want to run when we're just loading from file:
      if (current.IsSerializing) return;
      comment.Text = "Flow has " + subject.FlowTo.Count + " outgoing connections";
    }

  }

  public partial class TaskRuleExampleDomainModel
  {
    protected override Type[] GetCustomDomainModelTypes()
    {
      List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());
      types.Add(typeof(RoleRule));
      return types.ToArray();
    }
  }

}

```

## <a name="see-also"></a>Ayrıca Bkz.

- [Değişiklikleri Modelin Dışına Yayan Olay İşleyicileri](../modeling/event-handlers-propagate-changes-outside-the-model.md)
- [BoundsRules Şekil Konumunu ve Boyutunu Kısıtlamama](../modeling/boundsrules-constrain-shape-location-and-size.md)