---
title: CallTarget görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CallTarget task [MSBuild]
- MSBuild, CallTarget task
ms.assetid: bb1fe2c4-4383-436f-8326-c24cc4a46150
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 83240cfa9deec2585aaa23db4aa79fbfe6929b09
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31571678"
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