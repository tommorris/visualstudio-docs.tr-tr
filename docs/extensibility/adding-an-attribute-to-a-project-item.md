---
title: "Öznitelik bir proje öğesi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: attributes [Visual Studio], adding to a project item
ms.assetid: 404a71d5-cce5-44e7-9eaf-d747c794fedb
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fce6b9770703afda8e8c1af6e17c10287625f647
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="adding-an-attribute-to-a-project-item"></a>Öznitelik bir proje öğesi ekleme
Yöntemleri <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.GetItemAttribute%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> almak ve bir proje öğesi özniteliklerini değerini ayarlayın. Zaten yoksa, SetItemAttribute proje öğesi meta verilerde ekleme öznitelik oluşturur.  
  
## <a name="adding-an-attribute-to-a-project-item"></a>Öznitelik bir proje öğesi ekleme  
  
#### <a name="to-add-an-attribute-to-a-project-item"></a>Öznitelik bir proje öğesi eklemek için  
  
-   Aşağıdaki kod <xref:EnvDTE.DTE> Otomasyon nesnesi ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> öznitelik bir proje öğesi eklemek için yöntem. Proje öğesi kimliği proje öğesi adı "program.cs" elde edilir. Özniteliği "IMyData" Bu proje öğesi eklenir ve "MyValue" değeri verildiğinde.  
  
    ```  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution =     (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    IVsBuildPropertyStorage buildPropertyStorage = hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath =         (string)project.ProjectItems.Item("Program.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(  
            itemId, "MyAttribute", "MyValue");  
    }  
  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild proje dosyası içinde kalıcı veri](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)