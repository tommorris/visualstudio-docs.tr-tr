---
title: CPPClean görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c833640958cefd2ac4f7e798ca3db09cc8819e8d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="cppclean-task"></a>CPPClean Görevi
Visual C++ proje yapılandırıldığında MSBuild oluşturduğu geçici dosyaları siler. Derleme dosyaları silme işlemi olarak bilinen *Temizleme*.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **CPPClean** görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**DeletedFiles**|İsteğe bağlı `ITaskItem[]` çıkış parametresi.<br /><br /> Tüketilen ve görevler tarafından gösterilen MSBuild çıktı dosyası öğeleri dizisi tanımlar.|  
|**DoDelete**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, temiz geçici dosyaları derleme.|  
|**FilePatternsToDeleteOnClean**|Gerekli `String` parametresi.<br /><br /> Temiz dosyaların dosya uzantıları noktalı virgülle ayrılmış listesini belirtir.|  
|**FilesExcludedFromClean**|İsteğe bağlı `String` parametresi.<br /><br /> Değil temizlemek için dosyaların noktalı virgülle ayrılmış bir listesini belirtir.|  
|**FoldersToClean**|Gerekli `String` parametresi.<br /><br /> Temizlemeye dizinleri noktalı virgülle ayrılmış listesini belirtir. Tam veya göreli bir yol belirtin ve yolun joker karakter sembolünü içerebilir (**\*\***).|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)