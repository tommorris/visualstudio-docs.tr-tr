---
title: CPPClean görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e1ff85ffa4bdb7dd1dfb33fde37272606eb34a4
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151164"
---
# <a name="cppclean-task"></a>CPPClean Görevi
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)