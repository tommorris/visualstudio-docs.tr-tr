---
title: Dönüştürülecek kodu yeniden bir döngünün foreach deyimi
ms.date: 05/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 34758473bcbee8ccad7d9dff9df2f1478ca1202c
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="refactoring-to-convert-between-a-for-loop-and-a-foreach-statement"></a>Yeniden düzenleme arasında dönüştürme için bir döngü için ve foreach deyimi

Bu yapan yeniden düzenlemeler geçerlidir:

- C#

## <a name="convert-a-for-loop-to-a-foreach-statement"></a>Dönüştürme bir döngünün foreach deyimi

Varsa bir [için](/dotnet/csharp/language-reference/keywords/for) döngü kodunuzda bu yeniden düzenleme için dönüştürmek için kullanabileceğiniz bir [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) deyimi.

### <a name="why-convert"></a>Neden Dönüştür

Dönüştürme isteyebileceğiniz neden bir [için](/dotnet/csharp/language-reference/keywords/for) döngüsü bir [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) deyimi içerir:

- Öğeye erişmek için bir dizin olarak dışında döngü içinde yineleme sayısı değişkeni kullanmayın.

- Kodunuzu basitleştiren ve Başlatıcı, koşul ve yineleme deyimleri mantık hataları olasılığını azaltmak istiyor.

### <a name="how-to-use-it"></a>Nasıl kullanılacağını

1. İlk satırında imlecinizi yerleştirin `for` döngü.

1. Tuşuna **Ctrl**+**.** veya tornavida ![tornavida simgesi](../media/screwdriver-icon.png) kod dosyasının kenar boşluğunda simgesi.

   ![Foreach menüye dönüştürme](media/convert-to-foreach.png)

1. Seçin **'foreach' Dönüştür**. Ya da seçin **Önizleme değişiklikleri** açmak için [Değişiklikleri Önizle](../../ide/preview-changes.md) iletişim ve ardından **Uygula**.

## <a name="convert-a-foreach-statement-to-a-for-loop"></a>Foreach deyimi için dönüştürme bir döngü için

Varsa bir [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) kodunuzu deyiminde, bu yeniden düzenleme dönüştürebilir için kullanabileceğiniz bir [için](/dotnet/csharp/language-reference/keywords/for) döngü.

### <a name="why-convert"></a>Neden Dönüştür

Dönüştürme isteyebileceğiniz neden bir [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) ifadesine bir [için](/dotnet/csharp/language-reference/keywords/for) döngü içerir:

- Daha fazlasını öğesi erişmek için yineleme sayısı değişkeni döngü içinde kullanmak istediğiniz.

- Olduğunuz [çok boyutlu bir dizi yineleme](/dotnet/csharp/programming-guide/arrays/using-foreach-with-arrays) ve dizi öğeleri hakkında daha fazla denetime istiyor.

### <a name="how-to-use-it"></a>Nasıl kullanılacağını

1. İlk satırında imlecinizi yerleştirin `foreach` deyimi.

1. Tuşuna **Ctrl**+**.** veya tornavida ![tornavida simgesi](../media/screwdriver-icon.png) kod dosyasının kenar boşluğunda simgesi.

   ![Menü için Dönüştür](media/convert-to-for.png)

1. Seçin **'için' Dönüştür**. Ya da seçin **Önizleme değişiklikleri** açmak için [Değişiklikleri Önizle](../../ide/preview-changes.md) iletişim ve ardından **Uygula**.

1. Yeniden düzenleme yeni bir yineleme sayısı değişkeni oluşturduğundan **yeniden adlandırma** Kutusu Düzenleyicisi'ni sağ üst köşesinde görüntülenir. Değişkeni için farklı bir ad seçmek istiyorsanız, yazın ve sonra basın **Enter** veya seçin **Uygula** içinde **yeniden adlandırma** kutusu. Yeni bir ad seçin istemiyorsanız basın **Esc** veya seçin **Uygula** kapatmak için **yeniden adlandırma** kutusu.

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)