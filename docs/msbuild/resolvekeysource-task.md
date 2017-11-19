---
title: "ResolveKeySource görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#ResolveKeySource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveKeySource task [MSBuild]
- MSBuild, ResolveKeySource task
ms.assetid: 449f06c2-e9aa-4236-ab1e-c45c25452b2e
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: cdbbdd476d37d19be63402b970beef84e9802fb5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="resolvekeysource-task"></a>ResolveKeySource Görevi
Güçlü ad anahtarı kaynağı belirler.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `ResolveKeySource` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AutoClosePasswordPromptShow`|İsteğe bağlı `Int32` parametresi.<br /><br /> Alır veya ileti sayımı görüntülemek için saniye cinsinden süreyi ayarlar.|  
|`AutoClosePasswordPromptTimeout`|İsteğe bağlı `Int32` parametresi.<br /><br /> Alır veya parola istemi iletişim kutusunu kapatmadan önce beklenecek saniye cinsinden süreyi ayarlar.|  
|`CertificateFile`|İsteğe bağlı `String` parametresi.<br /><br /> Alır veya sertifika dosyasının yolunu ayarlar.|  
|`CertificateThumbprint`|İsteğe bağlı `String` parametresi.<br /><br /> Alır veya sertifika parmak izini ayarlar.|  
|`KeyFile`|İsteğe bağlı `String` parametresi.<br /><br /> Alır veya anahtar dosyasının yolunu ayarlar.|  
|`ResolvedKeyContainer`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Alır veya ayarlar çözülmüş anahtar kapsayıcısı.|  
|`ResolvedKeyFile`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Alır veya çözümlenmiş anahtar dosyası ayarlar.|  
|`ResolvedThumbprint`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Alır veya çözümlenmiş sertifika parmak izini ayarlar.|  
|`ShowImportDialogDespitePreviousFailures`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, önceki arızalarına karşı alma iletişim kutusunu göster.|  
|`SuppressAutoClosePasswordPrompt`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Alır veya parola istemi iletişim kutusu otomatik-kapatmaz olup olmadığını belirten bir Boole değeri ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)