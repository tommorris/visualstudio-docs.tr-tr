---
title: Proje Özellikleri alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties, displaying in tool window
- tool windows, displaying project propeties
ms.assetid: 96ba07ca-0811-4013-8602-12550ac4ba79
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d93e941c98293ca1d28f92bce1bc8c21f5ca2121
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127630"
---
# <a name="getting-project-properties"></a>Proje özelliklerini alma
Bu kılavuzda gösterir araç penceresinde proje özelliklerini görüntüler.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
### <a name="to-create-a-vsix-project-and-add-a-tool-window"></a>VSIX proje oluşturma ve bir araç penceresi eklemek için  
  
1.  Visual Studio uzantılarının uzantısı varlıklar yer alacağı VSIX dağıtım projesi ile başlar. Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adlı VSIX proje `ProjectPropertiesExtension`. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Adlı bir özel araç penceresi öğesi şablonu ekleyerek bir araç penceresi `ProjectPropertiesToolWindow`. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle iletişim**gidin **Visual C# öğeleri / genişletilebilirlik** seçip **özel araç penceresi**. İçinde **adı** alan iletişim kutusunun en altında dosya adını değiştirmek `ProjectPropertiesToolWindow.cs`. Özel araç penceresi oluşturma hakkında daha fazla bilgi için bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
3.  Çözümü derlemek ve hatasız derlendiğinden emin olun.  
  
### <a name="to-display-project-properties-in-a-tool-window"></a>Bir araç penceresinde proje özelliklerini görüntülemek için  
  
1.  ProjectPropertiesToolWindowCommand.cs dosyasında aşağıdaki ekleyin using deyimleri.  
  
    ```csharp  
    using EnvDTE;  
    using System.Windows.Controls;  
  
    ```  
  
2.  ProjectPropertiesToolWindowControl.xaml, varolan bir düğmeyi kaldırmak ve Araç Kutusu'ndan TreeView ekleyin. Ayrıca ProjectPropertiesToolWindowControl.xaml.cs dosyasından click olay işleyicisi kaldırabilirsiniz.  
  
3.  ProjectPropertiesToolWindowCommand.cs, projeyi açın ve özelliklerini okumak için ShowToolWindow() yöntemini kullanın, ardından TreeView özellikleri ekleyin. ShowToolWindow kodunu aşağıdaki gibi görünmelidir:  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        ToolWindowPane window = this.package.FindToolWindow(typeof(ProjectPropertiesToolWindow), 0, true);  
        if ((null == window) || (null == window.Frame))  
        {  
            throw new NotSupportedException("Cannot create window.");  
        }  
        IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
        Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
  
        // Get the tree view and populate it if there is a project open.  
        ProjectPropertiesToolWindowControl control = (ProjectPropertiesToolWindowControl)window.Content;  
        TreeView treeView = control.treeView;  
  
        // Reset the TreeView to 0 items.  
        treeView.Items.Clear();  
  
        DTE dte = (DTE)this.ServiceProvider.GetService(typeof(DTE));  
        Projects projects = dte.Solution.Projects;  
        if (projects.Count == 0)   // no project is open  
        {  
            TreeViewItem item = new TreeViewItem();  
            item.Name = "Projects";  
            item.ItemsSource = new string[]{ "no projects are open." };  
            item.IsExpanded = true;  
            treeView.Items.Add(item);  
            return;  
        }  
  
        Project project = projects.Item(1);  
        TreeViewItem item1 = new TreeViewItem();  
        item1.Header = project.Name + "Properties";  
        treeView.Items.Add(item1);  
  
        foreach (Property property in project.Properties)  
        {  
            TreeViewItem item = new TreeViewItem();  
            item.ItemsSource = new string[] { property.Name };  
            item.IsExpanded = true;  
            treeView.Items.Add(item);  
        }  
    }  
    ```  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmesi gerekir.  
  
5.  Deneysel örneğinde bir projeyi açın.  
  
6.  İçinde **görünüm / diğer pencereler** tıklatın **ProjectPropertiesToolWindow**.  
  
     Ağaç denetimi ile birlikte ilk proje adını ve tüm proje özelliklerini araç penceresinde görmeniz gerekir.