---
title: 'Nasıl yapılır: hedefleri ve görevleri yapılandırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
ms.assetid: 92814100-392a-471d-96fd-e26f637d6cc2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7a09f2ec1af511cb789f2101e2df0a675dd065e8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-configure-targets-and-tasks"></a>Nasıl Yapılır: Hedefleri ve Görevleri Yapılandırma
Seçili MSBuild görevleri, bunlar geliştirme bilgisayar ortamı bağımsız olarak hedef ortamdaki çalıştırmak için ayarlanabilir. Örneğin, bu hedefleri 32-bit mimari bir uygulama oluşturmak için bir 64-bit bilgisayarda kullandığınızda, seçili görevleri bir 32 bit işlemde çalıştırılır.  
  
> [!NOTE]
>  Derleme görevi Visual C# veya Visual Basic gibi bir .NET dilinde yazılmış ve yerel kaynaklar veya Araçlar kullanmaz, her hedef bağlamda uyarlama olmadan çalışır.  
  
## <a name="usingtask-attributes-and-task-parameters"></a>UsingTask öznitelikleri ve görev parametreleri  
 Aşağıdaki `UsingTask` öznitelikleri belirli derleme işlemindeki bir görevin tüm işlemleri etkiler:  
  
-   `Runtime` Özniteliği varsa, ortak dil çalışma zamanı (CLR) sürüm ayarlar ve bu değerlerden herhangi biri alabilir: `CLR2`, `CLR4`, `CurrentRuntime`, veya `*` (çalışma zamanı herhangi).  
  
-   `Architecture` Özniteliği varsa, verileri ve platform ayarlar ve bu değerlerden birini alabilir: `x86`, `x64`, `CurrentArchitecture`, veya `*` (herhangi bir mimarideki).  
  
-   `TaskFactory` Özniteliği varsa, oluşturur ve görev örneğini çalıştıran ve yalnızca değer sürer görev Üreteç ayarlar `TaskHostFactory`. Daha fazla bilgi için bu belgenin sonraki bölümlerinde görev oluşturucuları bölümüne bakın.  
  
```xml  
<UsingTask TaskName="SimpleTask"   
   Runtime="CLR2"  
   Architecture="x86"  
   AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v3.5.dll" />  
```  
  
 Aynı zamanda `MSBuildRuntime` ve `MSBuildArchitecture` tek bir görev hedef bağlamında ayarlamak için parametreler.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <SimpleTask MSBuildRuntime="CLR2" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
```  
  
 MSBuild görevi çalışmadan önce bir eşleştirme için görünüyor `UsingTask` aynı hedef bağlamı sahip.  Belirtilen parametreleri `UsingTask` ancak karşılık gelen görevde eşleştirilmesini kabul edilir.  Görev ancak karşılık gelen belirtilen parametreleri `UsingTask` de eşleştirilmesini kabul edilir. Parametre değerleri ya da belirtilmezse `UsingTask` ya da görev için varsayılan değerler `*` (herhangi bir parametre).  
  
> [!WARNING]
>  Birden fazla ise `UsingTask` var ve tüm eşleşen `TaskName`, `Runtime`, ve `Architecture` öznitelikleri, değerlendirilecek bir diğer yerini alır.  
  
 Parametreleri görevi ayarlarsanız MSBuild bulmaya çalışır bir `UsingTask` , bu parametreler eşleşen veya en azından, bunları çakışıyor değil.  Birden fazla `UsingTask` aynı hedef bağlamı belirtebilirsiniz.  Örneğin, farklı bir hedef ortamlar için farklı yürütülebilir dosyaları içeren bir görev bu şuna benzeyebilir:  
  
```xml  
<UsingTask TaskName="MyTool"   
   Runtime="CLR2"  
   Architecture="x86"  
   AssemblyFile="$(MyToolsPath)\MyTool.v2.0.dll" />  
  
<UsingTask TaskName="MyTool"   
   Runtime="CLR4"  
   Architecture="x86"  
   AssemblyFile="$(MyToolsPath)\MyTool.4.0.dll" />  
  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <MyTool MSBuildRuntime="CLR2" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
  
```  
  
## <a name="task-factories"></a>Görev Oluşturucular  
 Bir görevi çalışmadan önce MSBuild geçerli yazılım bağlamında çalışacak şekilde tasarlanmış olup olmadığını denetler.  Görev şekilde belirlendiyse, MSBuild bunu geçerli işlemde çalışan AssemblyTaskFactory geçirir; Aksi takdirde, MSBuild hedef bağlamı eşleşen bir işlemde görev çalışır TaskHostFactory görev geçirir. Geçerli bağlamı ve hedef bağlamı aynı olsa bile, görevin çalışmasına zorlayabilirsiniz zaman-ayarlayarak işlem (için yalıtımı, güvenlik veya diğer nedenlerle) `TaskFactory` için `TaskHostFactory`.  
  
```xml  
<UsingTask TaskName="MisbehavingTask"   
   TaskFactory="TaskHostFactory"  
   AssemblyFile="$(MSBuildToolsPath)\MyTasks.dll">  
</UsingTask>  
```  
  
## <a name="phantom-task-parameters"></a>Hayali görev parametreleri  
 Gibi diğer görev parametreleri, `MSBuildRuntime` ve `MSBuildArchitecture` derleme özelliklerinden ayarlayabilirsiniz.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <PropertyGroup>  
      <FrameworkVersion>3.0</FrameworkVersion>  
   </PropertyGroup>  
   <Target Name="MyTarget">  
      <SimpleTask MSBuildRuntime="$(FrameworkVerion)" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
```  
  
 Diğer görev parametreleri aksine `MSBuildRuntime` ve `MSBuildArchitecture` görev için görünür değildir.  İçinde çalıştığı bağlamı kullanan bir görev yazmak için gerekir, .NET Framework çağırarak bağlam test veya diğer görev parametreleri üzerinden bağlam bilgileri geçirmek için yapı özelliklerini kullanmak.  
  
> [!NOTE]
>  `UsingTask` öznitelikleri araç takımını ve ortam özelliklerinden ayarlayabilirsiniz.  
  
 `MSBuildRuntime` Ve `MSBuildArchitecture` en esnek bir şekilde ayarlanmış hedef bağlamı, ancak ayrıca en sınırlı kapsam için parametreleri sağlayın.  Bir yandan, değerlendirme süresi ve derleme zamanı sırasında kullanılabilen özelliklerin tam kapsamı kendi değerinden türetilemeyeceğini çünkü bunlar görev örneğinin kendisinde ayarlanmış olan ve çalıştırmak üzere görev olana kadar değerlendirilmez.  Öte yandan, bu parametrelerden yalnızca belirli bir hedefe görevde belirli bir örneği için geçerlidir.  
  
> [!NOTE]
>  Görev parametrelerini görev ana bilgisayar bağlamı içinde değil, üst düğümü bağlamında değerlendirilir. Çalışma zamanı veya mimarisi-(örneğin, Program dosyalarının konumu) bağımlıdır ortam değişkenleri üst düğümüyle eşleşen değere değerlendirir.  Aynı ortam değişkenini görev tarafından doğrudan salt okunur ise, ancak bunu doğru görev konak bağlamında değerlendirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefleri ve Görevleri Yapılandırma](../msbuild/configuring-targets-and-tasks.md)
