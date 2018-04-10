---
title: Hata görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Error
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Error task [MSBuild]
- MSBuild, Error task
ms.assetid: e96a90ee-a8ae-4e5b-8ef2-b5cf5fedd8b2
caps.latest.revision: 20
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1452fc4ba26b9d6483bbdfe296f22cbb9a7f6cea
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="error-task"></a>Hata Görevi
Bir yapı durdurur ve değerlendirilen bir koşullu ifadesine dayalı olarak bir hatayı günlüğe kaydeder.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri ayarlayamadı tablo açıklar `Error` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Code`|İsteğe bağlı `String` parametresi.<br /><br /> Şu hata ile ilişkilendirilecek hata kodu.|  
|`File`|İsteğe bağlı `String` parametresi.<br /><br /> Hatayı içeren dosya adı. Hiçbir dosya adı sağlanmazsa, hata görevini içeren dosya kullanılır.|  
|`HelpKeyword`|İsteğe bağlı `String` parametresi.<br /><br /> Şu hata ile ilişkilendirmek için Yardım anahtar sözcük.|  
|`Text`|İsteğe bağlı `String` parametresi.<br /><br /> Hata metni, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] günlüğe `Condition` parametresi hesaplar için `true`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `Error` Görev verir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projeleri için günlükçüleri hata metni vermek ve yapı yürütme durdurun.  
  
 Varsa `Condition` parametresi hesaplar için `true`, yapı durdurulursa ve bir hata günlüğe kaydedilir. Varsa bir `Condition` parametresi yok, hata günlüğe kaydedilir ve yapı yürütme durdurur. Günlüğe kaydetme hakkında daha fazla bilgi için bkz: [yapı günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, tüm gerekli özellikleri ayarlayın doğrular. Bunlar ayarlanmamışsa, projenin hata olayını başlatır ve değerini günlüklerini `Text` parametresinin `Error` görev.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Error  
            Text=" The 0 property must be set on the command line."  
            Condition="'$(0)' == ''" />  
        <Error  
            Text="The FREEBUILD property must be set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Derleme günlüklerini alma](../msbuild/obtaining-build-logs-with-msbuild.md)