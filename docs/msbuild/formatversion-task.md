---
title: FormatVersion görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c463f7e3bcd192a7ba217570d9fda051d8d23f9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="formatversion-task"></a>FormatVersion Görevi
Düzeltme numarası sürüm numarası ekler.  
  
-   Durum #1: Giriş: sürüm =\<tanımsız >;  Düzeltme =\<umursamaz >;   Çıkış: OutputVersion "1.0.0.0" =  
  
-   Durum #2: Giriş: sürüm "1.0.0.*" düzeltme = "5" çıktı =: OutputVersion "1.0.0.5" =  
  
-   Durum #3: Giriş: sürüm "1.0.0.0" = Düzeltme =\<umursamaz >;  Çıkış: OutputVersion "1.0.0.0" =  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `FormatVersion` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`FormatType`|İsteğe bağlı `String` parametresi.<br /><br /> Biçim türünü belirtir.<br /><br /> -"Sürüm" sürümü =.<br />-"Path"Değiştir ="." "_"; ile|  
|`OutputVersion`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Düzeltme numarası içeren çıktı sürümünü belirtir.|  
|`Revision`|İsteğe bağlı `Int32` parametresi.<br /><br /> Sürüme eklemek için düzeltmeyi belirtir.|  
|`Version`|İsteğe bağlı `String` parametresi.<br /><br /> Biçimlendirmek için sürüm numarası dizeyi belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)