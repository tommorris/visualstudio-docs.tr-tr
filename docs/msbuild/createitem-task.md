---
title: "CreateItem görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#CreateItem
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateItem task [MSBuild]
- MSBuild, CreateItem task
ms.assetid: c4311f38-979e-4324-b524-9e8c1cbdc41a
caps.latest.revision: "15"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6e9088f73310da32875636b33a5a843d277c1e8c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="createitem-task"></a>CreateItem Görevi
Öğe koleksiyonlarını giriş öğeleri ile doldurur. Bu öğeleri bir listeden diğerine kopyalanmasına izin verir.  
  
> [!NOTE]
>  Bu görev kullanım dışıdır. .NET Framework 3.5 ile öğesi grupları başlatılıyor yerleştirilebilir içinde [hedef](../msbuild/target-element-msbuild.md) öğeleri. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  
  
## <a name="attributes"></a>Öznitelikler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `CreateItem` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AdditionalMetadata`|İsteğe bağlı `String` dizi parametresi.<br /><br /> Çıktı öğeleri eklemek için ek meta veri belirtir.  Meta veri ad ve değer öğesi için aşağıdaki sözdizimi ile belirtin:<br /><br /> *MetadataName* `=` *MetadataValue*<br /><br /> Birden fazla meta veri ad/değer çifti noktalı virgülle ayrılmış olması gerekir. Ad veya değer noktalı virgül veya diğer özel karakterler içeriyorsa, bunlar kaçış uygulanmalıdır. Daha fazla bilgi için bkz: [nasıl yapılır: MSBuild kaçış özel karakterleri](../msbuild/how-to-escape-special-characters-in-msbuild.md).|  
|`Exclude`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Çıktı öğeyi koleksiyondan hariç tutmak için öğelerini belirtir. Bu parametre, joker karakter belirtimleri içerebilir. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md) ve [nasıl yapılır: dosyaları derlemeden Dışla](../msbuild/how-to-exclude-files-from-the-build.md).|  
|`Include`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> `[]`parametresi.<br /><br /> Çıktı öğesi koleksiyonda eklemek istediğiniz öğeleri belirtir. Bu parametre, joker karakter belirtimleri içerebilir.|  
|`PreserveExistingMetadata`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `True`, zaten mevcut değilse yalnızca ek meta veri geçerlidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde adlı yeni bir öğe koleksiyonu oluşturur `MySourceItemsWithMetadata` öğeyi koleksiyondan `MySourceItems`. `CreateItem` Görev doldurur maddeleri yeni öğe koleksiyonu `MySourceItems` öğesi. Ardından adlı bir ek meta veri girişi ekler `MyMetadata` değerini `Hello` yeni koleksiyondaki her öğe için.  
  
 Görev yürütüldükten sonra `MySourceItemsWithMetadata` öğe koleksiyonu içeren öğeleri `file1.resx` ve `file2.resx`, ikisi için meta veri girişleri ile `MyMetadata`. `MySourceItems` Öğe koleksiyonu değişmez.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MySourceItems Include="file1.resx;file2.resx" />  
    </ItemGroup>  
  
    <Target Name="NewItems">  
        <CreateItem  
            Include="@(MySourceItems)"  
            AdditionalMetadata="MyMetadata=Hello">  
           <Output  
               TaskParameter="Include"  
               ItemName="MySourceItemsWithMetadata"/>  
        </CreateItem>  
  
    </Target>  
  
</Project>  
```  
  
 Aşağıdaki tabloda, görev yürütme sonrasında çıktı öğesinin değeri açıklanmaktadır. Öğe meta verileri öğeden sonra parantez içinde gösterilir.  
  
|Öğe koleksiyonu|İçindekiler|  
|---------------------|--------------|  
|`MySourceItemsWithMetadata`|`file1.resx` (`MyMetadata="Hello"`)<br /><br /> `file2.resx` (`MyMetadata="Hello"`)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)