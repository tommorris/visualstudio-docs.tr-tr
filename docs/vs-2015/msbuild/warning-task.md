---
title: Uyarı görevi | Microsoft Docs
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
- http://schemas.microsoft.com/developer/msbuild/2003#Warning
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Warning task [MSBuild]
- MSBuild, Warning task
ms.assetid: 96ba5507-8b43-4f54-a1d7-9b15644dd56c
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93ac5f92f5912827a0ff73dcb21dd7ea8294b684
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632836"
---
# <a name="warning-task"></a>Uyarı Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [uyarı görevi](https://docs.microsoft.com/visualstudio/msbuild/warning-task).  
  
  
Günlükleri bir derleme sırasında bir uyarı değerlendirilen bir koşullu ifadeye göre.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `Warning` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Code`|İsteğe bağlı `String` parametresi.<br /><br /> Uyarıyla ilişkilendirilecek uyarı kodu.|  
|`File`|İsteğe bağlı `String` parametresi.<br /><br /> Varsa ilgili dosyayı belirtir. Uyarı görevi içeren dosyayı herhangi bir dosya sağlanırsa, kullanılır.|  
|`HelpKeyword`|İsteğe bağlı `String` parametresi.<br /><br /> Uyarıyla ilişkilendirilecek Yardım anahtar sözcüğü.|  
|`Text`|İsteğe bağlı `String` parametresi.<br /><br /> Uyarı metni, [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] günlüğe `Condition` parametresi değerlendirilen `true`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `Warning` Görev sağlayan [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] gerekli yapılandırma veya bir sonraki devam etmeden önce özellik varlığını denetlemek için projeleri derleme adımı.  
  
 Varsa `Condition` parametresinin `Warning` görev değerlendirilen `true`, değerini `Text` parametresi günlüğe kaydedilir ve yürütmek yapı devam eder. Varsa bir `Condition` parametre döndürrmek değil veya gerçekleştirmez, uyarı metni günlüğe kaydedilir. Günlüğe kaydetme hakkında daha fazla bilgi için bkz. [derleme günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, komut satırında ayarlanan özellikler denetler. Özellikleri ayarlanmadı varsa, projeye bir uyarı olayını başlatır ve değerini günlüklerini `Text` parametresinin `Warning` görev.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Warning  
            Text=" The 0 property was not set on the command line."  
            Condition="'$(0)' == ''" />  
        <Warning  
            Text=" The FREEBUILD property was not set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)



