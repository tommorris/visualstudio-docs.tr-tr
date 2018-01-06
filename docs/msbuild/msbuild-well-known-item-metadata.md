---
title: "MSBuild tanınmış öğe meta verisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, item metadata
- MSBuild, well-known item metadata
ms.assetid: b5e791b5-c68f-4978-ad8a-9247d03bb6c0
caps.latest.revision: "12"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b2f48162ed4c37358980c40b5c71c4f955880358
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-well-known-item-metadata"></a>MSBuild Tanınmış Öğe Meta Verisi
Aşağıdaki tabloda her öğenin oluşturulduktan sonra atanan meta veriler açıklanmaktadır. Dosyayı eklemek için kullanılan her örnekte, aşağıdaki öğeyi bildirimi `C:\MyProject\Source\Program.cs` projesinde.  
  
```xml  
<ItemGroup>  
    <MyItem Include="Source\Program.cs" />  
</ItemGroup>  
```  
  
|Öğe meta verileri|Açıklama|  
|-------------------|-----------------|  
|%(FullPath)|Öğenin tam yolunu içerir. Örneğin:<br /><br /> `C:\MyProject\Source\Program.cs`|  
|%(RootDir)|Öğesinin kök dizini içerir. Örneğin:<br /><br /> `C:\`|  
|%(Filename)|Dosya adı uzantısı olmadan öğesi içeriyor. Örneğin:<br /><br /> `Program`|  
|%(Extension)|Dosya adı uzantısı öğenin içerir. Örneğin:<br /><br /> `.cs`|  
|%(RelativeDir)|Belirtilen yolu içeren `Include` özniteliği, en son ters eğik çizgi (\\). Örneğin:<br /><br /> `Source\`|  
|%(Directory)|Kök dizin olmadan öğenin dizini içerir. Örneğin:<br /><br /> `MyProject\Source\`|  
|%(RecursiveDir)|Varsa `Include` öznitelik joker karakter içeren \* \*, joker karakter değiştirir yolun bir kısmı bu meta veriler belirtir. Joker karakterler hakkında daha fazla bilgi için bkz: [nasıl yapılır: derleme dosyalarına seçin](../msbuild/how-to-select-the-files-to-build.md).<br /><br /> Varsa klasörü *C:\MySolution\MyProject\Source\\*  Program.cs, dosyayı içeren ve proje dosyası bu öğeyi içeriyorsa:<br /><br /> `<ItemGroup>`<br /><br /> `<MyItem Include="C:\**\Program.cs" />`<br /><br /> `</ItemGroup>`<br /><br /> ardından değeri `%(MyItem.RecursiveDir)` olacaktır *MySolution\MyProject\Source\\*.|  
|%(Identity)|Belirtilen öğe `Include` özniteliği... Örneğin:<br /><br /> `Source\Program.cs`|  
|%(ModifiedTime)|Zaman damgası öğesi değiştirildiği son zamandan içerir. Örneğin:<br /><br /> `2004-07-01 00:21:31.5073316`|  
|%(CreatedTime)|Öğesinin oluşturulduğu gelen zaman damgası içerir. Örneğin:<br /><br /> `2004-06-25 09:26:45.8237425`|  
|%(AccessedTime)|Zaman damgası öğesi erişilen son zamandan içerir.<br /><br /> `2004-08-14 16:52:36.3168743`|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğeleri](../msbuild/msbuild-items.md)   
 [Toplu işleme](../msbuild/msbuild-batching.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)