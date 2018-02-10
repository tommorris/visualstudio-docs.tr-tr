---
title: "TaskExtension taban sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, tool task base class
- tool task base class [MSBuild]
ms.assetid: 08bb8059-b7e2-4565-89ba-d9034d4f0e16
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c2ac7a4811033eec63c5db3d8546b033b7db9c32
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="taskextension-base-class"></a>TaskExtension Taban Sınıfı
Birçok görevi devralınmalıdır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu devralma zincirini aktarımlar görevleri birkaç parametre ekler. Bu parametreler, bu belgede listelenir.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda temel sınıflarının parametreler açıklanmaktadır.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine> parametresi.<br /><br /> Görevler için kullanılabilir yapı altyapısı arabirimi belirtir. Yapı altyapısı geri içine çağırmak görevler izin vermek için bu parametreyi otomatik olarak ayarlar.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine2> parametresi.<br /><br /> Görevler için kullanılabilir yapı altyapısı arabirimi belirtir. Yapı altyapısı geri içine çağırmak görevler izin vermek için bu parametreyi otomatik olarak ayarlar.<br /><br /> Bu bir kolaylık özelliği, böylelikle bu sınıfından devralan görev yazarlar değerinden cast gerekmez `IBuildEngine` için `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine3> parametresi.<br /><br /> Ana bilgisayar tarafından sağlanan yapı altyapısı arabirimi belirtir.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskHost> parametresi.<br /><br /> (Null olabilir) ana bilgisayar nesnesi örneği belirtir. IDE konak bir konak nesnesi belirli bu görevle ilişkili varsa yapı altyapısı bu özelliği ayarlar.|  
|<xref:Microsoft.Build.Tasks.TaskExtension.Log%2A>|İsteğe bağlı <xref:Microsoft.Build.Utilities.TaskLoggingHelper> salt okunur parametresi.<br /><br /> Alır bir `TaskLoggingHelperExtension` görev günlük yöntemleri içeren nesne.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)