---
title: WriteLinesToFile görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#WriteLinesToFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- WriteLinesToFile task [MSBuild]
- MSBuild, WriteLinesToFile task
ms.assetid: 9c8862ac-8da5-4437-9430-ecc30421f1c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f321eadf4fa02d55e869dcc0d9c93b637a2d3ac3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="writelinestofile-task"></a>WriteLinesToFile Görevi
Belirtilen öğeleri yollarını belirtilen metin dosyasına yazar.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `WriteLinestoFile` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`File`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Öğeleri yazmak için dosyayı belirtir.|  
|`Lines`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Dosyasına yazmaya maddeler belirtir.|  
|`Overwrite`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev dosyasında varolan içeriğin üzerine yazar.|  
|`Encoding`|İsteğe bağlı `String` parametresi.<br /><br /> Örneğin, "Unicode" kodlaması karakter seçer.  Ayrıca bkz. <xref:System.Text.Encoding>.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `Overwrite` olan `true`, yeni bir dosya oluşturur, içeriği dosyaya yazmak ve dosyayı kapatır. Hedef dosya zaten varsa üzerine yazılır. Varsa `Overwrite` olan `false`, dosya için içeriği ekler, zaten yoksa, hedef dosya oluşturma.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `WriteLinesToFile` öğeleri yollarını yazmak için görev `MyItems` öğesi tarafından belirtilen dosya koleksiyonuna `MyTextFile` öğe koleksiyonu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyTextFile Include="Items.txt"/>  
        <MyItems Include="*.cs"/>  
    </ItemGroup>  
  
    <Target Name="WriteToFile">  
        <WriteLinesToFile  
            File="@(MyTextFile)"  
            Lines="@(MyItems)"  
            Overwrite="true"  
            Encoding="Unicode"/>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)