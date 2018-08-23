---
title: CPPClean görevi | Microsoft Docs
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
- vc.task.cppclean
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), CPPClean task
- CPPClean task (MSBuild (Visual C++))
ms.assetid: b62a482e-8fb5-4999-b50b-6605a078e291
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9437f72beef4f51568293543fcfaeeee2f65224c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690590"
---
# <a name="cppclean-task"></a>CPPClean Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CPPClean görevi](https://docs.microsoft.com/visualstudio/msbuild/cppclean-task).  
  
  
MSBuild Visual C++ proje derlenirken oluşturan geçici dosyaları siler. Derleme dosyaları silme işlemi olarak bilinir *Temizleme*.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır **CPPClean** görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**DeletedFiles**|İsteğe bağlı `ITaskItem[]` çıkış parametresi.<br /><br /> Tüketilen ve görevler tarafından yayılan MSBuild çıkış dosya öğeleri bir dizisi tanımlanmaktadır.|  
|**DoDelete**|İsteğe bağlı **Boole** parametresi.<br /><br /> Varsa `true`, temiz geçici dosyaları derleme.|  
|**FilePatternsToDeleteOnClean**|Gerekli `String` parametresi.<br /><br /> Noktalı virgülle ayrılmış bir temizlemeye dosyaların dosya uzantıları listesini belirtir.|  
|**FilesExcludedFromClean**|İsteğe bağlı `String` parametresi.<br /><br /> Dosyaları değil temizlemek için noktalı virgül ile ayrılmış bir listesini belirtir.|  
|**FoldersToClean**|Gerekli `String` parametresi.<br /><br /> Temizlemek için dizinlerin noktalı virgülle ayrılmış bir listesini belirtir. Tam veya göreli bir yol belirtin ve yolun joker karakter sembolünü içerebilir (**\*\***).|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



