---
title: Madde öğesi (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Item Element [MSBuild]
- <Item> Element [MSBuild]
ms.assetid: dcef5f91-0613-4bfc-8ee9-d7004bb6d3a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b55cadc738fb54b1a7fe07a2d891103c0daa755d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="item-element-msbuild"></a>Öğe Unsuru (MSBuild)
Kullanıcı tanımlı bir öğesiyle, meta verilerini içerir. Kullanılan her öğe bir [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] bir alt öğesi olarak proje belirtilen bir `ItemGroup` öğesi.  

 \<Proje >  
 \<ItemGroup >  
 \<Öğe >  

## <a name="syntax"></a>Sözdizimi  

```  
<Item Include="*.cs"  
        Exclude="MyFile.cs"  
        Remove="RemoveFile.cs"  
        Condition="'String A'=='String B'" >  
    <ItemMetadata1>...</ItemMetadata1>  
    <ItemMetadata2>...</ItemMetadata2>  
</Item>  
```  

## <a name="specify-metadata-as-attributes"></a>Meta veri olarak öznitelikleri belirtin
MSBuild 15.1 veya sonraki sürümlerde, herhangi bir meta veri öznitelikleri geçerli listesiyle çakışan olmayan bir ad ile isteğe bağlı olarak bir özniteliği olarak ifade edilebilir.

Örneğin, NuGet paketlerini listesini belirtmek için normalde aşağıdaki söz dizimini şöyle kullanırsınız.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1-beta1<Version>
  </PackageReference>
</ItemGroup>
```

Şimdi, ancak geçirebilirsiniz `Version` özniteliği olarak, aşağıdaki söz dizimini olduğu gibi meta veriler:

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1-beta1" />  
</ItemGroup>
```

## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  

### <a name="attributes"></a>Öznitelikler  

|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Include`|İsteğe bağlı öznitelik.<br /><br /> Dosya veya öğeler listesinde dahil etmek için joker karakter.|  
|`Exclude`|İsteğe bağlı öznitelik.<br /><br /> Dosya veya öğeleri listeden dışlamak için joker karakter.|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşulu. Daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).|  
|`Remove`|İsteğe bağlı öznitelik.<br /><br /> Dosya veya öğeler listesinden kaldırmak için joker karakter.<br /><br />|  
|`KeepDuplicates`|İsteğe bağlı öznitelik.<br /><br /> Varolan öğeyi tam bir kopyasını ise, öğenin hedef grubuna eklenmesi gerekip gerekmediğini belirtir. Kaynak ve hedef öğe aynı varsa `Include` değeri ancak farklı meta veriler, öğedir eklenen olsa bile `KeepDuplicates` ayarlanır `false`. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).<br /><br /> Bu öznitelik yalnızca bir öğe için belirtilmişse, geçerli bir `ItemGroup` alanında bir `Target`.|  
|`KeepMetadata`|İsteğe bağlı öznitelik.<br /><br /> Hedef öğe eklemek için kaynak öğeleri meta verileri. Yalnızca, adları noktalı virgülle ayrılmış bir listede belirtilen meta veriler, bir kaynak öğesinden hedef öğesine aktarılır. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).<br /><br /> Bu öznitelik yalnızca bir öğe için belirtilmişse, geçerli bir `ItemGroup` alanında bir `Target`.|  
|`RemoveMetadata`|İsteğe bağlı öznitelik.<br /><br /> Hedef öğe değil aktarılacak kaynak öğeleri meta verileri. Tüm meta veriler kaynak öğesinden dışında meta verileri hedef öğesine adları adları noktalı virgülle ayrılmış liste bulunan aktarılır. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).<br /><br /> Bu öznitelik yalnızca bir öğe için belirtilmişse, geçerli bir `ItemGroup` alanında bir `Target`.|  
|`Update`|İsteğe bağlı öznitelik. (Yalnızca Visual Studio 2017 veya daha sonra .NET Core projeleri için kullanılabilir.)<br /><br /> Meta veriler bir glob kullanarak bulunan bir dosyanın değiştirmenizi sağlar.<br /><br />  Bu öznitelik yalnızca bir öğe için belirtilmişse, geçerli bir `ItemGroup` içinde değil bir `Target`.|  

### <a name="child-elements"></a>Alt Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[Itemmetadata](../msbuild/itemmetadata-element-msbuild.md)|Öğe meta veri değeri içeren bir kullanıcı tanımlı meta verileri, öğe anahtarı. Sıfır veya daha fazla olabilir `ItemMetadata` öğeyi öğeler.|  

### <a name="parent-elements"></a>Üst Öğeler  

|Öğe|Açıklama|  
|-------------|-----------------|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Grouping öğesi öğeleri için.|  

## <a name="remarks"></a>Açıklamalar  
 `Item` öğeleri girdi yapı sisteme tanımlayın ve öğeyi koleksiyona kendi kullanıcı tanımlı koleksiyon adlarına göre gruplandırılır. Bu öğe koleksiyonları için parametre olarak kullanılan [görevleri](../msbuild/msbuild-tasks.md), hangi bireysel öğeleri koleksiyonlardaki yapı işleminin adımları gerçekleştirmek için kullanın. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  

 Gösterimini kullanarak `@(` *myType* `)` türü öğeleri koleksiyonu sağlar *myType* dizelerin noktalı virgülle ayrılmış listesi genişletilmiş ve bir parametre geçirildi. Parametre türü ise `string`, noktalı virgülle ayrılmış bir öğeler listesi parametresi değeri olur. Parametresi bir dize dizisi ise (`string[]`), noktalı virgül konumunu temelinde dizideki her öğe eklenen sonra. Görev parametre türü ise <xref:Microsoft.Build.Framework.ITaskItem> `[]`, öğe koleksiyonunun bağlı herhangi bir meta veri birlikte içeriğini değer ise. Noktalı virgül dışında bir karakter kullanarak her bir öğeyi sınırlamak üzere söz dizimini kullanın `@(` *myType*`, '`*ayırıcı*`')`.  

 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Altyapısı değerlendir joker karakterler gibi `*` ve `?` ve yinelemeli joker karakterler gibi `/**/*.cs`. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  

## <a name="examples"></a>Örnekler  
 Aşağıdaki kod örneği, iki öğe türü bildirmek gösterilmiştir `CSFile`. Öğeyi sahip meta verileri içeren ikinci bildirilen `MyMetadata` kümesine `HelloWorld`.  

```xml  
<ItemGroup>  
    <CSFile Include="engine.cs; form.cs" />  
    <CSFile Include="main.cs" >  
        <MyMetadata>HelloWorld</MyMetadata>  
    </CSFile>  
</ItemGroup>  
```  
Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir `Update` meta verilerde glob dahil somefile.cs adlı bir dosyayı değiştirmek için öznitelik. (Yalnızca Visual Studio 2017 veya daha sonra .NET Core projeleri için kullanılabilir.)

```xml  
<ItemGroup>
    <Compile Update="somefile.cs">  // or Update="*.designer.cs"
        <MetadataKey>MetadataValue</MetadataKey>
    </Compile>
</ItemGroup>  
```  


## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğeleri](../msbuild/msbuild-items.md)   
 [MSBuild özellikleri](../msbuild/msbuild-properties.md)   
 [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
