---
title: Hedef öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Target
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Target element [MSBuild]
- <Target> element [MSBuild]
ms.assetid: 350f6fc2-86b3-45f2-a31e-ece0e6bd4dca
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c5d60d41c7c7866ed396a90eacec4ba61a05238
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="target-element-msbuild"></a>Hedef Öğe (MSBuild)
Görevler için bir dizi içeren [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] sıralı olarak yürütülecek.  

 \<Proje >  
 \<Hedef >  

## <a name="syntax"></a>Sözdizimi  

```  
<Target Name="Target Name"  
        Inputs="Inputs"  
        Outputs="Outputs"  
        Returns="Returns"  
        KeepDuplicateOutputs="true/false"  
        BeforeTargets="Targets"  
        AfterTargets="Targets"  
        DependsOnTargets="DependentTarget"  
        Condition="'String A' == 'String B'">  
        Label="Label">  
    <Task>... </Task>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <OnError... />  
</Target>  
```  

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli öznitelik.<br /><br /> Hedefin adı.|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşulu. Koşul değerlendirilirse `false`, hedef hedef veya ayarlanmış olan tüm hedefleri gövdesi yürütmez `DependsOnTargets` özniteliği. Koşullar hakkında daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  
|`Inputs`|İsteğe bağlı öznitelik.<br /><br /> Bu hedefe girişleri form dosyalar. Birden çok dosya noktalı virgülle ayrılır. Zaman damgaları dosyaların dosyaların zaman damgalı karşılaştırıldığında `Outputs` belirlemek için olup olmadığını `Target` güncel. Daha fazla bilgi için bkz: [artımlı derlemeler](../msbuild/incremental-builds.md), [nasıl yapılır: artımlı olarak derleme](../msbuild/how-to-build-incrementally.md), ve [dönüştüren](../msbuild/msbuild-transforms.md).|  
|`Outputs`|İsteğe bağlı öznitelik.<br /><br /> Bu hedefe form çıkarır dosyalar. Birden çok dosya noktalı virgülle ayrılır. Zaman damgaları dosyaların dosyaların zaman damgalı karşılaştırıldığında `Inputs` belirlemek için olup olmadığını `Target` güncel. Daha fazla bilgi için bkz: [artımlı derlemeler](../msbuild/incremental-builds.md), [nasıl yapılır: artımlı olarak derleme](../msbuild/how-to-build-incrementally.md), ve [dönüştüren](../msbuild/msbuild-transforms.md).|  
|`Returns`|İsteğe bağlı öznitelik.<br /><br /> Bu hedef, örneğin, MSBuild görevleri çağırma görevlere kullanıma sunulacaktır öğeleri kümesi. Birden çok hedef noktalı virgülle ayrılır. Hedefleri dosyasında yoksa `Returns` öznitelikleri bunun yerine bu amaç için kullanılan çıkış öznitelikleri.|  
|`KeepDuplicateOutputs`|İsteğe bağlı Boole öznitelik.<br /><br /> Varsa `true`, hedefin döndürür aynı öğede birden fazla başvuru kaydedilir.  Varsayılan olarak, bu özniteliktir `false`.|  
|`BeforeTargets`|İsteğe bağlı öznitelik.<br /><br /> Hedef adları noktalı virgülle ayrılmış listesi.  Belirtildiğinde, bu hedefe belirtilen hedef veya hedefleri önce çalışması gerektiğini gösterir. Bu, doğrudan değiştirmeden hedefleri var olan bir dizi genişletme projesi yazarı olanak tanır. Daha fazla bilgi için bkz: [hedef derleme sırası](../msbuild/target-build-order.md).|  
|`AfterTargets`|İsteğe bağlı öznitelik.<br /><br /> Hedef adları noktalı virgülle ayrılmış listesi. Belirtildiğinde, bu hedefe belirtilen hedef veya hedefleri sonra çalışması gerektiğini gösterir. Bu, doğrudan değiştirmeden hedefleri var olan bir dizi genişletme projesi yazarı olanak tanır. Daha fazla bilgi için bkz: [hedef derleme sırası](../msbuild/target-build-order.md).|  
|`DependsOnTargets`|İsteğe bağlı öznitelik.<br /><br /> Bu hedef yürütülebilmesi yürütülmelidir hedefleri veya üst düzey Bağımlılık çözümlemesini ortaya çıkabilir. Birden çok hedef noktalı virgülle ayrılır.|  
|`Label`|İsteğe bağlı öznitelik.<br /><br /> Kimliğinizi belirlemek veya sistem ve kullanıcı öğeleri sipariş bir tanımlayıcı.|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Görev](../msbuild/task-element-msbuild.md)|Oluşturur ve bir örneğini yürüten bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] görev. Bir hedef olarak sıfır veya daha fazla görev olabilir.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Kullanıcı tanımlı bir kümesini içerir `Property` öğeleri. .NET Framework 3.5 başlayarak bir `Target` öğesi içerebilir `PropertyGroup` öğeleri.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Kullanıcı tanımlı bir kümesini içerir `Item` öğeleri. .NET Framework 3.5 başlayarak bir `Target` öğesi içerebilir `ItemGroup` öğeleri. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).|  
|[OnError](../msbuild/onerror-element-msbuild.md)|Neden olursa yürütmek bir veya daha fazla hedefleri `ContinueOnError` özniteliktir ErrorAndStop (veya `false`) için başarısız olan bir görevin. Sıfır veya daha fazla olabilir `OnError` bir hedef öğe. Varsa `OnError` öğeleri, son öğeleri olmalıdır `Target` öğesi.<br /><br /> Hakkında bilgi için `ContinueOnError` özniteliği için bkz: [görev öğesi (MSBuild)](../msbuild/task-element-msbuild.md).|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesinin bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] proje dosyası.|  

## <a name="remarks"></a>Açıklamalar  
 Yürütülecek ilk hedef çalışma zamanında belirtilir. Hedefleri diğer hedeflerde bağımlılıkları olabilir. Örneğin, dağıtım için bir hedef derleme için bir hedef bağlıdır. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Altyapısı bağımlılıkları göründükleri içinde sırayla yürütür `DependsOnTargets` soldan sağa özniteliği. Daha fazla bilgi için bkz: [hedefleri](../msbuild/msbuild-targets.md).  

 Birden fazla hedef üzerinde bir bağımlılığa sahip olsa bile bir hedef yalnızca bir derleme sırasında bir kez çalıştırılır.  

 Bir hedefi olduğundan atladıysanız kendi `Condition` özniteliği hesaplar için `false`, yapı içinde çağrılırsa hala çalıştırılabilir ve kendi `Condition` özniteliği hesaplar için `true` o zaman.  

 MSBuild 4 önce `Target` belirtilmiş herhangi bir öğeyi döndürülen `Outputs` özniteliği.  Bunu yapmak için derleme görevleri daha sonra bunları istenen durumunda bu öğelere kaydetmek MSBuild vardı. Hangi hedefleri arayanlar gerektirecek çıkışları vardı belirtmek için hiçbir şekilde olduğundan, tüm kaynaklardan tüm öğeleri MSBuild birikmiş `Outputs` tüm çağrılan `Target`s. Çok sayıda çıktı öğeleri vardı derlemeleri sorunlarını Ölçeklendirmesi bu sağlama.  

 Kullanıcı belirtiyorsa bir `Returns` herhangi `Target` proje sonra yalnızca öğesinde `Target`sahip s bir `Returns` özniteliği öğelerden kaydedin.  

 A `Target` her ikisini içerebilir bir `Outputs` özniteliğini ve bir `Returns` özniteliği.  `Outputs` ile birlikte kullanılan `Inputs` hedef güncel olup olmadığını belirlemek için. `Returns`, varsa, değerini geçersiz kılar `Outputs` hangi öğeleri arayanlara döndürülür belirlemek için.  Varsa `Returns` sonra yoksa `Outputs` daha önce açıklanan durumda dışında arayanlara kullanıma sunulacaktır.  

 MSBuild 4 önce herhangi bir zamanda bir `Target` aynı öğede birden fazla başvuru dahil kendi `Outputs`, yinelenen öğelerden kaydedilmesi. Çok sayıda çıktıları ve çok sayıda proje bağımlılıklarını sahip çok büyük oluşturur, bu çok miktarda bellek yinelenen öğeleri herhangi bir kullanımından değildi çünkü küçülttüğü iyi bir şekilde neden olur. Zaman `KeepDuplicateOutputs` özniteliği `true`, bu yinelemeleri kaydedilir.  

## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği kod bir `Target` yürütür öğesi `Csc` görev.  

```xml  
<Target Name="Compile" DependsOnTargets="Resources" Returns="$(TargetPath)">  
    <Csc Sources="@(CSFile)"  
          TargetType="library"  
          Resources="@(CompiledResources)"  
          EmitDebugInformation="$(includeDebugInformation)"  
          References="@(Reference)"  
          DebugType="$(debuggingType)" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
    </Csc>  
</Target>  
```  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefleri](../msbuild/msbuild-targets.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
