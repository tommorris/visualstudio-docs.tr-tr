---
title: "CallTarget görevi | Microsoft Docs"
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
- CallTarget task [MSBuild]
- MSBuild, CallTarget task
ms.assetid: bb1fe2c4-4383-436f-8326-c24cc4a46150
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 339882fadba46dc0a42c6796d135e761a3554e9c
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="calltarget-task"></a>CallTarget Görevi
Proje dosyası içinde belirtilen hedefleri çağırır.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `CallTarget` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`RunEachTargetSeparately`|İsteğe bağlı `Boolean` giriş parametresi.<br /><br /> Varsa `true`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] altyapısı hedef bir kez çağrılır. Varsa `false`, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] altyapısı adlı bir kez tüm hedefleri oluşturmak için. Varsayılan değer `false` şeklindedir.|  
|`TargetOutputs`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Tüm yerleşik hedefleri çıkışları içerir.|  
|`Targets`|İsteğe bağlı `String[]` parametresi.<br /><br /> Hedef veya oluşturmak için hedeflerin belirtir.|  
|`UseResultsCache`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, önbelleğe alınan sonuç varsa, döndürülür.<br /><br /> **Not** olduğunda bir MSBuild görev çalıştırıldığında, bir kapsamda (ProjectFileName, GlobalProperties) çıktısını önbelleğe alınmış [TargetNames], derleme öğelerin bir listesi olarak.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir hedef olarak belirtilmişse `Targets` başarısız olur ve `RunEachTargetSeparately` olan `true`, kalan hedefleri oluşturmak görev devam eder.  
  
 Varsayılan hedefler oluşturmak istiyorsanız, kullanmak [MSBuild görevi](../msbuild/msbuild-task.md) ve `Projects` parametresi eşit `$(MSBuildProjectFile)`.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çağrıları `TargetA` gelen içinde `CallOtherTargets`.  
  
```xml  
<Project DefaultTargets="CallOtherTargets"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <Target Name="CallOtherTargets">  
        <CallTarget Targets="TargetA"/>  
    </Target>  
  
    <Target Name="TargetA">  
        <Message Text="Building TargetA..." />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Hedefler](../msbuild/msbuild-targets.md)