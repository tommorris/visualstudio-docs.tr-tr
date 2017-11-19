---
title: "GetReferenceAssemblyPaths görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 178ef49c-5dee-405b-a14b-a37f41dc0609
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 587edbdf52f34b2a7f634cdc22d74f5fc6ead1ee
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="getreferenceassemblypaths-task"></a>GetReferenceAssemblyPaths Görevi
Başvuru çeşitli çerçeveleri derleme yolunu döndürür.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `GetReferenceAssemblyPaths` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ReferenceAssemblyPaths`|İsteğe bağlı `String[]` çıkış parametresi.<br /><br /> Temel yolunu döndürür `TargetFrameworkMoniker` parametresi. Varsa `TargetFrameworkMoniker` null veya boş, bu yol `String.Empty`.|  
|`FullFrameworkReferenceAssemblyPaths`|İsteğe bağlı `String[]` çıkış parametresi.<br /><br /> Temel yolunu döndürür `TargetFrameworkMoniker` ad profili parçası dikkate olmadan parametresi. Varsa `TargetFrameworkMoniker` null veya boş, bu yol `String.Empty`.|  
|`TargetFrameworkMoniker`|İsteğe bağlı `String` parametresi.<br /><br /> Başvuru derleme yollarını ile ilişkili hedef framework ad belirtir.|  
|`RootPath`|İsteğe bağlı `String` parametresi.<br /><br /> Başvuru derleme yolu oluşturmak için kök yolu belirtir.|  
|`BypassFrameworkInstallChecks`|İsteğe bağlı <xref:System.Boolean> parametresi.<br /><br /> Varsa `true`, temel denetimleri atlar, `GetReferenceAssemblyPaths` belirli çalışma zamanı çerçeveleri, bağlı olarak hedef Framework'ü yüklendiğinden emin olmak için varsayılan olarak gerçekleştirir.|  
|`TargetFrameworkMonikerDisplayName`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Hedef framework ad görünen adını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)