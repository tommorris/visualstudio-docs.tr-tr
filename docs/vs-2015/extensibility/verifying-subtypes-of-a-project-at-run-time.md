---
title: Çalışma zamanında proje alt türlerini doğrulama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- project subtypes
- check subtypes
ms.assetid: b87780ec-36a3-4e9a-9ee2-7abdc26db739
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e77fa60687ecfebdae8555b516af678cf3966211
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675785"
---
# <a name="verifying-subtypes-of-a-project-at-run-time"></a>Çalışma Zamanında Proje Alt Türlerini Doğrulama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [doğrulama proje alt türlerini çalışma zamanında](https://docs.microsoft.com/visualstudio/extensibility/verifying-subtypes-of-a-project-at-run-time).  
  
Özel proje alt türü üzerinde olduğu bir VSPackage'ı alt tür ve böylece alt mevcut değilse düzgün bir şekilde devredebilirsiniz aramak için mantık eklemeniz gerekir. Aşağıdaki yordam, belirtilen alt varlığını doğrulamak gösterilmektedir.  
  
### <a name="to-verify-the-presence-of-a-subtype"></a>Bir alt varlığını doğrulamak için  
  
1.  Proje ve çözüm nesneler olarak proje hiyerarşisi almak bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> , VSPackage için aşağıdaki kodu ekleyerek nesne.  
  
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
  
2.  Hiyerarşi için cast <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected> arabirimi.  
  
    ```  
    IVsAggregatableProjectCorrected AP;  
    AP = hierarchy as IVsAggregatableProjectCorrected;  
  
    ```  
  
3.  Çağırarak proje türü GUID'ın listesini alın <xref:Microsoft.VisualStudio.Shell.Flavor.IVsAggregatableProjectCorrected.GetAggregateProjectTypeGuids%2A>.  
  
    ```  
    string projTypeGuids = AP.GetAggregateProjectTypeGuids().ToUpper();  
  
    ```  
  
4.  Belirtilen alt türe GUİD'i kontrol edin.  
  
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
 [Proje alt türleri tasarımı](../extensibility/internals/project-subtypes-design.md)   
 [Proje Alt Türleri Tarafından Genişletilen Özellikler ve Metotlar](../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)

