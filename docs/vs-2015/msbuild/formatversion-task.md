---
title: FormatVersion görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 21154f63d6209683d2d6c2261d3a6ec8198ea252
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691188"
---
# <a name="formatversion-task"></a>FormatVersion Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [FormatVersion görevi](https://docs.microsoft.com/visualstudio/msbuild/formatversion-task).  
  
  
Düzeltme numarası için sürüm numarası ekler.  
  
-   #1. durum: Giriş: sürüm =\<tanımlanmamış >;  Gözden geçirme =\<umursamaz >;   Çıkış: OutputVersion "1.0.0.0" =  
  
-   #2. durum: Giriş: sürüm = "1.0.0.*" düzeltme "5" çıkış =: OutputVersion "1.0.0.5" =  
  
-   #3. durum: Giriş: sürüm = "1.0.0.0" Düzeltme =\<umursamaz >;  Çıkış: OutputVersion "1.0.0.0" =  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `FormatVersion` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`FormatType`|İsteğe bağlı `String` parametresi.<br /><br /> Biçim türünü belirtir.<br /><br /> -"Sürüm" = sürümü.<br />-"Path"= Değiştir"." ile "_";|  
|`OutputVersion`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Düzeltme numarası içeren çıkış sürümünü belirtir.|  
|`Revision`|İsteğe bağlı `Int32` parametresi.<br /><br /> Düzeltme sürümü eklenecek belirtir.|  
|`Version`|İsteğe bağlı `String` parametresi.<br /><br /> Sürüm numarası dizeyi biçimlendirmek için belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



