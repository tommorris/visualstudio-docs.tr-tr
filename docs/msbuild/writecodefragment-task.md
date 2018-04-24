---
title: WriteCodeFragment görevi | Microsoft Docs
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
- MSBuild, WriteCodeFragment task
- WriteCodeFragment task [MSBuild]
ms.assetid: 1d2514b4-5bef-43bb-bebe-496da8ef063c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 559ce46bf7a6dfa99af9eb13b67ef29c5d5015be
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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