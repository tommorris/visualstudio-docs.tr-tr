---
title: XmlPoke görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3295a5aee03badc52b980183e88f484e0d4bcc3a
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106953"
---
# <a name="xmlpoke-task"></a>XmlPoke Görevi

Bir XML dosyasına bir XPath sorgusu tarafından belirtilen değerlerini ayarlar.

## <a name="parameters"></a>Parametreler

 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `XmlPoke` görev.
  
|Parametre|Açıklama|
|---------------|-----------------|
|`Namespaces`|İsteğe bağlı `String` parametresi.<br /><br /> XPath sorgusu önekler için ad belirtir.|
|`Query`|İsteğe bağlı `String` parametresi.<br /><br /> XPath sorgusu belirtir.|
|`Value`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Belirtilen yola eklenecek değeri belirtir.|
|`XmlInputPath`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> XML Giriş bir dosya yolu belirtir.|

## <a name="remarks"></a>Açıklamalar

 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Ayrıca Bkz.

 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)