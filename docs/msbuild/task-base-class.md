---
title: Görev taban sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
caps.latest.revision: 6
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c27077237b3fd173be0ba368d1b34e54939ea1e2
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="task-base-class"></a>Görev Taban Sınıfı
Birçok görevi sonuçta devralınan <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu sınıf aktarımlar görevleri birkaç parametre ekler. Bu parametreler, bu belgede listelenir.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda bu temel sınıfın parametreler açıklanmaktadır.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine> parametresi.<br /><br /> Görevler için kullanılabilir yapı altyapısı arabirimi belirtir. Yapı altyapısı geri içine çağırmak görevler izin vermek için bu parametreyi otomatik olarak ayarlar.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine2> parametresi.<br /><br /> Görevler için kullanılabilir yapı altyapısı arabirimi belirtir. Yapı altyapısı geri içine çağırmak görevler izin vermek için bu parametreyi otomatik olarak ayarlar.<br /><br /> Bu bir kolaylık özelliği, böylelikle bu sınıfından devralan görev yazarlar değerinden cast gerekmez `IBuildEngine` için `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine3> parametresi.<br /><br /> Ana bilgisayar tarafından sağlanan yapı altyapısı arabirimi belirtir.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskHost> parametresi.<br /><br /> (Null olabilir) ana bilgisayar nesnesi örneği belirtir. IDE konak bir konak nesnesi belirli bu görevle ilişkili varsa yapı altyapısı bu özelliği ayarlar.|  
|<xref:Microsoft.Build.Utilities.Task.Log%2A>|İsteğe bağlı <xref:Microsoft.Build.Utilities.TaskLoggingHelper> salt okunur parametresi.<br /><br /> Günlüğe kaydetme yardımcı nesnesi...|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)