---
title: "AssignCulture görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#AssignCulture
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, AssignCulture task
- AssignCulture task [MSBuild]
ms.assetid: 8f8314cc-82a6-4f16-a62d-b9f0d1d5e274
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 40fb47caea1b9fcb0d25d45495cf3e3c1d3e04fb
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="assignculture-task"></a>AssignCulture Görevi
Bu görev, dosya adının bir parçası olarak geçerli bir .NET kültür tanımlayıcısı dizesi içerebilir öğelerin listesini kabul eder ve adlı bir meta veri içermeyen öğeleri üreten `Culture` karşılık gelen içeren kültür tanımlayıcısı. Bu görev meta verileri aynı adla sahip bir öğe üretecektir Örneğin, dosya adı Form1.fr fr.resx katıştırılmış bir kültür tanımlayıcısı "fr-fr", sahiptir, bu nedenle `Culture` eşit `fr-fr`. Görev dosya adları listesini dosya adı kaldırıldı kültür ile de üretir.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `AssignCulture` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AssignedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alınan öğeleri listesini içeren `Files` parametresi ile bir `Culture` meta veri girişi her öğesine eklendi.<br /><br /> Öğesinden gelen öğe varsa `Files` parametre zaten var. bir `Culture` meta veri girişi, özgün meta veri girişi kullanılır.<br /><br /> Görev, yalnızca atar bir `Culture` dosya adı geçerli bir kültür tanımlayıcısı içeriyorsa meta veri girişi. Bir kültür tanımlayıcısı son iki nokta filename arasında olmalıdır.|  
|`AssignedFilesWithCulture`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alt öğeleri kümesini içeren `AssignedFiles` sahip parametresi bir `Culture` meta veri girişi.|  
|`AssignedFilesWithNoCulture`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Alt öğeleri kümesini içeren `AssignedFiles` olmayan parametresi bir `Culture` meta veri girişi.|  
|`CultureNeutralAssignedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> İçinde üretilen öğeler aynı listesini içeren `AssignedFiles` parametresi, dosya adından kaldırıldı kültür olanlar dışında.<br /><br /> Geçerli bir kültür tanımlayıcısı ise görev kültürü yalnızca dosya adını kaldırır.|  
|`Files`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Katıştırılmış kültür adlarıyla bir kültür atamak için dosya listesini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek yürütür `AssignCulture` ile görev `ResourceFiles` öğe koleksiyonu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ResourceFiles Include="MyResource1.fr.resx"/>  
        <ResourceFiles Include="MyResource2.XX.resx"/>  
    </ItemGroup>  
  
    <Target Name="Culture">  
        <AssignCulture  
            Files="@(ResourceFiles)"  
            <Output TaskParameter="AssignedFiles"  
                ItemName="OutAssignedFiles"/>  
            <Output TaskParameter="AssignedFilesWithCulture"  
                ItemName="OutAssignedFilesWithCulture"/>  
            <Output TaskParameter="AssignedFilesWithNoCulture"  
                ItemName="OutAssignedFilesWithNoCulture"/>  
            <Output TaskParameter="CultureNeutralAssignedFiles"  
                ItemName="OutCultureNeutralAssignedFiles"/>  
        </AssignCulture>  
    </Target>  
</Project>  
```  
  
 Aşağıdaki tabloda, görev yürütme sonrasında çıktı öğelerin değerini açıklanmaktadır. Öğe meta verileri öğeden sonra parantez içinde gösterilir.  
  
|Öğe koleksiyonu|İçindekiler|  
|---------------------|--------------|  
|`OutAssignedFiles`|`MyResource1.fr.resx (Culture="fr")`<br /><br /> `MyResource2.XX.resx`(hiçbir ek meta veriler)|  
|`OutAssignedFilesWithCulture`|`MyResource1.fr.resx (Culture="fr")`|  
|`OutAssignedFilesWithNoCulture`|`MyResource2.XX.resx`(hiçbir ek meta veriler)|  
|`OutCultureNeutralAssignedFiles`|`MyResource1.resx (Culture="fr")`<br /><br /> `MyResource2.XX.resx (`ek meta veri yok)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)