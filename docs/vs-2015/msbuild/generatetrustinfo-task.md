---
title: Generatetrustınfo görevi | Microsoft Docs
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
- MSBuild, GenerateTrustInfo task
- GenerateTrustInfo task [MSBuild]
ms.assetid: 3ca60816-4bb0-4fef-ae43-ca0bfb63def3
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f755994c09e0634df814683b77d925f2293b6cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631178"
---
# <a name="generatetrustinfo-task"></a>GenerateTrustInfo Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Generatetrustınfo görevi](https://docs.microsoft.com/visualstudio/msbuild/generatetrustinfo-task).  
  
  
Uygulama güvenini taban bildirimini ve gelen oluşturur `TargetZone` ve `ExcludedPermissions` parametreleri.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `GenerateTrustInfo` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ApplicationDependencies`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Bağımlı derlemelerini belirtir.|  
|`BaseManifest`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Uygulama güveni oluşturmak için temel bildirimini belirtir.|  
|`ExcludedPermissions`|İsteğe bağlı `String` parametresi.<br /><br /> Bölge varsayılan izni kümeden hariç tutulacak bir veya daha fazla izni noktalı virgülle ayrılmış kimlik değerleri belirtir.|  
|`TargetZone`|İsteğe bağlı `String` parametresi.<br /><br /> Makine İlkesi'nden elde edilen bir bölgeye varsayılan izin kümesi belirtir.|  
|`TrustInfoFile`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> Uygulama güvenlik güven bilgilerini içeren dosyayı belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



