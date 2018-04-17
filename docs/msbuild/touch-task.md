---
title: Dokunma görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Touch
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Touch task
- Touch task [MSBuild]
ms.assetid: 8a978645-1393-4904-ae69-42afabd8c109
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d484340e4823dc73898f3ab0eaf8afffe1c1c18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="touch-task"></a>Dokunma Görevi
Dosya erişimi ve değişiklik zamanları ayarlar.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `Touch` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AlwaysCreate`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, henüz yoksa herhangi bir dosya oluşturur.|  
|`Files`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Touch dosya koleksiyonunu belirtir.|  
|`ForceTouch`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, salt okunur dosyalar olsa bile, dosya dokunma zorlar.|  
|`Time`|İsteğe bağlı `String` parametresi.<br /><br /> Geçerli saati dışında süreyi belirtir. Biçimi kabul edilebilir biçimde olmalıdır <xref:System.DateTime.Parse%2A> yöntemi.|  
|`TouchedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Başarıyla işlemdeki öğeleri koleksiyonu içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `Touch` belirtilen dosyaların erişim ve değişiklik saatlerini değiştirmek için görev `Files` öğe koleksiyonu ve başarıyla işlemdeki dosyaların listesini yerleştirir `FilesTouched` öğe koleksiyonu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
<ItemGroup>  
    <Files Include="File1.cs;File2.cs;File3.cs" />  
</ItemGroup>  
  
    <Target Name="TouchFiles">  
        <Touch  
            Files="@(Files)">  
            <Output  
                TaskParameter="TouchedFiles"  
                ItemName="FilesTouched"/>  
    </Touch>  
</Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)