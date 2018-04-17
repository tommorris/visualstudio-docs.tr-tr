---
title: Görev yazma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, writing tasks
- tasks, creating for MSBuild
- MSBuild, creating tasks
ms.assetid: 3ebc5f87-8f00-46fc-82a1-228f35a6823b
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 837adb53301d7fe870d50c9ee40f4b1391d3bb46
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="task-writing"></a>Görev Yazma
Görevler oluşturma işlemi sırasında çalışan bir kod sağlar. Görevler hedeflerini yer alır. Tipik görev kitaplığı ile birlikte gelir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], ve kendi görevler de oluşturabilirsiniz. Dahil edilen görevlerin Kitaplığı hakkında daha fazla bilgi için [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], bkz: [görev başvurusu](../msbuild/msbuild-task-reference.md).  
  
## <a name="tasks"></a>Görevler  
 Görevler örneklerindendir [kopya](../msbuild/copy-task.md), bir veya daha fazla kopyalar [MakeDir](../msbuild/makedir-task.md), bir dizin oluşturur ve [Csc](../msbuild/csc-task.md), hangi derlerken [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] kaynak kodu dosyaları. Her görev uygulayan bir .NET sınıfı olarak uygulanan <xref:Microsoft.Build.Framework.ITask> Microsoft.Build.Framework.dll derlemede tanımlanan arabirimi.  
  
 Bir görev uygularken kullanabileceğiniz iki yaklaşım vardır:  
  
-   Uygulama <xref:Microsoft.Build.Framework.ITask> doğrudan arabirim.  
  
-   Sınıfınızda yardımcı sınıfından türetilen <xref:Microsoft.Build.Utilities.Task>, Microsoft.Build.Utilities.dll derlemede tanımlanmış. Görev ITask uygular ve bazı ITask üyeleri varsayılan uygulamalarını sağlar. Ayrıca, günlük kaydı daha kolay olur.  
  
 Her iki durumda da adlı bir yöntem sınıfınıza eklemelisiniz `Execute`, görev çalıştığında çağrılan yöntemi. Bu yöntem parametre almayan ve döndüren bir `Boolean` değeri: `true` görev başarılı olursa ya da `false` başarısız olursa. Aşağıdaki örnek, hiçbir eylem gerçekleştirmeyen ve döndüren bir görev gösterir `true`.  
  
```csharp
using System;  
using Microsoft.Build.Framework;  
using Microsoft.Build.Utilities;  
  
namespace MyTasks  
{  
    public class SimpleTask : Task  
    {  
        public override bool Execute()  
        {  
            return true;  
        }  
    }  
}  
```  
  
 Bu görev aşağıdaki proje dosyasını çalıştırır:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="MyTarget">  
        <SimpleTask />  
    </Target>  
</Project>  
```  
  
 Görevler çalıştırdığınızda Görev sınıfını .NET özellikleri oluşturursanız, bunlar ayrıca girişleri Proje dosyasından alabilirsiniz. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Görevin hemen çağırmadan önce bu özellikleri ayarlar `Execute` yöntemi. Bir dize özelliği oluşturmak için görev kodu gibi kullanın:  
  
```csharp
using System;  
using Microsoft.Build.Framework;  
using Microsoft.Build.Utilities;  
  
namespace MyTasks  
{  
    public class SimpleTask : Task  
    {  
        public override bool Execute()  
        {  
            return true;  
         }  
  
        private string myProperty;  
        public string MyProperty  
        {  
            get { return myProperty; }  
            set { myProperty = value; }  
        }  
    }  
}  
```  
  
 Bu görev ve ayarlar aşağıdaki dosya çalıştırır proje `MyProperty` verilen değer için:  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <SimpleTask MyProperty="Value for MyProperty" />  
   </Target>  
</Project>  
```  
  
## <a name="registering-tasks"></a>Görevler kaydetme  
 Bir görevi çalıştırmak için bir proje edecekse [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görevi sınıfı içeren bütünleştirilmiş kodun bulma bilmeniz gerekir. Görevleri kullanarak kayıtlı [UsingTask öğesi (MSBuild)](../msbuild/usingtask-element-msbuild.md).  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Microsoft.Common.Tasks dosyasıdır listesini içeren bir proje dosyası `UsingTask` ile birlikte tüm görevler kaydetmek öğeleri [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Bu dosyayı her proje oluşturulurken otomatik olarak eklenir. Microsoft.Common.Tasks içinde kayıtlı bir görev geçerli proje dosyasında kayıtlı ise, geçerli proje dosyası öncelik kazanır; diğer bir deyişle, aynı ada sahip kendi görev varsayılan görevle geçersiz kılabilirsiniz.  
  
> [!TIP]
>  İle sağlanan görevlerinin listesini görebilirsiniz [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Microsoft.Common.Tasks içeriğini görüntüleyerek.  
  
## <a name="raising-events-from-a-task"></a>Bir görevin olaylar oluşturma  
 Görevinizi türetilen varsa <xref:Microsoft.Build.Utilities.Task> yardımcı sınıfı, kullanabileceğiniz aşağıdaki yardımcı yöntemlerinden birini üzerinde <xref:Microsoft.Build.Utilities.Task> sınıfı, yakalanan ve tüm kayıtlı günlükçüleri tarafından görüntülenen olayları yükseltmek için:  
  
```csharp
public override bool Execute()  
{  
    Log.LogError("messageResource1", "1", "2", "3");  
    Log.LogWarning("messageResource2");  
    Log.LogMessage(MessageImportance.High, "messageResource3");  
    ...  
}  
```  
  
 Görevinizi uyguluyorsa <xref:Microsoft.Build.Framework.ITask> doğrudan bu gibi olaylar hala yükseltebilirsiniz ancak IBuildEngine arabirimini kullanmanız gerekir. Aşağıdaki örnek, ITask uygulayan ve özel bir olayını Görev gösterir:  
  
```csharp
public class SimpleTask : ITask  
{  
    private IBuildEngine buildEngine;  
    public IBuildEngine BuildEngine  
    {  
        get{ return buildEngine; }  
        set{ buildEngine = value; }  
    }  
  
    public override bool Execute()  
    {  
        TaskEventArgs taskEvent =  
            new TaskEventArgs(BuildEventCategory.Custom,  
            BuildEventImportance.High, "Important Message",  
           "SimpleTask");  
        BuildEngine.LogBuildEvent(taskEvent);  
        return true;  
    }  
}  
```  
  
## <a name="requiring-task-parameters-to-be-set"></a>Görev için ayarlanacak parametreleri gerektirme  
 Böylece görev çalıştıran herhangi bir proje dosyasını bu özelliklerin değerlerini ayarlamanız gerekir veya derleme başarısız oluyor, belirli görev özellikleri "gerekli" olarak işaretleyebilirsiniz. Uygulama `[Required]` göreviniz .NET özelliğini aşağıdaki gibi özniteliğini:  
  
```csharp
private string requiredProperty;  
  
[Required]  
public string RequiredProperty  
{  
    get { return requiredProperty; }  
    set { requiredProperty = value; }  
}  
```  
  
 `[Required]` Özniteliği tarafından tanımlanan <xref:Microsoft.Build.Framework.RequiredAttribute> içinde <xref:Microsoft.Build.Framework> ad alanı.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu aşağıdaki [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] sınıfını gösterir türetme görev <xref:Microsoft.Build.Utilities.Task> yardımcı sınıfı. Bu görevi döndürür `true`, başarılı olduğunu gösteren.  
  
### <a name="code"></a>Kod  
  
```csharp
using System;  
using Microsoft.Build.Utilities;  
  
namespace SimpleTask1  
{  
    public class SimpleTask1: Task  
    {  
        public override bool Execute()  
        {  
            // This is where the task would presumably do its work.  
            return true;  
        }  
    }  
}  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu aşağıdaki [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] sınıfını gösterir uygulama görev <xref:Microsoft.Build.Framework.ITask> arabirimi. Bu görevi döndürür `true`, başarılı olduğunu gösteren.  
  
### <a name="code"></a>Kod  
  
```csharp
using System;  
using Microsoft.Build.Framework;  
  
namespace SimpleTask2  
{  
    public class SimpleTask2: ITask  
    {  
        //When implementing the ITask interface, it is necessary to  
        //implement a BuildEngine property of type  
        //Microsoft.Build.Framework.IBuildEngine. This is done for  
        //you if you derive from the Task class.  
        private IBuildEngine buildEngine;  
        public IBuildEngine BuildEngine  
        {  
            get  
            {  
                return buildEngine;  
            }  
            set  
            {  
                buildEngine = value;  
            }  
         }  
  
        // When implementing the ITask interface, it is necessary to  
        // implement a HostObject property of type Object.  
        // This is done for you if you derive from the Task class.  
        private Object hostObject;  
        public Object HostObject  
        {  
            get  
            {  
                return hostObject;  
            }  
  
            set  
            {  
                hostObject = value;  
            }  
        }  
  
        public bool Execute()  
        {  
            // This is where the task would presumably do its work.  
            return true;  
        }  
    }  
}  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] sınıfını gösterir türeyen bir görev <xref:Microsoft.Build.Utilities.Task> yardımcı sınıfı. Gerekli string özelliğine sahiptir ve tüm kayıtlı günlükçüleri tarafından görüntülenen bir olay başlatır.  
  
### <a name="code"></a>Kod  
 [!code-csharp[msbuild_SimpleTask3#1](../msbuild/codesnippet/CSharp/task-writing_1.cs)]  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, önceki örnek görev SimpleTask3 çağrılırken bir proje dosyası gösterir.  
  
### <a name="code"></a>Kod  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <UsingTask TaskName="SimpleTask3.SimpleTask3"   
        AssemblyFile="SimpleTask3\bin\debug\simpletask3.dll"/>  
  
    <Target Name="MyTarget">  
        <SimpleTask3 MyProperty="Hello!"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)