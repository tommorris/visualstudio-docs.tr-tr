---
redirect_url: /visualstudio/ide/logical-operators-in-search-expressions
ms.openlocfilehash: fe896af873197c95a4b226396e0b6333fdc40cfa
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
Başlık: "arama ifadelerindeki Gelişmiş arama işleçleri | Microsoft Docs"MS.özel:" "ms.date:" 06/02/2017"ms.reviewer:" "MS.Paket:" "ms.technology: 
  - "vs Yardım Görüntüleyicisi" ms.tgt_pltfrm: "" ms.topic: "makale" helpviewer_keywords: 
  - "Yardım Görüntüleyicisi, anahtar sözcük arama"
  - "Yardım Görüntüleyicisi, kod arama"
  - "Yardım Görüntüleyicisi programlama dili göre kod arama"
  - "Yardım Görüntüleyicisi, başlık arama"
  - "kod arama [Yardım Görüntüleyicisi]"
  - "[Yardım Görüntüleyicisi] başlıkları arama" ms.assetid: 0cdc1746-8481-45ec-9c53-d0d89cdcbd5e caps.latest.revision: 9 Yazar: "gewarren" ms.author: "gewarren" Yöneticisi: ghogen
---
# <a name="advanced-search-operators-in-search-expressions"></a>Arama işleçlerini arama ifadelerindeki Gelişmiş
Yardım Görüntüleyici'de Gelişmiş arama işleçleri kullanarak için arama terimi aramak için bir konu başlığı nereye belirterek içerik için aramanızı iyileştirebilirsiniz. Aşağıdaki tabloda dört kullanılabilen gelişmiş arama işleçleri açıklar.

|Aramak için|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|Örnek|Sonuç|  
|-------------------|---------|-------------|------------|  
|Konu Başlığı'nda terim|Başlık:|Başlık: binaryreader|Başlıklarında "binaryreader" içeren konulardır.|  
|Kod örneğinde bir terim|Kod:|Kod: readdouble|Kod örneğinde "readdouble" içeren konulardır.|  
|Belirli bir programlama dili örneği vadede|Kod: vb:|Kod: vb:string|Visual Basic kod örneğinde "dize" içeren konulardır.|  
|Özel dizin anahtar sözcüğü ile ilişkili bir konu|anahtar sözcük:|anahtar sözcüğü: readbyte|"Readbyte" dizin anahtar sözcüğü ile ilgili konular.|  

> [!WARNING]
>  Bunları tanıyabilmesi için Gelişmiş arama işleçleri son iki nokta üst üste ve iki nokta üst üste arama motoru için önce boşluk olmaması ile girmeniz gerekir.    

## <a name="programming-languages-for-code-examples"></a>Kod örnekleri için programlama dilleri
Kodu kullanabilirsiniz: çeşitli programlama dilleri, ancak hiçbirini hakkında içeriği bulmak için işleci yalnızca bir programlama dili etiketi ile işaretlenmiş içerik için sonuçları döndürür. Belirli bir programlama dil için örnekler döndürmek için aşağıdaki programlama dili değerlerden birini kullanın:  

|Programlama dili|Arama işleci sözdizimi|  
|--------------------|---------|  
|Visual Basic|Kod: vb<br/>Kod: visualbasic'tir|  
|C#|Kod: c#<br/>Kod: csharp|  
|C++|Kod: cpp<br/>Kod: c ++<br/>Kod: cplusplus|  
|F#|Kod: f #<br/>Kod: fsharp|  
|JavaScript|Kod: javascript<br/>Kod: js|  
|XAML|Kod: xaml|
