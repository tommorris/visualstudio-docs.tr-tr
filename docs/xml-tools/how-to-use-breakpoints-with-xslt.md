---
title: "Nasıl yapılır: kesme noktaları XSLT ile kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf7bbc2c-71dc-4cac-a6fc-add6b27d92ed
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8c077cab7bf02023d0bfb1714940f98020600477
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-breakpoints-with-xslt"></a>Nasıl yapılır: kesme noktaları XSLT ile kullanma
XSLT stil sayfasını veya XML kaynak belge kesme noktaları ayarlayabilirsiniz. Ayarlarsanız bir kesme noktası etikette yürütme kesme başladığında, kaynak satırı bilgileri içeren sonraki ifadeye taşınır.  
  
 Daha fazla bilgi için bkz: [hata ayıklama temelleri: kesme noktaları](http://msdn.microsoft.com/en-us/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e).  
  
## <a name="set-a-breakpoint-in-a-style-sheet"></a>Bir stil sayfanızda bir kesme noktası ayarlama  
 Kesme noktaları başlangıç etiketleri, bitiş etiketleri ve XSLT stil sayfasını metin düğümleri üzerinde ayarlanabilir. Kesme noktaları ayrıca kod bir betik bloğu içinde ayarlanabilir.  
  
#### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>Bir stil sayfanızda bir kesme noktası ayarlamak için  
  
1.  Stil sayfası XML düzenleyicisinde açın.  
  
2.  Kesme noktası konumda imleci getirin, sağ tıklayın, fareyle **kesme noktası**, tıklatıp **kesme noktası Ekle**.  
  
3.  Göz at düğmesine Gözat (**...** ) üzerinde **giriş** belge penceresinin alan.  
  
4.  XML kaynak belge bulun ve tıklatın **açık**.  
  
     XSLT dönüşümü için kullanılan kaynak belge dosyasını ayarlar.  
  
5.  Tıklatın **hata ayıklama XSL** XML Düzenleyicisi araç çubuğunda.  
  
## <a name="set-a-breakpoint-in-an-xml-source-document"></a>Bir XML kaynağını belgede bir kesme noktası ayarlayın  
 Kesme noktaları öğeleri, öznitelikleri, düğüm ad, açıklama, işlem yönergesi ve XML kaynak belgesinin metin düğümleri ayarlayabilirsiniz. Belge düğümü veya üst öğesinden devralınan bir ad alanı düğümünde bir kesme noktası ayarlanamıyor.  
  
#### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>Bir XML kaynağını belgesinde bir kesme noktası ayarlamak için  
  
1.  XML belgesi XML düzenleyicisinde açın.  
  
2.  Kesme noktası konumda imleci getirin, sağ tıklayın, fareyle **kesme noktası**, tıklatıp **kesme noktası Ekle**.  
  
3.  Göz at düğmesine Gözat (**...** ) üzerinde **stil** belge penceresinin alan.  
  
4.  XML kaynak belge bulun ve tıklatın **açık**.  
  
     XSLT dönüşümü için kullanılan kaynak belge dosyasını ayarlar.  
  
5.  Tıklatın **hata ayıklama XSL** XML Düzenleyicisi araç çubuğunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: bir XSLT stil sayfası hata ayıklama](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)