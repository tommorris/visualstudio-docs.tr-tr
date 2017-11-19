---
title: "Bağımlılık diyagramlarına komut ve hareket ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, adding custom commands
- dependency diagrams, adding custom gestures
ms.assetid: ac9c417b-0b40-4a90-86f5-ee3cbdce030b
caps.latest.revision: "38"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 40bad32ef38fb99032690804d572f630bb60ac6d
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="add-commands-and-gestures-to-dependency-diagrams"></a>Bağımlılık diyagramlarına komut ve hareket ekleme
Visual Studio'da bağımlılık diyagramları işleyicileri hareket ve bağlam menüsü komutları tanımlayın. Bu uzantılar içine bir Visual Studio Tümleştirme Uzantısı (diğer Visual Studio kullanıcılara dağıtabileceğiniz VSIX) paketleyebilirsiniz.  
  
 İstiyorsanız, aynı Visual Studio projede birkaç komut ve hareket işleyicileri tanımlayabilirsiniz. Ayrıca, bir VSIX birkaç proje birleştirebilirsiniz. Örneğin, katman komutları ve bir etki alanına özgü dil içeren tek bir VSIX tanımlayabilirsiniz.  
  
> [!NOTE]
>  Ayrıca, hangi kullanıcıların kaynağında bağımlılık diyagramları ile kod karşılaştırılır mimari doğrulaması özelleştirebilirsiniz. Ayrı bir Visual Studio projesi mimari doğrulaması tanımlamanız gerekir. Başka bir uzantısı olarak aynı VSIX için ekleyebilirsiniz. Daha fazla bilgi için bkz: [bağımlılık diyagramlarına özel mimari doğrulaması ekleme](../modeling/add-custom-architecture-validation-to-layer-diagrams.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Bkz: [gereksinimleri](../modeling/extend-layer-diagrams.md#prereqs).  
  
## <a name="defining-a-command-or-gesture-in-a-new-vsix"></a>Bir komut veya hareketi yeni bir VSIX tanımlama  
 Uzantı oluşturmanın en hızlı yöntemdir proje şablonu kullanmaktır. Bu seçenek, kod ve VSIX bildirimini aynı projeye yerleştirir.  
  
#### <a name="to-define-an-extension-by-using-a-project-template"></a>Bir proje şablonu kullanarak bir uzantısı tanımlamak için  
  
1.  Kullanarak yeni bir çözümde bir proje oluşturma **yeni proje** komutunu **dosya** menüsü.  
  
2.  İçinde **yeni proje** iletişim kutusunda **modelleme projeleri**, şunlardan birini seçin **katman Tasarımcısı komut uzantısı** veya **katman Tasarımcısı hareketi uzantısı** .  
  
     Şablon çalışan küçük bir örnek içeren bir proje oluşturur.  
  
3.  Uzantı sınamak için basın **CTRL + F5** veya **F5**.  
  
     Deneysel örneği [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] başlatır. Bu örnekte, bir bağımlılık diyagramı oluşturun. Bu diyagramda komut veya hareket uzantınızı çalışması gerekir.  
  
4.  Deneysel örneği kapatın ve örnek kodu değiştirin. Daha fazla bilgi için bkz: [gidin ve güncelleştirme modelleri program kodunda katman](../modeling/navigate-and-update-layer-models-in-program-code.md).  
  
5.  Daha fazla komut veya hareket işleyicileri aynı projeye ekleyebilirsiniz. Daha fazla bilgi için aşağıdaki bölümlerden birine bakın:  
  
     [Menü komutu tanımlama](#command)  
  
     [Hareket işleyicisi tanımlama](#gesture)  
  
6.  Ana örneğinde uzantıyı yüklemek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], veya başka bir bilgisayarda Bul **.vsix** dosyasını **bin\\\***. Yüklemek istediğiniz bilgisayara kopyalayın ve ardından çift tıklatın. Kaldırmak için kullanın **Uzantılar ve güncelleştirmeler** üzerinde **Araçları** menüsü.  
  
## <a name="adding-a-command-or-gesture-to-a-separate-vsix"></a>Bir komut veya hareketi için ayrı bir VSIX ekleme  
 Komutları, katman doğrulayıcıları ve diğer uzantıları içeren bir VSIX oluşturmak istiyorsanız, VSIX tanımlamak için bir proje ve işleyicileri için ayrı projeler oluşturmanızı öneririz.
  
#### <a name="to-add-layer-extensions-to-a-separate-vsix"></a>Katman uzantıları için ayrı bir VSIX eklemek için  
  
1.  Bir sınıf kitaplığı proje yeni veya varolan bir Visual Studio çözümünde oluşturun. İçinde **yeni proje** iletişim kutusu, tıklatın **Visual C#** ve ardından **sınıf kitaplığı**. Bu proje komutu içerebilir veya işleyici sınıfları hareket.  
  
    > [!NOTE]
    >  Bir sınıf kitaplığı'nda birden fazla komut veya hareket işleyicisi sınıfı tanımlayabilirsiniz, ancak ayrı Sınıf Kitaplığı'nda katman doğrulama sınıfları tanımlamanız gerekir.  
  
2.  Çözümünüzde VSIX projesi oluşturun veya tanımlayın. Bir VSIX proje adlı bir dosyayı içeren **source.extension.vsixmanifest**. VSIX proje eklemek için:  
  
    1.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C#**, ardından **genişletilebilirlik**ve ardından **VSIX proje**.  
  
    2.  Çözüm Gezgini'nde VSIX projesine sağ tıklayın ve ardından **başlangıç projesi olarak ayarla**.  
  
    3.  Tıklatın **sürümleri seçin** emin olun **Visual Studio** denetlenir.  
  
3.  İçinde **source.extension.vsixmanifest**altında **varlıklar**, komut eklemek veya hareket işleyicisi projesi bir MEF Bileşeni olarak.  
  
    1.  İçinde **varlıklar**.tab, seçin **yeni**.  
  
    2.  Konumundaki **türü**seçin **Microsoft.VisualStudio.MefComponent**.  
  
    3.  Konumundaki **kaynak**seçin **geçerli çözümde proje** ve komut veya hareket işleyicisi projenizin adını seçin.  
  
    4.  Dosyayı kaydedin.  
  
4.  Komut veya hareket işleyicisi projeye dönün ve aşağıdaki proje başvurularını ekleyin.  
  
|**Başvuru**|**Ne bu yapmanıza izin verir**|  
|-------------------|------------------------------------|  
|Program Files\Microsoft Visual Studio [sürüm] \Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.dll|Oluşturma ve düzenleme katmanları|  
|Microsoft.VisualStudio.Uml.Interfaces|Oluşturma ve düzenleme katmanları|  
|Microsoft.VisualStudio.ArchitectureTools.Extensibility|Diyagramdaki şekilleri değiştirin|  
|System.ComponentModel.Composition|Yönetilen Genişletilebilirlik Çerçevesi (MEF) kullanarak bileşenleri tanımlayın|  
|Microsoft.VisualStudio.Modeling.Sdk. [sürüm]|Model uzantılarını tanımlayın|  
|Microsoft.VisualStudio.Modeling.Sdk.Diagrams. [sürüm]|Şekilleri Güncelleştirme ve diyagramları|  
  
1.  Uzantınızı kodunu içerecek şekilde C# projesinde sınıf kitaplığı sınıfı dosyasını düzenleyin. Daha fazla bilgi için aşağıdaki bölümlerden birine bakın:  
  
     [Menü komutu tanımlama](#command)  
  
     [Hareket işleyicisi tanımlama](#gesture)  
  
     Ayrıca bkz. [gidin ve güncelleştirme modelleri program kodunda katman](../modeling/navigate-and-update-layer-models-in-program-code.md).  
  
2.  Özelliği test etmek için CTRL + F5'e veya F5 tuşuna basın. Deneysel örneği [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] açar. Bu örnekte oluşturun veya bir bağımlılık diyagramı açın.  
  
3.  Ana örneğinde VSIX yüklemek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], veya başka bir bilgisayarda Bul **.vsix** dosyasını **bin** VSIX proje dizininde. VSIX yüklemek istediğiniz bilgisayara kopyalayın. Windows Gezgini'nde (Windows 8 dosya Gezgini'nde) VSIX dosyasını çift tıklatın.  
  
     Kaldırmak için kullanın **Uzantılar ve güncelleştirmeler** üzerinde **Araçları** menüsü.  
  
##  <a name="command"></a>Menü komutu tanımlama  
 Daha fazla menü komutu tanımları varolan hareketi ya da komut projeye ekleyebilirsiniz. Her komut aşağıdaki özelliklere sahip bir sınıf tarafından tanımlanır:  
  
-   Sınıfı aşağıdaki gibi bildirilmiş:  
  
     `[LayerDesignerExtension]`  
  
     `[Export(typeof(ICommandExtension))]`  
  
     `public class`  *MyLayerCommand*  `: ICommandExtension { ... }`  
  
-   Ad alanı ve sınıf adını önemli.  
  
-   Uygulama yöntemleri `ICommandExtension` aşağıdaki gibidir:  
  
    -   `string Text {get;}`-Menüde görünen etiketi.  
  
    -   `void QueryStatus(IMenuCommand command)`-Kullanıcı diyagramda sağ tıklatır ve komut görünür ve kullanıcının geçerli seçim için etkin olup olmayacağını belirler olduğunda çağrılır.  
  
    -   `void Execute(IMenuCommand command)`-Kullanıcı komutu seçtiğinde çağrılır.  
  
-   Geçerli seçim belirlemek için aktarabilirsiniz `IDiagramContext`:  
  
     `[Import]`  
  
     `public IDiagramContext DiagramContext { get; set; }`  
  
     `...`  
  
     `DiagramContext.CurrentDiagram.SelectedShapes.Count()...`  
  
 Daha fazla bilgi için bkz: [gidin ve güncelleştirme modelleri program kodunda katman](../modeling/navigate-and-update-layer-models-in-program-code.md).  
  
 Yeni bir komut eklemek için aşağıdaki örneği içeren yeni bir kod dosyası oluşturun. Ardından test ve düzenleyin.  
  
```  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;  
using System.ComponentModel.Composition;  
using System.Linq;  
  
namespace MyLayerExtension // Change to your preference.  
{  
  // This is a feature for dependency diagrams:  
  [LayerDesignerExtension]  
  // This feature is a menu command:  
  [Export(typeof(ICommandExtension))]  
  // Change the class name to your preference:  
  public class MyLayerCommand : ICommandExtension  
  {  
    [Import]  
    public IDiagramContext DiagramContext { get; set; }  
  
    [Import]  
    public ILinkedUndoContext LinkedUndoContext { get; set; }  
  
    // Menu command label:  
    public string Text  
    {  
      get { return "Duplicate layers"; }  
    }  
  
    // Called when the user right-clicks the diagram.  
    // Defines whether the command is visible and enabled.  
    public void QueryStatus(IMenuCommand command)  
    {   
      command.Visible =   
      command.Enabled = DiagramContext.CurrentDiagram  
        .SelectedShapes.Count() > 0;  
    }  
  
    // Called when the user selects the command.  
    public void Execute(IMenuCommand command)  
    {  
      // A selection of starting points:  
      IDiagram diagram = this.DiagramContext.CurrentDiagram;  
      ILayerModel lmodel = diagram.GetLayerModel();  
      foreach (ILayer layer in lmodel.Layers)  
      { // All layers in model.  
      }  
      // Updates should be performed in a transaction:  
      using (ILinkedUndoTransaction t =  
        LinkedUndoContext.BeginTransaction("copy selection"))  
      {  
        foreach (ILayer layer in   
          diagram.SelectedShapes  
            .Select(shape=>shape.GetLayerElement())  
            .Where(element => element is ILayer))  
        {  
          ILayer copy = lmodel.CreateLayer(layer.Name + "+");  
          // Position the shapes:  
          IShape originalShape = layer.GetShape();  
          copy.GetShape().Move(  
            originalShape.XPosition + originalShape.Width * 1.2,  
            originalShape.YPosition);  
        }  
        t.Commit();  
      }  
    }  
  }  
}  
```  
  
##  <a name="gesture"></a>Hareket işleyicisi tanımlama  
 Hareket işleyicisi kullanıcı bağımlılık diyagram üzerine öğeleri sürüklendiğinde ve kullanıcı herhangi bir yere diyagramda tıklattığında yanıt verir.  
  
 Varolan bir komutu veya hareket işleyicisi VSIX proje için hareket işleyicisi tanımlayan bir kod dosyası ekleyebilirsiniz:  
  
```  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;  
using Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement;  
using Microsoft.VisualStudio.Modeling.ExtensionEnablement;  
using System.ComponentModel.Composition;  
using System.Linq;  
namespace MyLayerExtensions // change to your preference  
{  
  [LayerDesignerExtension]  
  [Export(typeof(IGestureExtension))]  
  public class MyLayerGestureHandler : IGestureExtension  
  {  
  }  
}  
```  
  
 Aşağıdaki noktaları hareket işleyicileri hakkında dikkat edin:  
  
-   Üyeleri `IGestureExtension` aşağıdaki gibidir:  
  
     **OnDoubleClick** -kullanıcı herhangi bir yere diyagramı tıklattığında çağrılır.  
  
     **CanDragDrop** - art arda diyagram üzerine bir öğe sürükleme sırasında kullanıcı fareyi hareket ederken denir. Hızlı bir şekilde çalışması gerekir.  
  
     **OnDragDrop** -kullanıcı bir öğeyi diyagram üzerine düştüğünde çağrılır.  
  
-   Her yöntem için ilk bağımsız değişken bir `IShape`, gelen katman öğesi alabilirsiniz. Örneğin:  
  
    ```  
    public void OnDragDrop(IShape target, IDataObject data)  
    {  
        ILayerElement element = target.GetLayerElement();  
        if (element is ILayer)  
        {  
            // ...  
        }  
    }  
    ```  
  
-   Sürüklenen öğenin bazı türleri için işleyiciler zaten tanımlanmış. Örneğin, kullanıcı öğeleri Çözüm Gezgini'nden bir bağımlılık diyagram üzerine sürükleyebilirsiniz. Bu tür bir öğe için bir Sürükle işleyici tanımlayamazsınız. Bu durumda, `DragDrop` yöntemleri değil çağrılabilir.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program kodunda katman modellerini gezinme ve güncelleştirme](../modeling/navigate-and-update-layer-models-in-program-code.md)   
 [Bağımlılık diyagramlarına özel mimari doğrulaması ekleme](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)   
