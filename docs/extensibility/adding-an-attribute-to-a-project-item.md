---
title: Öznitelik bir proje öğesi ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- attributes [Visual Studio], adding to a project item
ms.assetid: 404a71d5-cce5-44e7-9eaf-d747c794fedb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d601a4cb3a7804520f0c9c95e746275e27db4bcd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [MSBuild Proje Dosyasında Verileri Kalıcı Hale Getirme](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)