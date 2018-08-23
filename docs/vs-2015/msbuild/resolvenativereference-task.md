---
title: ResolveNativeReference görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveNativeReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNativeReference task
- ResolveNativeReference task [MSBuild]
ms.assetid: 56acd101-de77-4eec-92c6-f5c6d2187579
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d06171281706b2395cbac0c98b5b8a76c4da363c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633072"
---
# <a name="resolvenativereference-task"></a>ResolveNativeReference Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ResolveNativeReference görevi](https://docs.microsoft.com/visualstudio/msbuild/resolvenativereference-task).  
  
  
Yerel başvurular çözümleniyor. Implements <xref:Microsoft.Build.Tasks.ResolveNativeReference> sınıfı. Bu sınıf doğrudan sizin kodunuzdan kullanılmak üzere tasarlanmamıştır .NET Framework altyapısını destekler.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Parametreleri aşağıdaki tabloda açıklanmıştır `ResolveNativeReference` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AdditionalSearchPaths`|[String] gerekli (<!-- TODO: review code entity reference <xref:assetId:///String?qualifyHint=False&amp;autoUpgrade=True>  -->)`[]` parametresi.<br /><br /> Alır veya arama yollarını derleme kimliklerini yerel başvurular çözmek için ayarlar.|  
|`ContainedComComponents`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alır veya yerel derleme COM bileşenlerini ayarlar.|  
|`ContainedLooseEtcFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alır veya ayarlar yerel bildiriminde listelenen gevşek vb. dosyalar.|  
|`ContainedLooseTlbFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alır veya ayarlar yerel derleme gevşek .tlb dosyaları.|  
|`ContainedPrerequisiteAssemblies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alır veya ayarlar bildirimde kullanılabilmesi için önce mevcut olmalıdır derlemeler.|  
|`ContainedTypeLibraries`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alır veya yerel derleme tür kitaplıklarının ayarlar.|  
|`ContainingReferenceFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alır veya ayarlar başvuru dosyaları.|  
|`NativeReferences`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Alır veya ayarlar Win32 yerel bütünleştirilmiş kod başvuruları.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



