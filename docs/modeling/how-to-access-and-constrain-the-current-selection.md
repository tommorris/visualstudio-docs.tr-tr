---
title: 'Nasıl yapılır: Geçerli Seçime Erişme ve Seçimi Kısıtlama'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, accessing the current selection
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5d8fb0a2e5d218b76e972fc97a53afcd2f8ef3e6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-access-and-constrain-the-current-selection"></a>Nasıl yapılır: Geçerli Seçime Erişme ve Seçimi Kısıtlama

Etki alanına özgü dil için bir komut veya hareket işleyicisi yazdığınızda, kullanıcı sağ hangi öğe belirleyebilirsiniz. Ayrıca bazı şekiller veya alanlar seçilmesini engelleyebilirsiniz. Örneğin, kullanıcı bir simge oluşturma öğesi tıkladığında, içerdiği şekli yerine seçili düzenleyebilirsiniz. Bu şekilde seçim sınırlama yazmak zorunda işleyicileri sayısını azaltır. Ayrıca, herhangi bir yere şeklinde oluşturma öğesi kaçının gerek kalmadan tıklatabilirsiniz kullanıcıya, kolaylaştırır.

## <a name="access-the-current-selection-from-a-command-handler"></a>Bir komut işleyici Geçerli seçimdeki erişim

Bir etki alanına özgü dil komut kümesi sınıfı özel komutlar için komut işleyicileri içerir. <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> Sınıfı, bir etki alanına özgü dil komut kümesi sınıfı kendisinden türetilen, geçerli seçim erişmek için birkaç üyeyi sağlar.

Komut bağlı olarak komut işleyici modeli Tasarımcısı'nı, model Gezgini ya da etkin pencereyi seçim yapmanız gerekebilir.

### <a name="to-access-selection-information"></a>Seçim bilgilere erişmek için

1.  <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> Sınıfı, geçerli seçim erişmek için kullanılan aşağıdaki üyeleri tanımlar.

    |Üye|Açıklama|
    |------------|-----------------|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsAnyDocumentSelectionCompartment%2A> Yöntemi|Döndürür `true` herhangi bir modeli Tasarımcısı'nda seçili ise, bir bölme şekli; Aksi halde, `false`.|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsDiagramSelected%2A> Yöntemi|Döndürür `true` diyagram modeli Tasarımcısı'nda seçilen; Aksi takdirde ise `false`.|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsSingleDocumentSelection%2A> Yöntemi|Döndürür `true` tam olarak bir öğe, model Tasarımcısı'nda seçilen Aksi takdirde `false`.|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsSingleSelection%2A> Yöntemi|Döndürür `true` tam olarak bir öğe varsa etkin penceresinde seçili; Aksi takdirde `false`.|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.CurrentDocumentSelection%2A> Özelliği|Modeli Tasarımcısı'nda seçili öğe salt okunur bir koleksiyonunu alır.|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.CurrentSelection%2A> Özelliği|Etkin penceresinde seçili öğe salt okunur bir koleksiyonunu alır.|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.SingleDocumentSelection%2A> Özelliği|Seçimi birincil öğenin modeli Tasarımcısı'nda alır.|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.SingleSelection%2A> Özelliği|Seçimin birincil öğe Etkin pencerede alır.|

2.  <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet.CurrentDocView%2A> Özelliği <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> sınıfı erişim sağlar <xref:Microsoft.VisualStudio.Modeling.Shell.DiagramDocView> modeli Tasarımcısı penceresi temsil eder ve seçilen öğeleri modeli Tasarımcısı'nda ek erişim sağlayan nesne.

3.  Ayrıca, oluşturulan kod Gezgini araç penceresi özelliği tanımlar ve etki alanına özgü dil için sınıf komutu explorer seçimi özelliğinde ayarlayın.

    -   Explorer araç penceresi özelliği etki alanına özgü dil explorer araç penceresi sınıfı örneğini döndürür. Explorer araç penceresi sınıfı türetilen <xref:Microsoft.VisualStudio.Modeling.Shell.ModelExplorerToolWindow> sınıfı ve etki alanına özgü dil için model Gezgini temsil eder.

    -   `ExplorerSelection` Özelliği, etki alanına özgü dil için model Gezgini penceresinde seçili öğeyi döndürür.

## <a name="determine-which-window-is-active"></a>Hangi penceresi etkin olduğunda belirleme

<xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> Arabirimi içerir Kabuk geçerli seçim durumunda erişim sağlamak üyeleri tanımlar. Alabileceğiniz bir <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> paket sınıfı ya da komut kümesi sınıf etki alanına özgü dil nesnesinden `MonitorSelection` özelliği her bir taban sınıf içinde tanımlanmış. Paket sınıfı türetilen <xref:Microsoft.VisualStudio.Modeling.Shell.ModelingPackage> sınıfı ve komut kümesi sınıfı türer <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> sınıfı.

### <a name="to-determine-from-a-command-handler-what-type-of-window-is-active"></a>Bir komut işleyici penceresi ne tür etkin olduğunu belirlemek için

1.  <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.MonitorSelection%2A> Özelliği <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> sınıf döndürür bir <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> Kabuğu'nda geçerli seçim durumuna erişim sağlayan nesne.

2.  <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService.CurrentSelectionContainer%2A> Özelliği <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> arabirimi etkin pencereden farklı olabilir etkin seçim kapsayıcısı alır.

3.  Komutu için aşağıdaki özellikleri sizin için ne tür bir pencere etkin olduğunu belirlemek için etki alanına özgü dil set sınıfı ekleyin.

    ```csharp
    // using Microsoft.VisualStudio.Modeling.Shell;

    // Returns true if the model designer is the active selection container;
    // otherwise, false.
    protected bool IsDesignerActive
    {
        get
        {
            return (this.MonitorSelection.CurrentSelectionContainer
                is DiagramDocView);
        }
    }

    // Returns true if the model explorer is the active selection container;
    // otherwise, false.
    protected bool IsExplorerActive
    {
        get
        {
            return (this.MonitorSelection.CurrentSelectionContainer
                is ModelExplorerToolWindow);
        }
    }
    ```

## <a name="constrain-the-selection"></a>Seçimi sınırlamak

Seçim kuralları ekleyerek, kullanıcı bir öğeyi modelde seçtiğinde hangi öğelerin seçilir kontrol edebilirsiniz. Örneğin, tek bir birim olarak öğe sayısı işlemek izin vermek için bir seçim kuralı kullanabilirsiniz.

### <a name="to-create-a-selection-rule"></a>Bir seçim kuralı oluşturmak için

1.  Özel kod dosyası DSL projesi oluşturun

2.  Türetilmiş bir seçim kuralı sınıf tanımlama <xref:Microsoft.VisualStudio.Modeling.Diagrams.DiagramSelectionRules> sınıfı.

3.  Geçersiz kılma <xref:Microsoft.VisualStudio.Modeling.Diagrams.DiagramSelectionRules.GetCompliantSelection%2A> seçim kriterleri uygulamak için seçim kuralı sınıfının yöntemi.

4.  ClassDiagram sınıfı için bir parçalı sınıf tanımı özel kod dosyanıza ekleyin.

     `ClassDiagram` Sınıfı türer <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram> sınıfı ve DSL projesinde Diagram.cs, oluşturulan kod dosyasında tanımlanır.

5.  Geçersiz kılma <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.SelectionRules%2A> özelliği `ClassDiagram` özel seçim kuralı döndürülecek sınıfı.

     Varsayılan uygulaması <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.SelectionRules%2A> özellik seçimi değiştirmez bir seçim kuralı nesnesi alır.

### <a name="example"></a>Örnek

Aşağıdaki kod dosyası başlangıçta seçilen etki alanı şekillerin her biri tüm örneklerini dahil etmek için seçimi genişletir bir seçim kuralı oluşturur.

```csharp
using System;
using System.Collections.Generic;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;

namespace CompanyName.ProductName.GroupingDsl
{
    public class CustomSelectionRules : DiagramSelectionRules
    {
        protected Diagram diagram;
        protected IElementDirectory elementDirectory;

        public CustomSelectionRules(Diagram diagram)
        {
            if (diagram == null) throw new ArgumentNullException();

            this.diagram = diagram;
            this.elementDirectory = diagram.Store.ElementDirectory;
        }

        /// <summary>Called by the design surface to allow selection filtering.
        /// </summary>
        /// <param name="currentSelection">[in] The current selection before any
        /// ShapeElements are added or removed.</param>
        /// <param name="proposedItemsToAdd">[in/out] The proposed DiagramItems to
        /// be added to the selection.</param>
        /// <param name="proposedItemsToRemove">[in/out] The proposed DiagramItems
        /// to be removed from the selection.</param>
        /// <param name="primaryItem">[in/out] The proposed DiagramItem to become
        /// the primary DiagramItem of the selection. A null value signifies that
        /// the last DiagramItem in the resultant selection should be assumed as
        /// the primary DiagramItem.</param>
        /// <returns>true if some or all of the selection was accepted; false if
        /// the entire selection proposal was rejected. If false, appropriate
        /// feedback will be given to the user to indicate that the selection was
        /// rejected.</returns>
        public override bool GetCompliantSelection(
            SelectedShapesCollection currentSelection,
            DiagramItemCollection proposedItemsToAdd,
            DiagramItemCollection proposedItemsToRemove,
            DiagramItem primaryItem)
        {
            if (currentSelection.Count == 0 && proposedItemsToAdd.Count == 0) return true;

            HashSet<DomainClassInfo> itemsToAdd = new HashSet<DomainClassInfo>();

            foreach (DiagramItem item in proposedItemsToAdd)
            {
                if (item.Shape != null)
                    itemsToAdd.Add(item.Shape.GetDomainClass());
            }
            proposedItemsToAdd.Clear();
            foreach (DomainClassInfo classInfo in itemsToAdd)
            {
                foreach (ModelElement element
                    in this.elementDirectory.FindElements(classInfo, false))
                {
                    if (element is ShapeElement)
                    {
                        proposedItemsToAdd.Add(
                            new DiagramItem((ShapeElement)element));
                    }
                }
            }

            return true;
        }
    }

    public partial class ClassDiagram
    {
        protected CustomSelectionRules customSelectionRules = null;

        protected bool multipleSelectionMode = true;

        public override DiagramSelectionRules SelectionRules
        {
            get
            {
                if (multipleSelectionMode)
                {
                    if (customSelectionRules == null)
                    {
                        customSelectionRules = new CustomSelectionRules(this);
                    }
                    return customSelectionRules;
                }
                else
                {
                    return base.SelectionRules;
                }
            }
        }
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet>
- <xref:Microsoft.VisualStudio.Modeling.Shell.ModelingPackage>
- <xref:Microsoft.VisualStudio.Modeling.Shell.DiagramDocView>
- <xref:Microsoft.VisualStudio.Modeling.Shell.ModelExplorerToolWindow>
- <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService>
- <xref:Microsoft.VisualStudio.Modeling.Diagrams.DiagramSelectionRules>
- <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>