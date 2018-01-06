---
title: "Çalışma zamanında bir projenin Subtypes doğrulanıyor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 18049c034286c33247aec11aba77071daa93ef5c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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