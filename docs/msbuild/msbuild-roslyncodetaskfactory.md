---
title: MSBuild satır içi görevleri ile RoslynCodeTaskFactory | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2017
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, tasks
ms.assetid: e72e6506-4a11-4edf-ae8d-cfb5a3b9d8a0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b12d0ae775d37a436898bb34acca0c7f4a50e649
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37059365"
---
# <a name="msbuild-inline-tasks-with-roslyncodetaskfactory"></a>RoslynCodeTaskFactory ile MSBuild satır içi görevleri
Benzer şekilde [CodeTaskFactory](../msbuild/msbuild-inline-tasks.md), RoslynCodeTaskFactory satır içi görevleri olarak kullanmak için bellek içi görev derlemeleri oluşturma için platformlar arası Roslyn derleyicileri kullanır.  RolynCodeTaskFactory görevler .NET standart hedef ve .NET Framework ve .NET çekirdeği çalışma zamanları ve bunun yanı sıra Linux ve Mac OS gibi diğer platformlarda çalışabilir.

**Not:** `RolynCodeTaskFactory` MSBuild 15,8 ve yalnızca yukarıda kullanılabilir.
  
## <a name="the-structure-of-an-inline-task-with-roslyncodetaskfactory"></a>Satır içi göre RoslynCodeTaskFactory ile yapısı
 Aynı şekilde içinde bildirilen RoslynCodeTaskFactory satır içi görevleri [CodeTaskFactory](../msbuild/msbuild-inline-tasks.md). .NET standart hedefi olan tek fark.  Satır içi görev ve `UsingTask` içerdiği öğesi genellikle bir .targets dosyasında bulunur ve gerektiği gibi diğer proje dosyalarını içeri aktarılan. Temel satır içi görev aşağıdadır. Hiçbir şey yapmaz dikkat edin.  
  
```xml  
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- This simple inline task does nothing. -->  
  <UsingTask  
    TaskName="DoNothing"  
    TaskFactory="RoslynCodeTaskFactory"  
    AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.Core.dll" >  
    <ParameterGroup />  
    <Task>  
      <Reference Include="" />  
      <Using Namespace="" />  
      <Code Type="Fragment" Language="cs">  
      </Code>  
    </Task>  
  </UsingTask>  
</Project>  
```  
  
 `UsingTask` Örnek öğesinde görev ve derlendiğinden satır içi görev Fabrika açıklamak üç özniteliklere sahip.  
  
-   `TaskName` Öznitelik adları görev bu durumda, `DoNothing`.  
  
-   `TaskFactory` Öznitelik adları satır içi görev Fabrika uygulayan sınıf.  
  
-   `AssemblyFile` Özniteliği satır içi görev Fabrika konumunu sağlar. Alternatif olarak, kullanabileceğiniz `AssemblyName` özniteliği genel derleme önbelleğinde (GAC) genellikle bulunan satır içi görev Üreteç sınıfını tam adını belirtin.  
  
 Kalan öğeleri `DoNothing` görev boş ve satır içi göre yapısını ve sırası göstermek için sağlanmıştır. Bu konunun ilerleyen bölümlerinde daha sağlam bir örnek sunulur.  
  
-   `ParameterGroup` Öğesidir isteğe bağlıdır. Belirtilen görev parametrelerini bildirir. Giriş ve çıkış parametreleri hakkında daha fazla bilgi için "Giriş ve çıkış parametreleri" bölümüne bakın.  
  
-   `Task` Öğesi açıklar ve görev kaynak kodunu içerir.  
  
-   `Reference` Öğesi kodunuzda kullanarak .NET derlemelerini başvurular belirtir. Bu, Visual Studio'da bir projesine bir başvuru ekleme ile eşdeğerdir. `Include` Özniteliği başvurulan derlemeyi yolunu belirtir.  
  
-   `Using` Öğesi erişmek istediğiniz ad alanları listeler. Bu benzer `Using` deyimi Visual C#. `Namespace` Özniteliği eklemek için ad alanını belirtir.  
  
 `Reference` ve `Using` dilden bağımsız öğeleridir. Satır içi görevleri desteklenen .NET CodeDom diller, örneğin, Visual Basic veya Visual C# herhangi birinde yazılabilir.  
  
> [!NOTE]
>  Tarafından bulunan öğeleri `Task` öğesi görev üreteci için bu durumda, kod görev Fabrika özeldir.  
  
### <a name="code-element"></a>Code Öğesi  
 İçinde görünmesi son alt öğesi `Task` öğesi `Code` öğesi. `Code` Öğesi içeriyor veya bir görev derlenecek istediğiniz kodunu bulur. Ne içine `Code` öğesi bağlıdır nasıl görev yazmak istediğiniz üzerinde.  
  
 `Language` Özniteliği kodunuzu yazılır dili belirtir. Kabul edilebilir değerler `cs` için C# ' ta, `vb` Visual Basic.  
  
 `Type` Özniteliği içinde bulunan kod türünü belirten `Code` öğesi.  
  
-   Varsa değerini `Type` olan `Class`, sonra `Code` ögesinin türeyen bir sınıf için kod <xref:Microsoft.Build.Framework.ITask> arabirimi.  
  
-   Varsa değerini `Type` olan `Method`, geçersiz kılma kod tanımlar sonra `Execute` yöntemi <xref:Microsoft.Build.Framework.ITask> arabirimi.  
  
-   Varsa değerini `Type` olan `Fragment`, kod içeriğini tanımlar sonra `Execute` yöntemi, ancak imza veya `return` deyimi.  
  
 Kod arasında genellikle görünür bir `<![CDATA[` işaret ve `]]>` işaretçisi. Kod bir CDATA bölümü olduğundan, ayrılmış karakterleri kaçış hakkında endişelenmeniz gerekmez "\<" veya ">".  
  
 Alternatif olarak, kullanabileceğiniz `Source` özniteliği `Code` öğesi göreviniz kodunu içeren bir dosya konumunu belirtin. Kaynak dosya kodda tarafından belirtilen türde olması gerekir `Type` özniteliği. Varsa `Source` öznitelik varsa varsayılan değer olan `Type` olan `Class`. Varsa `Source` olduğundan, varsayılan değer yoksa `Fragment`.  
  
> [!NOTE]
>  Kaynak dosyasında görev sınıfı tanımlarken, sınıf adı ile kabul etmelisiniz `TaskName` ilgili öznitelik [UsingTask](../msbuild/usingtask-element-msbuild.md) öğesi.  
  
## <a name="hello-world"></a>Merhaba Dünya  
 Burada, daha sağlam bir satır içi görev RoslynCodeTaskFactory ile verilmiştir. HelloWorld görev görüntüler "Hello, world!" Varsayılan hata günlüğünü aygıtta olduğu genellikle sistem konsolu veya Visual Studio **çıkış** penceresi. `Reference` Örnek öğesinde yalnızca çizim için eklenmiştir.  
  
```xml  
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- This simple inline task displays "Hello, world!" -->  
  <UsingTask  
    TaskName="HelloWorld"  
    TaskFactory="RoslynCodeTaskFactory"  
    AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.Core.dll" >  
    <ParameterGroup />  
    <Task>  
      <Reference Include="System.Xml"/>
      <Using Namespace="System"/>  
      <Using Namespace="System.IO"/>  
      <Code Type="Fragment" Language="cs">  
<![CDATA[  
// Display "Hello, world!"  
Log.LogError("Hello, world!");  
]]>  
      </Code>  
    </Task>  
  </UsingTask>  
</Project>  
```  
  
 HelloWorld görev HelloWorld.targets adlı bir dosyaya kaydedin ve aşağıdaki gibi bir projeden çağırma.  
  
```xml  
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <Import Project="HelloWorld.targets" />  
  <Target Name="Hello">  
    <HelloWorld />  
  </Target>  
</Project>  
```  
  
## <a name="input-and-output-parameters"></a>Giriş ve çıkış parametreleri  
 Satır içi görev parametreleridir alt öğelerinin bir `ParameterGroup` öğesi. Her bir parametre tanımladığı öğesinin adını alır. Aşağıdaki kod parametre tanımlar `Text`.  
  
```xml  
<ParameterGroup>  
    <Text />  
</ParameterGroup>  
```  
  
 Parametreleri, bir veya daha fazla bu öznitelikler sahip olabilir:  
  
-   `Required` İsteğe bağlı bir özniteliği olan `false` varsayılan olarak. Varsa `true`, parametresi gereklidir ve görev çağırmadan önce bir değer verilmesi gerekir.  
  
-   `ParameterType` İsteğe bağlı bir özniteliği olan `System.String` varsayılan olarak. Bir öğe veya için ve bir dizeden System.Convert.ChangeType kullanarak dönüştürülebilir bir değeri tam bir türü için ayarlanabilir. (Dış görev gelen ve giden aktarılabilecek diğer bir deyişle, herhangi bir türü.)  
  
-   `Output` İsteğe bağlı bir özniteliği olan `false` varsayılan olarak. Varsa `true`, parametre değeri yürütme yönteminden döndürmeden önce verilmelidir.  
  
Örneğin,  
  
```xml  
<ParameterGroup>  
    <Expression Required="true" />  
    <Files ParameterType="Microsoft.Build.Framework.ITaskItem[]" Required="true" />  
    <Tally ParameterType="System.Int32" Output="true" />  
</ParameterGroup>  
```  
  
şu üç parametreyi tanımlar:  
  
-   `Expression` System.String türünde gerekli giriş parametresi değil.  
  
-   `Files` gerekli öğe listesi giriş parametresi değil.  
  
-   `Tally` bir çıkış System.Int32 türünde bir parametredir.  
  
 Varsa `Code` öğeye sahip `Type` özniteliği `Fragment` veya `Method`, sonra özellikleri her parametre için otomatik olarak oluşturulur. Aksi takdirde özellikleri görev kaynak kodunda açıkça bildirilmelidir ve parametre tanımlarını tam olarak eşleşmelidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki satır içi görev bazı iletilerini günlüğe kaydeder ve bir dize döndürür.  
  
```xml  
<Project xmlns='http://schemas.microsoft.com/developer/msbuild/2003' ToolsVersion="15.0">  
  
    <UsingTask TaskName="MySample"
               TaskFactory="RoslynCodeTaskFactory"
               AssemblyFile="$(MSBuildBinPath)\Microsoft.Build.Tasks.Core.dll">
        <ParameterGroup>
            <Parameter1 ParameterType="System.String" Required="true" />
            <Parameter2 ParameterType="System.String" />
            <Parameter3 ParameterType="System.String" Output="true" />
        </ParameterGroup>
        <Task>
            <Using Namespace="System" />
            <Code Type="Fragment" Language="C#">
              <![CDATA[
              Log.LogMessage(MessageImportance.High, "Hello from an inline task created by Roslyn!");
              Log.LogMessageFromText($"Parameter1: '{Parameter1}'", MessageImportance.High);
              Log.LogMessageFromText($"Parameter2: '{Parameter2}'", MessageImportance.High);
              Parameter3 = "A value from the Roslyn CodeTaskFactory";
            ]]>
            </Code>
        </Task>
    </UsingTask>
  
    <Target Name="Demo">  
      <MySample Parameter1="A value for parameter 1" Parameter2="A value for parameter 2">
          <Output TaskParameter="Parameter3" PropertyName="NewProperty" />
      </MySample>

      <Message Text="NewProperty: '$(NewProperty)'" />
    </Target>  
</Project>  
```  

 Bu satır içi görevleri yolları birleştirmek ve dosya adı.  
  
```xml  
<Project xmlns='http://schemas.microsoft.com/developer/msbuild/2003' ToolsVersion="15.0">  
  
    <UsingTask TaskName="PathCombine"
               TaskFactory="RoslynCodeTaskFactory"
               AssemblyFile="$(MSBuildBinPath)\Microsoft.Build.Tasks.Core.dll">
        <ParameterGroup>
            <Paths ParameterType="System.String[]" Required="true" />
            <Combined ParameterType="System.String" Output="true" />
        </ParameterGroup>
        <Task>
            <Using Namespace="System" />
            <Code Type="Fragment" Language="C#">
            <![CDATA[
            Combined = Path.Combine(Paths);
            ]]>
            </Code>
        </Task>
    </UsingTask>

    <UsingTask TaskName="PathGetFileName"
             TaskFactory="RoslynCodeTaskFactory"
             AssemblyFile="$(MSBuildBinPath)\Microsoft.Build.Tasks.Core.dll">
        <ParameterGroup>
            <Path ParameterType="System.String" Required="true" />
            <FileName ParameterType="System.String" Output="true" />
        </ParameterGroup>
        <Task>
            <Using Namespace="System" />
            <Code Type="Fragment" Language="C#">
            <![CDATA[
            FileName = System.IO.Path.GetFileName(Path);
            ]]>
            </Code>
        </Task>
    </UsingTask>
  
    <Target Name="Demo">  
        <PathCombine Paths="$(Temp);MyFolder;$([System.Guid]::NewGuid()).txt">
            <Output TaskParameter="Combined" PropertyName="MyCombinedPaths" />
        </PathCombine>

        <Message Text="Combined Paths: '$(MyCombinedPaths)'" />

        <PathGetFileName Path="$(MyCombinedPaths)">
            <Output TaskParameter="FileName" PropertyName="MyFileName" />
        </PathGetFileName>

        <Message Text="File name: '$(MyFileName)'" />
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [İzlenecek Yol: Satır İçi Göre Oluşturma](../msbuild/walkthrough-creating-an-inline-task.md)
