---
title: "Nasıl yapılır: alfa önceden çoğaltılmış olan doku verme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05348afa-f079-4f53-a05b-ecd91d13adab
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7b8b5c213a7184eaab0034ede6bc71acda496ba8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-export-a-texture-that-has-premultiplied-alpha"></a>Nasıl yapılır: Ön Çarpımlı Alfa kullanan Doku Dışa Aktarma
Görüntü içerik ardışık düzen önceden çoğaltılmış alfa dokuları kaynak görüntüden oluşturabilir. Bunlar kullanmak daha basit ve daha sağlamdır önceden çoğaltılmış alfa içermeyen dokuları olabilir.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Görüntü içerik ardışık düzen tarafından işlenmek üzere kaynak görüntü yapılandırma.  
  
-   Görüntü içerik önceden çoğaltılmış alfa oluşturmak için ardışık düzen yapılandırma.  
  
## <a name="premultiplied-alpha"></a>Önceden çoğaltılmış alfa  
 Önceden çoğaltılmış alfa texel'ın renk katkı ayırarak daha iyi fiziksel malzemeleri ışık gerçek etkileşim olabilmesinden dolayı Geleneksel, önceden çoğaltılmış olmayan alfa, birkaç avantaj sunar (ekler rengi Sahne) gelen kendi translucency (aracılığıyla sağlayan temel renk miktarı). Önceden çoğaltılmış alfa kullanmanın yararları bazıları şunlardır:  
  
-   İle önceden çoğaltılmış Alfa karışım ilişkilendirilebilir bir işlemdir; birden çok saydam dokuları karıştırma, bakılmaksızın aynı dokuları karıştırılan sipariş sonucudur.  
  
-   İle önceden çoğaltılmış Alfa karışım ilişkilendirilebilir yapısı nedeniyle, çok geçişi işleme saydam nesnelerin basitleştirilmiştir.  
  
-   Önceden çoğaltılmış alfa kullanarak, saf eklenebilir (göre ayarlama alfa sıfıra) karıştırma hem doğrusal olarak ara değerli karıştırma aynı anda elde edilebilir. Örneğin, bir parçacık sisteminde additively karışık yangın parçacık doğrusal ilişkilendirme kullanarak karıştırılan saydam bir Duman parçacık haline gelebilir. Önceden çoğaltılmış alfa yangın parçacık ayrı olarak Duman parçacık çizme ve çizim çağrıları arasında işleme durumunu değiştirmek gerekir.  
  
-   Önceden çoğaltılmış alfa kullanmak dokuları Sıkıştır içermeyen olandan daha yüksek kalitesiyle ve rengi kenarları sergilemesine yok — veya "etkin hale" — önceden çoğaltılmış alfa kullanmayan dokuları blend zaman sonuçlanabilir.  
  
#### <a name="to-create-a-texture-that-uses-premultiplied-alpha"></a>Önceden çoğaltılmış alfa kullanan bir doku oluşturmak için  
  
1.  Temel bir doku ile başlar. Varolan bir görüntü dosyası yüklemek ya da açıklandığı gibi oluşturmak [nasıl yapılır: temel bir doku oluşturma](../designers/how-to-create-a-basic-texture.md).  
  
2.  Görüntü içerik ardışık düzen tarafından işlenen doku dosyasını yapılandırın. İçinde **Çözüm Gezgini**, doku dosyası için kısayol menüsünü açın ve ardından **özellikleri**. Üzerinde **yapılandırma özellikleri**, **genel** sayfasında **öğesi türü** özelliğine **görüntü içerik ardışık düzen**. Olduğundan emin olun **içerik** özelliği ayarlanmış **Evet** ve **gelen hariç yapı** ayarlanır **Hayır**ve ardından  **Uygulama** düğmesi. **Görüntü içerik ardışık düzen** yapılandırması özellik sayfası görüntülenir.  
  
3.  Görüntü içerik önceden çoğaltılmış alfa oluşturmak için ardışık düzenini yapılandırın. Üzerinde **yapılandırma özellikleri**, **görüntü içerik ardışık düzen**, **genel** sayfasında **önceden çarpılan alfa biçimine dönüştürme** özelliğine **Evet (/ generatepremultipliedalpha)**.  
  
4.  Seçin **Tamam** düğmesi.  
  
 Projeyi derlerken görüntü içerik ardışık düzen kaynak görüntü çalışma biçiminden belirttiğiniz çıkış biçimine dönüştürür — bu görüntüyü dönüştürme önceden çoğaltılmış alfa biçimine içerir — ve sonucu için proje çıktı kopyalanır Dizin.