---
title: "MSBuild görevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tasks
- MSBuild, tasks
ms.assetid: 5d3cc4a7-e5db-4f73-b707-8b6882fddcf8
caps.latest.revision: "18"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: fc2afbe7b0226cb5983aa3022ff4b24ac31fe7aa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-tasks"></a>MSBuild Görevleri
Yapı platformunu oluşturma işlemi sırasında herhangi bir sayıda eylemleri yürütmek için yeteneğinin de olması gerekir. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]kullanan *görevleri* bu eylemleri gerçekleştirmek için. Bir görev tarafından kullanılan yürütülebilir kod birimidir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] atomik yapı işlemleri gerçekleştirmek için.  
  
## <a name="task-logic"></a>Görev mantığı  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] XML proje dosyası biçimi dışındaki proje dosyasını kendi, bunu görev mantığı işlemleri uygulanan derleme tam olarak yürütülemiyor.  
  
 Görev Yürütme mantığını uygulayan bir .NET sınıfı olarak uygulanan <xref:Microsoft.Build.Framework.ITask> tanımlanan arabirimi <xref:Microsoft.Build.Framework> ad alanı.  
  
 Görev sınıfı giriş ve çıkış parametreleri göreve proje dosyasında da tanımlar. Görev sınıfı tarafından kullanıma sunulan tüm ortak ayarlanabilir statik olmayan Özet olmayan özelliklere proje dosyasında aynı ada sahip karşılık gelen bir öznitelik yerleştirerek tarafından erişilebilir [görev](../msbuild/task-element-msbuild.md) öğesi.  
  
 Uygulayan bir yönetilen sınıf yazarak kendi görev yazabilirsiniz <xref:Microsoft.Build.Framework.ITask> arabirimi. Daha fazla bilgi için bkz: [görev yazma](../msbuild/task-writing.md).  
  
## <a name="executing-a-task-from-a-project-file"></a>Bir proje dosyasından bir görevi yürütülüyor  
 Proje dosyasında bir görev yürütülmeden önce görev adına sahip görevi uygulayan derlemesinde türünü ilk eşlenmelidir [UsingTask](../msbuild/usingtask-element-msbuild.md) öğesi. Bu olanak tanır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyanızda bulduğunda, görev yürütme mantığı için nereye bakacağı.  
  
 Bir görevi çalıştırmak için bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası, bir öğenin alt öğesi olarak görev adı ile oluşturmak bir `Target` öğesi. Bir görev parametreleri kabul ederse, bu öğenin öznitelikleri geçirilir.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]öğe listeleri ve özellikleri parametre olarak kullanılabilir. Örneğin, aşağıdaki çağrıları kod `MakeDir` görev ve değerini ayarlar `Directories` özelliği `MakeDir` nesne değerine eşit `BuildDir` özellik önceki örnekte bildirilmiş.  
  
```xml  
<Target Name="MakeBuildDirectory">  
    <MakeDir  
        Directories="$(BuildDir)" />  
</Target>  
```  
  
 Görevler de bilgi öğeleri veya daha sonra kullanmak için özelliklerinde saklanan proje dosyasını geri dönebilirsiniz. Örneğin, aşağıdaki çağrıları kod `Copy` görev ve bilgileri depolar `CopiedFiles` çıkış özelliğinde `SuccessfullyCopiedFiles` öğe listesi.  
  
```xml  
<Target Name="CopyFiles">  
    <Copy  
        SourceFiles="@(MySourceFiles)"  
        DestinationFolder="@(MyDestFolder)">  
        <Output  
            TaskParameter="CopiedFiles"  
            ItemName="SuccessfullyCopiedFiles"/>  
     </Copy>  
</Target>  
```  
  
## <a name="included-tasks"></a>Dahil edilen görevleri  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]gibi birçok görevi ile birlikte gelen [kopya](../msbuild/copy-task.md), dosyaları kopyalar [MakeDir](../msbuild/makedir-task.md), dizinleri, oluşturur ve [Csc](../msbuild/csc-task.md), hangi derlerken [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] kaynak kodu dosyaları. Kullanılabilir görevler ve kullanım bilgilerini tam listesi için bkz: [görev başvurusu](../msbuild/msbuild-task-reference.md).  
  
## <a name="overridden-tasks"></a>Geçersiz kılınan görevleri  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]Görevler çeşitli konumlarda arar. İlk konum uzantısına sahip dosyalar kullanılıyor. .NET Framework dizinlerde depolanan OverrideTasks. Bu dosyalar görevlerinde aynı adlarıyla proje dosyasında görevleri dahil herhangi bir görevi geçersiz. İkinci konum uzantılı dosyalar içinde değil. .NET Framework dizinlerde görevler. Görev bu konumlardan birini bulunmazsa proje dosyasında görev kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild kavramları](../msbuild/msbuild-concepts.md)   
 [MSBuild](../msbuild/msbuild.md)   
 [Görev yazma](../msbuild/task-writing.md)   
 [Satır içi görevleri](../msbuild/msbuild-inline-tasks.md)