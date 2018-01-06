---
title: "Findınlist görevi | Microsoft Docs"
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
helpviewer_keywords:
- FindInList task [MSBuild]
- MSBuild, FindInList task
ms.assetid: d49b9f84-52a2-4242-9269-b741a7a7e9f7
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8f64a5949dbb4440ccb940cdd5e0315c4f23d58b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="findinlist-task"></a>FindInList Görevi
Belirtilen bir listede eşleşen itemspec sahip öğeyi bulur.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır [Findınlist görevi](../msbuild/findinlist-task.md).  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`CaseSensitive`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`arama büyük küçük harfe duyarlı; Aksi takdirde, bu değildir. Varsayılan değer `true`.|  
|`FindLastMatch`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, en son eşleşmeyi döndürür; Aksi halde, ilk eşleşmeyi döndürür. Varsayılan değer `false`.|  
|`ItemFound`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` salt okunur çıktı parametresi.<br /><br /> İlk eşleşen öğe listede varsa bulunamadı.|  
|`ItemSpecToFind`|Gerekli `String` parametresi.<br /><br /> Aranacak itemspec.|  
|`List`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Listede itemspec için aranacak.|  
|`MatchFileNameOnly`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, yalnızca dosya adı kısmını itemspec karşı eşleşen; Aksi halde, tüm itemspec karşı eşleşmesi. Varsayılan değer `true`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)