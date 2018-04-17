---
title: Metin şablonlarında çıkış sıraları kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, escape sequences
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7362d6f4fa722c9ef7a119b22028baad418fbf85
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Nasıl yapılır: Çıkış Sıraları Kullanarak Şablonlardan Şablon Oluşturma](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)