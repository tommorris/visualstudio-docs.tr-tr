---
title: "FormatVersion görevi | Microsoft Docs"
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
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 468d5e60b2107118cdc2cf0e17b3e78b1133cc1c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="formatversion-task"></a>FormatVersion Görevi
Düzeltme numarası sürüm numarası ekler.  
  
-   Durum #1: Giriş: sürüm =\<tanımsız >;  Düzeltme =\<umursamaz >;   Çıkış: OutputVersion "1.0.0.0" =  
  
-   Case #2: Input: Version="1.0.0.*"  Revision="5"  Output: OutputVersion="1.0.0.5"  
  
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