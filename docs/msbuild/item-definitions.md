---
title: "Öğe tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: msbuild, item definitions
ms.assetid: 8e3dc223-f9e5-4974-aa0e-5dc7967419cb
caps.latest.revision: "21"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a7df40a697bb294e369964fb6a4252b884794aea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="item-definitions"></a>Öğe Tanımları
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]2.0 kullanarak proje dosyalarını öğelerde statik bildirimi etkinleştirir [ItemGroup](../msbuild/itemgroup-element-msbuild.md) öğesi. Ancak, meta veriler için tüm öğeleri aynı olsa bile, meta verileri yalnızca öğe düzeyinde eklenebilir. İtibariyle [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5, adlandırılmış bir proje öğesi [Itemdefinitiongroup](../msbuild/itemdefinitiongroup-element-msbuild.md) bu sınırlamaya üstesinden gelen. *Itemdefinitiongroup* adlandırılmış öğe türü içindeki tüm öğeler için varsayılan meta veri değerlerini ekleyin öğe tanımları kümesini tanımlamasına olanak tanır.  
  
 *Itemdefinitiongroup* öğesi görünür hemen sonra [proje](../msbuild/project-element-msbuild.md) proje dosyası öğesidir. Öğe tanımları aşağıdaki işlevleri sağlar:  
  
-   Genel varsayılan meta veri öğeleri dışında bir hedef için tanımlayabilirsiniz. Diğer bir deyişle, aynı meta verileri belirtilen türde tüm öğeler için geçerlidir.  
  
-   Birden fazla tanımı öğesi türlerine sahip olabilir. Ek meta veri belirtimleri türüne eklendiğinde, son belirtimi önceliklidir. \(Meta veri özelliklerini izleyin aynı alma sırada izler.\)  
  
-   Meta veri olabilir eklenebilir. Örneğin, CDefines değerleri koşullu olarak ayarlanan özellikler bağlı olarak toplanır. Örneğin, `MT;STD_CALL;DEBUG;UNICODE`.  
  
-   Meta veri kaldırılabilir.  
  
-   Koşullar, meta veri ekleme denetlemek için kullanılabilir.  
  
## <a name="item-metadata-default-values"></a>Öğe meta verileri varsayılan değerler  
 Bir Itemdefinitiongroup tanımlanan öğe meta verileri yalnızca bir varsayılan meta verilerin bildirimidir. Meta veri değerleri içeren bir ItemGroup kullanan bir madde tanımlamadığınız sürece meta verileri geçerli değildir.  
  
> [!NOTE]
>  Birçok bu konudaki örnekler, bir Itemdefinitiongroup öğesi gösterilen ancak karşılık gelen ItemGroup tanımına daha anlaşılır olması için atlanır.  
  
 Bir ItemGroup açıkça tanımlanmış meta verileri Itemdefinitiongroup meta veriler daha önceliklidir. Itemdefinitiongroup meta veriler, yalnızca bir ItemGroup tanımsız meta veriler için uygulanır. Örneğin:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <n>n1</n>  
    </i>        
</ItemDefinitionGroup>  
<ItemGroup>  
    <i Include="a">  
        <o>o1</o>  
        <n>n2</n>  
    </i>  
</ItemGroup>  
```  
  
 Bu örnekte, "m" meta veri öğesi "i" tarafından açıkça tanımlanmadığından varsayılan meta veri "m" "i" öğesine uygulanır. Ancak, meta verileri "n" "i" öğe tarafından zaten tanımlı olduğu için varsayılan meta veri "n" öğesi "i" uygulanmıyor.  
  
> [!NOTE]
>  XML öğesi ve parametre adları olan durum\-hassas. Öğe meta verileri ve madde\/özellik adları büyük/küçük harf olmayan\-hassas. Bu nedenle, yalnızca örneğe göre farklı adlara sahip Itemdefinitiongroup öğeleri aynı ItemGroup değerlendirilmelidir.  
  
## <a name="value-sources"></a>Değer kaynakları  
 Bir Itemdefinitiongroup tanımlı meta veriler için değerleri aşağıdaki gibi birçok farklı kaynaklardan gelebilir:  
  
-   PropertyGroup özelliği  
  
-   Bir Itemdefinitiongroup öğesinden  
  
-   Itemdefinitiongroup öğesi üzerinde öğesi dönüştürme  
  
-   Ortam değişkeni  
  
-   Genel özellik \(MSBuild.exe komut satırından\)  
  
-   Ayrılmış özelliği  
  
-   İyi\-metadata bir öğe üzerinde bir Itemdefinitiongroup bilinen  
  
-   CDATA bölümü \< \! \[CDATA\[burada bir şey yok ayrıştırılır\]\]\>  
  
> [!NOTE]
>  Itemdefinitiongroup öğeleri ItemGroup öğeleri önce işlendiğinden bir ItemGroup öğesi meta verilerini bir Itemdefinitiongroup meta verileri bildiriminde kullanışlı değildir.  
  
## <a name="additive-and-multiple-definitions"></a>ADDITIVE ve birden çok tanımları  
 Tanımları ekleme veya birden çok ItemDefinitionGroups kullanırken aşağıdakileri unutmayın:  
  
-   Ek meta veri belirtimine türüne eklenir.  
  
-   Son belirtimi önceliklidir.  
  
 Birden çok ItemDefinitionGroups varsa, her sonraki belirtimi önceki tanımına meta verilerini ekler. Örneğin:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <n>n1</n>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <o>o1</o>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 Bu örnekte, "m" ve "n" için "o" meta veri eklenir.  
  
 Ayrıca, önceden tanımlanmış meta veri değerlerinin de eklenebilir. Örneğin:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m>%(m);m2</m>  
    </i>  
</ItemDefinitionGroup>    
```  
  
 Bu örnekte, "m" meta verileri için önceden tanımlanmış değer \(m1\) yeni değere eklenen \(m2\), böylece son değeri "m1; m2".  
  
> [!NOTE]
>  Bu ayrıca aynı Itemdefinitiongroup ortaya çıkabilir.  
  
 Önceden tanımlanmış meta verileri geçersiz kıldığınızda, son belirtimi önceliklidir. Aşağıdaki örnekte, "m" meta veri son değerini "m1" "m1a" gider.  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m>m1a</m>  
    </i>  
</ItemDefinitionGroup>    
```  
  
## <a name="using-conditions-in-an-itemdefinitiongroup"></a>Koşul bir Itemdefinitiongroup kullanma  
 Meta veri ekleme denetlemek için bir Itemdefinitiongroup koşulları kullanabilirsiniz. Örneğin:  
  
```xml  
<ItemDefinitionGroup Condition="'$(Configuration)'=='Debug'">  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 Bu durumda, yalnızca "Yapılandırma" özelliğinin değeri "Hata ayıklama" ise varsayılan meta veri "m1" "i" öğede dahil edilir.  
  
> [!NOTE]
>  Yalnızca yerel meta veri başvurularını koşullarında desteklenir.  
  
 Bir önceki Itemdefinitiongroup içinde tanımlanan meta veri öğesi, tanım grubu yerel başvurusudur. Başvuru kapsamı olan öğesi başka bir deyişle,\-belirli. Örneğin:  
  
```xml  
<ItemDefinitionGroup>  
    <test>  
        <yes>1</yes>  
    </test>  
    <i> 
        <m>m0</m>
        <m Condition="'%(test.yes)'=='1'">m1</m>  
    </i>  
</ItemDefinitionGroup>  
  
```  
  
Yukarıdaki örnekte, "i" öğesi "test" kendi koşulunda öğesi başvurur. Hiçbir zaman başka bir öğenin meta verilerde bir Itemdefinitiongroup boş dize olarak başvuru MSBuild yorumlar bu koşul true olur. Bu nedenle, "m" "m0" ayarlanır
 
```xml 
  <ItemDefinitionGroup>
    <i>
      <m>m0</m>
      <yes>1</yes>
      <m Condition="'%(i.yes)'=='1'">m1</m>
    </i>
  </ItemDefinitionGroup>

```

Koşul başvuruları "i" öğesi olarak yukarıdaki örnekte, "m" "m1" değerine ayarlanır 's "Evet" öğesi için meta veri değeri 
  
## <a name="overriding-and-deleting-metadata"></a>Geçersiz kılma ve meta verileri silme  
 Itemdefinitiongroup öğesi tanımlanan meta veriler bir sonraki Itemdefinitiongroup öğesi meta veri değeri için boş ayarlayarak geçersiz kılınabilir. Bir meta veri öğesi boş bir değer olarak ayarlayarak da etkili bir şekilde silebilirsiniz. Örneğin:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m></m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 "İ" öğesi hala "m" meta veri içeriyor, ancak değeri şimdi boştur.  
  
## <a name="scope-of-metadata"></a>Meta veri kapsamı  
 Tanımlanmış olan her yerde ItemDefinitionGroups tanımlı ve genel özellikleri genel kapsama sahip. Varsayılan meta veri bir Itemdefinitiongroup tanımlarında self olabilir\-başvuru. Örneğin, aşağıdaki basit meta verileri başvuru kullanır:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <m>%(m);m2</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 Bir tam meta verileri başvuru da kullanılabilir:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
      <m>m1</m>  
      <m>%(i.m);m2</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 Ancak, aşağıdakiler geçerli değil:  
  
```xml  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <m>@(x)</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 ' Den başlayarak [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5, ItemGroups de olabilir kendini\-başvuru. Örneğin:  
  
```xml  
<ItemGroup>  
    <item Include="a">  
        <m>m1</m>  
        <m>%(m);m2</m>  
    </item>  
</ItemGroup>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Toplu işleme](../msbuild/msbuild-batching.md)
