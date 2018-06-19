---
title: FormatVersion görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f5215f054f8da0e1118d4c7e66bc9c3c99d84c7b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31568221"
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