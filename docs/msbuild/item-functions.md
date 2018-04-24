---
title: Öğe işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, Item functions
ms.assetid: 5e6df3cc-2db8-4cbd-8fdd-3ffd03ac0876
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93c8a16b1ab15354deafc236d9f4845b051d58f7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="item-functions"></a>Öğe İşlevleri
MSBuild 4.0 ile başlayarak, görev ve hedeflerini kodu projede öğeleri hakkında bilgi almak için öğe işlevleri çağırabilir. Bu işlevler alma Distinct() öğeleri basitleştirmek ve öğeler arasında döngü daha hızlıdır.  
  
## <a name="string-item-functions"></a>Dize öğesi işlevleri  
 Herhangi bir öğeyi değer üzerinde çalışması için .NET Framework dize yöntemleri ve özellikleri kullanabilirsiniz. İçin <xref:System.String> yöntemleri, yöntem adını belirtin. İçin <xref:System.String> özellikleri, özellik adı "get_ sonra" belirtin.  
  
 Birden çok dizeleri olan öğeleri dize yöntemi veya özelliği her dizesi çalışır.  
  
 Aşağıdaki örnekte bu dize öğesi işlevlerinin nasıl kullanılacağı gösterilir.  
  
```xml  
<ItemGroup>  
    <theItem Include="andromeda;tadpole;cartwheel" />  
</ItemGroup>  
  
<Target Name = "go">  
    <Message Text="IndexOf  @(theItem->IndexOf('r'))" />  
    <Message Text="Replace  @(theItem->Replace('tadpole', 'pinwheel'))" />  
    <Message Text="Length   @(theItem->get_Length())" />  
    <Message Text="Chars    @(theItem->get_Chars(2))" />  
</Target>  
  
  <!--  
  Output:  
    IndexOf  3;-1;2  
    Replace  andromeda;pinwheel;cartwheel  
    Length   9;7;9  
    Chars    d;d;r  
  -->  
```  
  
## <a name="intrinsic-item-functions"></a>İç öğe işlevleri  
 Aşağıdaki tabloda öğeler için kullanılabilen iç işlevleri listeler.  
  
|İşlev|Örnek|Açıklama|  
|--------------|-------------|-----------------|  
|`Count`|`@(MyItem->Count())`|Öğelerin sayısını döndürür.|  
|`DirectoryName`|`@(MyItem->DirectoryName())`|Denk döndürür `Path.DirectoryName` her öğe için.|  
|`Distinct`|`@(MyItem->Distinct())`|Farklı olan döndürür öğeler `Include` değerleri. Meta veri göz ardı edilir. Karşılaştırma büyük/küçük harfe duyarlıdır.|  
|`DistinctWithCase`|`@(MyItem->DistinctWithCase())`|Farklı olan döndürür öğeler `itemspec` değerleri. Meta veri göz ardı edilir. Karşılaştırma büyük/küçük harfe duyarlıdır.|  
|`Reverse`|`@(MyItem->Reverse())`|Öğeleri ters sırada döndürür.|  
|`AnyHaveMetadataValue`|`@(MyItem->AnyHaveMetadataValue("MetadataName", "MetadataValue"))`|Döndürür bir `boolean` herhangi bir öğeyi belirtilen meta veriler ada ve değere sahip olup olmadığını belirtmek için. Karşılaştırma büyük/küçük harfe duyarlıdır.|  
|`ClearMetadata`|`@(MyItem->ClearMetadata())`|Öğeleri temizlenmiş bunların meta verilerini döndürür. Yalnızca `itemspec` korunur.|  
|`HasMetadata`|`@(MyItem->HasMetadata("MetadataName"))`|Belirtilen meta veri adı olan öğelerini döndürür. Karşılaştırma büyük/küçük harfe duyarlıdır.|  
|`Metadata`|`@(MyItem->Metadata("MetadataName"))`|Meta veri adı olan meta veri değerlerini döndürür.|  
|`WithMetadataValue`|`@(MyItem->WithMetadataValue("MetadataName", "MetadataValue"))`|Belirtilen meta veriler ad ve değer sahip öğeleri döndürür. Karşılaştırma büyük/küçük harfe duyarlıdır.|  
  
 Aşağıdaki örnek, iç öğesi işlevlerinin nasıl kullanılacağı gösterilir.  
  
```xml  
<ItemGroup>  
    <TheItem Include="first">  
        <Plant>geranium</Plant>  
    </TheItem>  
    <TheItem Include="second">  
        <Plant>algae</Plant>  
    </TheItem>  
    <TheItem Include="third">  
        <Plant>geranium</Plant>  
    </TheItem>  
</ItemGroup>  
  
<Target Name="go">  
    <Message Text="MetaData:    @(TheItem->Metadata('Plant'))" />  
    <Message Text="HasMetadata: @(theItem->HasMetadata('Plant'))" />  
    <Message Text="WithMetadataValue: @(TheItem->WithMetadataValue('Plant', 'geranium'))" />  
    <Message Text=" " />  
    <Message Text="Count:   @(theItem->Count())" />  
    <Message Text="Reverse: @(theItem->Reverse())" />  
</Target>  
  
  <!--   
  Output:  
    MetaData:    geranium;algae;geranium  
    HasMetadata: first;second;third  
    WithMetadataValue: first;third  
  
    Count:   3  
    Reverse: third;second;first  
  -->  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğeleri](../msbuild/msbuild-items.md)
