---
title: Dokunma görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89116c56f3d3c24128b1b90d2130b98d04b071d0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682127"
---
# <a name="touch-task"></a>Dokunma Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Touch görevi](https://docs.microsoft.com/visualstudio/msbuild/touch-task).  
  
  
Dosya erişim ve değişiklik saatlerini ayarlar.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `Touch` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AlwaysCreate`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, zaten mevcut olan tüm dosyaları oluşturur.|  
|`Files`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Dokunmaya dosya koleksiyonunu belirtir.|  
|`ForceTouch`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, salt okunur dosyalar olsa bile dosya touch zorlar.|  
|`Time`|İsteğe bağlı `String` parametresi.<br /><br /> Geçerli saat dışında bir süreyi belirtir. Biçim için kabul edilebilir bir biçimde olmalıdır <xref:System.DateTime.Parse%2A> yöntemi.|  
|`TouchedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Başarıyla dokunulan öğeleri koleksiyonunu içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte `Touch` içinde belirtilen dosya erişim ve değişiklik saatlerini değiştirmek için görev `Files` öğe koleksiyonu ve başarıyla bilgiler dosyaların listesini koyar `FilesTouched` öğe koleksiyonu.  
  
```  
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
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



