---
title: IDE içinden derleme başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- build
ms.assetid: 936317aa-63b7-4eb0-b9db-b260a0306196
caps.latest.revision: 5
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 307d05c9f35309d97b3813dfaa4cc4db1cf1f91c
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="starting-a-build-from-within-the-ide"></a>IDE İçinden Derleme Başlatma
Özel proje sistemleri kullanmalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildManagerAccessor> derlemeleri başlatmak için. Bu konu, bunun nedeni açıklar ve yordam açıklanmaktadır.  
  
## <a name="parallel-builds-and-threads"></a>Paralel yapılar ve iş parçacıkları  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Aracı ortak kaynaklara erişim gerektiren paralel derlemeleri sağlar. Proje sistemleri çalıştırabilirsiniz derlemeleri zaman uyumsuz olarak, ancak bu sistemlere yapı işlevlerinde çağrısı çağırmamalıdır geri yapı yöneticisi sağlanır.  
  
 Proje sistem ortam değişkenlerini değiştirirse, yapı NodeAffinity OutOfProc için ayarlamanız gerekir. Bu işlem dışı düğüm gerektiren bu yana ana bilgisayar nesneleri kullanamayacağınız anlamına gelir.  
  
## <a name="using-ivsbuildmanageraccessor"></a>IVSBuildManagerAccessor kullanma  
 Aşağıdaki kod, proje sistemi bir yapı başlatmak için kullanabileceğiniz bir yöntem özetlenmektedir:  
  
```csharp
  
public bool Build(Project project, bool isDesignTimeBuild)  
{  
    // Get the accessor from the IServiceProvider interface for the   
    // project system  
    IVsBuildManagerAccessor accessor =  
        serviceProvider.GetService(typeof(SVsBuildManagerAccessor)) as     
        IVsBuildManagerAccessor;  
    bool releaseUIThread = false;  
    try  
    {  
        if(accessor != null)  
        {  
            // Claim the UI thread under the following conditions:  
            // 1. The build must use a resource that uses the UI thread  
            // or,  
            // 2. The build requires the in-proc node AND waits on the   
            // UI thread for the build to complete  
            if(NeedsUIThread)  
            {  
                int result = accessor.ClaimUIThreadForBuild();  
                if(result != S_OK)  
                {  
                     // Not allowed to claim the UI thread right now  
                     return false;  
                }  
                releaseUIThread = true;  
             }  
             if(isDesignTimeBuild)  
             {  
// Start the design time build  
                  int result = accessor.BeginDesignTimeBuild();  
                  if(result != S_OK)  
                  {  
                      // Not allowed to begin a design-time build at  
                      // this time. Try again later.  
                      return false;  
                  }  
             }  
         }  
         bool buildSucceeded = false;  
         // perform project-system specific build set up tasks  
         // Create your BuildRequestData  
         // This assumes a IHostServices variable (hostServices) set   
   // to your host services. If you don't use a project instance   
         // (you build from a file for example) then use another   
         // constructor.  
         BuildRequestData requestData = new   
             BuildRequestData(project.CreateProjectInstance(),   
             "myTarget", hostServices,   
             BuildRequestData.BuildRequestDataFlags.None);  
         // Mark your your submission as Pending  
         BuildSubmission submission =  
              BuildManager.DefaultBuildManager.  
              PendBuildRequest(requestData);  
         // Register the loggers in BuildLoggers  
         if (accessor != null)  
         {  
               foreach (ILogger logger in BuildLoggers)  
               {  
                    accessor.RegisterLogger(submission.SubmissionId,   
                        logger);  
               }  
         }  
         BuildResult buildResult = submission.Execute();  
         return buildResult;  
     }  
     // Clean up resources  
     finally  
     {  
         if(accessor != null)  
         {  
             // Unregister the loggers, if necessary.  
             accessor.UnregisterLoggers(submission.SubmissionId);  
             // Release the UI thread, if used  
             if(releaseUIThread)  
             {  
                  accessor.ReleaseUIThreadForBuild();  
             }  
             // End the design time build, if used  
             if(isDesignTimeBuild)  
             {  
                  accessor.EndDesignTimeBuild();  
             }  
         }  
     }  
}  
  
```