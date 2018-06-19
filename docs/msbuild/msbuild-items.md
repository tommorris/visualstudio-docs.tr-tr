---
title: MSBuild öğeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, Items
ms.assetid: d762eff4-c92a-4b5f-a944-1ca30aa22319
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d860d2d80cbb93c36a75c56a73895a401bc47660
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31577541"
---
# <a name="msbuild-items"></a>MSBuild Öğeleri
MSBuild öğeleri girdileridir yapı sisteme ve bunlar genellikle dosyaları temsil eder. Öğeleri öğesi türlerine kendi öğesi adlarına göre gruplandırılır. Öğe türleri parametre olarak görevleri için kullanılabilir öğeleri listesi olarak adlandırılır. Görev öğesi değerleri yapı işleminin adımları gerçekleştirmek için kullanın.  
  
 Ait oldukları öğesi türü tarafından adlandırılmış öğesi olduğundan koşulları "öğesi" ve "öğesi değeri" birbirinin yerine kullanılabilir.  
  
 **Bu konudaki**  
  
-   [Öğeleri bir proje dosyası oluşturma](#BKMK_Creating1)  
  
-   [Yürütme sırasında öğeleri oluşturma](#BKMK_Creating2)  
  
-   [Proje dosyası öğelerde başvurma](#BKMK_ReferencingItems)  
  
-   [Öğelerini belirtmek için joker karakterleri kullanma](#BKMK_Wildcards)  
  
-   [Dışlama özniteliğini kullanma](#BKMK_ExcludeAttribute)  
  
-   [Öğe meta verileri](#BKMK_ItemMetadata)  
  
    -   [Bir proje dosyasında başvuruda bulunan öğe meta verileri](#BKMK_ReferencingItemMetadata)  
  
    -   [Tanınmış öğe meta verisi](#BKMK_WellKnownItemMetadata)  
  
    -   [Meta verileri kullanarak öğesi türlerini dönüştürme](#BKMK_Transforming)  
  
-   [Öğe Tanımları](#BKMK_ItemDefinitions)  
  
-   [Bir ItemGroup öğeleri hedefi için öznitelikler](#BKMK_AttributesWithinTargets)  
  
    -   [Özniteliği Kaldır](#BKMK_RemoveAttribute)  
  
    -   [KeepMetadata özniteliği](#BKMK_KeepMetadata)  
  
    -   [RemoveMetadata özniteliği](#BKMK_RemoveMetadata)  
  
    -   [KeepDuplicates özniteliği](#BKMK_KeepDuplicates)  
  
##  <a name="BKMK_Creating1"></a> Öğeleri bir proje dosyası oluşturma  
 Öğeleri alt öğeleri proje dosyasında bildirme bir [ItemGroup](../msbuild/itemgroup-element-msbuild.md) öğesi. Öğenin türü alt öğesi adıdır. `Include` Öğesinin özniteliği bu öğe türü ile dahil edilecek öğeleri (dosyaları) belirtir. Örneğin, aşağıdaki XML adlı bir öğe türü oluşturur `Compile`, iki dosya içerir.  
  
```xml  
<ItemGroup>  
    <Compile Include = "file1.cs"/>  
    <Compile Include = "file2.cs"/>  
</ItemGroup>  
```  
  
 "file2.cs" öğesi "file1.cs"; maddesini değil Bunun yerine, dosya adı için değerler listesi eklenecek `Compile` öğesi türü. Bir yapı değerlendirme aşamasında öğesi türünden bir öğe kaldırılamıyor.  
  
 Her iki dosya birinde bildirerek aynı öğe türü aşağıdaki XML oluşturur `Include` özniteliği. Dosya adları noktalı virgülle ayrılır dikkat edin.  
  
```xml  
<ItemGroup>  
    <Compile Include = "file1.cs;file2.cs"/>  
</ItemGroup>  
```  
  
##  <a name="BKMK_Creating2"></a> Yürütme sırasında öğeleri oluşturma  
 Dışında olan öğeleri [hedef](../msbuild/target-element-msbuild.md) öğeleri bir yapı değerlendirme aşamasında değerler atanır. Sonraki yürütme aşamasında öğeler oluşturulur ve aşağıdaki yollarla değiştiren:  
  
-   Herhangi bir görev, bir öğe yayma. Bir öğe yaymak üzere [görev](../msbuild/task-element-msbuild.md) öğesinin bir alt olmalı [çıkış](../msbuild/output-element-msbuild.md) sahip öğe bir `ItemName` özniteliği.  
  
-   [CreateItem](../msbuild/createitem-task.md) görev öğeyi yayma. Bu kullanım önerilmiyor.  
  
-   .NET Framework 3.5 Başlangıç `Target` öğeleri içerebilir [ItemGroup](../msbuild/itemgroup-element-msbuild.md) içerebilir öğeleri öğeleri öğesi.  
  
##  <a name="BKMK_ReferencingItems"></a> Proje dosyası öğelerde başvurma  
 Proje dosyası boyunca öğesi türleri başvurmak için şu sözdizimini kullanın. @(`ItemType`). Örneğin, kullanarak önceki örnekte öğesi türü başvuru `@(Compile)`. Şu sözdizimini kullanarak, bu görev bir parametre olarak öğe türü belirterek görevlere öğeleri geçirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: derleme dosyalarına seçin](../msbuild/how-to-select-the-files-to-build.md).  
  
 Varsayılan olarak, bu genişletildiğinde bir öğe türü öğeleri noktalı virgülle (;) ayrılır. Sözdizimini kullanabilirsiniz @(*ItemType*, '*ayırıcı*') varsayılan dışındaki bir ayırıcı belirtmek için. Daha fazla bilgi için bkz: [nasıl yapılır: bir öğe listesi ayrılmış virgüllerle görüntülemek](../msbuild/how-to-display-an-item-list-separated-with-commas.md).  
  
##  <a name="BKMK_Wildcards"></a> Öğelerini belirtmek için joker karakterleri kullanma  
 Kullanabileceğiniz **, \*, ve? bir dosya grubunun her dosya ayrı olarak listeleniyor yerine bir yapı için girdi olarak belirtmek için joker karakter.  
  
-   ? joker karakter, bir tek karakterle eşleşir.  
  
-   * Joker karakterle eşleşen sıfır veya daha fazla karakter.  
  
-   ** Joker karakter dizisi eşleşen bir kısmi yol.  
  
 Örneğin, proje dosyasında aşağıdaki öğeyi kullanarak proje dosyasını içeren dizine tüm .cs dosyaları belirtebilirsiniz.  
  
```xml  
<CSFile Include="*.cs"/>  
```  
  
 Aşağıdaki öğe D: sürücüsündeki tüm .vb dosyaları seçer:  
  
```xml  
<VBFile Include="D:/**/*.vb"/>  
```  
  
 Joker karakterler hakkında daha fazla bilgi için bkz: [nasıl yapılır: derleme dosyalarına seçin](../msbuild/how-to-select-the-files-to-build.md).  
  
##  <a name="BKMK_ExcludeAttribute"></a> Dışlama özniteliğini kullanma  
 Öğesi öğeleri içerebilir `Exclude` belirli öğeleri (dosyaları) öğesi türünden dışlar özniteliği. `Exclude` Özniteliği genellikle joker karakter ile birlikte kullanılır. Örneğin, aşağıdaki XML dışında CSFile öğesi türü için her .cs dosyası dizinde ekler `DoNotBuild.cs` dosya.  
  
```xml  
<ItemGroup>  
    <CSFile  Include="*.cs"  Exclude="DoNotBuild.cs"/>  
</ItemGroup>  
```  
  
 `Exclude` Özniteliği tarafından eklenen öğeler etkiler `Include` özniteliği öğesi öğesindeki her ikisinin de içerir. Aşağıdaki örnek, önceki öğesi öğe eklendi Form1.cs dosyasını dışlayın olmayacaktır.  
  
```xml  
<Compile Include="*.cs" />  
<Compile Include="*.res" Exclude="Form1.cs">  
```  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: dosyaları derlemeden Dışla](../msbuild/how-to-exclude-files-from-the-build.md).  
  
##  <a name="BKMK_ItemMetadata"></a> Öğe meta verileri  
 Öğeleri, meta veri bilgileri yanı sıra içerebilir `Include` ve `Exclude` öznitelikleri. Bu meta veriler, toplu iş görevleri ve hedefleri için veya öğeler hakkında daha fazla bilgi gerektiren görevleri tarafından kullanılabilir. Daha fazla bilgi için bkz: [Batching](../msbuild/msbuild-batching.md).  
  
 Meta veri öğesi öğenin alt öğeleri olarak proje dosyasında bildirilen anahtar-değer çiftleri koleksiyonudur. Alt öğe adını meta verileri adıdır ve meta veri değeri alt öğesinin değeri.  
  
 Meta veriler içerdiği öğesi öğesi ile ilişkilendirilmiştir. Örneğin, aşağıdaki XML ekler `Culture` değerine sahip meta verileri `Fr` "one.cs" ve "two.cs" öğelerini CSFile için öğesi türü.  
  
```xml  
<ItemGroup>  
    <CSFile Include="one.cs;two.cs">  
        <Culture>Fr</Culture>  
    </CSFile>  
</ItemGroup>  
```  
  
 Bir öğe sıfır veya daha fazla meta veri değerine sahip olabilir. Meta veri değerlerinin dilediğiniz zaman değiştirebilirsiniz. Meta veriler için boş bir değer ayarlarsanız, etkili bir şekilde derlemeden kaldırın.  
  
###  <a name="BKMK_ReferencingItemMetadata"></a> Bir proje dosyasında başvuruda bulunan öğe meta verileri  
 Sözdizimi kullanılarak %(öğe meta verisi proje dosyası boyunca başvurabilir`ItemMetadataName`). Belirsizlik varsa öğe türü adını kullanarak bir başvuru uygun bulabilirsiniz. For example, belirleyebileceğiniz %(*ItemType.ItemMetaDataName*). Aşağıdaki örnek, ileti görevi toplu görüntü meta verileri kullanır. Toplu işleme için öğe meta verileri kullanma hakkında daha fazla bilgi için bkz: [toplu görev işlemede öğe meta verisi](../msbuild/item-metadata-in-task-batching.md).  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Stuff Include="One.cs" >  
            <Display>false</Display>  
        </Stuff>  
        <Stuff Include="Two.cs">  
            <Display>true</Display>  
        </Stuff>  
    </ItemGroup>  
    <Target Name="Batching">  
        <Message Text="@(Stuff)" Condition=" '%(Display)' == 'true' "/>  
    </Target>  
</Project>  
```  
  
###  <a name="BKMK_WellKnownItemMetadata"></a> Tanınmış öğe meta verisi  
 Bir öğe türü için bir öğe eklendiğinde, o öğe iyi bilinen bazı meta verileri atanır. Örneğin, iyi bilinen meta verileri tüm öğeleri sahip `%(Filename)`, değeri öğenin dosya adıdır. Daha fazla bilgi için bkz: [tanınmış öğe meta verisi](../msbuild/msbuild-well-known-item-metadata.md).  
  
###  <a name="BKMK_Transforming"></a> Meta verileri kullanarak öğesi türlerini dönüştürme  
 Meta verileri kullanarak yeni öğe listelerine öğesi listeleri dönüştürebilirsiniz. Örneğin, bir öğe türü dönüştürebilirsiniz `CppFiles` , ifade kullanarak .cpp dosyaları .obj dosyaların karşılık gelen bir listesini temsil eden öğeleri olan `@(CppFiles -> '%(Filename).obj')`.  
  
 Aşağıdaki kod oluşturur bir `CultureResource` öğesi tüm kopyalarını içerir türünü `EmbeddedResource` öğeler `Culture` meta verileri. `Culture` Meta veri değeri olur ve yeni meta değerini `CultureResource.TargetDirectory`.  
  
```xml  
<Target Name="ProcessCultureResources">  
    <ItemGroup>  
        <CultureResource Include="@(EmbeddedResource)"  
            Condition="'%(EmbeddedResource.Culture)' != ''">  
            <TargetDirectory>%(EmbeddedResource.Culture) </TargetDirectory>  
        </CultureResource>  
    </ItemGroup>  
</Target>  
```  
  
 Daha fazla bilgi için bkz: [dönüştüren](../msbuild/msbuild-transforms.md).  
  
##  <a name="BKMK_ItemDefinitions"></a> Öğe tanımları  
 .NET Framework 3. 5'ten başlayarak, varsayılan meta verileri herhangi bir öğe türüne kullanarak ekleyebilirsiniz [Itemdefinitiongroup öğesi](../msbuild/itemdefinitiongroup-element-msbuild.md). İyi bilinen meta verileri gibi varsayılan meta veri öğesi türünün belirttiğiniz tüm öğelerle ilişkilidir. Açıkça varsayılan meta veri öğesi tanımında geçersiz kılabilirsiniz. Örneğin, aşağıdaki XML verir `Compile` "one.cs" ve "three.cs" meta veri öğeleri `BuildDay` "Pazartesi" değerine sahip. Kod öğesi "two.cs" meta veri sağlar. `BuildDay` "Salı" değerine sahip.  
  
```xml  
<ItemDefinitionGroup>  
    <Compile>  
        <BuildDay>Monday</BuildDay>  
    </Compile>  
</ItemDefinitionGroup>  
<ItemGroup>  
    <Compile Include="one.cs;three.cs" />  
    <Compile Include="two.cs">  
        <BuildDay>Tuesday</BuildDay>  
    </Compile>  
</ItemGroup>  
```  
  
 Daha fazla bilgi için bkz: [öğe tanımları](../msbuild/item-definitions.md).  
  
##  <a name="BKMK_AttributesWithinTargets"></a> Bir ItemGroup öğeleri hedefi için öznitelikler  
 .NET Framework 3.5 Başlangıç `Target` öğeleri içerebilir [ItemGroup](../msbuild/itemgroup-element-msbuild.md) içerebilir öğeleri öğeleri öğesi. Bir öğe için belirtildiğinde bu bölümdeki öznitelikleri geçerli bir `ItemGroup` alanında bir `Target`.  
  
###  <a name="BKMK_RemoveAttribute"></a> Özniteliği Kaldır  
 Alanındaki öğelerin bir `ItemGroup` hedefi içerebilir `Remove` belirli öğeleri (dosyaları) içinden öğe türünü kaldırır özniteliği. Bu öznitelik, .NET Framework 3. 5 ' sunulmuştur.  
  
 Aşağıdaki örnek, her .config dosyası derleme öğesi türünden kaldırır.  
  
```xml  
<Target>  
    <ItemGroup>  
        <Compile Remove="*.config"/>  
    </ItemGroup>  
</Target>  
```  
  
###  <a name="BKMK_KeepMetadata"></a> KeepMetadata özniteliği  
 Bir öğe içinde bir hedef oluşturulursa öğe unsuru içerebilir `KeepMetadata` özniteliği. Bu özniteliği belirtilmezse, adları noktalı virgülle ayrılmış listesi belirtilen meta veri kaynağı öğesinden hedef öğesine aktarılır. Bu öznitelik için boş bir değer, onu belirtmeden için eşdeğerdir. `KeepMetadata` Özniteliği, .NET Framework 4. 5 ' sunulmuştur.  
  
 Aşağıdaki örnekte nasıl kullanılacağını anlatan `KeepMetadata` özniteliği.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
ToolsVersion="4.0">  
  
    <ItemGroup>  
        <FirstItem Include="rhinoceros">  
            <Class>mammal</Class>  
            <Size>large</Size>  
        </FirstItem>  
  
    </ItemGroup>  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <SecondItem Include="@(FirstItem)" KeepMetadata="Class" />  
        </ItemGroup>  
  
        <Message Text="FirstItem: %(FirstItem.Identity)" />  
        <Message Text="  Class: %(FirstItem.Class)" />  
        <Message Text="  Size:  %(FirstItem.Size)"  />  
  
        <Message Text="SecondItem: %(SecondItem.Identity)" />  
        <Message Text="  Class: %(SecondItem.Class)" />  
        <Message Text="  Size:  %(SecondItem.Size)"  />  
    </Target>  
</Project>  
  
<!--  
Output:  
  FirstItem: rhinoceros  
    Class: mammal  
    Size:  large  
  SecondItem: rhinoceros  
    Class: mammal  
    Size:   
-->  
```  
  
###  <a name="BKMK_RemoveMetadata"></a> RemoveMetadata özniteliği  
 Bir öğe içinde bir hedef oluşturulursa öğe unsuru içerebilir `RemoveMetadata` özniteliği. Bu özniteliği belirtilmezse, tüm meta veri kaynağı öğesinden dışında meta verileri hedef öğesine adları adları noktalı virgülle ayrılmış liste bulunan aktarılır. Bu öznitelik için boş bir değer, onu belirtmeden için eşdeğerdir. `RemoveMetadata` Özniteliği, .NET Framework 4. 5 ' sunulmuştur.  
  
 Aşağıdaki örnekte nasıl kullanılacağını anlatan `RemoveMetadata` özniteliği.  
  
```xml  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <MetadataToRemove>Size;Material</MetadataToRemove>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <Item1 Include="stapler">  
            <Size>medium</Size>  
            <Color>black</Color>  
            <Material>plastic</Material>  
        </Item1>  
    </ItemGroup>  
  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <Item2 Include="@(Item1)" RemoveMetadata="$(MetadataToRemove)" />  
        </ItemGroup>  
  
        <Message Text="Item1: %(Item1.Identity)" />  
        <Message Text="  Size:     %(Item1.Size)" />  
        <Message Text="  Color:    %(Item1.Color)" />  
        <Message Text="  Material: %(Item1.Material)" />  
        <Message Text="Item2: %(Item2.Identity)" />  
        <Message Text="  Size:     %(Item2.Size)" />  
        <Message Text="  Color:    %(Item2.Color)" />  
        <Message Text="  Material: %(Item2.Material)" />  
    </Target>  
</Project>  
  
<!--  
Output:   
  Item1: stapler  
    Size:     medium  
    Color:    black  
    Material: plastic  
  Item2: stapler  
    Size:       
    Color:    black  
    Material:   
-->  
```  
  
###  <a name="BKMK_KeepDuplicates"></a> KeepDuplicates özniteliği  
 Bir öğe içinde bir hedef oluşturulursa öğe unsuru içerebilir `KeepDuplicates` özniteliği. `KeepDuplicates` olan bir `Boolean` öğe varolan öğeyi tam bir kopyasını ise öğeyi hedef grubuna eklenmesi gerekip gerekmediğini belirten özniteliği.  
  
 Kaynak ve hedef öğe farklı meta veriler ancak aynı INCLUDE değeri varsa, öğe eklenmiş olsa bile `KeepDuplicates` ayarlanır `false`. Bu öznitelik için boş bir değer, onu belirtmeden için eşdeğerdir. `KeepDuplicates` Özniteliği, .NET Framework 4. 5 ' sunulmuştur.  
  
 Aşağıdaki örnekte nasıl kullanılacağını anlatan `KeepDuplicates` özniteliği.  
  
```xml  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Item1 Include="hourglass;boomerang" />  
        <Item2 Include="hourglass;boomerang" />  
    </ItemGroup>  
  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <Item1 Include="hourglass" KeepDuplicates="false" />  
            <Item2 Include="hourglass" />  
        </ItemGroup>  
  
        <Message Text="Item1: @(Item1)" />  
        <Message Text="  %(Item1.Identity)  Count: @(Item1->Count())" />  
        <Message Text="Item2: @(Item2)" />  
        <Message Text="  %(Item2.Identity)  Count: @(Item2->Count())" />  
    </Target>  
</Project>  
  
<!--  
Output:   
  Item1: hourglass;boomerang  
    hourglass  Count: 1  
    boomerang  Count: 1  
  Item2: hourglass;boomerang;hourglass  
    hourglass  Count: 2  
    boomerang  Count: 1  
-->  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild Kavramları](../msbuild/msbuild-concepts.md)  
 [MSBuild](../msbuild/msbuild.md)   
 [Nasıl yapılır: derleme dosyalarını seçin](../msbuild/how-to-select-the-files-to-build.md)   
 [Nasıl yapılır: dosyaları derlemeden dışlama](../msbuild/how-to-exclude-files-from-the-build.md)   
 [Nasıl yapılır: virgülle ayrılmış bir öğe listesini görüntüleme](../msbuild/how-to-display-an-item-list-separated-with-commas.md)   
 [Öğe tanımları](../msbuild/item-definitions.md)   
 [Toplu işleme](../msbuild/msbuild-batching.md)   
 [Öğe Unsuru (MSBuild)](../msbuild/item-element-msbuild.md)