---
title: Program Kodunda Modeli Gezinme ve Güncelleştirme
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, programming domain models
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 18f4153db019dd6ded97337d4599f02a6b02ef49
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748940"
---
# <a name="navigate-and-update-a-model-in-program-code"></a>Program Kodunda Modelde Gezinme ve Modeli Güncelleştirme

Model öğelerini silin, bunların özelliklerini ayarlamak ve oluşturulur ve öğeler arasındaki bağlantıları silmek üzere kod yazabilirsiniz. Bir işlem içinde yapılan tüm değişiklikler gerekir. Öğeleri bir diyagramda görüntülerse diyagram "otomatik olarak işlem sonunda düzeltilecektir".

## <a name="in-this-topic"></a>Bu Konu kapsamında
 [Bir örnek DSL tanımı](#example)

 [Model gezinme](#navigation)

 [Sınıf bilgilerine erişme](#metadata)

 [Bir işlemin içindeki değişiklikleri gerçekleştirin](#transaction)

 [Model öğelerini oluşturma](#elements)

 [İlişki bağlantılar oluşturma](#links)

 [Öğeleri silme](#deleteelements)

 [İlişki bağlantıları silme](#deletelinks)

 [Bir ilişki bağlantılar yeniden sıralama](#reorder)

 [Kilitler](#locks)

 [Kopyala ve Yapıştır](#copy)

 [Gezinme ve diyagramları güncelleştiriliyor](#diagrams)

 [Şekiller ve öğeleri arasında gezinme](#views)

 [Şekiller ve bağlayıcılar özellikleri](#shapeProperties)

 [DocView ve DocData](#docdata)

##  <a name="example"></a> Bir örnek DSL tanımı
 Bu ana DslDefinition.dsl için bu konudaki örnekler parçasıdır:

 ![DSL tanımı diyagramı &#45; Aile Ağacı Modeli](../modeling/media/familyt_person.png)

 Bu model, bu DSL örneğidir:

 ![Tudor Aile Ağacı Modeli](../modeling/media/tudor_familytreemodel.png)

### <a name="references-and-namespaces"></a>References ve ad alanları
 Bu konudaki kodu çalıştırmak için başvuru:

 `Microsoft.VisualStudio.Modeling.Sdk.11.0.dll`

 Kodunuzu bu ad alanı kullanır:

 `using Microsoft.VisualStudio.Modeling;`

 Ayrıca, DSL tanımlandığı olandan farklı bir proje kodunu yazıyorsanız Dsl projenin oluşturduğu derleme almanız gerekir.

##  <a name="navigation"></a> Model gezinme

### <a name="properties"></a>Özellikler
 DSL açıklamasında tanımlayın etki alanı özellikleri program kodunda erişebildiği özellikleri olur:

 `Person henry = ...;`

 `if (henry.BirthDate < 1500) ...`

 `if (henry.Name.EndsWith("VIII")) ...`

 Bir özelliği ayarlamak istiyorsanız, bunu içinde yapmalısınız bir [işlem](#transaction):

 `henry.Name = "Henry VIII";`

 DSL tanımının, bir özellik içindeki IF **türü** olan **hesaplanan**, bunu göremezsiniz. Daha fazla bilgi için bkz: [hesaplanan ve özel depolama özellikleri](../modeling/calculated-and-custom-storage-properties.md).

### <a name="relationships"></a>İlişkiler
 DSL açıklamasında tanımlayın etki alanı ilişkilerini özellikleri, bir sınıf ilişkisinin her iki ucunda çiftlerini haline gelir. Özellik adlarını DslDefinition diyagramda ilişkiyi her tarafında rolleri etiket olarak görünür. Role çokluğu bağlı olarak, ilişkinin diğer ucundaki sınıfı ya da bu sınıfın bir koleksiyon özelliği türüdür.

 `foreach (Person child in henry.Children) { ... }`

 `FamilyTreeModel ftree = henry.FamilyTreeModel;`

 Bir ilişki ters ucundaki her zaman özelliklerdir devrik. Bir bağlantı oluşturulduğunda veya silindiğinde, her iki öğelerde rolü özellikleri güncelleştirilir. Aşağıdaki ifade (uzantılarını kullanan `System.Linq`) örnek ParentsHaveChildren ilişkisinde için her zaman geçerlidir:

 `(Person p) => p.Children.All(child => child.Parents.Contains(p))`

 `&& p.Parents.All(parent => parent.Children.Contains(p));`

 **ElementLinks**. Bir ilişki adlı bir model öğesi tarafından temsil edilen bir *bağlantı*, etki alanı ilişki türünün bir örneği değil. Bir bağlantı, bir kaynak öğesi ve bir hedef öğe her zaman vardır. Source öğesi ve hedef öğe aynı olabilir.

 Bir bağlantı ve özelliklerini erişebilirsiniz:

 `ParentsHaveChildren link = ParentsHaveChildren.GetLink(henry, edward);`

 `// This is now true:`

 `link == null || link.Parent == henry && link.Child == edward`

 Varsayılan olarak, herhangi bir model öğelerini çifti bağlamak için bir ilişki birden fazla örneğine izin verilir. Ancak DSL tanımında varsa, `Allow Duplicates` bayrağı ilişki için doğrudur sonra birden fazla bağlantı olabilir ve kullanmanız gerekir `GetLinks`:

 `foreach (ParentsHaveChildren link in ParentsHaveChildren.GetLinks(henry, edward)) { ... }`

 Bağlantılar erişmek için diğer yöntemler vardır. Örneğin:

 `foreach (ParentsHaveChildren link in     ParentsHaveChildren.GetLinksToChildren(henry)) { ... }`

 **Gizli rolleri.** DSL tanımında varsa, **oluşturulur özelliği** olan **false** belirli bir rol için ardından özellik bu role karşılık gelen oluşturulur. Ancak, yine bağlantıları erişebilir ve ilişki yöntemleri kullanılarak bağlantılar:

 `foreach (Person p in ParentsHaveChildren.GetChildren(henry)) { ... }`

 En sık kullanılan örnek <xref:Microsoft.VisualStudio.Modeling.Diagrams.PresentationViewsSubject> diyagramda görüntüler şeklin bir model öğesi bağlantıları ilişki:

 `PresentationViewsSubject.GetPresentation(henry)[0] as PersonShape`

### <a name="the-element-directory"></a>Öğe dizini
 Öğe dizini kullanarak deposundaki tüm öğeleri erişebilirsiniz:

 `store.ElementDirectory.AllElements`

 Aşağıdaki gibi öğeleri bulmak için yöntemleri vardır:

 `store.ElementDirectory.FindElements(Person.DomainClassId);`

 `store.ElementDirectory.GetElement(elementId);`

##  <a name="metadata"></a> Sınıf bilgilerine erişme
 Sınıfları, ilişkileri ve diğer yönlerini DSL tanımı hakkında bilgi alabilirsiniz. Örneğin:

 `DomainClassInfo personClass = henry.GetDomainClass();`

 `DomainPropertyInfo birthProperty =`

 `personClass.FindDomainProperty("BirthDate")`

 `DomainRelationshipInfo relationship =`

 `link.GetDomainRelationship();`

 `DomainRoleInfo sourceRole = relationship.DomainRole[0];`

 Model öğelerini üst sınıflarını aşağıdaki gibidir:

-   Model öğesi - tüm öğeleri ve ilişkileri olan ModelElements

-   ElementLink - tüm ilişkiler ElementLinks olan

##  <a name="transaction"></a> Bir işlemin içindeki değişiklikleri gerçekleştirin
 Program kodunuzu deposundaki herhangi bir şey değiştiğinde, bunu bir işlem içinde yapmalısınız. Bu, tüm model öğelerini, ilişkileri, şekiller, diyagramları ve bunların özelliklerini için geçerlidir. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.Modeling.Transaction>.

 Bir işlem yönetme en kolay yöntem olan bir `using` deyimi içine bir `try...catch` deyimi:

```
Store store; ...
try
{
  using (Transaction transaction =
    store.TransactionManager.BeginTransaction("update model"))
    // Outermost transaction must always have a name.
  {
    // Make several changes in Store:
    Person p = new Person(store);
    p.FamilyTreeModel = familyTree;
    p.Name = "Edward VI";
    // end of changes to Store

    transaction.Commit(); // Don't forget this!
  } // transaction disposed here
}
catch (Exception ex)
{
  // If an exception occurs, the Store will be
  // rolled back to its previous state.
}
```

 Herhangi bir sayıda bir işlem içinde değişiklikleri yapabilirsiniz. Yeni bir işlem etkin bir işlem içinde açabilirsiniz.

 Değişikliklerinizi kalıcı yapmak için şunları yapmalısınız `Commit` bırakılana önce işlem. İşlem içinde yakalandı bir özel durum oluşursa, deposu değişiklikleri önce durumuna sıfırlar.

##  <a name="elements"></a> Model öğelerini oluşturma
 Bu örnek, var olan bir model için bir öğe ekler:

```
FamilyTreeModel familyTree = ...; // The root of the model.
using (Transaction t =
    familyTree.Store.TransactionManager
    .BeginTransaction("update model"))
{
  // Create a new model element
  // in the same partition as the model root:
  Person edward = new Person(familyTree.Partition);
  // Set its embedding relationship:
  edward.FamilyTreeModel = familyTree;
          // same as: familyTree.People.Add(edward);
  // Set its properties:
  edward.Name = "Edward VII";
  t.Commit(); // Don't forget this!
}
```

 Bu örnekte, bir öğe oluşturma hakkında daha fazla bu önemli noktaları gösterilmektedir:

-   Yeni öğe deposu belirli bir bölüme oluşturun. Model öğelerini ve ilişkileri ancak değil şekiller için bu genellikle varsayılan bölümdür.

-   Katıştırma bir ilişki hedef kolaylaştırır. Bu örnek DslDefinition içinde her kişi ilişki FamilyTreeHasPeople katıştırma hedefi olması gerekir. Bunun için biz kişi nesnesinin FamilyTreeModel rol özelliğini ayarlayın veya FamilyTreeModel nesnesinin kişiler rol özelliğine kişiyi ekler.

-   Özellikle özelliği olduğu için yeni bir öğe özelliklerini ayarla `IsName` DslDefinition doğrudur. Bu bayrak öğe sahibi içinde benzersiz şekilde tanımlamak için kullanılır özelliği işaretler. Bu durumda, Name özelliği bu bayrağı vardır.

-   Bu DSL DSL tanımını deposuna yüklenmiş olmalıdır. Uzantı menü komutu gibi yazıyorsanız, bu genellikle önceden true olması gerekir. Diğer durumlarda, açıkça modeli deposuna yüklemek veya için kullanmak <xref:Microsoft.VisualStudio.Modeling.Integration.ModelBus> yüklemek için. Daha fazla bilgi için bkz: [nasıl yapılır: Program kodundaki dosyasından Model açmak](../modeling/how-to-open-a-model-from-file-in-program-code.md).

 Bu şekilde bir öğeyi oluşturduğunuzda (DSL diyagram varsa) bir şekli otomatik olarak oluşturulur. Varsayılan Şekil, renk ve diğer özellikleri otomatik olarak atanmış bir konumda görünür. Nerede ve nasıl ilişkili şekli görünür denetlemek istiyorsanız bkz [bir öğe ve şeklini oluşturma](#merge).

##  <a name="links"></a> İlişki bağlantılar oluşturma
 DSL tanımı örnekte tanımlanan iki ilişkisi vardır. Her ilişkiyi tanımlayan bir *rol özellik* ilişkisinin her iki ucunda sınıfı.

 Bir ilişki örneği oluşturabileceğiniz üç yolu vardır. Bu üç yöntemlerin her biri aynı etkiye sahiptir:

-   Kaynak rolü player özelliğini ayarlayın. Örneğin:

    -   `familyTree.People.Add(edward);`

    -   `edward.Parents.Add(henry);`

-   Hedef rolü player özelliğini ayarlayın. Örneğin:

    -   `edward.familyTreeModel = familyTree;`

         Bu role çokluğu olan `1..1`, biz değerini atayın.

    -   `henry.Children.Add(edward);`

         Bu role çokluğu olan `0..*`, biz koleksiyonuna ekleyin.

-   İlişki örneği açıkça oluşturun. Örneğin:

    -   `FamilyTreeHasPeople edwardLink = new FamilyTreeHasPeople(familyTreeModel, edward);`

    -   `ParentsHaveChildren edwardHenryLink = new ParentsHaveChildren(henry, edward);`

 Son yöntem ilişkinin kendisini özelliklerini ayarlamak istiyorsanız kullanışlıdır.

 Bu şekilde bir öğeyi oluşturduğunuzda, diyagramdan bir bağlayıcı otomatik olarak oluşturulur, ancak varsayılan şekil, renk ve diğer özellikleri vardır. İlişkili bağlayıcısının nasıl oluşturulacağını denetlemek için bkz: [bir öğe ve şeklini oluşturma](#merge).

##  <a name="deleteelements"></a> Öğeleri silme
 Çağırarak öğeyi Sil `Delete()`:

 `henry.Delete();`

 Bu işlem de silinmesine neden olur:

-   Bağlantılar öğeden ilişki. Örneğin, `edward.Parents` artık içerecek `henry`.

-   Rollerin öğeler `PropagatesDelete` bayrağı doğrudur. Örneğin, öğenin görüntülediğini şekli silinir.

 Varsayılan olarak, her katıştırma ilişkisine sahip `PropagatesDelete` hedefi rolü true. Silme `henry` silmediği `familyTree`, ancak `familyTree.Delete()` tüm silebilirsiniz `Persons`. Daha fazla bilgi için bkz: [özelleştirme silme davranışı](../modeling/customizing-deletion-behavior.md).

 Varsayılan olarak, `PropagatesDelete` başvuru ilişkileri roller için geçerli değildir.

 Bir nesne sildiğinizde belirli yayma atlamak silme kuralları neden olabilir. Bu için başka bir öğe değiştirerek yararlıdır. Kendisi için silme değil dağıtılmasını bir veya daha fazla rol GUID sağlayın. GUID ilişki sınıfından edinilebilir:

 `henry.Delete(ParentsHaveChildren.SourceDomainRoleId);`

 (Bu belirli örnekte hiçbir etkisi yoktur, çünkü `PropagatesDelete` olan `false` rolleri için `ParentsHaveChildren` ilişkisi.)

 Bazı durumlarda, silme, öğe veya yayma tarafından silinecek bir öğe üzerinde bir kilit varlığı tarafından engellenir. Kullanabileceğiniz `element.CanDelete()` öğesi silinmiş olup olmadığını denetlemek için.

##  <a name="deletelinks"></a> İlişki bağlantıları silme
 Bir öğenin bir rol özelliğinden kaldırarak bir ilişki bağlantısı silebilirsiniz:

 `henry.Children.Remove(edward); // or:`

 `edward.Parents.Remove(henry);  // or:`

 Bağlantıyı açıkça silebilirsiniz:

 `edwardHenryLink.Delete();`

 Tüm bu üç yöntem aynı etkiye sahiptir. Yalnızca bunlardan birini kullanmanız gerekebilir.

 Rol 0.. 1 çokluğa veya 1..1 Çokluk varsa, onu ayarlayabilirsiniz `null`, veya başka bir değer için:

 `edward.FamilyTreeModel = null;` ya da:

 `edward.FamilyTreeModel = anotherFamilyTree;`

##  <a name="reorder"></a> Bir ilişki bağlantılar yeniden sıralama
 Belirli bir sırada kaynaklanan veya belirli model öğede hedeflenen belirli bir ilişki bağlantınız. İçinde eklendikleri sırayla görünürler. Örneğin, bu deyimi her zaman aynı sırada alt sunacak:

 `foreach (Person child in henry.Children) ...`

 Bağlantıların sırasını değiştirebilirsiniz:

 `ParentsHaveChildren link = GetLink(henry,edward);`

 `ParentsHaveChildren nextLink = GetLink(henry, elizabeth);`

 `DomainRoleInfo role =`

 `link.GetDomainRelationship().DomainRoles[0];`

 `link.MoveBefore(role, nextLink);`

##  <a name="locks"></a> Kilitler
 Değişikliklerinizi kilidi ile engellenebilir. Kilitleri ayrı ayrı öğeler, bölümler ve mağaza ayarlayabilirsiniz. Bu düzeyleri birini yapmak istediğiniz değişikliği tür engelleyen bir kilit varsa, onu çalıştığınızda bir özel durum oluşturulabilir. Kilitleri öğesini kullanarak ayarlanıp ayarlanmadığını bulabilir. Ad alanında tanımlı bir genişletme yöntemi olan GetLocks() <xref:Microsoft.VisualStudio.Modeling.Immutability>.

 Daha fazla bilgi için bkz: [kilitleme ilkesi oluşturma salt okunur segmentlere tanımlama](../modeling/defining-a-locking-policy-to-create-read-only-segments.md).

##  <a name="copy"></a> Kopyala ve Yapıştır
 Öğeleri veya öğelerine grupları kopyalayabilirsiniz bir <xref:System.Windows.Forms.IDataObject>:

```
Person person = personShape.ModelElement as Person;
Person adopter = adopterShape.ModelElement as Person;
IDataObject data = new DataObject();
personShape.Diagram.ElementOperations
      .Copy(data, person.Children.ToList<ModelElement>());
```

 Öğeleri bir seri hale getirilmiş öğesi grubu olarak depolanır.

 Bir modele IDataObject öğelerini birleştirebilirsiniz:

```
using (Transaction t = targetDiagram.Store.
        TransactionManager.BeginTransaction("paste"))
{
  adopterShape.Diagram.ElementOperations.Merge(adopter, data);
}
```

 `Merge ()` kabul ya da bir `PresentationElement` veya `ModelElement`. Bu bildirimde bir `PresentationElement`, üçüncü parametre olarak hedef diyagramdaki bir konum belirtebilirsiniz.

##  <a name="diagrams"></a> Gezinme ve diyagramları güncelleştiriliyor
 Bir DSL, kişi veya şarkı gibi bir kavram temsil eder, etki alanı model öğesi diyagramı gördükleri temsil eden şekli öğeden ayrıdır. Etki alanı model öğesi ilişkileri kavramları ve önemli özellikleri depolar. Şekil öğesi, konumu ve boyutu nesnenin görünümü diyagramda rengini ve düzenini bileşen parçalarından depolar.

### <a name="presentation-elements"></a>Sunu öğelerini
 ![Sınıf diyagramında temel şekli ve öğesi türleri](../modeling/media/dslshapesandelements.png)

 DSL tanımınızı belirttiğiniz her öğesi aşağıdaki standart sınıflarının birinden türetilmiş bir sınıf oluşturur.

|Öğesinin türü|Taban sınıfı|
|---------------------|----------------|
|Etki alanı sınıfı|<xref:Microsoft.VisualStudio.Modeling.ModelElement>|
|Etki alanı ilişkisi|<xref:Microsoft.VisualStudio.Modeling.ElementLink>|
|Şekil|<xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape>|
|Bağlayıcı|<xref:Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape>|
|Diyagram|<xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>|

 Bir öğeyi diyagramında genellikle bir model öğesi temsil eder. Genellikle (ancak her zaman), bir <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape> bir etki alanı sınıfı örneğini temsil eder ve bir <xref:Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape> bir etki alanı ilişki örneği temsil eder. <xref:Microsoft.VisualStudio.Modeling.Diagrams.PresentationViewsSubject> İlişkiyi temsil ettiği model öğesi bir düğüme veya bağlantıya şekli bağlar.

 Her düğüme veya bağlantıya şeklin bir diyagrama ait. Bir ikili bağlantı şekli iki düğüm şekil bağlanır.

 Şekilleri alt şekilleri iki kümelerinde olabilir. Bir şekli `NestedChildShapes` kümesi üst sınırlayıcı kutusuna sınırlı. Bir şekli `RelativeChildShapes` liste dışında veya kısmen - örneğin bir etiket veya bağlantı noktası üst sınırları dışında görünebilir. Bir diyagram sahip olmayan `RelativeChildShapes` ve hiçbir `Parent`.

###  <a name="views"></a> Şekiller ve öğeleri arasında gezinme
 Etki alanı model öğelerini ve Şekil öğelerine ilgili tarafından <xref:Microsoft.VisualStudio.Modeling.Diagrams.PresentationViewsSubject> ilişki.

```csharp
// using Microsoft.VisualStudio.Modeling;
// using Microsoft.VisualStudio.Modeling.Diagrams;
// using System.Linq;
Person henry = ...;
PersonShape henryShape =
  PresentationViewsSubject.GetPresentation(henry)
    .FirstOrDefault() as PersonShape;
```

 Aynı ilişki ilişkileri diyagramda bağlayıcılar bağlantılarını içerir:

```
Descendants link = Descendants.GetLink(henry, edward);
DescendantConnector dc =
   PresentationViewsSubject.GetPresentation(link)
     .FirstOrDefault() as DescendantConnector;
// dc.FromShape == henryShape && dc.ToShape == edwardShape
```

 Bu ilişki diyagrama ayrıca modelin kökü bağlantılarını içerir:

```
FamilyTreeDiagram diagram =
   PresentationViewsSubject.GetPresentation(familyTree)
      .FirstOrDefault() as FamilyTreeDiagram;
```

 Bir şekli tarafından temsil edilen model öğesi almak için kullanın:

 `henryShape.ModelElement as Person`

 `diagram.ModelElement as FamilyTreeModel`

### <a name="navigating-around-the-diagram"></a>Geçici bir çözüm diyagramı gezinme
 Genel olarak, şekilleri ve bağlayıcıları diyagramda arasında gezinmek için önerilmez. Yalnızca Diyagram görünümünü çalışması gerekli olduğunda bağlayıcılar ve şekiller arasında taşıma modelin ilişkilerde gezinme daha iyidir. Bu yöntemlerin her iki ucunda şekillere bağlayıcılar Bağla:

 `personShape.FromRoleLinkShapes, personShape.ToRoleLinkShapes`

 `connector.FromShape, connector.ToShape`

 Birçok şekil bileşik; yine de uygun istiyor musunuz? Bunlar bir üst şekli ve bir veya daha fazla Katmanlar alt oluşur. Başka bir şekil göre konumlandırılmış şekiller denirse olacak şekilde kendi *alt*. Üst şekil taşındığında, alt öğelerini birlikte taşınır.

 *Göreli alt* üst şekil sınırlayıcı kutunun dışında yer alabilir. *İç içe geçmiş* alt öğe üst sınırları içinde kesinlikle görünür.

 Bir diyagram şekillerdeki üst kümesi almak için kullanın:

 `Diagram.NestedChildShapes`

 Şekiller ve bağlayıcıların üst sınıfları şunlardır:

 <xref:Microsoft.VisualStudio.Modeling.ModelElement>

 -- <xref:Microsoft.VisualStudio.Modeling.Diagrams.PresentationElement>

 -- <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement>

 ----- <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape>

 ------- <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>

 ------- *YourShape*

 ----- <xref:Microsoft.VisualStudio.Modeling.Diagrams.LinkShape>

 ------- <xref:Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape>

 --------- *YourConnector*

###  <a name="shapeProperties"></a> Şekiller ve bağlayıcılar özellikleri
 Çoğu durumda, şekillere açık değişiklik yapmak gerekli değildir. Model öğelerini değiştirildiğinde "Düzelt" kuralları şekilleri ve bağlayıcıları güncelleştirin. Daha fazla bilgi için bkz: [yanıtlama ve yayılıyor değişiklikleri](../modeling/responding-to-and-propagating-changes.md).

 Ancak, bazı açık şekiller model öğelerini bağımsız özelliklerinde değişiklik kullanışlıdır. Örneğin, bu özellikleri değiştirebilirsiniz:

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape.Size%2A> -Şeklin genişliği ve yüksekliği belirler.

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape.Location%2A> -konumuna göre üst şekli veya diyagramı

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.StyleSet%2A> -kalemler ve Şekil veya bağlayıcı çizmek için kullanılan Fırçalar kümesi

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.Hide%2A> -Şekli görünmez yapar

-   <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement.Show%2A> -Şekli sonra görünür hale getirir bir `Hide()`

###  <a name="merge"></a> Bir öğe ve şeklini oluşturma
 Bir öğe oluşturun ve ilişkileri katıştırma ağacına Bağla bir şekli otomatik olarak oluşturulan ve onunla ilişkili. Bu işlemin sonunda yürütme "düzeltmesi" kuralları tarafından gerçekleştirilir. Ancak, otomatik olarak atanmış bir konumda şekli görünür ve şeklini, rengini ve diğer özellikleri varsayılan değerlere sahip olur. Şeklin nasıl oluşturulacağını denetlemek için birleştirme işlevi kullanabilirsiniz. Önce bir ElementGroup eklemek istediğiniz öğeleri ekleyin ve sonra Grup diyagrama birleştirin.

 Bu yöntem:

-   Bir özellik öğesi olarak atanmışsa adını ayarlar.

-   Hiçbir öğe birleştirme DSL tanımında belirtilen yönergeleri görür.

 Kullanıcı diyagram tıkladığında bu örnek bir şekli fare konumunda oluşturur. Bu örnek için DSL tanımında `FillColor` özelliği `ExampleShape` kullanıma sunulan.

```

using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;
partial class MyDiagram
{
  public override void OnDoubleClick(DiagramPointEventArgs e)
  {
    base.OnDoubleClick(e);

    using (Transaction t = this.Store.TransactionManager
        .BeginTransaction("double click"))
    {
      ExampleElement element = new ExampleElement(this.Store);
      ElementGroup group = new ElementGroup(element);

      { // To use a shape of a default size and color, omit this block.
        ExampleShape shape = new ExampleShape(this.Partition);
        shape.ModelElement = element;
        shape.AbsoluteBounds = new RectangleD(0, 0, 1.5, 1.0);
        shape.FillColor = System.Drawing.Color.Azure;
        group.Add(shape);
      }

      this.ElementOperations.MergeElementGroupPrototype(
        this,
        group.CreatePrototype(),
        PointD.ToPointF(e.MousePosition));
      t.Commit();
    }
  }
}

```

 Birden fazla şekil sağlamak istiyorsanız, ilgili konumlarını kullanarak ayarlayın `AbsoluteBounds`.

 Renk ve bu yöntemi kullanarak bağlayıcılar sunulan diğer özelliklerini de ayarlayabilirsiniz.

### <a name="use-transactions"></a>İşlemleri kullanma
 Şekil, bağlayıcılar ve diyagramları olan alt türleri, <xref:Microsoft.VisualStudio.Modeling.ModelElement> ve dinamik depolama. Bu nedenle değişiklikler için yalnızca bir işlem içinde yapmanız gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: kullanım modeli güncelleştirmek için işlemleri](../modeling/how-to-use-transactions-to-update-the-model.md).

##  <a name="docdata"></a> Belge görünümü ve belge verileri
 ![Standart diyagram türleri sınıf diyagramı](../modeling/media/dsldiagramsanddocs.png)

## <a name="store-partitions"></a>Bölüm
 Bir model yüklendiğinde eşlik eden diyagramı aynı anda yüklenir. Genellikle, model Store.DefaultPartition yüklenir ve diyagramı içeriği başka bir bölüme yüklenir. Genellikle, her bölümün içeriğini yüklenen ve ayrı bir dosyaya kaydedilir.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.Modeling.ModelElement>
- [Etki Alanına Özgü bir Dilde Doğrulama](../modeling/validation-in-a-domain-specific-language.md)
- [Etki Alanına Özgü Dilden Kod Oluşturma](../modeling/generating-code-from-a-domain-specific-language.md)
- [Nasıl yapılır: Modeli Güncelleştirmek için İşlemleri Kullanma](../modeling/how-to-use-transactions-to-update-the-model.md)
- [Visual Studio Modelbus'ı Kullanarak Modelleri Tümleştirme](../modeling/integrating-models-by-using-visual-studio-modelbus.md)
- [Değişikliklere Yanıt Verme ve Değişiklikleri Yayma](../modeling/responding-to-and-propagating-changes.md)
