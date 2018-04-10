---
title: WriteCodeFragment görevi | Microsoft Docs
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
- MSBuild, WriteCodeFragment task
- WriteCodeFragment task [MSBuild]
ms.assetid: 1d2514b4-5bef-43bb-bebe-496da8ef063c
caps.latest.revision: 5
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6d08d4499ba0fcdc044b7189abeb9de1716b7ba4
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="writecodefragment-task"></a>WriteCodeFragment Görevi
Bir geçici kod dosyası belirtilen oluşturulan kod parçasını oluşturur. Dosyayı silmez.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `WriteCodeFragment` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`AssemblyAttributes`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Yazmak için öznitelikler açıklaması. Öğe `Include` özniteliği, örneğin, "System.AssemblyVersionAttribute" tam tür adını bir değerdir.<br /><br /> Her meta verileri ad-değer çiftinin bir parametrenin türü olmalıdır `String`. Bazı öznitelikler yalnızca konumsal oluşturucu bağımsız değişkenleri izin verir. Ancak, herhangi bir öznitelik gibi değişkenler kullanabilirsiniz. Konumsal Oluşturucusu öznitelikleri ayarlamak için "_Parameter1", "_Parameter2" ve benzer meta verileri adları kullanın.<br /><br /> Bir parametre dizini atlanamaz.|  
|`Language`|Gerekli `String` parametresi.<br /><br /> Üreten kod dilini belirtir.<br /><br /> `Language` CodeDom sağlayıcısının kullanılabilir herhangi bir dil örneğin, "C#" veya "Visualbasic'tir" olabilir. Verilmiş dosya o dil için varsayılan dosya adı uzantısına sahip.|  
|`OutputDirectory`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Oluşturulan kod, genellikle Ara klasör için hedef klasör belirtir.|  
|`OutputFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> çıkış parametresi.<br /><br /> Oluşturulan dosyasının yolunu belirtir. Bu parametre bir dosya adı kullanarak ayarlandıysa, hedef klasör dosya adına eklenir. Bir kök kullanılarak ayarlandıysa, hedef klasöre göz ardı edilir.<br /><br /> Bu parametre ayarlanmamışsa, çıktı dosyası adını hedef klasör, rasgele dosya adını ve belirtilen dil için varsayılan dosya adı uzantısı ' dir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)