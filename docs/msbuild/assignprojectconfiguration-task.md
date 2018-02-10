---
title: "AssignProjectConfiguration görevi | Microsoft Docs"
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
ms.assetid: 09633a0b-8f6f-4aba-8058-7cb4d13ce2c0
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7a4a803647afac9de77096e4a16d41987ff70c4f
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="assignprojectconfiguration-task"></a>AssignProjectConfiguration Görevi
Bu görev listesi yapılandırma dize kabul eder ve bunları belirtilen projelerine atar.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `AssignProjectConfiguration` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`SolutionConfigurationContents`|İsteğe bağlı `string` çıkış parametresi.<br /><br /> Her proje için bir proje yapılandırma içeren bir XML dizesini içerir. Yapılandırmaları adlandırılmış projelerine atanır.|  
|`DefaultToVcxPlatformMapping`|İsteğe bağlı `string` çıkış parametresi.<br /><br /> Kullanılan platform adlarından eşlemeleri noktalı virgülle ayrılmış bir listesini içerir<br /><br /> Bu .vcxproj dosyalar tarafından kullanılan çoğu türlerine göre.<br /><br /> Örneğin:<br /><br /> `"AnyCPU=Win32;X86=Win32;X64=X64"`|  
|`VcxToDefaultPlatformMapping`|İsteğe Bağlı<br /><br /> `string`çıkış parametresi.<br /><br /> Çoğu türleri platform adları kullanarak .vcxproj platform adlarından eşlemelere noktalı virgülle ayrılmış bir listesini içerir.<br /><br /> Örneğin:<br /><br /> `"Win32=AnyCPU;X64=X64"`|  
|`CurrentProjectConfiguration`|İsteğe bağlı `string` çıkış parametresi.<br /><br /> Geçerli proje için yapılandırmayı içerir.|  
|`CurrentProjectPlatform`|İsteğe bağlı `string` çıkış parametresi.<br /><br /> Geçerli projenin platform içerir.|  
|`OnlyReferenceAndBuildProjectsEnabledInSolutionConfiguration`|İsteğe bağlı `bool` çıkış parametresi.<br /><br /> Proje yapılandırmada devre dışı olsa bile başvuruları oluşturulmuş olduğunu belirten bir bayrak içeriyor.|  
|`ShouldUnsetParentConfigurationAndPlatform`|İsteğe bağlı `bool` çıkış parametresi.<br /><br /> Üst yapılandırma ve platform unset olup olmayacağını belirten bir bayrak içeriyor.|  
|`OutputType`|İsteğe bağlı `string` çıkış parametresi.<br /><br /> Proje için çıktı türünü içerir.|  
|`ResolveConfigurationPlatformUsingMappings`|İsteğe bağlı `bool` çıkış parametresi.<br /><br /> Yapı varsayılan eşlemeleri yapılandırması ve platformu geçirilen çözümlemek için kullanmanızın gerekli olup olmadığını belirten bir bayrak içeriyor proje başvuruları içinde.|  
|`AssignedProjects`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Çözümlenen başvuru yollarını listesini içerir.|  
|`UnassignedProjects`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Çıkış önceden çözümlenmiş listesini kullanarak çözümlenemedi proje başvurusu öğeleri listesini içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)