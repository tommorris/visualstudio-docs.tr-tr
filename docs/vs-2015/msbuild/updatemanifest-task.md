---
title: UpdateManifest görevi | Microsoft Docs
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
- MSBuild, UpdateManifest task
- UpdateManifest task [MSBuild]
ms.assetid: 1291fd33-b89e-4e15-8fb1-69f9625cf2d2
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 39bd26aacba67b8eb87fecdc46bc54f01e600dfe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695695"
---
# <a name="updatemanifest-task"></a>UpdateManifest Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [UpdateManifest görevi](https://docs.microsoft.com/visualstudio/msbuild/updatemanifest-task).  
  
  
Bir bildirimdeki seçili özelliklerini güncelleştirir ve Çekildi.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `UpdateManifest` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ApplicationManifest`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Uygulama bildirimini belirtir.|  
|`ApplicationPath`|Gerekli `String` parametresi.<br /><br /> Uygulama bildiriminin yolu belirtir.|  
|`InputManifest`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Güncelleştirilecek bildirimini belirtir.|  
|`OutputManifest`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> Güncelleştirilmiş özellikleri içeren bildirimini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametreleri devralan <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [görev temel sınıf](../msbuild/task-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



