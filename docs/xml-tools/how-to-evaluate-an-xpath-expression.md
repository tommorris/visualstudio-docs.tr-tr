---
title: "Nasıl yapılır: bir XPath ifadesi değerlendirmek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d549afb96465590a21e516f649d860f23f4056f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-evaluate-an-xpath-expression"></a>Nasıl yapılır: bir XPath ifadesi değerlendir
XPath ifadelerle değerlendirebilir **QuickWatch** iletişim kutusu. XPath ifadesi W3C XPath 1.0 öneri göre geçerli olmalıdır. Geçerli XSLT bağlamı — diğer bir deyişle, `self::node()` düğümünde **Yereller** penceresi — XPath ifadesi değerlendirme bağlamı sağlar.  
  
 Aşağıdaki listede, hangi işlevlerin bir XPath ifadesi hesaplanırken desteklenen açıklanmaktadır:  
  
-   Yerleşik XPath işlevleri desteklenir.  
  
-   Yerleşik XSLT işlevleri desteklenmez.  
  
-   Kullanıcı tanımlı işlevler desteklenmez.  
  
> [!NOTE]
>  Aşağıdaki yordam belowAvg.xsl ve books.xml dosyalarından kullanır [izlenecek yol: bir XSLT stil sayfası hata ayıklama](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md) konu.  
  
### <a name="to-evaluate-an-xpath-expression"></a>Bir XPath ifadesi değerlendirmek için  
  
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
 [XSLT hata ayıklama](../xml-tools/debugging-xslt.md)