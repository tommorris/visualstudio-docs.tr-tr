---
title: XslTransformation görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
caps.latest.revision: 4
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4eb192777b85adbfc270c7cbdb4469548333c5ec
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="xsltransformation-task"></a>XslTransformation Görevi
Bir XML dönüşümler XSLT kullanarak giriş veya XSLT ve bir çıkış aygıtı veya bir dosyaya çıkışları derlenmiş.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `XslTransformation` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`OutputPaths`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> XML dönüşümü için çıktı dosyaları belirtir.|  
|`Parameters`|İsteğe bağlı `String` parametresi.<br /><br /> XSLT giriş belge için parametreleri belirtir.|  
|`XmlContent`|İsteğe bağlı `String` parametresi.<br /><br /> XML girişi bir dize olarak belirtir.|  
|`XmlInputPaths`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> XML girdi dosyaları belirtir.|  
|`XslCompiledDllPath`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Derlenmiş XSLT belirtir.|  
|`XslContent`|İsteğe bağlı `String` parametresi.<br /><br /> XSLT girişi bir dize olarak belirtir.|  
|`XslInputPath`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> XSLT giriş dosyasını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)