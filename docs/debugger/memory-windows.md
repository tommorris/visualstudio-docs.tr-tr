---
title: Hata ayıklayıcı değişkenleri için bellek görüntülemek | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.memory
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Memory window
- strings [Visual Studio], viewing
- debugger [Visual Studio], Memory window
- memory [Visual Studio], debugging
- debugging [Visual Studio], Memory window
- buffers, viewing
ms.assetid: 7f7a0439-10e4-4966-bb2d-51f04cda4fe2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 550c5ffe641fac5bb2d080a892143bf3ff9744b0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="use-the-memory-windows-in-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısında bellek pencerelerini kullanma
**Bellek** pencere, uygulamanız tarafından kullanılan bellek alanına bir görünüm sağlar. **İzleme** penceresinde **QuickWatch** iletişim kutusu, **otomobiller** penceresinde ve **Yereller** penceresini olan değişkenlerinin içeriğini göster belirli konumlara bellekte depolanır. Ancak **bellek** penceresi büyük ölçekli resim gösterir. Bu görünüm büyük (arabellekleri veya örneğin büyük dizeleri) de diğer windows gösterme veri parçaları incelemek için kullanışlı olabilir. Ancak, **bellek** penceresi verileri görüntülemek için sınırlı değildir. İçerik atanmamış bellekte verileri, kod veya Çöp rastgele bitleri olup her şeyi bellek alanını görüntüler.  
  
 **Bellek** penceredir yalnızca adres düzeyi hata ayıklama içinde etkinse kullanılabilir **seçenekleri** iletişim kutusu, **hata ayıklama** düğümü. **Bellek** penceresi komut dosyası veya bellek kavramı tanımaz diller SQL için kullanılabilir değil.  
  
## <a name="opening-a-memory-window"></a>Bellek penceresini açma  
  
#### <a name="to-open-a-memory-window"></a>Bellek penceresi açmak için  
  
1.  Zaten hata ayıklama modunda olup olmadığı, hata ayıklama, başlatın.  
  
2.  İçinde **hata ayıklama** menüsündeki **Windows**. Ardından, **bellek** ve ardından **bellek 1**, **bellek 2**, **bellek 3**, veya **bellek 4**. (Düşük düzeyli sürümleri [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yalnızca tek bir **bellek** penceresi. Bu sürümlerinden birini kullanıyorsanız, tıklatmanız **bellek**.)  
  
## <a name="paging-in-the-memory-window"></a>Bellek penceresi disk belleği  
 **Bellek** penceresine sahip bir dikey kaydırma çubuğu standart olmayan bir şekilde çalışır. Modern bir bilgisayarın adres alanı çok büyük ve, kolayca scrollbar Flash ele geçirme ve rastgele bir konuma sürükleyerek kayıp. Bu nedenle, Flash "üzerinde" ve her zaman scrollbar Merkezi'nde kalır. Yerel kod uygulamalarında yukarı veya aşağı sayfasında ancak hakkında serbestçe kaydırma yapamıyorsunuz.  
  
 Daha yüksek bellek adresleri pencerenin alt kısmında görüntülenir. Daha yüksek bir adresi görüntülemek için değil kadar kaydırın.  
  
#### <a name="to-page-up-or-down-in-memory"></a>Yukarı veya aşağı bellek sayfası  
  
1.  Page DOWN (daha yüksek bellek adresini Git) için dikey kaydırma çubuğu kaydırma altında tıklatın.  
  
2.  (Düşük bellek adresini Git) sayfasında için Flash dikey kaydırma çubuğu düğmesini tıklatın.  
  
## <a name="selecting-a-memory-location"></a>Bellek konumu seçme  
 Anında bellekte seçili bir konuma taşımak istiyorsanız, bir Sürükle ve bırak işlemi kullanarak veya değer düzenleyerek bunu yapabilirsiniz **adresi** kutusu. **Adresi** kutusu yalnızca sayısal değerler aynı zamanda adreslere değerlendirmek ifadeleri kabul eder. Varsayılan olarak, **bellek** penceresi değerlendirir bir **adresi** programınızı yürütür olarak hangi değerlendirilir canlı bir ifade olarak ifade. Canlı ifadeleri çok kullanışlı olabilir. Örneğin, bir işaretçi işlemdeki bellek görüntülemek için bunları kullanabilirsiniz.  
  
#### <a name="to-select-a-memory-location-by-dragging-and-dropping"></a>Sürükleme ve bırakma bellek konumu seçmek için  
  
1.  Tüm penceresinde bellek adresini içeren bir bellek adresi veya işaretçi değişkeni seçin.  
  
2.  Adres veya işaretçi sürükleyin **bellek** penceresi.  
  
#### <a name="to-select-a-memory-location-by-editing"></a>Düzenleyerek bir bellek konumunu seçmek için  
  
1.  İçinde **bellek** penceresinde, seçin **adresi** kutusu.  
  
2.  Tuşuna basın ve görmek istediğiniz adresini yazın veya yapıştırın **ENTER**.  
  
## <a name="changing-the-way-the-memory-window-displays-information"></a>Bellek penceresi görüntüler bilgileri şekilde değiştirme  
 Biçimini özelleştirebilirsiniz **bellek** penceresi bellek içeriğini gösterir. Varsayılan olarak, bellek içeriğini onaltılık biçimde bir-bayt tamsayı olarak görünür ve sütun sayısı geçerli penceresinin genişliğini tarafından otomatik olarak belirlenir.  
  
#### <a name="to-change-the-format-of-the-memory-contents"></a>Bellek içeriğini biçimini değiştirmek için  
  
1.  Sağ **bellek** penceresi.  
  
2.  İstediğiniz biçimi seçin.  
  
#### <a name="to-change-the-number-of-columns-in-the-memory-window"></a>Bellek penceresi sütun sayısını değiştirmek için  
  
1.  Üstündeki araç çubuğunda **bellek** penceresinde bulun **sütunları** listesi.  
  
2.  İçinde **sütunları** listesinde, görüntülemek veya seçmek istediğiniz sütun sayısını seçin **otomatik** penceresinin genişliğini sığması otomatik olarak ayarlamayı için.  
  
 İçeriğini istemiyorsanız **bellek** programınızı değiştirmek için pencere çalıştırır, Canlı ifade değerlendirmesi devre dışı bırakabilir.  
  
#### <a name="to-toggle-live-evaluation"></a>Canlı değerlendirme geçiş yapmak için  
  
1.  Sağ **bellek** penceresi.  
  
2.  Kısayol menüsünde **otomatik olarak yeniden**.  
  
     Canlı değerlendirme açıksa seçeneği seçili olmalıdır ve tıklatarak Canlı değerlendirme devre dışı bırakır. Canlı değerlendirme kapalıysa, seçeneği seçili değilse ve canlı değerlendirmeye tıklatarak kapatır.  
  
 Gizlemek veya en üstündeki araç çubuğunu görüntüleme **bellek** penceresi. Araç çubuğu gizli sürece kutusunu veya diğer araçları adres erişebilir değil.  
  
#### <a name="to-toggle-the-toolbar"></a>Araç çubuğu geçiş yapmak için  
  
1.  Sağ bir **bellek** penceresi.  
  
2.  Kısayol menüsünde **araç çubuğunu göster**.  
  
     Araç, önceki durumuna bağlı olarak kaybolur ya da görünür.  
  
## <a name="following-a-pointer-through-memory"></a>Bellek işaretçiyi aşağıdaki  
 Yerel kod uygulamalarda yazmaç adları dinamik ifadeleri olarak kullanabilirsiniz. Örneğin, yığın işaretçisi yığın izlemek için kullanabilirsiniz.  
  
#### <a name="to-follow-a-pointer-through-memory"></a>Bellek işaretçiyi izlemek için  
  
1.  İçinde **bellek** penceresi **adresi** bir işaretçi ifadesi yazın. İşaretçi değişkeni geçerli kapsamda olmalıdır. Dil bağlı olarak başvurabilir gerekebilir.  
  
2.  Tuşuna **ENTER**.  
  
     Şimdi, kullandığınızda, bir yürütme komutu gibi **adım**, görüntülenen bellek adresi işaretçi değişiklikleri otomatik olarak değiştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)