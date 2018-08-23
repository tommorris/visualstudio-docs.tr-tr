---
title: Kaçış için özel karakterler | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd69e5ad896db0949a380ac64d57dbc925b3878f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688159"
---
# <a name="special-characters-to-escape"></a>Kaçış İçin Özel Karakterler
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kaçış için özel karakterler](https://docs.microsoft.com/visualstudio/msbuild/special-characters-to-escape).  
  
  
Yalnızca özel bir anlamı, kullanıldıkları bağlam içinde oluşturulduysa özel karakterleri kaçış karakterleri eklenmelidir. Örneğin, yıldız işareti (*) bir özel karakter yalnızca bir öğe tanımının "Ekleme" ve "Dışarıda bırak" öznitelikleri veya bir çağrıda olduğu <xref:Microsoft.Build.Tasks.CreateItem>. Diğer durumlarda, yıldız işareti değişmez bir yıldız işareti kabul edilir. Her yerde proje dosyaları yıldız işareti kaçış gerekmez ancak bunun yapılması bir zararı şekilde yapar.  
  
 Gösterim % kullanmak*xx* özel karakter yerine burada *xx* ASCII karakter onaltılık değerini temsil eder. Örneğin, sabit karakter olarak yıldız işareti (*) kullanmak için değerini kullanın. `%2A`.  
  
 Kaçış için özel karakterler tam listesini aşağıdaki gibidir:  
  
|Karakter|Açıklama|  
|---------------|-----------------|  
|%|Meta veri başvurmak için kullanılan yüzde işareti.|  
|$|Dolar işareti, özellikleri başvurmak için kullanılır.|  
|@|Öğe listeleri başvurmak için kullanılan oturum sırasında.|  
|(|Açık parantez, listelerinde kullanılır.|  
|)|Kapatma parantezleri, listelerinde kullanılır.|  
|`|Kesme işareti (veya değer çizgisi), koşullar ve diğer ifadeleri kullanılır.|  
|;|Noktalı virgül, liste ayırıcı.|  
|?|Soru işareti, bir öğenin dahil edin/dışlayın bölümünde bir dosya belirtimi tanımlarken bir joker karakter.|  
|*|Yıldız işareti, bir öğenin dahil edin/dışlayın bölümünde bir dosya belirtimi tanımlarken bir joker karakter.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: özel msbuild'de kaçış karakterleri](../msbuild/how-to-escape-special-characters-in-msbuild.md)   
 [MSBuild Başvurusu](../msbuild/msbuild-reference.md)



