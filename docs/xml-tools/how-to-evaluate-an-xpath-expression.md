---
title: 'Nasıl yapılır: bir XPath ifadesi değerlendir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f2956e0c19e7cf50fdde39765bc5b26112986b84
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-evaluate-an-xpath-expression"></a>Nasıl yapılır: bir XPath ifadesi değerlendir

XPath ifadelerle değerlendirebilir **QuickWatch** iletişim kutusu. XPath ifadesi W3C XPath 1.0 öneri göre geçerli olmalıdır. Geçerli XSLT bağlamı — diğer bir deyişle, `self::node()` düğümünde **Yereller** penceresi — XPath ifadesi değerlendirme bağlamı sağlar.

 Aşağıdaki listede, hangi işlevlerin bir XPath ifadesi hesaplanırken desteklenen açıklanmaktadır:

-   Yerleşik XPath işlevleri desteklenir.

-   Yerleşik XSLT işlevleri desteklenmez.

-   Kullanıcı tanımlı işlevler desteklenmez.

> [!NOTE]
> Aşağıdaki yordam belowAvg.xsl ve books.xml dosyalarından kullanır [izlenecek yol: bir XSLT stil sayfası hata ayıklama](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md) konu.

## <a name="to-evaluate-an-xpath-expression"></a>Bir XPath ifadesi değerlendirmek için

1.  Kesme noktasında Ekle `xsl:if` başlangıç etiketi.

2.  Tıklatın **hata ayıklama XSL** XML Düzenleyicisi araç çubuğunda.

     Hata ayıklayıcı başlar ve üzerinde sonları `xsl:if` etiketi.

3.  Sağ tıklatıp **QuickWatch**.

     **QuickWatch** iletişim kutusu görüntülenir.

4.  Girin `./price/text()` içinde **ifade** alanını **QuickWatch** iletişim kutusu ve tıklatın **yeniden**.

     Geçerli kitap düğümünün fiyat görünür **değeri** kutusu.

5.  XPath ifadesi değiştirme `./price/text() < $bookAverage` tıklatıp **yeniden**.

     **Değeri** kutusu gösterir XPath ifadesi hesaplandığında sonucunu `true`.

## <a name="see-also"></a>Ayrıca Bkz.

- [XSLT Hatalarını Ayıklama](../xml-tools/debugging-xslt.md)