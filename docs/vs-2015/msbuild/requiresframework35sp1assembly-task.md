---
title: RequiresFramework35SP1Assembly görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- RequiresFramework35SP1Assembly task [MSBuild]
- MSBuild, RequiresFramework35SP1Assembly task
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0ffc3b685314983949026a67f9be95f0fce1245
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689314"
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [RequiresFramework35SP1Assembly görevi](https://docs.microsoft.com/visualstudio/msbuild/requiresframework35sp1assembly-task).  
  
  
Uygulama .NET Framework 3.5 SP1 isteyip istemediğini belirler.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `RequiresFramework35SP1Assembly` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Assemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Uygulama içinde başvurulan bir derleme belirtir.|  
|`CreateDesktopShortcut`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, yükleme sırasında masaüstünde bir kısayol simgesini oluşturur.|  
|`DeploymentManifestEntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Uygulama için bildirim dosyası adını belirtir.|  
|`EntryPoint`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Uygulamayı çalıştırdığınızda, yürütülmesi gereken derleme belirtir.|  
|`ErrorReportUrl`|İsteğe bağlı `String` parametresi.<br /><br /> ClickOnce yüklemeleri sırasında karşılaşılan iletişim kutularında görüntülenen Web sitesini belirtir.|  
|`Files`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Uygulama yayınlandığında, dağıtılacak dosyaların listesini belirtir.|  
|`ReferencedAssemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Projede başvurulan bir derleme belirtir.|  
|`RequiresMinimumFramework35SP1`|İsteğe bağlı `Boolean` çıkış parametresi.<br /><br /> Varsa `true`, uygulama .NET Framework 3.5 SP1 gerektirir.|  
|`SigningManifests`|İsteğe bağlı `Boolean` çıkış parametresi.<br /><br /> Varsa `true`, ClickOnce bildirimlerinin imzalı.|  
|`SuiteName`|İsteğe bağlı `String` parametresi.<br /><br /> Klasörün adını belirtir **Başlat** menü, uygulama yüklenir.|  
|`TargetFrameworkVersion`|İsteğe bağlı `String` parametresi.<br /><br /> .NET Framework sürümünü belirtir. Bu uygulama hedefler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



