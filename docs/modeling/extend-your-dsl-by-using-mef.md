---
title: "MEF kullanarak, DSL genişletme | Microsoft Docs"
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
ms.openlocfilehash: 735de60d18bc5cbca7dc2ba509372d81622038be
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="extend-your-dsl-by-using-mef"></a>MEF kullanarak DSL'nizi genişletme
Yönetilen Genişletilebilirlik Çerçevesi (MEF) kullanarak etki alanına özgü dil (DSL) genişletebilirsiniz. Siz veya diğer geliştiriciler DSL tanımı ve programın kodunu değiştirmeden uzantıları için DSL yazabilmesi olacaktır. Bu tür uzantılar menü komutları, sürükle ve bırak işleyicileri ve doğrulama içerir. Kullanıcılar, DSL yükleyin ve ardından isteğe bağlı olarak uzantıları için yüklemek mümkün olacaktır.  
  
 MEF, DSL etkinleştirdiğinizde, tüm DSL ile birlikte yerleşik olan olsa bile ek olarak, bunu daha kolay, DSL özelliklerden bazıları yazmak için olabilir.  
  
 MEF hakkında daha fazla bilgi için bkz: [Yönetilen Genişletilebilirlik Çerçevesi (MEF)](/dotnet/framework/mef/index).  
  
### <a name="to-enable-your-dsl-to-be-extended-by-mef"></a>MEF tarafından genişletilmesi, DSL etkinleştirmek için  
  
1.  Adlı yeni bir klasör oluşturun **MefExtension** içinde **DslPackage** projesi. Aşağıdaki dosyaları ekleyin:  
  
     Dosya adı:`CommandExtensionVSCT.tt`  
  
    > [!IMPORTANT]
    >  Bu dosyadaki DslPackage\GeneratedCode\Constants.tt içinde tanımlanan GUID CommandSetId aynı olacak şekilde GUID'i ayarlayın  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#  
    // CmdSet Guid must be defined before master template is included  
    // This Guid must be kept synchronized with the CommandSetId Guid in Constants.tt  
    Guid guidCmdSet = new Guid ("00000000-0000-0000-0000-000000000000");  
    string menuidCommandsExtensionBaseId="0x4000";  
    #>  
    <#@ include file="DslPackage\CommandExtensionVSCT.tt" #>  
    ```  
  
     Dosya adı:`CommandExtensionRegistrar.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="DslPackage\CommandExtensionRegistrar.tt" #>  
    ```  
  
     Dosya adı:`ValidationExtensionEnablement.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="DslPackage\ValidationExtensionEnablement.tt" #>  
    ```  
  
     Dosya adı:`ValidationExtensionRegistrar.tt`  
  
     Bu dosya eklerseniz, doğrulama, DSL anahtarları en az birini kullanarak etkinleştirmelisiniz **EditorValidation** DSL Explorer'da.  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="DslPackage\ValidationExtensionRegistrar.tt" #>  
    ```  
  
     Dosya adı:`PackageExtensionEnablement.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="DslPackage\PackageExtensionEnablement.tt" #>  
    ```  
  
2.  Adlı yeni bir klasör oluşturun **MefExtension** içinde **Dsl** projesi. Aşağıdaki dosyaları ekleyin:  
  
     Dosya adı:`DesignerExtensionMetaDataAttribute.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="Dsl\DesignerExtensionMetadataAttribute.tt" #>  
    ```  
  
     Dosya adı:`GestureExtensionEnablement.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="Dsl\GestureExtensionEnablement.tt" #>  
    ```  
  
     Dosya adı:`GestureExtensionController.tt`  
  
    ```  
    <#@ Dsl processor="DslDirectiveProcessor" requires="fileName='..\..\Dsl\DslDefinition.dsl'" #>  
    <#@ include file="Dsl\GestureExtensionController.tt" #>  
    ```  
  
3.  Adlı varolan dosyanın sonuna aşağıdaki satırı ekleyin **DslPackage\Commands.vsct**:  
  
    ```  
    <Include href="MefExtension\CommandExtensionVSCT.vsct"/>  
    ```  
  
     Varolan sonra satır Ekle `<Include>` yönergesi.  
  
4.  `Open DslDefinition.dsl.`  
  
5.  DSL Gezgini'nde seçin **Editor\Validation**.  
  
6.  Özellikler penceresinde özellikleri en az biri adlı emin olun **kullanan...**  olan `true`.  
  
7.  Çözüm Gezgini araç çubuğunda **tüm şablonları dönüştürme**.  
  
     Temsilci dosyaları her eklediğiniz dosyaların altında görünür.  
  
8.  Derleme ve hala çalıştığından emin olmak için çözümü çalıştırın.  
  
 DSL MEF etkin sunulmuştur. Menü komutları, hareketleri işleyicileri ve doğrulama kısıtlamaları MEF uzantıları olarak yazabilirsiniz. Bu uzantılar, diğer özel kod ile birlikte DSL çözümünüzdeki yazabilirsiniz. Ayrıca, siz veya diğer geliştiriciler ayrı yazabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , DSL genişleten uzantılar.  
  
## <a name="creating-an-extension-for-a-mef-enabled-dsl"></a>Uzantı için MEF etkin DSL oluşturma  
 Kendinize veya başka birisi tarafından oluşturulan bir MEF etkin DSL erişiminiz varsa, uzantıları için yazabilirsiniz. Uzantıları menü komutları, hareketleri işleyicileri veya doğrulama kısıtlamaları eklemek için kullanılabilir. Bu uzantılar yazmak için kullandığınız bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı (VSIX) çözümü. Çözüm iki bölümden oluşur: kod derleme yapıları bir sınıf kitaplığı proje ve derleme paketleri VSIX proje.  
  
#### <a name="to-create-a-dsl-extension-vsix"></a>DSL uzantısı VSIX oluşturmak için  
  
1.  Yeni bir sınıf kitaplığı projesi oluşturun. Bunu yapmak için **yeni proje** iletişim kutusunda **Visual Basic** veya **Visual C#** ve ardından **sınıf kitaplığı**.  
  
2.  Yeni sınıf kitaplığı projesinde DSL derlemesine başvuru ekleyin.  
  
    -   Bu derleme genellikle ile biten bir adı vardır ". DSL.dll".  
  
    -   DSL proje erişiminiz varsa, derleme dosyası dizininin altında bulabilirsiniz **Dsl\bin\\\***  
  
    -   DSL VSIX dosyasına erişiminiz varsa, derleme ".zip" VSIX dosyasının dosya adı uzantısını değiştirerek bulabilirsiniz. .Zip dosyasını açın.  
  
3.  Aşağıdaki .NET derlemelerini başvurular ekleyin:  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.11.0.dll  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0.dll  
  
    -   Microsoft.VisualStudio.Modeling.Sdk.Shell.11.0.dll  
  
    -   System.ComponentModel.Composition.dll  
  
    -   System.Windows.Forms.dll  
  
4.  VSIX proje aynı çözüm içinde oluşturun. Bunu yapmak için **yeni proje** iletişim kutusunda, genişletin **Visual Basic** veya **Visual C#**, tıklatın **genişletilebilirlik**ve ardından seçin **VSIX proje**.  
  
5.  Çözüm Gezgini'nde VSIX projesine sağ tıklayın ve ardından **başlangıç projesi olarak ayarla**.  
  
6.  Yeni projede açmak **source.extension.vsixmanifest**.  
  
7.  Tıklatın **içerik ekleme**. İletişim kutusunda ayarlanan **içerik türü** için **MEF Bileşeni**, ve **kaynak proje** sınıf kitaplığını projenize.  
  
8.  DSL VSIX başvuru ekleyin.  
  
    1.  İçinde **source.extension.vsixmanifest**, tıklatın **Başvuru Ekle**  
  
    2.  İletişim kutusunda **eklemek yükü** ve DSL VSIX dosyasını bulun. VSIX DSL çözümde, yerleşik **DslPackage\bin\\\***.  
  
         Bu, kullanıcıların DSL ve uzantınızı aynı anda yüklemesine olanak tanır. Kullanıcı zaten DSL yüklediyse, yalnızca dahili yüklenir.  
  
9. Gözden geçirin ve diğer alanlarını güncelleştirme **source.extension.vsixmanifest**. Tıklatın **sürümleri seçin** doğrulayın doğru [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sürümleri ayarlanır.  
  
10. Kod sınıf kitaplığını projenize ekleyin. Örnekler bir sonraki bölümde bir kılavuz olarak kullanın.  
  
     Komut, hareketi ve doğrulama sınıfları herhangi bir sayıda ekleyebilirsiniz.  
  
11. Uzantı sınamak için basın **F5**. Deneysel örneğinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]oluşturun veya DSL ait bir örnek dosyası açın.  
  
## <a name="writing-mef-extensions-for-dsls"></a>MEF uzantıları için DSL'ler yazma  
 Ayrı bir DSL uzantısı çözümü derleme kod projesinde uzantıları yazabilirsiniz. Komutları, hareketleri ve doğrulama kodu DSL bir parçası olarak yazmak için kolay bir yol olarak DslPackage projenizde MEF de kullanabilirsiniz.  
  
### <a name="menu-commands"></a>Menü Komutları  
 Menü komutu yazmak için uygulayan bir sınıf tanımlama <xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement.ICommandExtension> ve adlandırılmış, DSL içinde tanımlı öznitelik sınıfı önek *YourDsl*`CommandExtension`. Birden çok menü komutu sınıfı yazabilirsiniz.  
  
 `QueryStatus()`Kullanıcı diyagramda sağ tıklatır olduğunda çağrılır. Geçerli seçim inceleyebilir ve ayarlama `command.Enabled` komutu uygulanabilir olduğunda belirtmek için.  
  
```  
using System.ComponentModel.Composition;  
using System.Linq;  
using Company.MyDsl; // My DSL  
using Company.MyDsl.ExtensionEnablement; // My DSL  
using Microsoft.VisualStudio.Modeling; // Transactions  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement; // IVsSelectionContext  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement; // ICommandExtension  
  
namespace MyMefExtension  
{  
  // Defined in Dsl\MefExtension\DesignerExtensionMetaDataAttribute.cs:  
  [MyDslCommandExtension]   
  public class MyCommandClass : ICommandExtension  
  {   
    /// <summary>  
    /// Provides access to current document and selection.  
    /// </summary>  
    [Import]  
    IVsSelectionContext SelectionContext { get; set; }  
  
    /// <summary>  
    /// Called when the user selects this command.  
    /// </summary>  
    /// <param name="command"></param>  
    public void Execute(IMenuCommand command)  
    {  
      // Transaction is required if you want to update elements.  
      using (Transaction t = SelectionContext.CurrentStore  
              .TransactionManager.BeginTransaction("fix names"))  
      {  
        foreach (ExampleShape shape in SelectionContext.CurrentSelection)  
        {  
          ExampleElement element = shape.ModelElement as ExampleElement;  
          element.Name = element.Name + " !";  
        }  
        t.Commit();  
      }  
    }  
  
    /// <summary>  
    /// Called when the user right-clicks the diagram.  
    /// Determines whether the command should appear.  
    /// This method should set command.Enabled and command.Visible.  
    /// </summary>  
    /// <param name="command"></param>  
    public void QueryStatus(IMenuCommand command)  
    {  
      command.Enabled =  
        command.Visible = (SelectionContext.CurrentSelection.OfType<ExampleShape>().Count() > 0);  
    }  
  
    /// <summary>  
    /// Called when the user right-clicks the diagram.  
    /// Determines the text of the command in the menu.  
    /// </summary>  
    public string Text  
    {  
      get { return "My menu command"; }  
    }  
  }  
}  
  
```  
  
### <a name="gesture-handlers"></a>Hareket işleyicileri  
 Hareket işleyicisi içine veya dışına diyagram üzerine yerden sürüklenen nesnelerle ilgili [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Aşağıdaki örnek dosyalar Windows Gezgini'nden diyagram üzerine sürükleyin olanak tanır. Dosya adlarını içeren öğeleri oluşturur.  
  
 Diğer DSL modeller ve UML modellerini drags ile mücadele etmek için işleyiciler yazabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md).  
  
```  
  
using System.ComponentModel.Composition;  
using System.Linq;  
using Company.MyDsl;  
using Company.MyDsl.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling; // Transactions  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;   
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;   
  
namespace MefExtension  
{  
  [MyDslGestureExtension]  
  class MyGestureExtension : IGestureExtension  
  {  
    public void OnDoubleClick(ShapeElement targetElement, DiagramPointEventArgs diagramPointEventArgs)  
    {  
      System.Windows.Forms.MessageBox.Show("double click!");  
    }  
  
    /// <summary>  
    /// Called when the user drags anything over the diagram.  
    /// Return true if the dragged object can be dropped on the current target.  
    /// </summary>  
    /// <param name="targetMergeElement">The shape or diagram that the mouse is currently over</param>  
    /// <param name="diagramDragEventArgs">Data about the dragged element.</param>  
    /// <returns></returns>  
    public bool CanDragDrop(ShapeElement targetMergeElement, DiagramDragEventArgs diagramDragEventArgs)  
    {  
      // This handler only allows items to be dropped onto the diagram:  
      return targetMergeElement is MefDsl2Diagram &&  
      // And only accepts files dragged from Windows Explorer:  
        diagramDragEventArgs.Data.GetFormats().Contains("FileNameW");  
    }  
  
    /// <summary>  
    /// Called when the user drops an item onto the diagram.  
    /// </summary>  
    /// <param name="targetDropElement"></param>  
    /// <param name="diagramDragEventArgs"></param>  
    public void OnDragDrop(ShapeElement targetDropElement, DiagramDragEventArgs diagramDragEventArgs)  
    {  
      MefDsl2Diagram diagram = targetDropElement as MefDsl2Diagram;  
      if (diagram == null) return;  
  
      // This handler only accepts files dragged from Windows Explorer:  
      string[] draggedFileNames = diagramDragEventArgs.Data.GetData("FileNameW") as string[];  
      if (draggedFileNames == null || draggedFileNames.Length == 0) return;   
  
      using (Transaction t = diagram.Store.TransactionManager.BeginTransaction("file names"))  
      {  
        // Create an element to represent each file:  
        foreach (string fileName in draggedFileNames)  
        {  
          ExampleElement element = new ExampleElement(diagram.ModelElement.Partition);  
          element.Name = fileName;  
  
          // This method of adding the new element allows the position  
          // of the shape to be specified:            
          ElementGroup group = new ElementGroup(element);  
          diagram.ElementOperations.MergeElementGroupPrototype(  
            diagram, group.CreatePrototype(), PointD.ToPointF(diagramDragEventArgs.MousePosition));  
        }  
        t.Commit();  
      }  
    }  
  }  
}  
  
```  
  
### <a name="validation-constraints"></a>Doğrulama kısıtlamaları  
 Doğrulama yöntemlerinin işaretlenmiş `ValidationExtension` DSL tarafından ve aynı zamanda tarafından oluşturulan öznitelik <xref:Microsoft.VisualStudio.Modeling.Validation.ValidationMethodAttribute>. Yöntemi, bir öznitelik tarafından işaretlenmemiş herhangi bir sınıf içinde görünebilir.  
  
 Daha fazla bilgi için bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md).  
  
```  
using Company.MyDsl;  
using Company.MyDsl.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.Validation;  
  
namespace MefExtension  
{  
  class MyValidationExtension // Can be any class.  
  {  
    // SAMPLE VALIDATION METHOD.  
    // All validation methods have the following attributes.  
  
    // Specific to the extended DSL:  
    [MyDslValidationExtension]   
  
    // Determines when validation is applied:  
    [ValidationMethod(  
       ValidationCategories.Save  
     | ValidationCategories.Open  
     | ValidationCategories.Menu)]  
  
    /// <summary>  
    /// When validation is executed, this method is invoked  
    /// for every element in the model that is an instance  
    /// of the second parameter type.  
    /// </summary>  
    /// <param name="context">For reporting errors</param>  
    /// <param name="elementToValidate"></param>  
    private void ValidateClassNames  
      (ValidationContext context,  
       // Type determines to what elements this will be applied:  
       ExampleElement elementToValidate)  
    {   
      // Write code here to test values and links.  
      if (elementToValidate.Name.IndexOf(' ') >= 0)  
      {  
        // Log any unacceptable values:  
        context.LogError(  
          // Description:  
          "Name must not contain spaces"   
          // Error code unique to this type of error:  
          , "MyDsl001"   
          // Element to highlight when user double-clicks error:  
          , elementToValidate);   
} } } }  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio uzantıları aktarma](../extensibility/shipping-visual-studio-extensions.md)   
 [Yönetilen Genişletilebilirlik Çerçevesi (MEF)](/dotnet/framework/mef/index)   
 [Nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Etki Alanına Özgü bir Dilde Doğrulama](../modeling/validation-in-a-domain-specific-language.md)