---
title: "Metin şablonlarında çıkış sıraları kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, escape sequences
ms.assetid: 36fff542-2f42-460f-a2d5-03fc76817f3b
caps.latest.revision: "29"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: fdf062c9b33dd4a160f54bba83991a3cdda7f0d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="using-escape-sequences-in-text-templates"></a>Metin Şablonlarında Çıkış Sıraları Kullanma
Metin şablonu etiketleri oluşturulacak metin şablonları ve (C# kodunda yalnızca) kaçış sıraları kullanabilirsiniz çıkış denetim karakterleri ve tırnak işaretleri.  
  
 Çıktı dosyası için bir standart kod bloğu için açık ve kapalı etiketler yazdırmak için etiketler gibi kaçış:  
  
```  
\<# ... \#>  
```  
  
 Diğer metin şablonu yönerge ve kod bloğu etiketleri ile aynı yapabilirsiniz.  
  
 Bir metin bloğunu metin şablonu etiketleri kaçınmak için kullanılan dizelerin içeriyorsa, aşağıdaki çıkış sıraları kullanma:  
  
-   Metin şablonu etiketi kaçış tarafından çift sayıda öncesinde varsa (\\) şablonu karakterleri ayrıştırıcısı kaçış karakterleri yarısı içerir ve bir metin şablonu etiketi olarak dizisi içerir. Örneğin, metin şablonu dört kaçış karakterleri varsa olacaktır iki "\\" oluşturulan dosyanın karakter.  
  
-   Metin şablonu etiketi kaçış tek sayıda tarafından öncesinde varsa (\\) karakterleri, şablonu ayrıştırıcısı içereceği yarısı "\\" karakterleri etiketi (\<# veya #>). Etiket metin şablonu etiketi olarak kabul değil.  
  
-   Bir kaçış varsa (\\) istediğiniz sırayla burada bir denetim karakteri veya (C# ' de yalnızca) teklifi çıkışları dışında başka herhangi bir yerde görünür karakter, karakter doğrudan çıktı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: çıkış sıraları kullanarak şablonlardan şablonlar oluşturma](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)