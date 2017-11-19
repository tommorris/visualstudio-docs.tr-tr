---
title: "Kullanıcı Arabirimi (XSLT) hata ayıklayıcı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 846fdabd-e5c3-4688-9b0d-a93fbeea1b96
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 422dd91a5b8e22bb9859d8ffa10160bdbe77a021
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="debugger-user-interface-xslt"></a>Hata ayıklayıcı kullanıcı arabirimi (XSLT)
Bu konuda hata ayıklayıcı windows ve iletişim kutuları açıklanmaktadır. Yalnızca, XSLT özgü hata ayıklama davranışı sahip kullanıcı arabirimi parçaları anlatılır.  
  
 Daha fazla bilgi için bkz: [hata ayıklama kullanıcı arabirimi başvurusu](../debugger/debugging-user-interface-reference.md).  
  
## <a name="locals-window"></a>Yerel öğeler penceresi  
 Yerel öğeler penceresi stil sayfanızda tanımlanan değişkenler hakkındaki bilgileri görüntüler. Yerel öğeler penceresi bilgilerinin üç sütunları içerir:  
  
 **Ad**  
 Bu sütun geçerli kapsamdaki tüm yerel değişkenler adlarını içerir. Düğüm kümeleri, klasörlerinden görmek için detaya ağaç denetimi vardır.  
  
 **Değer**  
 Bu sütunda her bir değişken tarafından bulunan değer görüntülenir. Öznitelik işleme yönergesi, açıklama, metin ve CData düğümler, düğümün metin değeri görüntüler. Namespace düğümler ad alanı URI'si gösterir.  
  
 **Türü**  
 Bu sütunda listelenen her bir değişken veri türünü tanımlayan **adı** sütun.  
  
 Yerel öğeler penceresi de XSLT dönüşümü bağlamında izleyen tanımlanmış bağlam değişkenleri görüntüler. Aşağıdaki tabloda XSLT hata ayıklayıcı tarafından kullanılan önceden tanımlanmış bağlam değişkenler açıklanmaktadır.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`last()`|İçerik boyutu.|  
|`position()`|Konum, veya bağlam düğümünün bağlam boyutuna göre dizin numarası.|  
|`self::node()`|Bağlam düğümünün değeri.|  
  
## <a name="output-window"></a>Çıktı Penceresi  
 Çıktı penceresi herhangi bir hata iletileri veya hata ayıklama sırasında oluşan güvenlik özel durumlarını gösterir.  
  
 XSLT hata ayıklayıcısı hata ayıklayıcı çıktı görüntülemek için ayrı bir pencerede kullanır. Bu çıkışı görüntülemek için kullanılan aynı penceredir bir **Göster XSL çıkış** komutu.  
  
## <a name="task-list"></a>Görev Listesi  
 Görev listesi, stil sayfasında tüm derleme hataları listeler. Hata çift hata içeren satırı için imleci alır.  
  
 Görev listesi XSLT dosyasını komut dosyası bloklarında oluşan hataları içerir.  
  
> [!NOTE]
>  XSLT hata ayıklayıcı hiçbir uyarı sahiptir, bu nedenle hiçbir görev listesinde görünürler.  
  
## <a name="breakpoints-window"></a>Kesme noktaları penceresi  
 Kesme noktaları penceresi geçerli projede ayarlamak tüm kesme noktalarını gösterir. Pencere görünür durumdayken bir kesme noktası eklediyseniz, pencerenin yeni kesme noktası göstermek için otomatik olarak güncelleştirilir.  
  
 Kesme noktaları penceresi, diğer Visual Studio hata ayıklayıcıları aynı şekilde davranır.  
  
## <a name="command-windowimmediate-window"></a>Komut penceresinde/komut penceresi  
 XSLT hata ayıklayıcı bu sürümde uygulanmadı.  
  
## <a name="watch-window"></a>Gözcü penceresi  
 Gözcü penceresi değişkenleri değerlendirmek için kullanılır. Değişkenlerin değerleri de değiştirebilirsiniz.  
  
 Gözcü penceresinde görüntülenen geçerli bağlam (en üstteki öğe çağrı yığınında) için değişkenlerdir. Bağlam değiştirirseniz, Gözcü penceresi güncelleştirir ve bu bağlam için ayarlanan değişkenler görüntüler.  
  
## <a name="call-stack-window"></a>Çağrı yığını penceresi  
 Çağrı yığını penceresi işlevlerin adları çağrı yığını, parametre türleri ve parametre değerlerini görüntülemek için kullanılır. Çağrı yığını bilgileri yalnızca ayıklanacak programın sonu durumda olduğunda gösterilir.  
  
 Çağrı yığını XSLT yürütme oluşturulmak çeşitli bağlamı temsil eder. Örneğin, bir çağrı şablondan ise "a" Şablon "b", şablon "a" ve "b" şablonu görünür listenin çok konumundaki geçerli bağlamda ile çağrı yığını penceresinde. Kullanıcı şu anda yürütülmekte sorgu görmeye değil.  
  
 Şablonları XSLT dosyasında bir adı yoksa, XSLT işlemcisi tarafından üretilen adları kullanılır.  
  
 Listenin başındaki farklı bir öğeyi tıklatarak Burada XSLT yürütme şube standart yeşil vurgulama kullanarak oldu ve okları yeşil Görüntüleyicisi gösterir.  
  
## <a name="quickwatch-dialog-box"></a>QuickWatch iletişim kutusu  
 **QuickWatch** iletişim kutusu XPath 1.0 ifadeleri değerlendirmek için kullanılır. Bağlam düğümü ( `self::node()` yerel öğeler penceresi düğümden) XPath ifadesi yürütülmesi için bir bağlam sağlar. XPath ifadesi yürütmenin sonucu Gözcü penceresi görüntülenir.  
  
 Aşağıdaki listede bazı kısıtlamalar XPath ifadesi değerlendirmeye açıklanmaktadır.  
  
-   Yalnızca yerleşik XPath işlevleri izin verilir.  
  
-   Yerleşik XSLT işlevleri gibi `document()`, `key()`ve benzeri izin verilmez.  
  
-   Kullanıcı tanımlı işlevlere izin verilmiyor.  
  
Daha fazla bilgi için bkz: [nasıl yapılır: bir XPath ifadesi değerlendirmek](../xml-tools/how-to-evaluate-an-xpath-expression.md).  
  
## <a name="disassembly-window"></a>Ayrıştırma penceresi  
 Ayrıştırılmış kod penceresini XSLT derleyici tarafından üretilen bütünleştirilmiş kodu gösterir. Bu pencere, diğer Visual Studio çözümünü windows aynı şekilde kullanılabilir.  
  
 Daha fazla bilgi için [nasıl yapılır: Ayrıştırılmış kod penceresini kullanma](../debugger/how-to-use-the-disassembly-window.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XSLT hata ayıklama](../xml-tools/debugging-xslt.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)   
 [Otomatik değişkenler değişkenleri ve Visual Studio Yereller Windows inceleyin.](../debugger/autos-and-locals-windows.md)