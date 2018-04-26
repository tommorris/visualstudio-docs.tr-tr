---
title: Metin Şablonu Denetim Blokları
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, template code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: f0fa4a3848fedae642c6471dd001933ca1b7d011
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="text-template-control-blocks"></a>Metin Şablonu Denetim Blokları
Denetim blokları çıktıyı değiştirmek için metin şablonunuzda kod yazmanıza olanak tanır. Kendi açılan parantezler göre ayırt edilen denetim blokları üç tür vardır:

-   `<# Standard control blocks #>` ifadeleri içerebilir.

-   `<#= Expression control blocks #>` ifadeleri içerebilir.

-   `<#+ Class feature control blocks #>` yöntemleri, alanlar ve özellikler içerebilir.

## <a name="standard-control-block"></a>Standart denetim bloğu
 Standart denetim blokları deyimleri içerir. Örneğin, aşağıdaki standart bloğu XML belgesinde tüm öznitelikleri adlarını alır:

```
<#@ assembly name="System.Xml.dll" #>
<#@ import namespace="System.Xml" #>

<#
    List<string> allAttributes = new List<string>();
    XmlDocument xDoc = new XmlDocument();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes.Count > 0)
    {
       foreach (XmlAttribute attr in attributes)
       {
           allAtributes.Add(attr.Name);
       }
     }
#>
```

 Bileşik deyim içindeki düz metin gibi katıştırmak `if` veya `for`. Örneğin, bu parçasını her döngü tekrarında bir çıktı satırı oluşturur:

```
<#
       foreach (XmlAttribute attr in attributes)
       {
#>
Found another one!
<#
           allAtributes.Add(attr.Name);
       }
#>
```

> [!WARNING]
>  Her zaman, {...} kullanın Katıştırılmış düz metin içeren iç içe geçmiş deyimler sınırlandırmak için. Aşağıdaki örnek düzgün çalışmayabilir:
>
>  `<# if (ShouldPrint) #> Some text. -- WRONG`
>
>  Bunun yerine, {kaşlı} gibi içermelidir:

```

<#
 if (ShouldPrint)
 {   //  "{" REQUIRED
#>
Some text.
<#
 }
#>

```

## <a name="expression-control-block"></a>İfade denetim bloğu
 İfade denetim blokları çıktı dosyasına yazılması için dizeleri sağlar kodu için kullanılır. Örneğin, yukarıdaki örnek ile kod bloğunu şu şekilde değiştirerek çıkış dosyasının özniteliklerin adlarıyla yazdırabilirsiniz:

```
<#
    XmlDocument xDoc = new XmlDocument();
    xDoc.Load(@"E:\CSharp\Overview.xml");
    XmlAttributeCollection attributes = xDoc.Attributes;
    if (attributes != null)
    {
       foreach (XmlAttribute attr in attributes)
       {
#><#= attr.Name #><#
       }
    }
#>
```

## <a name="class-feature-control-block"></a>Sınıf özelliği denetim bloğu
 Sınıf özelliği denetim blokları yöntemler, özellikler, alanlar veya bile iç içe geçmiş sınıflar, metin şablonuna eklemek için kullanabilirsiniz. Sınıf özelliği blokları en yaygın kullanımı metin şablonu diğer bölümlerinde kodu için yardımcı işlevleri sağlamaktır. Örneğin, aşağıdaki sınıf özelliği bloğu öznitelik adı ilk harfini büyük yapar (veya adı boşluk içeriyorsa, her sözcüğün ilk harfini büyük yapar):

```
<#@ import namespace="System.Globalization" #>
```

```
<#+
    private string FixAttributeName(string name)
    {
        return CultureInfo.CurrentCulture.TextInfo.ToTitleCase(name);
    }
#>
```

> [!NOTE]
>  Bir sınıf özelliği denetim bloğu standart denetim blokları aynı şablon dosyasında gelmelidir değil. Ancak, bu kısıtlama kullanmanın sonucu için geçerli değildir `<#@include#>` yönergeleri. Eklenen her dosya sınıf özelliği bloklarla ardından standart blokları olabilir.

 Bir sınıf özelliği denetim bloğu metin ve ifade bloklarında gömerek çıktı oluşturan bir işlev oluşturabilirsiniz. Örneğin:

```
<#+
    private void OutputFixedAttributeName(string name)
    {
#>
 Attribute:  <#= CultureInfo.CurrentCulture.TextInfo.ToTitleCase(name) #>
<#+  // <<< Notice that this is also a class feature block.
    }
#>
```

 Bu işlev, standart bir blok veya başka bir sınıf özelliği bloğu çağırabilirsiniz:

```
<# foreach (Attribute attribute in item.Attributes)
{
  OutputFixedAttributeName(attribute.Name);
}
#>
```

## <a name="how-to-use-control-blocks"></a>Denetim blokları kullanma
 Tüm standart ve ifade denetim blokları (kod dahil şablonlarında dahil) tek bir şablonda forma birleştirilmiş tüm kod `TransformText()` yöntemi oluşturulan kod. (Diğer metin şablonları hakkında daha fazla bilgi için `include` yönerge, bkz: [T4 metin şablonu yönergeleri](../modeling/t4-text-template-directives.md).)

 Denetim blokları kullanırken aşağıdaki noktaları göz önünde bulundurmalıdır:

-   **Dili.** Bir metin şablonuna C# veya Visual Basic kodu kullanabilirsiniz. Varsayılan dil C# olmakla birlikte, Visual Basic ile belirtebilirsiniz `language` parametresinin `template` yönergesi. (Hakkında daha fazla bilgi için `template` yönerge, bkz: [T4 metin şablonu yönergeleri](../modeling/t4-text-template-directives.md).)

     Denetim bloklarında kullandığınız dilin dil veya bir metin şablonu oluştur metin biçimi ile ilgisi vardır. C# Visual Basic kodu veya bunun tersini de kullanarak oluşturabilirsiniz.

     Verilen metni şablonunda dahil olan tüm metin şablonları dahil olmak üzere, yalnızca bir dil kullanmak `include` yönergesi.

-   **Yerel değişkenler.** Standart ve ifade denetimindeki tüm kod blokları bu yana bir metin şablonuna tek bir yöntem olarak oluşturulur ve yerel değişken adlarıyla çakışmalar olduğundan emin olmanız gerekir. Diğer metin şablonları ekliyorsanız, değişken adları dahil tüm şablonları arasında benzersiz olduğundan emin olmanız gerekir. Bunu sağlamanın bir yolu, bir dize içinde bildirilen metin şablonu tanımlayan her yerel değişken adına eklemektir.

     Özellikle birden çok metin şablonları eklerken, bunları bildirirken duyarlı değerleri için yerel değişkenleri başlatmak için de iyi bir fikirdir.

-   **İç içe geçmiş denetim blokları.** Denetim blokları diğer içinde bulunmayabilir. Başka bir açmadan önce her zaman belirli denetim bloğu Sonlandır gerekir. Örneğin, aşağıdaki standart denetim bloğu bir parçası olarak bir ifade bloğundaki bazı metinleri yazdırmak nasıl gösterir.

    ```
    <#
    int x = 10;
    while (x-- > 0)
    {
    #>
    <#= x #>
    <# } #>
    ```

-   **Yeniden düzenleme.** Metin şablonlarınızı kısa ve kolay anlaşılır tutmak için sınıf özelliği bloklarındaki yardımcı işlevleri içine yeniden kullanılabilir kod Finansman veya devralır kendi metin şablonu sınıfı oluşturarak yinelenen kodlardan kaçının önerilir Microsoft.VisualStudio.TextTemplating.TextTransformation sınıfından.