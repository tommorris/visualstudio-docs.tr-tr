---
title: Mantıksal işleçler ve arama ifadelerindeki Gelişmiş operatörler
ms.date: 11/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: reference
helpviewer_keywords:
- Help Viewer, logical operators in search
- logical operators in search [Help Viewer]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de351e019c4daacc61bbbdd2757b0f0d9a46e584
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31942847"
---
# <a name="logical-and-advanced-operators-in-search-expressions"></a>Arama ifadelerindeki mantıksal ve Gelişmiş işleçler

Mantıksal işleçler ve Gelişmiş arama işleçleri aramanızı Yardım içeriğinin için kullanabileceğiniz **Yardım Görüntüleyici**.

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
|Makale başlığı'nda terim|`title:`|`title:binaryreader`|Başlıklarında "binaryreader" içeren konulardır.|
|Kod örneğinde bir terim|`code:`|`code:readdouble`|Kod örneğinde "readdouble" içeren konulardır.|
|Belirli bir programlama dili örneği vadede|`code:vb:`|`code:vb:string`|Visual Basic kod örneğinde "dize" içeren konulardır.|
|Özel dizin anahtar sözcüğü ile ilişkili bir makale|`keyword:`|`keyword:readbyte`|"Readbyte" dizin anahtar sözcüğü ile ilgili konular.|

> [!IMPORTANT]
> Bunları tanıyabilmesi için Gelişmiş arama işleçleri son iki nokta üst üste ve iki nokta üst üste arama motoru için önce boşluk olmaması ile girmeniz gerekir.

### <a name="programming-languages-for-code-examples"></a>Kod örnekleri için programlama dilleri

Kullanabileceğiniz `code:` çeşitli programlama dillerini hiçbirini hakkında içeriği bulmak için işleci. Belirli bir programlama dili için örnekler döndürmek için aşağıdaki programlama dili değerlerden birini kullanın:

|Programlama dili|Arama işleci sözdizimi|
|--------------------|---------|
|Visual Basic|`code:vb`<br/>`code:visualbasic`|
|C#|`code:c#`<br/>`code:csharp`|
|C++|`code:cpp`<br/>`code:c++`<br/>`code:cplusplus`|
|F#|`code:f#`<br/>`code:fsharp`|
|JavaScript|`code:javascript`<br/>`code:js`|
|XAML|`code:xaml`|

> [!NOTE]
> `code:` İşleci yalnızca genel kodu olarak işaretlenmiş içerik aksine bir programlama dili etiketi ile işaretlenmiş içerik bulur.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Konu Arama](how-to-search-for-topics.md)
- [Microsoft Yardım Görüntüleyicisi](microsoft-help-viewer.md)
