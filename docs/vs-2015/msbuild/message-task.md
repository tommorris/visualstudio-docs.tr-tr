---
title: İleti görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Message
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Message task
- Message task [MSBuild]
ms.assetid: 2293309d-42b6-46dc-9684-8c146f66bc28
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7993fe70c52cfd0694bd50d873425eda82c0a7c6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633875"
---
# <a name="message-task"></a>İleti Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ileti görevini](https://docs.microsoft.com/visualstudio/msbuild/message-task).  
  
  
Derleme sırasında bir ileti kaydeder.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `Message` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Importance`|İsteğe bağlı `String` parametresi.<br /><br /> İletinin önemini belirtir. Bu parametre değerini alabilir `high`, `normal` veya `low`. Varsayılan değer `normal` şeklindedir.|  
|`Text`|İsteğe bağlı `String` parametresi.<br /><br /> Oturum hata metni.|  
  
## <a name="remarks"></a>Açıklamalar  
 `Message` Görev sağlayan [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] projeleri günlükçüleri farklı derleme işlemindeki adımları sırasında sorun iletileri.  
  
 Varsa `Condition` parametresi değerlendirilen `true`, değerini `Text` parametresi kaydedilir ve yapı yürütülmeye devam eder. Varsa bir `Condition` parametresi mevcut değil, ileti metnini günlüğe kaydedilir. Günlüğe kaydetme hakkında daha fazla bilgi için bkz. [derleme günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Varsayılan olarak MSBuild konsol Oluşturucusu'na ileti gönderilir. Bu ayarı değiştirilebilir <xref:Microsoft.Build.Tasks.TaskExtension.Log%2A> parametresi. Günlükçü yorumlar `Importance` parametresi.  
  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, tüm kayıtlı günlükçüler için iletileri günlüğe kaydeder.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="DisplayMessages">  
        <Message Text="Project File Name = $(MSBuildProjectFile)" />  
        <Message Text="Project Extension = $(MSBuildProjectExtension)" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Derleme günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md)



