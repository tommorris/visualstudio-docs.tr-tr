---
title: "İleti görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Message
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Message task
- Message task [MSBuild]
ms.assetid: 2293309d-42b6-46dc-9684-8c146f66bc28
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 442ce8ab8a137f6ca359a4ff8ebc6fcd7e2272cc
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="message-task"></a>İleti Görevi
Derleme sırasında bir ileti kaydeder.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri ayarlayamadı tablo açıklar `Message` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Importance`|İsteğe bağlı `String` parametresi.<br /><br /> İletinin önemini belirtir. Bu parametre değerini olabilir `high`, `normal` veya `low`. Varsayılan değer `normal` şeklindedir.|  
|`Text`|İsteğe bağlı `String` parametresi.<br /><br /> Oturum hata metni.|  
  
## <a name="remarks"></a>Açıklamalar  
 `Message` Görev verir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri günlükçüleri derleme sürecindeki farklı adımlar, sorunu iletileri.  
  
 Varsa `Condition` parametresi hesaplar için `true`, değeri `Text` parametresi oturum açmış olmanız ve yapı yürütülmeye devam eder. Varsa bir `Condition` parametresi yok, ileti metni günlüğe kaydedilir. Günlüğe kaydetme hakkında daha fazla bilgi için bkz: [yapı günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Varsayılan olarak, ileti MSBuild konsol Günlükçü gönderilir. Bu ayar değiştirilebilir <xref:Microsoft.Build.Tasks.TaskExtension.Log%2A> parametresi. Günlükçü yorumlar `Importance` parametresi.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği için tüm kayıtlı günlükçüleri iletilerini günlüğe kaydeder.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="DisplayMessages">  
        <Message Text="Project File Name = $(MSBuildProjectFile)" />  
        <Message Text="Project Extension = $(MSBuildProjectExtension)" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Derleme günlüklerini alma](../msbuild/obtaining-build-logs-with-msbuild.md)