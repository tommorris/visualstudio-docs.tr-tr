---
title: 'Nasıl yapılır: virgülle ayrılmış bir öğe listesini görüntüleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, separating items with semicolons
- MSBuild, formatting item collections
ms.assetid: 3cae844c-7c6d-4144-82dc-efad10ba458f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a79e8c0f21a63bd5b64af69c2bf9778c07822d83
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-display-an-item-list-separated-with-commas"></a>Nasıl Yapılır: Virgülle Ayrılmış Bir Öğe Listesini Görüntüleme
Öğe ile çalışırken listeler [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]), bu öğe listelerini içeriğini okumak kolay bir şekilde görüntülemek bazen yararlıdır. Veya bir özel ayırıcı dizeyle ayrılmış öğeleri listesini alır bir görev olabilir. Her iki durumda, bir öğe listesi için bir ayırıcı dize belirtebilirsiniz.  
  
## <a name="separating-items-in-a-list-with-commas"></a>Bir listedeki öğeleri virgül ile ayırarak  
 Varsayılan olarak, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] listedeki öğeleri ayırmak için noktalı virgül kullanır. Örneğin, göz önünde bulundurun bir `Message` öğesi şu değere sahip:  
  
 `<Message Text="This is my list of TXT files: @(TXTFile)"/>`  
  
 Zaman `@(TXTFile)` öğe listesi App1.txt, App2.txt ve App3.txt öğelerini içerir, ileti:  
  
 `This is my list of TXT files: App1.txt;App2.txt;App3.txt`  
  
 Varsayılan davranışı değiştirmek istiyorsanız, kendi ayırıcı belirtebilirsiniz. Bir öğe listesi ayırıcı belirtmek için sözdizimi aşağıdaki gibidir:  
  
 `@(ItemListName, '<separator>')`  
  
 Ayırıcı tek bir karakter veya bir dize olabilir ve tek tırnak içine alınmalıdır.  
  
#### <a name="to-insert-a-comma-and-a-space-between-items"></a>Virgül ve öğeleri arasında bir boşluk eklemek için  
  
-   Aşağıdakine benzer öğe gösterimini kullanın:  
  
     `@(TXTFile, ', ')`  
  
## <a name="example"></a>Örnek  
 Bu örnekte, [Exec](../msbuild/exec-task.md) görev Phrases.txt dosyasında belirtilen metin dizeleri bulmak için findstr aracını çalıştırır. Değişmez değer dizeleri belirtilir findstr komutta **. / c:** geçiş, bunu öğesi ayırıcı `/c:` öğeleri arasına eklenen `@(Phrase)` öğe listesi.  
  
 Bu örnekte, eşdeğer komut satırı komut şöyledir:  
  
 `findstr /i /c:hello /c:world /c:msbuild phrases.txt`  
  
```xml  
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