---
title: "Kopyalama davranışını özelleştirme | Microsoft Docs"
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
ms.openlocfilehash: a9a17cba8e1ff1cca66f82c1d3934ff179b04fd9
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="customizing-copy-behavior"></a>Kopyalama Davranışını Özelleştirme
İle oluşturulmuş bir etki alanına özgü dil (DSL) içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Görselleştirme ve modelleme SDK, kullanıcı kopyalar ve öğeleri gönderebilir ne olur değiştirebilirsiniz.  
  
## <a name="standard-copy-and-paste-behavior"></a>Standart Kopyala ve yapıştır davranışı  
 Kopyalama etkinleştirmek için ayarlanmış **etkinleştirmek kopyalayıp yapıştırın** özelliği **Düzenleyicisi** DSL Gezgininde düğümü.  
  
 Varsayılan olarak, aşağıdaki öğeleri de kullanıcı öğeleri Panoya kopyalarken kopyalanır:  
  
-   Seçilen öğeleri katıştırılmış alt öğeleri. (Diğer bir deyişle, öğeleri adresindeki kaynaklanan ilişkileri katıştırma hedefleri olan öğeler kopyalanır.)  
  
-   Kopyalanan öğeleri arasındaki ilişki bağlantılar.  
  
 Bu kural kopyalanan öğeleri ve bağlantıları yinelemeli olarak uygulanır.  
  
 ![Kopyalanır ve öğeleri yapıştırılan](../modeling/media/dslcopypastedefault.png "DslCopyPasteDefault")  
  
 Bağlantılar ve kopyalanan öğelerin seri içinde depolanan ve bir <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype> (EGP) Pano'ya yerleştirilir.  
  
 Görüntüyü kopyalanan öğelerin ayrıca panoya yerleştirilir. Bu kullanıcının Word gibi diğer uygulamaları yapıştırın olanak sağlar.  
  
 Kullanıcı DSL tanımına göre öğeleri kabul edebileceği bir hedef üzerine kopyalanan öğelerin yapıştırabilirsiniz. Örneğin, bileşenleri çözüm şablondan oluşturulan bir DSL içinde kullanıcı bileşenleri üzerine ancak diyagram üzerine olmayan bağlantı noktaları yapıştırabilirsiniz; ve bileşenlerinin diyagram üzerine ancak diğer bileşenleri üzerine değildir yapıştırabilirsiniz.  
  
## <a name="customizing-copy-and-paste-behavior"></a>Kopyala ve Yapıştır davranışını özelleştirme  
 Program kodunu kullanarak model özelleştirme hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 **Etkinleştirmek veya kopyalama, kesme ve yapıştırma devre dışı bırakın.**  
 DSL Explorer'da ayarlayın **etkinleştirmek kopyalayıp yapıştırın** özelliği **Düzenleyicisi** düğümü.  
  
 **Bağlantıları aynı hedefe kopyalayın.** Örneğin, kopyalanan açıklama kutusunun sağlamak için aynı konu öğesine bağlı.  
 Ayarlama **yayar kopyalama** rolüne özelliğinin **yalnızca bağlamak için kopyalama yayılması**. Daha fazla bilgi için bkz: [bağlantı kopyalama davranışını özelleştirme](#customizeLinks).  
  
 Bağlantılı öğeler kopyalayın. Örneğin, yeni bir öğe kopyaladığınızda, hiçbir bağlı açıklama kutusu kopyalarını da yapılır.  
 Ayarlama **yayar kopyalama** rolüne özelliğinin **kopyalama bağlamak ve rol player ters yayılması**. Daha fazla bilgi için bkz: [bağlantı kopyalama davranışını özelleştirme](#customizeLinks).  
  
 **Kopyalama ve yapıştırma tarafından hızlı bir şekilde yinelenen öğeler.** Normalde, kopyaladığınız öğeyi seçiliyken ve aynı türdeki öğe üzerine yapıştıramazsınız.  
 Bir öğenin birleştirme yönergesi etki alanı sınıfına ekleyin ve üst sınıfı için İleri birleştirme ayarlayın. Bu aynı sürükleme işlemleri üzerindeki etkisi olmaz. Daha fazla bilgi için bkz: [özelleştirme öğesi oluşturma ve taşıma](../modeling/customizing-element-creation-and-movement.md).  
  
 \-veya -  
  
 Geçersiz kılarak öğeleri yapıştırmadan önce diyagramı `ClipboardCommandSet.ProcessOnPasteCommand()`. Özel bir DslPackage proje dosyasında bu kodu ekleyin:  
  
```csharp  
namespace Company.MyDsl {  
using System.Linq;  
using Microsoft.VisualStudio.Modeling.Diagrams;   
using Microsoft.VisualStudio.Modeling.Shell;  
partial class MyDslClipboardCommandSet  
{  
  protected override void ProcessOnMenuPasteCommand()  
  {  
 // Deselect the current selection after copying:  
 Diagram diagram = (this.CurrentModelingDocView as SingleDiagramDocView).Diagram;  
    this.CurrentModelingDocView  
     .SelectObjects(1, new object[] { diagram }, 0);  
  }  
} }  
  
```  
  
 **Seçili hedef kullanıcı gönderebilir, ek bağlantılar oluşturun.** Örneğin, bir açıklama kutusu öğenin üzerine yapıştırılırken bağlantı aralarında yapılır.  
 Bir öğenin birleştirme yönergesi hedef etki alanı sınıfına ekleyin ve birleştirme bağlantılar ekleyerek işlemek için ayarlayın. Bu aynı sürükleme işlemleri üzerindeki etkisi olmaz. Daha fazla bilgi için bkz: [özelleştirme öğesi oluşturma ve taşıma](../modeling/customizing-element-creation-and-movement.md).  
  
 \-veya -  
  
 Geçersiz kılma `ClipboardCommandSet.ProcessOnPasteCommand()` temel yöntemi çağrıldıktan sonra ek bağlantılar oluşturmak için.  
  
 **Hangi öğeleri kopyalanabilir biçimleri özelleştirme** bit eşlem formun kenarlık eklemek için dış uygulamalara - Örneğin,.  
 Geçersiz kılma *MyDsl* `ClipboardCommandSet.ProcessOnMenuCopyCommand()` DslPackage projesinde.  
  
 **Nasıl öğeleri Panoya Kopyala komutu tarafından ancak bir sürükleme işlemi kopyalanır özelleştirin.**  
 Geçersiz kılma *MyDsl* `ClipboardCommandSet.CopyModelElementsIntoElementGroupPrototype()` DslPackage projesinde.  
  
 **Şekil düzenini kopyalama aracılığıyla korumak ve yapıştırın.**  
 Kullanıcı birden çok şekil kopyaladığında, bunlar yapıştırılırken ilgili konumlarını koruyabilirsiniz. Bu teknik örneğe tarafından gösterilen [VMSDK: hattı diyagramları örnek](http://go.microsoft.com/fwlink/?LinkId=213879).  
  
 Bu etkiyi elde etmek için kopyalanan ElementGroupPrototype şekilleri ve bağlayıcıları ekleyin. Geçersiz kılmak için en uygun ElementOperations.CreateElementGroupPrototype() yöntemdir. Bunu yapmak için Dsl projeye aşağıdaki kodu ekleyin:  
  
```csharp  
  
public class MyElementOperations : DesignSurfaceElementOperations  
{  
  // Create an EGP to add to the clipboard.  
  // Called when the elements to be copied have been  
  // collected into an ElementGroup.  
 protected override ElementGroupPrototype CreateElementGroupPrototype(ElementGroup elementGroup, ICollection<ModelElement> elements, ClosureType closureType)  
  {  
 // Add the shapes and connectors:  
 // Get the elements already in the group:  
    ModelElement[] mels = elementGroup.ModelElements  
        .Concat(elementGroup.ElementLinks) // Omit if the paste target is not the diagram.  
        .ToArray();  
 // Get their shapes:  
    IEnumerable<PresentationElement> shapes =   
       mels.SelectMany(mel =>   
            PresentationViewsSubject.GetPresentation(mel));  
    elementGroup.AddRange(shapes);  
  
 return base.CreateElementGroupPrototype  
           (elementGroup, elements, closureType);  
  }  
  
 public MyElementOperations(IServiceProvider serviceProvider, ElementOps1Diagram diagram)  
      : base(serviceProvider, diagram)  
  { }  
}  
  
// Replace the standard ElementOperations  
// singleton with your own:  
partial class MyDslDiagram // EDIT NAME  
{  
 /// <summary>  
 /// Singleton ElementOperations attached to this diagram.  
 /// </summary>  
 public override DesignSurfaceElementOperations ElementOperations  
  {  
 get  
    {  
 if (singleton == null)  
      {  
        singleton = new MyElementOperations(this.Store as IServiceProvider, this);  
      }  
 return singleton;  
    }  
  }  
 private MyElementOperations singleton = null;  
}  
  
```  
  
 **Geçerli imleç konumu gibi seçtiğiniz bir konumda şekiller yapıştırın.**  
 Kullanıcı birden çok şekil kopyaladığında, bunlar yapıştırılırken ilgili konumlarını koruyabilirsiniz. Bu teknik örneğe tarafından gösterilen [VMSDK: hattı diyagramları örnek](http://go.microsoft.com/fwlink/?LinkId=213879).  
  
 Bu etkiyi elde etmek için geçersiz kılma `ClipboardCommandSet.ProcessOnMenuPasteCommand()` konuma özgü sürümünü kullanmak üzere `ElementOperations.Merge()`. Bunu yapmak için DslPackage projesinde aşağıdaki kodu ekleyin:  
  
```csharp  
  
partial class MyDslClipboardCommandSet // EDIT NAME  
{  
   /// <summary>  
    /// This method assumes we only want to paste things onto the diagram  
    /// - not onto anything contained in the diagram.  
    /// The base method pastes in a free space on the diagram.  
    /// But if the menu was used to invoke paste, we want to paste in the cursor position.  
    /// </summary>  
    protected override void ProcessOnMenuPasteCommand()  
    {  
  
  NestedShapesSampleDocView docView = this.CurrentModelingDocView as NestedShapesSampleDocView;  
  
      // Retrieve data from clipboard:  
      System.Windows.Forms.IDataObject data = System.Windows.Forms.Clipboard.GetDataObject();  
  
      Diagram diagram = docView.CurrentDiagram;  
      if (diagram == null) return;  
  
      if (!docView.IsContextMenuShowing)  
      {  
        // User hit CTRL+V - just use base method.  
  
        // Deselect anything that's selected, otherwise  
        // pasted item will be incompatible:  
        if (!this.IsDiagramSelected())  
        {  
          docView.SelectObjects(1, new object[] { diagram }, 0);  
        }  
  
        // Paste into a convenient spare space on diagram:  
    base.ProcessOnMenuPasteCommand();  
      }  
      else  
      {  
        // User right-clicked - paste at mouse position.  
  
        // Utility class:  
        DesignSurfaceElementOperations op = diagram.ElementOperations;  
  
        ShapeElement pasteTarget = diagram;  
  
        // Check whether what's in the paste buffer is acceptable on the target.  
        if (pasteTarget != null && op.CanMerge(pasteTarget, data))  
        {  
  
        // Although op.Merge would be a no-op if CanMerge failed, we check CanMerge first  
          // so that we don't create an empty transaction (after which Undo would be no-op).  
          using (Transaction t = diagram.Store.TransactionManager.BeginTransaction("paste"))  
          {  
            PointD place = docView.ContextMenuMousePosition;  
            op.Merge(pasteTarget, data, PointD.ToPointF(place));  
            t.Commit();  
          }  
        }  
      }  
    }  
  }  
```  
  
 **Sürükleme ve bırakma öğeleri kullanıcının izin verin.**  
 Bkz: [nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md).  
  
##  <a name="customizeLinks"></a>Bağlantı kopyalama davranışını özelleştirme  
 Kullanıcı bir öğeyi kopyaladığında, standart tüm katıştırılmış öğeleri de kopyalanır davranıştır. Davranış kopyalama standart değiştirebilirsiniz. DSL tanımı'nda bir ilişkinin ve özellikleri penceresinde ayarlanmış bir tarafta bir rol seçin **yayar kopyalama** değeri.  
  
 ![Kopya etki alanı rolü özelliğinin yayar](../modeling/media/dslpropagatescopy.png "DslPropagatesCopy")  
  
 Üç değer vardır:  
  
-   Kopyalama yayılmamasını  
  
-   Yalnızca - bağlamak için kopyalama yayılması Grup yapıştırılırken Bu bağlantı yeni kopyasını bağlantısının diğer ucundaki varolan öğesine başvurur.  
  
-   Bağlantı için Kopyala yayar ve rol player - kopyalanan Grup bağlantısının diğer ucundaki öğenin bir kopyasını içerir.  
  
 ![İle PropagateCopyToLinkOnly kopyalama etkisini](../modeling/media/dslpropagatecopy.png "DslPropagateCopy")  
  
 Yaptığınız değişiklikler öğeleri ve kopyalanan görüntü etkiler.  
  
## <a name="programming-copy-and-paste-behavior"></a>Programlama Kopyala ve yapıştır davranışı  
 Kopyalama, yapıştırma, oluşturma ve nesnelerin silinmesi açısından DSL'ın davranış pek çok görünüşünün bir örneği tarafından yönetilir <xref:Microsoft.VisualStudio.Modeling.ElementOperations> diyagrama bağlı. Kendi sınıfından türetilen DSL'in davranışını değiştirebilirsiniz <xref:Microsoft.VisualStudio.Modeling.ElementOperations> ve geçersiz kılma <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.ElementOperations%2A> diyagramı sınıfının özelliği.  
  
> [!TIP]
>  Program kodunu kullanarak model özelleştirme hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 ![Kopyalama işleminin sıralı diyagram](../modeling/media/dslcopyseqdiagram.png "dslCopySeqDiagram")  
  
 ![Yapıştırma işlemi dizisi diyagramı](../modeling/media/dslpasteseqdiagram.png "dslPasteSeqDiagram")  
  
#### <a name="to-define-your-own-elementoperations"></a>Kendi ElementOperations tanımlamak için  
  
1.  Yeni bir dosyada DSL projenizdeki, türetilmiş bir sınıf oluşturun <xref:Microsoft.VisualStudio.Modeling.Diagrams.DesignSurfaceElementOperations>.  
  
2.  Diyagram sınıfınız için bir parçalı sınıf tanımını ekleyin. Bu sınıfın adını bulunabilir **Dsl\GeneratedCode\Diagrams.cs**.  
  
     Diyagram sınıfında geçersiz kılma <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.ElementOperations%2A> ElementOperations alt sınıf örneği dönün. Her çağrısında aynı örneğini döndürmelidir.  
  
 Özel kod dosyasında DslPackage projesinde bu kodu ekleyin:  
  
```csharp  
  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;  
  
  public partial class MyDslDiagram  
  {  
    public override DesignSurfaceElementOperations ElementOperations  
    {  
      get  
      {  
        if (this.elementOperations == null)  
        {  
          this.elementOperations = new MyElementOperations(this.Store as IServiceProvider, this);  
        }  
        return this.elementOperations;  
      }  
    }  
    private MyElementOperations elementOperations = null;  
  }  
  
  public class MyElementOperations : DesignSurfaceElementOperations  
  {  
    public MyElementOperations(IServiceProvider serviceProvider, MyDslDiagram diagram)  
      : base(serviceProvider, diagram)  
    { }  
    // Overridden methods follow  
  }  
  
```  
  
## <a name="receiving-items-dragged-from-other-models"></a>Diğer modellerinden sürüklenen öğelerini alma  
 ElementOperations, kopyalama ve taşıma, silme ve sürükle ve bırak davranışını tanımlamak için de kullanılabilir. ElementOperations kullanımını bir örnek, burada verilen örnek özel sürükle ve bırak davranışını tanımlar. Ancak, bu amaçla açıklanan alternatif bir yaklaşım göz önünde tutabileceğiniz [nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md), olduğu daha genişletilebilir.  
  
 İki yöntem ElementOperations sınıfınızda tanımlayın:  
  
-   `CanMerge(ModelElement targetElement, System.Windows.Forms.IDataObject data)`source öğesi hedef şekli, bağlayıcı veya diyagramı sürüklenebilir olup olmadığını belirler.  
  
-   `MergeElementGroupPrototype(ModelElement targetElement, ElementGroupPrototype sourcePrototype)`hangi hedefe source öğesi birleştirir.  
  
### <a name="canmerge"></a>CanMerge()  
 `CanMerge()`Fare diyagramı üzerinde hareket ederken, kullanıcıya verilen geri bildirim belirlemek için çağrılır. Yöntemine üzerinde fare getirildiğinde öğesi ve sürükleme işlemi gerçekleştirildikten kaynak hakkındaki verileri parametreleridir. Kullanıcının herhangi bir yere ekranda sürükleyebilirsiniz. Bu nedenle, kaynak nesne birçok farklı türde olabilir ve farklı biçimlerde seri hale getirilebilir. Kaynak DSL veya UML model veri parametresi serileştirmek ise, bir <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>. Sürükleme, kopyalama ve araç kutusu işlemleri ElementGroupPrototypes modelleri parçalarını temsil etmek için kullanın.  
  
 Bir öğe grubunu prototip öğeleri ve bağlantıları herhangi bir sayı içerebilir. Öğe türleri GUID'ler göre tanımlanabilir. Temel alınan model öğesi değil sürüklenen şeklin GUID'dir. Aşağıdaki örnekte, `CanMerge()` sınıfı şekli UML Diyagramı'ndan Bu diyagram üzerine sürüklediğiniz, true değerini döndürür.  
  
```csharp  
public override bool CanMerge(ModelElement targetShape, System.Windows.Forms.IDataObject data)  
 {  
  // Extract the element prototype from the data.  
  ElementGroupPrototype prototype = ElementOperations.GetElementGroupPrototype(this.ServiceProvider, data);  
  if (targetShape is MyTargetShape && prototype != null &&  
        prototype.RootProtoElements.Any(rootElement =>   
          rootElement.DomainClassId.ToString()   
          ==  "3866d10c-cc4e-438b-b46f-bb24380e1678")) // Guid of UML Class shapes  
          // or SourceClass.DomainClassId  
        return true;  
   return base.CanMerge(targetShape, data);  
 }  
  
```  
  
## <a name="mergeelementgroupprototype"></a>MergeElementGroupPrototype()  
 Bu yöntem, kullanıcının bir öğenin bir diyagram, bir şekli veya bir bağlayıcı üstüne düştüğünde çağrılır. Sürüklenen içeriği hedef öğede birleştirin. Bu örnekte, kodu, hedef ve prototip türlerinin birleşimi tanıdığı olup olmadığını belirler; Bu durumda, yöntemi sürüklenen öğeler modeline eklenmesi gereken öğeler prototipi dönüştürür. Base yöntemi, dönüştürülmüş veya Dönüştürülmeyen öğelerinin ya da birleştirme için çağrılır.  
  
```csharp  
public override void MergeElementGroupPrototype(ModelElement targetShape, ElementGroupPrototype sourcePrototype)  
{  
  ElementGroupPrototype prototypeToMerge = sourcePrototype;  
  MyTargetShape pel = targetShape as MyTargetShape;  
  if (pel != null)  
  {  
    prototypeToMerge = ConvertDraggedTypeToLocal(pel, sourcePrototype);  
  }  
  if (prototypeToMerge != null)  
    base.MergeElementGroupPrototype(targetShape, prototypeToMerge);  
}  
  
```  
  
 Bu örnek, bir UML sınıf diyagramdan sürüklenen UML sınıfı öğelerini ile ilgilidir. DSL UML sınıflarını doğrudan depolamak üzere tasarlanmamıştır, ancak bunun yerine, biz sürüklenen her UML sınıf için bir DSL öğesi oluşturun. Örneğin, bir örnek diyagramı DSL ise, bu yararlı olacaktır. Kullanıcı sınıfları bu sınıfların örnekleri oluşturmak için diyagram üzerine sürükleyin.  
  
```csharp  
  
private ElementGroupPrototype ConvertDraggedTypeToLocal (MyTargetShape snapshot, ElementGroupPrototype prototype)  
{  
  // Find the UML project:  
  EnvDTE.DTE dte = snapshot.Store.GetService(typeof(EnvDTE.DTE)) as EnvDTE.DTE;  
  foreach (EnvDTE.Project project in dte.Solution.Projects)  
  {  
    IModelingProject modelingProject = project as IModelingProject;  
    if (modelingProject == null) continue; // not a modeling project  
    IModelStore store = modelingProject.Store;  
    if (store == null) continue;  
    // Look for the shape that was dragged:  
    foreach (IDiagram umlDiagram in store.Diagrams())  
    {  
      // Get modeling diagram that implements UML diagram:  
      Diagram diagram = umlDiagram.GetObject<Diagram>();  
      Guid elementId = prototype.SourceRootElementIds.FirstOrDefault();  
      ShapeElement shape = diagram.Partition.ElementDirectory.FindElement(elementId) as ShapeElement;  
      if (shape == null) continue;  
      IClass classElement = shape.ModelElement as IClass;  
      if (classElement == null) continue;  
  
      // Create a prototype of elements in my DSL, based on the UML element:  
      Instance instance = new Instance(snapshot.Store);  
      instance.Type = classElement.Name;  
      // Pack them into a prototype:  
      ElementGroup group = new ElementGroup(instance);  
      return group.CreatePrototype();  
    }  
  }  
  return null;  
}  
  
```  
  
## <a name="standard-copy-behavior"></a>Standart kopyalama davranışı  
 Bu bölümdeki kod yapabilecekleriniz yöntemleri kopyalama davranışı değiştirmek için geçersiz kılabilirsiniz gösterir. Kendi özelleştirmelerini elde etmek nasıl görmenize yardımcı olmak için bu bölümü kopyalama söz konusu yöntemlerini geçersiz kılar kodu gösterir, ancak standart davranış değişmez.  
  
 Ne zaman kullanıcı CTRL + C bastığında veya kopya menü komutu, yöntemi kullanan <xref:Microsoft.VisualStudio.Modeling.Shell.ClipboardCommandSet.ProcessOnMenuCopyCommand%2A> olarak adlandırılır. Nasıl bu ayarlanır görebilirsiniz **DslPackage\Generated Code\CommandSet.cs**. Nasıl komutları kurulur hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir komut için kısayol menüsü ekleme](../modeling/how-to-add-a-command-to-the-shortcut-menu.md).  
  
 Bir parçalı sınıf tanımını ekleyerek ProcessOnMenuCopyCommand geçersiz kılabilirsiniz *MyDsl* `ClipboardCommandSet` DslPackage projesinde.  
  
```csharp  
using System.Collections.Generic;  
using System.Drawing;  
using System.Windows.Forms;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
partial class MyDslClipboardCommandSet  
{  
  /// <summary>  
  /// Override ProcessOnMenuCopyCommand() to copy elements to the  
  /// clipboard in different formats, or to perform additional tasks  
  /// before or after copying - for example deselect the copied elements.  
  /// </summary>  
  protected override void ProcessOnMenuCopyCommand()  
  {  
    IList<ModelElement> selectedModelElements = this.SelectedElements;  
    if (selectedModelElements.Count == 0) return;  
  
    // System container for clipboard data.  
    // The IDataObject can contain data in several formats.  
    IDataObject dataObject = new DataObject();  
  
    Bitmap bitmap = null; // For export to other programs.  
    try  
    {  
      #region Create EGP for copying to a DSL.  
      this.CopyModelElementsIntoElementGroupPrototype  
                     (dataObject, selectedModelElements);  
      #endregion  
  
      #region Create bitmap for copying to another application.   
      // Find all the shapes associated with this selection:  
      List<ShapeElement> shapes = new List<ShapeElement>(  
        this.ResolveExportedShapesForClipboardImages  
              (dataObject, selectedModelElements));  
  
      bitmap = this.CreateBitmapForClipboard(shapes);  
      if (bitmap != null)  
      {  
        dataObject.SetData(DataFormats.Bitmap, bitmap);  
      }  
      #endregion   
  
      // Add the data to the clipboard:  
      Clipboard.SetDataObject(dataObject, true, 5, 100);  
    }  
    finally  
    {  
      // Dispose bitmap after SetDataObject:  
      if (bitmap != null) bitmap.Dispose();  
    }  
  }  
/// <summary>  
/// Override this to customize the element group that is copied to the clipboard.  
/// </summary>  
protected override void CopyModelElementsIntoElementGroupPrototype(IDataObject dataObject, IList<ModelElement> selectedModelElements)  
{  
  return this.ElementOperations.Copy(dataObject, selectedModelElements);  
}  
}  
```  
  
 Her diyagramı ElementOperations tek örneğini sahiptir. Kendi türevi sağlayabilir. DSL projesinde yerleştirilebilir, bu dosya bu geçersiz kılmaları koduyla aynı davranacaktır:  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
  
namespace Company.MyDsl  
{  
  partial class MyDslDiagram  
  {  
    /// <summary>  
    /// Singleton ElementOperations attached to this diagram.  
    /// </summary>  
    public override DesignSurfaceElementOperations ElementOperations  
    {  
      get  
      {  
        if (this.elementOperations == null)  
        {  
          this.elementOperations = new MyElementOperations(this.Store as IServiceProvider, this);  
        }  
        return this.elementOperations;  
      }  
    }  
    private MyElementOperations elementOperations = null;  
  }  
  
  // Our own version of ElementOperations so that we can override:  
  public class MyElementOperations : DesignSurfaceElementOperations  
  {  
    public MyElementOperations(IServiceProvider serviceProvider, ElementOps1Diagram diagram)  
      : base(serviceProvider, diagram)  
    { }  
  
    /// <summary>  
    /// Copy elements to the clipboard data.  
    /// Provides a hook for adding custom data.  
    /// </summary>  
    public override void Copy(System.Windows.Forms.IDataObject data,   
      ICollection<ModelElement> elements,   
      ClosureType closureType,   
      System.Drawing.PointF sourcePosition)  
    {  
      if (CanAddElementGroupFormat(elements, closureType))  
      {  
        AddElementGroupFormat(data, elements, closureType);   
      }  
  
      // Override these to store additional data:  
      if (CanAddCustomFormat(elements, closureType))  
      {  
        AddCustomFormat(data, elements, closureType, sourcePosition);  
      }  
    }  
  
    protected override void AddElementGroupFormat(System.Windows.Forms.IDataObject data, ICollection<ModelElement> elements, ClosureType closureType)  
    {  
      // Add the selected elements and those implied by the propagate copy rules:  
      ElementGroup elementGroup = this.CreateElementGroup(elements, closureType);  
  
      // Mark all the elements that are not embedded under other elements:  
      this.MarkRootElements(elementGroup, elements, closureType);  
  
      // Store in the clipboard data:  
      ElementGroupPrototype elementGroupPrototype = this.CreateElementGroupPrototype(elementGroup, elements, closureType);  
      data.SetData(ElementGroupPrototype.DefaultDataFormatName, elementGroupPrototype);  
    }  
  
    /// <summary>  
    /// Override this to store additional elements in the element group:  
    /// </summary>  
    protected override ElementGroupPrototype CreateElementGroupPrototype(ElementGroup elementGroup, ICollection<ModelElement> elements, ClosureType closureType)  
    {  
      ElementGroupPrototype prototype = new ElementGroupPrototype(this.Partition, elementGroup.RootElements, elementGroup);  
      return prototype;  
    }  
  
    /// <summary>  
    /// Create an element group from the given starting elements, using the   
    /// copy propagation rules specified in the DSL Definition.  
    /// By default, this includes all the embedded descendants of the starting elements,  
    /// and also includes reference links where both ends are already included.  
    /// </summary>  
    /// <param name="startElements">model elements to copy</param>  
    /// <param name="closureType"></param>  
    /// <returns></returns>  
    protected override ElementGroup CreateElementGroup(ICollection<ModelElement> startElements, ClosureType closureType)  
    {  
      // ElementClosureWalker finds all the connected elements,   
      // according to the propagate copy rules specified in the DSL Definition:  
      ElementClosureWalker walker = new ElementClosureWalker(this.Partition,   
        closureType, // Normally ClosureType.CopyClosure  
        startElements,   
        true, // Do not load other models.  
        null, // Optional list of domain roles not to traverse.  
        true); // Include relationship links where both ends are already included.  
  
      walker.Traverse(startElements);  
      IList<ModelElement> closureList = walker.ClosureList;  
      Dictionary<object, object> closureContext = walker.Context;  
  
      // create a group for this closure  
      ElementGroup group = new ElementGroup(this.Partition);  
      group.AddRange(closureList, false);  
  
      // create the element group prototype for the group  
      foreach (object key in closureContext.Keys)  
      {  
        group.SourceContext.ContextInfo[key] = closureContext[key];  
      }  
  
      return group;  
    }  
  }  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

[Öğe oluşturma ve taşıma özelleştirme](../modeling/customizing-element-creation-and-movement.md)   
[Nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md)   
[Silme davranışı özelleştirme](../modeling/customizing-deletion-behavior.md)   
[Örnek: VMSDK hattı diyagramları örnek](http://go.microsoft.com/fwlink/?LinkId=213879)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]