---
title: "AssignTargetPath görevi | Microsoft Docs"
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
ms.assetid: 0e830e31-3bcf-4259-b2a8-a5df49b92d51
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: dac2cd390d6b7b706785d4807e659ca44620def9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="assigntargetpath-task"></a>AssignTargetPath Görevi
Bu görev listesini dosyaları ve ekler kabul `<TargetPath>` zaten belirtilmezse, öznitelikleri.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `AssignTargetPath` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`RootFolder`|İsteğe bağlı `string` giriş parametresi.<br /><br /> Hedef bağlantılar içeren klasörün yolunu içerir.|  
|`Files`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` giriş parametresi.<br /><br /> Dosyaları gelen listesini içerir.|  
|`AssignedFiles`|İsteğe Bağlı<br /><br /> <xref:Microsoft.Build.Framework.ITaskItem>`[]` çıkış parametresi.<br /><br /> Sonuçta elde edilen dosyaların listesini içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek yürütür `AssignTargetPath` bir proje yapılandırma görev.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="MyProject">  
        <AssignTargetPath  
RootFolder="Resources"  
            Files="@(ResourceFiles)"  
            <Output TaskParameter="AssignedFiles"  
                ItemName="OutAssignedFiles"/>  
        </AssignTargetPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)