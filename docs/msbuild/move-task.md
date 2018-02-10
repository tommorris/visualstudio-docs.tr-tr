---
title: "Taşıma görevi | Microsoft Docs"
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
- MSBuild, Move task
- Move task [MSBuild]
ms.assetid: d1405347-1309-4f18-b565-905408093d59
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f4f0803767083a0a7302efe4c49c8524f4f2dd00
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="move-task"></a>Taşıma Görevi
Dosyayı yeni bir konuma taşır.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri ayarlayamadı tablo açıklar `Move` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`DestinationFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Kaynak dosyaların taşınacağı dosyaların listesini belirtir. Bu liste belirtilen listesine bire bir eşleme olması bekleniyor `SourceFiles` parametresi. Diğer bir deyişle, belirtilen ilk dosya `SourceFiles` belirtilen ilk konumuna taşınır `DestinationFiles`, vb.|  
|`DestinationFolder`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Dosyaları taşımak istediğiniz dizini belirtir.|  
|`MovedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Başarıyla taşındı öğeleri içerir.|  
|`OverwriteReadOnlyFiles`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, salt okunur dosyalar işaretlenmiş olsa bile dosyaların üzerine yazar.|  
|`SourceFiles`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Dosyaların belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Her iki `DestinationFolder` parametresi veya `DestinationFiles` parametresi belirtilen, ancak her ikisi de olmalıdır. Eğer her ikisi de belirtilirse görev başarısız olur ve bir hata günlüğe kaydedilir.  

 `Move` Görev istenen hedef dosyaları için gerekli olarak klasörler oluşturur.

 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)
