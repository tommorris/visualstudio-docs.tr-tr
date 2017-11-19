---
title: "FormatVersion görevi | Microsoft Docs"
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
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: c74b737febc0fd91286abd4e4c43c5f84b9e6452
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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