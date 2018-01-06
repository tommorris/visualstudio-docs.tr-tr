---
title: "Özellikleri ve öğeleri karşılaştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: msbuild, msbuild properties
ms.assetid: b9da45ae-d6a6-4399-8628-397deed31486
caps.latest.revision: "16"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6210f6e96c4e0b1330ee83a3f0f19ae58849dfce
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-properties-and-items"></a>Özellikleri ve Öğeleri Karşılaştırma
MSBuild özellikleri ve öğeleri ikisi de bilgi görevlere geçirmek, koşulları değerlendirin ve proje dosyası başvurulabilir değerlerini depolamak için kullanılır.  
  
-   Ad-değer çiftleri özelliklerdir. Daha fazla bilgi için bkz: [MSBuild özellikleri](../msbuild/msbuild-properties.md).  
  
-   Genellikle dosyaları temsil eden nesneler öğelerdir. Öğesi nesneleri ilişkili meta verileri koleksiyonlar. Meta veri olan ad-değer çiftleri. Daha fazla bilgi için bkz: [öğeleri](../msbuild/msbuild-items.md).  
  
## <a name="scalars-and-vectors"></a>Skalerler ve vektörler  
 MSBuild özellikleri yalnızca bir dize değerine sahip ad-değer çiftleri olduğundan, bunlar genellikle olarak açıklanan *skaler*. MSBuild öğesi türlerini listeler öğelerinin olduğundan, bunlar genellikle olarak açıklanan *vektör*. Ancak, uygulama, Özellikler birden çok değer gösterebilir ve öğesi türleri sıfır veya bir öğe olabilir.  
  
### <a name="target-dependency-injection"></a>Hedef Bağımlılık ekleme  
 Özellikler birden çok değer nasıl gösterebilir görmek için bir hedef oluşturulacak hedefleri listesine eklemek için genel bir kullanım desen göz önünde bulundurun. Bu liste, hedef adlarını noktalı virgülle ayırarak ile bir özellik değeri tarafından tipik olarak temsil edilir.  
  
```xml  
<PropertyGroup>  
    <BuildDependsOn>  
        BeforeBuild;  
        CoreBuild;  
        AfterBuild  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
 `BuildDependsOn` Özellik genelde bir hedef bağımsız değişken olarak kullanılan `DependsOnTargets` etkili bir şekilde bir öğeyi listeye dönüştürme özniteliği. Bu özellik, bir hedef eklemek veya hedef yürütme sırasını değiştirmek için geçersiz kılınabilir. Örneğin,  
  
```xml  
<PropertyGroup>  
    <BuildDependsOn>  
        $(BuildDependsOn);  
        CustomBuild;  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
 CustomBuild hedef hedef listesine ekler vermiş `BuildDependsOn` değeri `BeforeBuild;CoreBuild;AfterBuild;CustomBuild`.  
  
 MSBuild 4.0 ile başlayarak, hedef bağımlılık ekleme kullanım dışıdır. Kullanım `AfterTargets` ve `BeforeTargets` yerine öznitelikleri. Daha fazla bilgi için bkz: [hedef derleme sırası](../msbuild/target-build-order.md).  
  
### <a name="conversions-between-strings-and-item-lists"></a>Dizeler ve öğesi listeleri arasında dönüştürmeler  
 MSBuild dönüşümleri öğesi türleri ve gerektiğinde dize değerlerini gelen ve giden gerçekleştirir. Bir öğe listesini bir dize değeri nasıl olabileceğini görmek için bir öğe türü bir MSBuild özelliğinin değeri olarak kullanıldığında, ne olacağını düşünün:  
  
```xml  
<ItemGroup>  
    <OutputDir Include="KeyFiles\;Certificates\" />  
  </ItemGroup>  
<PropertyGroup>  
    <OutputDirList>@(OutputDir)</OutputDirList>  
</PropertyGroup>  
```  
  
 OutputDir sahip öğesi türü bir `Include` öznitelik değeri olan "KeyFiles\\; Sertifikaları\\". MSBuild iki öğeleri bu dizeyi ayrıştırır: KeyFiles\ ve sertifikaları\\. Öğe türü OutputDir OutputDirList özelliğinin değeri olarak kullanıldığında, MSBuild dönüştürür veya "noktalı virgülle ayrılmış dize içine öğesi türüne düzleştirir" "KeyFiles\\; Sertifikaları\\".  
  
## <a name="properties-and-items-in-tasks"></a>Özellikleri ve öğeleri görevler  
 Özellikleri ve öğeleri girişleri ve çıkışları MSBuild görevleri için kullanılır. Daha fazla bilgi için bkz: [görevleri](../msbuild/msbuild-tasks.md).  
  
 Özellikler görevlere öznitelik olarak geçirilir. İçinde görev, MSBuild özelliği için ve bir dize değeri dönüştürülebilir bir özellik türü ile temsil edilir. Desteklenen özellik türleri dahil `bool`, `char`, `DateTime`, `Decimal`, `Double`, `int`, `string`, ve herhangi bir türü <xref:System.Convert.ChangeType%2A> işleyebilir.  
  
 Öğeleri görevlere geçirilir <xref:Microsoft.Build.Framework.ITaskItem> nesneleri. Görev içinde <xref:Microsoft.Build.Framework.ITaskItem.ItemSpec%2A> öğenin değerini temsil eder ve <xref:Microsoft.Build.Framework.ITaskItem.GetMetadata%2A> meta verilerini alır.  
  
 Öğe listesinden bir öğe türü bir dizisi olarak geçirilebilir `ITaskItem` nesneleri. .NET Framework 3.5 ile başlayarak, öğeleri bir öğe listesinden bir hedef kullanarak Kaldırılabilir `Remove` özniteliği. Öğeleri bir öğeyi listeden kaldırılabilir olduğundan, sıfır öğe olan bir öğe türü için mümkündür. Bir öğe listesi göreve aktarılırsa görev kodunda bu olasılığı için kontrol etmeniz gerekir.  
  
## <a name="property-and-item-evaluation-order"></a>Özelliği ve öğe değerlendirme sırası  
 Bir yapı değerlendirme aşamasında, içe aktarılan dosyaları göründükleri sırada derleme halinde birleştirilir. Özellikleri ve öğeleri aşağıdaki sırayla üç geçiş tanımlanmıştır:  
  
-   Özellikler tanımlanır ve göründükleri sırada değiştirdi.  
  
-   Öğe tanımları tanımlanır ve göründükleri sırada değiştirdi.  
  
-   Öğeleri tanımlanır ve göründükleri sırada değiştirdi.  
  
 Derleme yürütme aşamasında özellikleri ve hedefleri içinde tanımlanan öğeleri birlikte tek bir aşamada göründükleri sırada değerlendirilir.  
  
 Ancak, tam Öykü değil. Bir özellik, öğesi tanımı veya öğesi tanımlandığında değeri değerlendirilir. İfade değerlendirici değeri belirten bir dize genişletir. Dize genişletme yapı aşamaya bağlıdır. Daha ayrıntılı bir özelliği ve öğe değerlendirme sırası şöyledir:  
  
-   Derleme sırasında Değerlendirme Aşaması:  
  
    -   Özellikler tanımlanır ve göründükleri sırada değiştirdi. Özellik işlevleri yürütülür. Form $(PropertyName) özellik değerlerinde içinde ifadeleri genişletilir. Özellik değeri genişletilmiş ifade ayarlanır.  
  
    -   Öğe tanımları tanımlanır ve göründükleri sırada değiştirdi. Özellik işlevleri zaten içinde ifadeleri genişletilmiştir. Meta veri değerleri genişletilmiş ifadeleri için ayarlanır.  
  
    -   Öğe türleri tanımlanır ve göründükleri sırada değiştirdi. Form @(ItemType) öğesi değerleri genişletilir. Öğe dönüşümleri da genişletilir. Özellik işlevleri ve değerleri zaten içinde ifadeleri genişletilmiştir. Öğe listeleme ve meta veri değerleri genişletilmiş ifadeleri için ayarlanır.  
  
-   Bir yapı yürütme aşamasında:  
  
    -   Özellikleri ve hedefleri içinde tanımlanan öğeleri birlikte göründükleri sırayla değerlendirilir. Özellik işlevleri yürütülür ve özellik değerlerini içinde ifadeleri genişletilir. Madde değerlerini ve madde dönüştürmeleri ayrıca genişletilir. Özellik değerleri, öğe türü değerleri ve meta veri değerlerinin genişletilmiş ifadeleri için ayarlanır.  
  
### <a name="subtle-effects-of-the-evaluation-order"></a>Değerlendirme sırası Zarif etkileri  
 Bir yapı değerlendirme aşaması, özellik değerlendirmesi öğesi değerlendirme önce gelir. Bununla birlikte, Özellikler öğesi değerlerine bağımlı görünmesini değerlere sahip olabilir. Aşağıdaki komut dosyası düşünün.  
  
```xml  
<ItemGroup>  
    <KeyFile Include="KeyFile.cs">  
        <Version>1.0.0.3</Version>  
    </KeyFile>  
</ItemGroup>  
<PropertyGroup>  
    <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
</PropertyGroup>  
<Target Name="AfterBuild">  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 İleti görevi Yürütülüyor şu ileti görüntülenir:  
  
```  
KeyFileVersion: 1.0.0.3  
```  
  
 Bunun nedeni, değeri `KeyFileVersion` gerçekten dizesi "@('% (sürüm)' KeyFile ->)". Öğe ve madde dönüşümleri genişletilmemiş özelliği ilk tanımlanırken, böylece `KeyFileVersion` özelliği unexpanded dize değerini atandı.  
  
 İleti görevi işlediğinde, derleme yürütme aşamasında MSBuild dize genişletir. "@('% (sürüm)' KeyFile ->)" "1.0.0.3" elde etmek üzere.  
  
 Özelliği ve öğe grupları sırayla ters kaydedildi olsa bile aynı iletiyi görüneceği dikkat edin.  
  
 İkinci bir örnek olarak, özellik ve öğesi grupları hedefleri içinde bulunan zaman neler olabileceğini göz önünde bulundurun:  
  
```xml  
<Target Name="AfterBuild">  
    <PropertyGroup>  
        <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
    </PropertyGroup>  
    <ItemGroup>  
        <KeyFile Include="KeyFile.cs">  
            <Version>1.0.0.3</Version>  
        </KeyFile>  
    </ItemGroup>  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 İleti görevi şu ileti görüntülenir:  
  
```  
KeyFileVersion:   
```  
  
 Derleme yürütme aşamasında hedefleri içinde tanımlanan özelliği ve öğe gruplar değerlendirilir Bunun nedeni aynı anda yukarıdan. Zaman `KeyFileVersion` tanımlanan `KeyFile` bilinmiyor. Bu nedenle, boş bir dize öğesi dönüştürme genişletir.  
  
 Bu durumda, özelliği ve öğe grupların sırasını ters özgün ileti geri yükler:  
  
```xml  
<Target Name="AfterBuild">  
    <ItemGroup>  
        <KeyFile Include="KeyFile.cs">  
            <Version>1.0.0.3</Version>  
        </KeyFile>  
    </ItemGroup>  
    <PropertyGroup>  
        <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
    </PropertyGroup>  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 Değeri `KeyFileVersion` "1.0.0.3" ve değil "@('% (sürüm)' KeyFile ->)". İleti görevi şu ileti görüntülenir:  
  
```  
KeyFileVersion: 1.0.0.3  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş kavramlar](../msbuild/msbuild-advanced-concepts.md)