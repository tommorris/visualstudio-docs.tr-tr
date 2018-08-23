---
title: XmlPeek görevi | Microsoft Docs
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
helpviewer_keywords:
- XmlPeek task [MSBuild]
- MSBuild, XmlPeek task
ms.assetid: 19196031-a3bc-41b5-9c4a-f2572630e179
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f85283ec6e3d9f172bc081363403863a94be89c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688387"
---
# <a name="xmlpeek-task"></a>XmlPeek Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [XmlPeek görevi](https://docs.microsoft.com/visualstudio/msbuild/xmlpeek-task).  
  
  
Bir XML dosyasından XPath sorgusu tarafından belirtilen değerleri döndürür.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `XmlPeek` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Namespaces`|İsteğe bağlı `String` parametresi.<br /><br /> XPath sorgusu ön ekleri için ad alanlarını belirtir.|  
|`Query`|İsteğe bağlı `String` parametresi.<br /><br /> XPath sorgusu belirtir.|  
|`Result`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Bu görev tarafından döndürülen sonuçları içerir.|  
|`XmlContent`|İsteğe bağlı `String` parametresi.<br /><br /> XML Giriş bir dize olarak belirtir.|  
|`XmlInputPath`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> XML Giriş bir dosya yolu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



