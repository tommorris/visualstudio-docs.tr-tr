---
title: "Uyarı görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ca4e9906d31468b028f1ad9a39c196bd54e3fb9e
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="warning-task"></a>Uyarı Görevi
Günlükleri bir uyarı derleme sırasında değerlendirilen bir koşullu ifadesine dayalı olarak.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri ayarlayamadı tablo açıklar `Warning` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Code`|İsteğe bağlı `String` parametresi.<br /><br /> Uyarı ile ilişkilendirmek için uyarı kodu.|  
|`File`|İsteğe bağlı `String` parametresi.<br /><br /> İlgili dosya varsa belirtir. Hiçbir dosya sağlanırsa, dosyanın uyarısı görevini içeren kullanılır.|  
|`HelpKeyword`|İsteğe bağlı `String` parametresi.<br /><br /> Uyarı ile ilişkilendirmek için Yardım anahtar sözcük.|  
|`Text`|İsteğe bağlı `String` parametresi.<br /><br /> Uyarı metni, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] günlüğe `Condition` parametresi hesaplar için `true`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `Warning` Görev verir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] gerekli yapılandırmaya veya sonraki işlemine devam etmeden önce özelliği varlığını denetlemek için projeleri derleme adımı.  
  
 Varsa `Condition` parametresinin `Warning` görev değerlendirir `true`, değeri `Text` parametresi bir günlüğe kaydedilir ve yapı yürütmeye devam eder. Varsa bir `Condition` parametresi döndürrmek değil veya yok, uyarı metni günlüğe kaydedilir. Günlüğe kaydetme hakkında daha fazla bilgi için bkz: [yapı günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde komut satırında ayarlanan özelliklerini denetler. Özellikleri ayarlanmadı varsa, proje uyarı olayını başlatır ve değerini günlüklerini `Text` parametresinin `Warning` görev.  
  
```xml  
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
 [Derleme günlüklerini alma](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)