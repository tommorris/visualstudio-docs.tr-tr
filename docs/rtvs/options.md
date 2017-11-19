---
title: "R araçları Visual Studio seçenekleri | Microsoft Docs"
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
f1_keywords:
- vs.toolsoptionspages.r_tools
- vs.toolsoptionspages.r_tools.advanced
- vs.toolsoptionspages.r_tools.#150
ms.topic: article
ms.assetid: 554dc602-ecad-4cd0-8e6f-a60bb8a2328f
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 82e17109ff595ae566ea326dae9237274ee5ad15
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="r-tools-for-visual-studio-options"></a>Visual Studio seçenekleri için R araçları
 
Ayarları aracılığıyla erişimi olan **R Araçlar > Seçenekler** menüsünde aracılığıyla veya **araçları > Seçenekleri** ve kaydırmayı **R Araçları**:
 
  ![R araçları için Seçenekler iletişim kutusu](media/options-dialog.png)

Aşağıdaki bölümlerde, bu sayfada kullanılabilir farklı seçenekler açıklanmaktadır.

> [!Note]
> Seçenekleri genel erişirken **Araçlar > Seçenekler** menüsünde ihtiyacınız olabilecek seçmek **tüm ayarları göster** için alttaki kutusu **R Araçları** görünmesi sayfa.

< a name = "veri Bilimcisi düzeni"</a>

**R Araçlar > veri bilimi ayarları** menü öğesi de yapılandırır Visual Studio IDE veri bilimcilerine gereksinimleriniz için en iyi hale getirilmiş bir düzende. Özellikle, bu seçenek açar [etkileşimli](interactive-repl.md), [değişken Explorer](variable-explorer.md), ve [çalışma alanları](workspaces.md) windows:

![Visual Studio'da veri Bilimcisi pencere düzeni](media/installation-data-scientist-layout-result.png)

> [!Important]      
> Daha sonra diğer Visual Studio ayarlarına döndürmek için önce kullanın **Araçlar > içeri ve dışarı aktarma ayarları** komutu, select **verme seçili ortam ayarlarını**ve bir dosya adı belirtin. Bu ayarları geri yüklemek için aynı komutunu kullanın ve seçin **seçili ortam ayarları**. Veri Bilimcisi düzenini değiştirmek ve daha sonra kullanmak yerine döndürmek isterseniz de aynı komutları kullanabilirsiniz **veri bilimi ayarları** doğrudan komutu.

## <a name="debugging"></a>Hata Ayıklama

Bu seçenekler değerlerin nasıl işleneceğini kontrol [değişken Explorer](variable-explorer.md) ve izleme ve Yereller gibi hata ayıklayıcı windows (bkz [hata ayıklama](debugging.md).

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| Etkin bağlamaları değerlendir | `True` | Zaman `True`, her zaman en güncel değeri değişkenlerin ve özelliklerin incelerken gördüğünüz sağlar. Bu ifadeler yan nasıl uygulanan bağlı olarak etkileri, neden olabilecek değerlendirme riskidir. |
| Nokta önekli değişkenleri Göster | `False` | Değişkenleri önekine sahip olup olmadığını belirtir `.` gösterilir. |

## <a name="general"></a>Genel

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| Anket/haber onay | `Once a week` | R araçları Haberler ve Anket güncelleştirmeleri sunucusuyla ne sıklıkta denetleyeceğini belirtir. | 

## <a name="help"></a>Yardım

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| F1 Web tarayıcısı | `Internal` | Ctrl + F1 kullanarak bir terimi ararken Yardım nasıl görüntüleneceğini denetler. Ayarlandığında `Internal`, Yardım araç penceresi Visual Studio içinde işlenir. Ayarlandığında `External`, Yardım varsayılan web tarayıcınızda görüntülenir. | 
| F1 Web arama dizesi | `R site:stackoverflow.com` | Bir terim Düzenleyicisi'nde üzerinde Ctrl + F1 tuşuna bastığınızda arama terimleri arama motorunuz nasıl geçirilir denetler. Varsayılan olarak dizedir `R site:stackoverflow.com`, hangi ekler `R` arama sürenizin için. `site:stackoverflow.com` İçinde sayfalar için arama kapsamını kendisine söyleyen bir arama motoruna yönergesi olup `stackoverflow.com` etki alanı. | 
| R Yardım tarayıcı | `Automatic` | F1 kullanarak R belgelerine ararken Yardım görüntülenme denetimleri `?`, veya `??`. Ayarlandığında `Automatic`, Yardım uygun penceresinde işler. Örneğin, varsayılan PDF programınız PDF görünür ancak HTML Yardımı Visual Studio araç penceresi içinde görüntülenir. Ayarlandığında `External`, Yardım, varsayılan web tarayıcınızda işlenir. |

## <a name="history"></a>Geçmiş

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| Her zaman geçmiş Kaydet | `True` | RTVS komut geçmişinizde yazıp yazmayacağını denetler. bir `.RHistory` proje kapalı olduğunda çalışma dizininizi dosyasında. Çıkmadan önce projenizi kaydetme olsa bile geçmişini kaydetme olur. |
| Arama filtresi Sıfırla | `True` | Geçmiş penceresini substring eşleşen R geçmişi iletişim filtre vadede karşı komutları göstermek üzere komut geçmişinizde filtre olup olmadığını belirler. Bu ayar her yeni bir komut çalıştırmak veya farklı bir yükünü tetikleyen bir yeni projesine geçiş geçmişi arama filtresi sıfırlanıp sıfırlanmayacağını belirler `.RHistory` dosya. Varsayılan ayar `True` beklenmedik biçimde bir filtre kümesi ile bir komut çalıştırdığınızda ve neden yalnızca çalıştırdığınız komut geçmişinde görünmesini kaydetmedi merak ediyor olduğunda en aza indirir. |
| Çok satırlı seçimini kullan | `True` | Çok satırlı deyimi geçmişinde tek bir tıklatmayla seçebileceğiniz olup olmadığını belirtir. Ayrıca yukarı/aşağı ok Gezinti etkileşimli Windows satırları yerine deyimleri tarafından sağlar. |

## <a name="html"></a>HTML

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| HTML sayfaları tarayıcı | `External` | İçerik gibi yerlerde belirler bir `ggvis` çizim, veya bir `shiny` uygulama işlenir. `Internal`Visual Studio'da bir araç penceresi içinde olan HTML çıktısı gösterir; `External` varsayılan tarayıcınızda HTML çıktısını görüntüler. | 

## <a name="logging"></a>Günlüğe Kaydetme

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| Günlük olayları | `Normal` | Ayrıntı RTVS tanılama için kullanılan günlük denetler. Varsayılan ayar `Normal` bir günlük dosyası oluşturur, `TEMP` dizin. Ayarlandığında `Traffic`, RTVS oturumunuzda tüm komutları ve yanıtları kaydeder. Bu günlük dosyaları hiçbir zaman makinenizi bırakın, ancak RTVS sorunları tanılamak için yararlı olabilir. |

## <a name="markdown"></a>Markdown

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| Markdown önizlemesini tarayıcı | `External` | RMarkdown HTML çıktısı görüntülenir burada belirler. `Internal`Visual Studio'da bir araç penceresi içinde RMarkdown HTML belgesi gösterir; `External` RMarkdown varsayılan tarayıcı kullanarak HTML görüntüler. | 

## <a name="r-engine"></a>R altyapısı

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| Kod sayfası | `(OS Default)` | Kod sayfası (yerel) r için ayarlar Varsayılan olarak işletim sisteminin temel alınan yerel kullanır. | 
| CRAN yansıtma | `(Use .Rprofile)` | Paket yüklemeleri için varsayılan CRAN yansıtma ayarlar. Varsayılan ayar `Use .Rprofile` CRAN yansıtma ayarlarında dikkate alır, `.RProfile` dosya. |
| Çalışma dizini | kullanıcıya özgü klasörü | Ayarlar, her bir proje açıldığında, tipik olarak ayarlanan geçerli çalışma dizini olur. |

## <a name="workspace"></a>Çalışma alanı

| Seçenek | Varsayılan değer | Açıklama | 
| --- | --- | --- |
| Proje açıldığında çalışma alanı yükleme | `No` | Ayarını `Yes` oturum verilerini yüklemeyi etkinleştirir `.RData` projesi açıldığında genel ortam dosyasına. |
| Çalışma alanı Sıfırla kaydetmeden önce sor | `Yes` | Ayarını `No` etkileşimli penceresinde Sıfırla düğmesini tıkladığınızda çalışma alanınızı kaydetmek isteyen devre dışı bırakır. |
| Proje kapandığında çalışma alanı Kaydet | `No` | Ayarını `Yes` genel ortama kaydetmeyi etkinleştirir `.RData` proje kapatıldığında dosya. |
| Çalışma alanları değiştirmeden önce onay iletişim kutusunu göster | `Yes` | Ayarını `No` farklı çalışma alanları arasında geçiş yaparken onay kullanıcıdan devre dışı bırakır. Bkz: [çalışma alanları arasında geçiş yapma](workspaces.md#switching-between-workspaces) |
 
