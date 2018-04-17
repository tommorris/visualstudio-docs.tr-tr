---
title: GetReferenceAssemblyPaths görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 178ef49c-5dee-405b-a14b-a37f41dc0609
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 06cd1da1a30e4d19981465dbe65218fe337e1fef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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