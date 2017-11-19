---
title: "Mantıksal işleçler ve Gelişmiş operatörler arama ifadeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help Viewer, logical operators in search
- logical operators in search [Help Viewer]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3378a554a9e576bde011a70916c48597218bb512
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="logical-and-advanced-operators-in-search-expressions"></a>Arama ifadelerindeki mantıksal ve Gelişmiş işleçler
Yardım Görüntüleyici'de Yardım içeriğinin aramanızı daraltmak için mantıksal işleçler ve Gelişmiş arama işleçleri kullanabilirsiniz.

## <a name="logical-operators"></a>Mantıksal işleçler
Mantıksal işleçler birden çok arama terimleri bir arama sorgusu birleştirilmelidir belirtin. Aşağıdaki tabloda, mantıksal işleçler AND, OR gösterir değil ve YAKININDA.
  
|Aramak için|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|Örnek|Sonuç|  
|-------------------|---------|-------------|------------|  
|Her iki terim aynı makaledeki|AND|DIB ve paleti|"DIB" ve "paleti" içeren konulardır.|  
|Bir makalede her iki terim|VEYA|Izgara veya vektör|"Izgara" veya "vektör" içeren konular.|  
|Aynı makalenin ikinci vadede olmadan ilk terimi|DEĞİL|"işletim sistemi" değil DOS|"İşletim sistemi" ancak değil "DOS" içeren konulardır.|  
|Birbirine yakın bir makaledeki her iki terim|YAKIN|Kullanıcı çekirdek yakın|İçindeki "kullanıcı" içeren konuları "çekirdek" yakınlığını kapatın.|  
  
> [!IMPORTANT]
> Mantıksal işleçler bunları tanıyabilmesi arama motoru için tümü büyük harfle girmeniz gerekir.

## <a name="advanced-operators"></a>Gelişmiş işleçler
Gelişmiş arama işleçleri için arama terimi aramak için bir makalede where belirterek içerik için aramanızı daraltın. Aşağıdaki tabloda dört kullanılabilen gelişmiş arama işleçleri açıklar.

|Aramak için|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|Örnek|Sonuç|  
|-------------------|---------|-------------|------------|  
|Makale başlığı'nda terim|Başlık:|Başlık: binaryreader|Başlıklarında "binaryreader" içeren konulardır.|  
|Kod örneğinde bir terim|Kod:|Kod: readdouble|Kod örneğinde "readdouble" içeren konulardır.|  
|Belirli bir programlama dili örneği vadede|Kod: vb:|Kod: vb:string|Visual Basic kod örneğinde "dize" içeren konulardır.|  
|Özel dizin anahtar sözcüğü ile ilişkili bir makale|anahtar sözcük:|anahtar sözcüğü: readbyte|"Readbyte" dizin anahtar sözcüğü ile ilgili konular.|  

> [!IMPORTANT]
> Bunları tanıyabilmesi için Gelişmiş arama işleçleri son iki nokta üst üste ve iki nokta üst üste arama motoru için önce boşluk olmaması ile girmeniz gerekir.    

### <a name="programming-languages-for-code-examples"></a>Kod örnekleri için programlama dilleri
Kullanabileceğiniz **kodu:** çeşitli programlama dillerini hiçbirini hakkında içeriği bulmak için işleci. Belirli bir programlama dili için örnekler döndürmek için aşağıdaki programlama dili değerlerden birini kullanın:  

|Programlama dili|Arama işleci sözdizimi|  
|--------------------|---------|  
|Visual Basic|Kod: vb<br/>Kod: visualbasic'tir|  
|C#|Kod: c#<br/>Kod: csharp|  
|C++|Kod: cpp<br/>Kod: c ++<br/>Kod: cplusplus|  
|F#|Kod: f #<br/>Kod: fsharp|  
|JavaScript|Kod: javascript<br/>Kod: js|  
|XAML|Kod: xaml|

> [!NOTE]
> **Kodu:** işleci yalnızca genel kodu olarak işaretlenmiş içerik aksine bir programlama dili etiketi ile işaretlenmiş içerik bulur. 
  
## <a name="see"></a>Bkz.  
[Nasıl yapılır: Konu Arama](how-to-search-for-topics.md)  
[Microsoft Yardım Görüntüleyicisi](microsoft-help-viewer.md)