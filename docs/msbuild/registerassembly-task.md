---
title: "RegisterAssembly görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#RegisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, RegisterAssembly task
- RegisterAssembly task [MSBuild]
ms.assetid: ba5f19ac-6764-4d28-9b79-a86de58f8987
caps.latest.revision: "16"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2b540f2b38385bdd18b1d97e4dee3e361b1c8710
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="registerassembly-task"></a>RegisterAssembly Görevi
Belirtilen derlemedeki meta verileri okur ve gerekli girişleri oluşturmak COM istemcileri veren kayıt defterine ekler [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] saydam sınıfları. Bu görev davranışını benzer, ancak aynı, [Regasm.exe (derleme kayıt aracı)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `RegisterAssembly` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Assemblies`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Derlemeleri com ile kaydedilmesine izin belirtir|  
|`AssemblyListFile`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Arasında durumu hakkında bilgi içeren `RegisterAssembly` görev ve [UnregisterAssembly](../msbuild/unregisterassembly-task.md) görev. Bu engeller `UnregisterAssembly` kaydetmek için başarısız bir derleme kaydı çalışılıyor görevin `RegisterAssembly` görev.|  
|`CreateCodeBase`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, genel derleme önbelleğinde yüklü olmayan bir derlemenin dosya yolunu belirtir kayıt codebase girişi oluşturur. Sonrasında genel derleme önbelleğine kaydettiriyor olduğunuz derlemeyi yükleyecekseniz bu seçeneği belirtmemelisiniz.|  
|`TypeLibFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Belirtilen derlemeden oluşturmak için tür kitaplığı belirtir. Oluşturulan tür kitaplığı derlemede tanımlanan erişilebilir türlerinin tanımlarını içerir. Tür kitaplığı, aşağıdakilerden biri doğruysa yalnızca oluşturulur:<br /><br /> -Bir tür kitaplığı, adın bu konumda mevcut değil.<br />-Bir tür kitaplığı var, ancak geçirilen derleme daha eski.<br /><br /> Tür kitaplığı geçirilen derleme yeniyse, yeni bir tane oluşturulmaz, ancak derleme hala kayıtlı.<br /><br /> Bu parametre belirtilmezse, aynı sayıda öğe olmalıdır `Assemblies` parametresi ya da görev başarısız olur. Hiç giriş belirtilmişse, görev derlemenin adını varsayılan ve öğenin uzantısını .tlb için değiştirin.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `RegisterAssembly` görev tarafından belirtilen derlemesini kaydetme `MyAssemblies` öğe koleksiyonu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyAssemblies Include="MyAssembly.dll" />  
    <ItemGroup>  
  
    <Target Name="RegisterAssemblies">  
        <RegisterAssembly  
            Assemblies="@(MyAssemblies)" >  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)