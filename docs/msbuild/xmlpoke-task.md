---
title: XmlPoke görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
caps.latest.revision: 4
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3b189fbaa7cb03b8a20f67c0f57d19fa9c304c1b
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="xmlpoke-task"></a>XmlPoke Görevi
Bir XML dosyasına bir XPath sorgusu tarafından belirtilen değerlerini ayarlar.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `XmlPoke` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Namespaces`|İsteğe bağlı `String` parametresi.<br /><br /> XPath sorgusu önekler için ad belirtir.|  
|`Query`|İsteğe bağlı `String` parametresi.<br /><br /> XPath sorgusu belirtir.|  
|`Value`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Çıkış dosyasını belirtir.|  
|`XmlInputPath`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> XML Giriş bir dosya yolu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)