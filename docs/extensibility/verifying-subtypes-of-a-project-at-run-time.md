---
title: Çalışma zamanında bir projenin Subtypes doğrulanıyor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b8898da6850c01c1a248b57b0fbc5f46be2a8ff4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31136835"
---
# <a name="verifying-subtypes-of-a-project-at-run-time"></a>Çalışma zamanında bir projenin Subtypes doğrulanıyor
Bir özel proje alt bağlıdır VSPackage alt tür ve böylece alt mevcut değilse düzgün biçimde edilemeyebilir aranacak mantığının içermelidir. Aşağıdaki yordamda, belirtilen alt türe varlığını doğrulamak gösterilmiştir.  
  
### <a name="to-verify-the-presence-of-a-subtype"></a>Bir alt türü varlığını doğrulamak için  
  
1.  Proje ve çözüm nesneler olarak proje hiyerarşisi almak bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> aşağıdaki kod, VSPackage ekleyerek nesne.  
  
    ```  
    EnvDTE.DTE dte;  
    dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
  
    EnvDTE.Project project;  
    project = dte.Solution.Projects.Item(1);  
  
    IVsSolution solution;  
    solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
  
    IVsHierarchy hierarchy;  
    hierarchy = solution.GetProjectOfUniqueName(project.UniqueName);  
  
    ```  
  
2.  Hiyerarşiye cast <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> arabirimi.  
  
    ```  
    IVsAggregatableProjectCorrected AP;  
    AP = hierarchy as IVsAggregatableProjectCorrected;  
  
    ```  
  
3.  Proje türü GUID listesini çağırarak alma <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A>.  
  
    ```  
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();  
  
    ```  
  
4.  Belirtilen alt türe GUID için kontrol edin.  
  
    ```  
    // Replace the string "MyGUID" with the GUID of the subtype.  
    string guidMySubtype = "MyGUID";  
    if (projTypeGuids.IndexOf(guidMySubtype) > 0)  
    {  
        // The specified subtype is present.  
    }  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje alt türleri](../extensibility/internals/project-subtypes.md)   
 [Proje Subtypes tasarım](../extensibility/internals/project-subtypes-design.md)   
 [Proje Alt Türleri Tarafından Genişletilen Özellikler ve Metotlar](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)