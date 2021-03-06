---
title: 'Nasıl yapılır: virgülle ayrılmış bir öğe listesini görüntüleme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSBuild, separating items with semicolons
- MSBuild, formatting item collections
ms.assetid: 3cae844c-7c6d-4144-82dc-efad10ba458f
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62fbbfd7df89eee06f476a496b5a7c020c0ff211
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632314"
---
# <a name="how-to-display-an-item-list-separated-with-commas"></a>Nasıl Yapılır: Virgülle Ayrılmış Bir Öğe Listesini Görüntüleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: bir öğe listesi ayrılmış virgüllerle görüntüleme](https://docs.microsoft.com/visualstudio/msbuild/how-to-display-an-item-list-separated-with-commas).  
  
  
Öğesi ile çalışırken listeleri [!INCLUDE[vstecmsbuildengine](../includes/vstecmsbuildengine-md.md)] ([!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)]), bu öğe listeleri içeriğini okumak kolay bir şekilde görüntülemek bazen kullanışlıdır. Veya özel ayırıcı dize ile ayrılmış olan öğelerin listesini alan bir görev olabilir. Her iki durumda, bir öğe listesi için bir ayırıcı dize belirtebilirsiniz.  
  
## <a name="separating-items-in-a-list-with-commas"></a>Bir listedeki öğeler virgülle ayırma  
 Varsayılan olarak, [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] listedeki öğeleri ayırmak için noktalı virgül kullanır. Örneğin, bir `Message` şu değere sahip öğe:  
  
 `<Message Text="This is my list of TXT files: @(TXTFile)"/>`  
  
 Zaman `@(TXTFile)` öğe listesi App1.txt App2.txt ve App3.txt öğeleri içeren, ileti şöyle:  
  
 `This is my list of TXT files: App1.txt;App2.txt;App3.txt`  
  
 Varsayılan davranışı değiştirmek isterseniz, kendi ayırıcı belirtebilirsiniz. Bir öğe liste ayırıcı belirtmek için sözdizimi aşağıdaki gibidir:  
  
 `@(ItemListName, '<separator>')`  
  
 Ayırıcı, tek bir karakter veya bir dize olabilir ve tek tırnak içine alınmalıdır.  
  
#### <a name="to-insert-a-comma-and-a-space-between-items"></a>Bir virgül ve öğeleri arasına boşluk eklemek için  
  
-   Aşağıdakine benzer bir öğe gösterimini kullanın:  
  
     `@(TXTFile, ', ')`  
  
## <a name="example"></a>Örnek  
 Bu örnekte, [Exec](../msbuild/exec-task.md) görev Phrases.txt dosyasında belirtilen metin dizelerini bulmak için findstr aracını çalıştırır. Findstr komut içinde değişmez değer dizeleri tarafından belirtilen **/c:** geçiş, bunu öğesi ayırıcısı `/c:` bulunan öğeler arasındaki eklenen `@(Phrase)` öğe listesi.  
  
 Bu örnekte, eşdeğer komut satırı komutudur:  
  
 `findstr /i /c:hello /c:world /c:msbuild phrases.txt`  
  
```  
<Project DefaultTargets = "Find"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <Phrase Include="hello"/>  
        <Phrase Include="world"/>  
        <Phrase Include="msbuild"/>  
    </ItemGroup>  
  
    <Target Name = "Find">  
        <!-- Find some strings in a file -->  
        <Exec Command="findstr /i /c:@(Phrase, ' /c:') phrases.txt"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Öğeleri](../msbuild/msbuild-items.md)



