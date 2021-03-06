---
title: Görev taban sınıfı | Microsoft Docs
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
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b2b269d718871c58cb082ce09ed50ce70736b55
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686942"
---
# <a name="task-base-class"></a>Görev Taban Sınıfı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [görev temel sınıf](https://docs.microsoft.com/visualstudio/msbuild/task-base-class).  
  
  
Birçok görevi sonuçta devralınacak <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu sınıf, bunlardan türeyen görevlere birkaç parametre ekler. Bu parametreler, bu belgede listelenir.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda, bu temel sınıfın parametreler açıklanmıştır.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine> parametresi.<br /><br /> Görevler için kullanılabilir derleme altyapısı arabirimi belirtir. Yapı altyapısının geri içine çağırmak görevlere izin vermek için bu parametreyi otomatik olarak ayarlar.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine2> parametresi.<br /><br /> Görevler için kullanılabilir derleme altyapısı arabirimi belirtir. Yapı altyapısının geri içine çağırmak görevlere izin vermek için bu parametreyi otomatik olarak ayarlar.<br /><br /> Bu sınıftan devralmayı görev yazarları, değerinden dönüştürme gerekmez. böylece bu kullanışlı bir özelliktir `IBuildEngine` için `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.IBuildEngine3> parametresi.<br /><br /> Ana bilgisayar tarafından sağlanan yapı altyapısı arabirimi belirtir.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskHost> parametresi.<br /><br /> (Null olabilir) konak nesne örneğini belirtir. Yapı altyapısının, IDE konak bir konak nesnesi bu belirli görev ile ilişkili varsa bu özelliği ayarlar.|  
|<xref:Microsoft.Build.Utilities.Task.Log%2A>|İsteğe bağlı <xref:Microsoft.Build.Utilities.TaskLoggingHelper> salt okunur parametre.<br /><br /> Günlüğe kaydetme yardımcı nesnesi...|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevleri](../msbuild/msbuild-tasks.md)



