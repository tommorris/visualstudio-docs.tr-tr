---
title: "Bir proje öğesi özelliği kalıcı yapma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, adding to a project item
- project items, adding properties
ms.assetid: d7a0f2b0-d427-4d49-9536-54edfb37c0f3
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e732821cf1ea14497038a65d49f2a10ce22c28a5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="persisting-the-property-of-a-project-item"></a>Bir proje öğesi özelliği kalıcı yapma
Kaynak dosyaya yazar gibi bir proje öğesi ekleme özelliği kalıcı hale getirmek isteyebilirsiniz. Proje dosyasında özelliği depolayarak bunu yapabilirsiniz.  
  
 Bir özellik bir proje dosyası ile kalıcı hale getirmek için ilk adım proje olarak hiyerarşisini elde edilir bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> arabirimi. Bu arabirim otomasyonu kullanarak veya kullanarak elde edebilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>. Arabirim edindikten sonra hangi proje öğesi seçili belirlemek için kullanabilirsiniz. Proje öğesi Kimliğine sahip olduğunuzda, kullanabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> özelliği eklemek için.  
  
 Aşağıdaki yordamlarda VsPkg.cs özelliği kalıcı `Author` değerle `Tom` proje dosyasında.  
  
### <a name="to-obtain-the-project-hierarchy-with-the-dte-object"></a>Proje hiyerarşisi DTE nesnesiyle edinme  
  
1.  Aşağıdaki kod, VSPackage ekleyin:  
  
    ```csharp  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    ```  
  
### <a name="to-persist-the-project-item-property-with-the-dte-object"></a>Proje öğesi özelliği DTE nesnesiyle kalıcı hale getirmek için  
  
1.  Yöntemi önceki yordamda verilen kod aşağıdaki kodu ekleyin:  
  
    ```csharp  
    IVsBuildPropertyStorage buildPropertyStorage =   
        hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath = (string)project.ProjectItems.Item(  
            "VsPkg.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom");  
    }  
    ```  
  
### <a name="to-obtain-the-project-hierarchy-using-ivsmonitorselection"></a>IVsMonitorSelection kullanarak proje hiyerarşisi edinme  
  
1.  Aşağıdaki kod, VSPackage ekleyin:  
  
    ```csharp  
    IVsHierarchy hierarchy = null;  
    IntPtr hierarchyPtr = IntPtr.Zero;  
    IntPtr selectionContainer = IntPtr.Zero;  
    uint itemid;  
  
    // Retrieve shell interface in order to get current selection  
    IVsMonitorSelection monitorSelection =     Package.GetGlobalService(typeof(SVsShellMonitorSelection)) as     IVsMonitorSelection;  
    if (monitorSelection == null)  
        throw new InvalidOperationException();  
  
    try  
    {  
        // Get the current project hierarchy, project item, and selection container for the current selection  
        // If the selection spans multiple hierachies, hierarchyPtr is Zero  
        IVsMultiItemSelect multiItemSelect = null;  
        ErrorHandler.ThrowOnFailure(  
            monitorSelection.GetCurrentSelection(  
                out hierarchyPtr, out itemid,   
                out multiItemSelect, out selectionContainer));  
  
        // We only care if there is only one node selected in the tree  
        if (!(itemid == VSConstants.VSITEMID_NIL ||   
            hierarchyPtr == IntPtr.Zero ||  
            multiItemSelect != null ||  
            itemid == VSConstants.VSITEMID_SELECTION))  
        {  
            hierarchy = Marshal.GetObjectForIUnknown(hierarchyPtr)  
                as IVsHierarchy;  
        }  
    }  
    finally  
    {  
        if (hierarchyPtr != IntPtr.Zero)  
            Marshal.Release(hierarchyPtr);  
        if (selectionContainer != IntPtr.Zero)  
            Marshal.Release(selectionContainer);  
    }  
    ```  
  
2.  
  
### <a name="to-persist-the-selected-project-item-property-given-the-project-hierarchy"></a>Seçili proje öğesi özelliği proje hiyerarşisi verilen kalıcı hale getirmek için  
  
1.  Yöntemi önceki yordamda verilen kod aşağıdaki kodu ekleyin:  
  
    ```  
    IVsBuildPropertyStorage buildPropertyStorage =   
        hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom");  
    }  
    ```  
  
### <a name="to-verify-that-the-property-is-persisted"></a>Özellik kalıcı olduğunu doğrulamak için  
  
1.  Başlat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve ardından açın veya bir çözüm oluşturun.  
  
2.  Projeyi seçin, VsPkg.cs öğesi **Çözüm Gezgini**.  
  
3.  Aksi takdirde, VSPackage yüklenir ve SetItemAttribute çalıştığını belirlemek veya bir kesme noktası kullanın.  
  
    > [!NOTE]
    >  Autoload VSPackage UI bağlamda yapabilecekleriniz <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT_SolutionExists>. Daha fazla bilgi için bkz: [yüklenirken VSPackages](../extensibility/loading-vspackages.md).  
  
4.  Kapat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve proje dosyasını Not Defteri'nde açın. Görmeniz gerekir \<Yazar > zel, değerle şu şekilde etiketleyin:  
  
    ```  
    <Compile Include="VsPkg.cs">  
        <Author>Tom</Author>  
    </Compile>  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Araçlar](../extensibility/internals/custom-tools.md)