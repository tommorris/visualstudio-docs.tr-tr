---
title: Biçim belirticiler hata ayıklayıcısında (C#) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- expressions [C#], formatting values
- variables [debugger], watch variable symbols
- symbols, watch variable formatting
- QuickWatch dialog box, using format specifiers
- specifiers, watch variable format
- QuickWatch dialog box, format specifiers in C#
- specifiers
- watch variable symbols
- Watch window, format specifiers in C#
- format specifiers, debugger
- debugger, format specifiers recognized by
ms.assetid: 345c8589-5f36-4d34-a58c-e56271687dd6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 0e8605671d1c245826ce6d699e91795fcd7ee32e
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756866"
---
# <a name="format-specifiers-in-c-in-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısında C# içindeki Biçim belirticileri
İçinde bir değer görüntülenir biçimini değiştirebilirsiniz **izleme** penceresi biçim belirticilerini kullanma. İçindeki Biçim belirticileri de kullanabilirsiniz **hemen** penceresinde **komutu** penceresi, [tracepoints](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints)ve hatta kaynak windows. Bu windows deyimde üzerinde duraklatmak, sonuç DataTip içinde görünür. DataTips DataTip görüntüsündeki biçim belirticisi yansıtır.  
  
 Bir biçim belirticisi kullanmak için virgül ve ifadeyi yazın. Sonra virgül, uygun belirleyici ekleyin.  
  
## <a name="using-format-specifiers"></a>Biçim belirticilerini kullanma  
 Aşağıdaki kodu varsa:  
  
```csharp  
{  
        int my_var1 = 0x0065;  
        int my_var2 = 0x0066;  
        int my_var3 = 0x0067;  
}  
```  
  
 Ekleme `my_var1` Gözcü penceresi değişken (hata ayıklama, **hata ayıklama > Windows > İzleme > İzleme 1**) ve görüntü onaltılık-ayarlayın (içinde **izleme** penceresinde, değişkeni sağ tıklayın ve seçin **onaltılı görüntü**). Şimdi **izleme** penceresi gösterir 0x0065 değeri içerir. Bkz sonra değişken adı, Ad sütununda, onaltılık bir tamsayı yerine ondalık bir tamsayı olarak ifade bu değere ondalık biçim belirteci eklemek için: **, d**. Değer sütunu artık ondalık değer 101 görüntüler  
  
 ![WatchFormatCSharp](../debugger/media/watchformatcsharp.png "WatchFormatCSharp")  
  
## <a name="format-specifiers"></a>Biçim belirticiler  
 Aşağıdaki tablo hata ayıklayıcı tarafından tanınan C# biçim belirticileri gösterir.  
  
|Belirleyici|Biçimi|Özgün izleme değeri|Görüntüler|  
|---------------|------------|--------------------------|--------------|  
|AC|Bir ifadenin değerlendirmesine zorlar. Örtük değerlendirme özellikleri ve dolaylı işlev çağrıları devre dışı bırakıldığında bu yararlı olabilir.|"Dolaylı İşlev değerlendirmesi kullanıcı tarafından devre dışı" iletisi|\<Değer >|  
|d|ondalık tamsayı|0x0065|101|  
|dinamik|Dinamik bir görünümü kullanarak belirtilen nesneyi görüntüler|Dinamik görünüm dahil olmak üzere bu nesnenin tüm üyelerini görüntüler|Yalnızca dinamik görünümü görüntüler|  
|h|onaltılık tamsayı|61541|0x0000F065|  
|Nq|tırnak işaretleri olmadan dize|"Dize my"|My dize|  
|nse|Davranış, biçimi değil belirtir. "Hiçbir yan etkisi" ifadesiyle değerlendirir. İfade yorumlanamayan ve yalnızca Değerlendirme sürümü (örneğin, bir işlev çağrısı) çözülebilir, bunun yerine bir hata görürsünüz.|Yok|Yok|
|gizli|Tüm genel ve genel olmayan üyeler görüntüler|Görüntüler Genel üyeler|Tüm üyeler görüntüler|  
|Ham|Ham öğesi düğümünde göründüğü gibi öğesi görüntüler. Proxy nesneleri yalnızca geçerli.|Sözlük\<T >|Sözlük ham görünümünü\<T >|  
|sonuçlar|Değişkeninin IEnumerable veya IEnumerable arabirimini uygulayan bir tür ile kullanılan\<T >, genellikle bir sorgu ifadesi sonucu. Sorgu sonucu içeren üyelerini görüntüler.|Tüm üyelerini görüntüler.|Üyeleri karşılamak görüntüler sorgunun koşullarını.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzleme ve QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Otomatik değişkenler ve yerel Windows](../debugger/autos-and-locals-windows.md)
