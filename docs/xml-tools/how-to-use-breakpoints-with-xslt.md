---
title: 'Nasıl yapılır: kesme noktaları XSLT ile kullanma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba1c3a5e2001726c0f082bf17d279eb22a03fc86
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-breakpoints-with-xslt"></a>Nasıl yapılır: kesme noktaları XSLT ile kullanma

XSLT stil sayfasını veya XML kaynak belge kesme noktaları ayarlayabilirsiniz. Ayarlarsanız bir kesme noktası etikette yürütme kesme başladığında, kaynak satırı bilgileri içeren sonraki ifadeye taşınır.

Daha fazla bilgi için bkz: [hata ayıklama temelleri: kesme noktaları](../debugger/using-breakpoints.md).

## <a name="set-a-breakpoint-in-a-style-sheet"></a>Bir stil sayfanızda bir kesme noktası ayarlama

Kesme noktaları başlangıç etiketleri, bitiş etiketleri ve XSLT stil sayfasını metin düğümleri üzerinde ayarlanabilir. Kesme noktaları ayrıca kod bir betik bloğu içinde ayarlanabilir.

### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>Bir stil sayfanızda bir kesme noktası ayarlamak için

1.  Stil sayfası XML düzenleyicisinde açın.

2.  Kesme noktası konumda imleci getirin, sağ tıklayın, fareyle **kesme noktası**, tıklatıp **kesme noktası Ekle**.

3.  Gözat düğmesine (**...** ) üzerinde **giriş** belge penceresinin alan.

4.  XML kaynak belge bulun ve tıklatın **açık**.

     XSLT dönüşümü için kullanılan kaynak belge dosyasını ayarlar.

5.  Tıklatın **hata ayıklama XSL** XML Düzenleyicisi araç çubuğunda.

## <a name="set-a-breakpoint-in-an-xml-source-document"></a>Bir XML kaynağını belgede bir kesme noktası ayarlayın

Kesme noktaları öğeleri, öznitelikleri, düğüm ad, açıklama, işlem yönergesi ve XML kaynak belgesinin metin düğümleri ayarlayabilirsiniz. Belge düğümü veya üst öğesinden devralınan bir ad alanı düğümünde bir kesme noktası ayarlanamıyor.

### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>Bir XML kaynağını belgesinde bir kesme noktası ayarlamak için

1.  XML belgesi XML düzenleyicisinde açın.

2.  Kesme noktası konumda imleci getirin, sağ tıklayın, fareyle **kesme noktası**, tıklatıp **kesme noktası Ekle**.

3.  Gözat düğmesine (**...** ) üzerinde **stil** belge penceresinin alan.

4.  XML kaynak belge bulun ve tıklatın **açık**.

     XSLT dönüşümü için kullanılan kaynak belge dosyasını ayarlar.

5.  Tıklatın **hata ayıklama XSL** XML Düzenleyicisi araç çubuğunda.

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek Yol: XSLT Stil Sayfasında Hata Ayıklama](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)