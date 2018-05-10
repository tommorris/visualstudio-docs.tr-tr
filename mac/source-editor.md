---
title: Kaynak Düzenleyici
description: Mac için Visual Studio Kaynak Düzenleyicisi'ni kullanarak
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: A018A314-C1C4-4F36-BCB6-2D434208FCFE
ms.openlocfilehash: c617ed1bae10569291b88d038e8d875ca966ad43
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="source-editor"></a>Kaynak Düzenleyici

Bir güvenilir kaynak Düzenleyici temellerini ve verimli bir şekilde kod yazmak için gereklidir. Mac için Visual Studio IDE ile etkileşimlerinizde merkezinde bir Gelişmiş kaynak Düzenleyicisi sağlar. Kaynak Düzenleyici beklediğiniz ve işinizi kolaylıkla yapmak gereken özellikleri sağlar: Böyle sözdizimi vurgulama, kod parçacıkları ve kod Katlama, kendi Roslyn derleyici tümleştirme avantajlarından gibi tam olarak işlevsel IntelliSense kod temelleri tamamlama.

Mac için Visual Studio kaynak düzenleyicisinde diğer işlevleri hata ayıklama, yeniden düzenleme ve sürüm denetimi tümleştirmesi gibi IDE'de ile sorunsuz bir deneyim sağlar.

Bu makalede, Kaynak Düzenleyici önemli özelliklerinden bazıları tanıtır ve mümkün olduğunca verimli olması için Mac için Visual Studio nasıl kullanabileceğinizi açıklar.

## <a name="the-source-editor-experience"></a>Kaynak Düzenleyici deneyimi

Görüntüleme ve verimli bir şekilde kodunuzda taşıma geliştirme iş akışı ayrılmaz bir parçasıdır. Tam olarak nasıl görüntülemek ve geliştiricilerin - ve genellikle projeler arasında değişen bir kişisel karar kod korumak karar.

Mac için Visual Studio erişilebilir ve olabildiğince kullanışlı olarak platformlar arası geliştirmeyi kolaylaştıran birçok güçlü özellikler sunar. Aşağıdaki bölümlerde vurgular bazıları açıklanmaktadır.


## <a name="code-folding"></a>Kod Katlama

Kod Katlama gösterin veya gizleyin yönergeleri, Demirbaş kod ve açıklamaları ve #region deyimleri kullanarak gibi kodun, tam bölümlerini geliştiricilerine vererek büyük kaynak kodu dosyaları yönetmenizi kolaylaştırır. Kod Katlama Visual Studio'da varsayılan Mac için devre dışı

Kod Katlama açmak için gidin **Visual Studio > tercihleri... > Metin Düzenleyicisi > Genel > kod Katlama**:

![Seçenekler Katlama kodu](media/source-editor-image1.png)

Bu menü seçeneği varsayılan olarak kod yerine adlandırılmış bir ipucu görüntüleme #regions ve açıklamalar Katlama de içerir.

Göster veya gizle bölümler için satır numarası yanındaki açıklama pencere öğesini kullanın:

 ![Gösteren veya kod bölümlerde gizleme](media/source-editor-image2.png)

Gösterme ve Katlama kullanarak gizleme arasında geçiş yapabilirsiniz **Görünüm > Katlama > geçiş Katlama / tüm Katlama geçiş** menü öğesi:

 ![Menü öğesi Katlama](media/source-editor-image19.png)

Bu menü öğesini etkinleştirmek veya kod Katlama devre dışı bırakmak için de kullanılabilir.

## <a name="white-space"></a>Beyaz alan

Kaynak kodunda görünmez karakterleri görüntülemeniz için gerekli olabilir. Kodlama standartları ve gereksiz yere değil yer harcama bağlı emin olmak için görünür bir yoludur. Ayrıca kod değerlendirmek için tam olarak girintili satırları bağlıdır F # yazarken yararlı olacaktır.

Boşluk giderek göstermek için seçenekleri ayarlayın **Visual Studio > Tercihler > Metin Düzenleyicisi > işaretçileri ve bunlara Cetveller**. Bu seçenek olanak ayarı _zaman_ görünmez karakter gösterilecek: hiçbir zaman, seçimde veya her zaman:

 ![Görünmez karakter seçenekleri göster](media/source-editor-image3.png)

Sekmeler, boşluk ve satır sonları göstermek için seçeneği de mevcuttur:

 ![Sekmeleri ve Boşlukları Göster](media/source-editor-image4.png)

 Görünmez karakterler gri nokta aşağıdaki görüntüde gösterildiği gibi görüntülenir:

 ![Görüntülenen boşluk](media/source-editor-image22.png)


## <a name="ruler"></a>Cetvel

Sütun cetvel satır uzunluklarını özellikle satır uzunluğu yönergeleri içeren bir ekipte çalışırken belirlemede yararlıdır. Sütun cetvel açmak veya kapatmak için giderek açılabilir **Visual Studio > tercihleri... > Metin Düzenleyicisi > işaretçileri ve bunlara Cetveller** ve seçme (ya da seçimini) **Sütun Göster cetvel**de gösterildiği gibi Aşağıdaki görüntüde:

 ![](media/source-editor-image5.png)

 Bu, kaynak düzenleyicisinde dikey açık gri satırı olarak görüntüler.


## <a name="highlight-identifier-references"></a>Tanımlayıcı başvuruları vurgulayın

"Seçeneğinin etkinleştirilmiş Vurgu tanımlayıcı başvuruları", kaynak kodunda herhangi bir simge seçin ve Kaynak Düzenleyici o dosyadaki tüm diğer başvurular için görsel bir kılavuz sağlar. Bu seçeneği etkinleştirmek için şu adrese gidin **Visual Studio > tercihleri... > Metin Düzenleyicisi > işaretçileri ve bunlara Cetveller** seçip _vurgulayın tanımlayıcı başvuruları_aşağıdaki görüntüde gösterildiği gibi:

![](media/source-editor-image6.png)

Vurgulama renk de bir atanan veya başvurulan belirten için yararlıdır. Bir şey atanırsa, kırmızıyla vurgulanır. başvurulduğunda, mavi renkte vurgulanmıştır:

![](media/source-editor-image7.png)



