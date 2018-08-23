---
title: ResolveKeySource görevi | Microsoft Docs
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
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveKeySource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveKeySource task [MSBuild]
- MSBuild, ResolveKeySource task
ms.assetid: 449f06c2-e9aa-4236-ab1e-c45c25452b2e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a51b9b07be214a6713da4d9d6f9ccf99814b270f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689762"
---
# <a name="resolvekeysource-task"></a>ResolveKeySource Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ResolveKeySource görevi](https://docs.microsoft.com/visualstudio/msbuild/resolvekeysource-task).  
  
  
Tanımlayıcı ad anahtar kaynağını belirler.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Parametreleri aşağıdaki tabloda açıklanmıştır `ResolveKeySource` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AutoClosePasswordPromptShow`|İsteğe bağlı `Int32` parametresi.<br /><br /> Alır veya ileti sayımın görüntülemek için saniye cinsinden süreyi ayarlar.|  
|`AutoClosePasswordPromptTimeout`|İsteğe bağlı `Int32` parametresi.<br /><br /> Alır veya parola istemi iletişim kutusunu kapatmadan önce beklenecek saniye cinsinden süreyi ayarlar.|  
|`CertificateFile`|İsteğe bağlı `String` parametresi.<br /><br /> Alır veya sertifika dosyasının yolunu ayarlar.|  
|`CertificateThumbprint`|İsteğe bağlı `String` parametresi.<br /><br /> Alır veya sertifika parmak izini ayarlar.|  
|`KeyFile`|İsteğe bağlı `String` parametresi.<br /><br /> Alır veya ayarlar anahtar dosyasının yolu.|  
|`ResolvedKeyContainer`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Alır veya ayarlar çözümlenen anahtar kapsayıcısı.|  
|`ResolvedKeyFile`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Alır veya ayarlar çözümlenen anahtar dosyası.|  
|`ResolvedThumbprint`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Alır veya çözümlenen sertifika parmak izini ayarlar.|  
|`ShowImportDialogDespitePreviousFailures`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, önceki arızalarına Al iletişim kutusunu göster.|  
|`SuppressAutoClosePasswordPrompt`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Alır veya ayarlar parola istemi iletişim otomatik-kapatmaz olmadığını belirten bir Boole değeri.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



