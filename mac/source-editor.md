---
title: "Kaynak Düzenleyici | Microsoft Docs"
description: "Mac için Visual Studio Kaynak Düzenleyicisi'ni kullanarak"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: A018A314-C1C4-4F36-BCB6-2D434208FCFE
ms.openlocfilehash: f52e60c0ade8cebc78b3408b4ef81ef85fcd767b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="source-editor"></a>Kaynak Düzenleyici

Bir güvenilir kaynak Düzenleyici temellerini ve verimli bir şekilde kod yazmak için gereklidir. Mac için Visual Studio IDE ile etkileşimlerinizde merkezinde bir Gelişmiş kaynak Düzenleyicisi sağlar. Kaynak Düzenleyici beklediğiniz ve işinizi kolaylıkla yapmak gereken özellikleri sağlar: Böyle sözdizimi vurgulama, kod parçacıkları ve kod Katlama, kendi Roslyn derleyici tümleştirme avantajlarından gibi tam olarak işlevsel IntelliSense kod temelleri tamamlama.

Mac için Visual Studio kaynak düzenleyicisinde hata ayıklama, yeniden düzenleme ve sürüm denetimi tümleştirmesi gibi IDE tarafından sağlanan diğer işlevleri ile sorunsuz bir deneyim sağlar.

Bu konu, Kaynak Düzenleyici önemli özelliklerinden bazıları tanıtır ve mümkün olduğunca verimli olması için Mac için Visual Studio nasıl kullanabileceğinizi açıklar.

## <a name="the-source-editor-experience"></a>Kaynak Düzenleyici deneyimi

Görüntüleme ve verimli bir şekilde kodunuzda taşıma geliştirme iş akışı ayrılmaz bir parçasıdır. Tam olarak nasıl görüntülemek ve geliştiricilerin - ve genellikle projeler arasında değişen bir kişisel karar kod korumak karar.

Mac için Visual Studio erişilebilir ve olabildiğince kullanışlı olarak platformlar arası geliştirmeyi kolaylaştıran birçok güçlü özellikler sunar. Aşağıdaki bölümler vurgular bazıları açıklanmaktadır.


### <a name="code-folding"></a>Kod Katlama

Kod Katlama gösterin veya gizleyin yönergeleri, Demirbaş kod ve açıklamaları ve #region deyimleri kullanarak gibi kodun, tam bölümlerini geliştiricilerine vererek büyük kaynak kodu dosyaları yönetmenizi kolaylaştırır. Bu Visual Studio'da varsayılan Mac için devre dışı

Kod Katlama açmak için gidin **Visual Studio > tercihleri... > Metin Düzenleyicisi > Genel > kod Katlama**:

![Seçenekler Katlama kodu](media/source-editor-image1.png)

Katlama kod etkinleştirme seçeneği sağlamanın yanı sıra, bu menü seçeneği varsayılan olarak kod yerine adlandırılmış bir ipucu görüntüleme #regions ve açıklamalar Katlama de içerir.

Göster veya gizle bölümler için satır numarası yanındaki açıklama pencere öğesini kullanın:

 ![Gösteren veya kod bölümlerde gizleme](media/source-editor-image2.png)

Gösterme ve Katlama kullanarak gizleme arasında geçiş yapabilirsiniz **Görünüm > Katlama > geçiş Katlama / tüm Katlama geçiş** menü öğesi:

 ![Menü öğesi Katlama](media/source-editor-image19.png)

Bu menü öğesini etkinleştirmek veya kod Katlama devre dışı bırakmak için de kullanılabilir.

### <a name="white-space"></a>Beyaz alan

Kaynak kodunda görünmez karakterleri görüntülemek gerekli olabilir. Kodlama standartları ve gereksiz yere değil yer harcama karşıladığınızdan emin olmak için görünür bir yoludur. Ayrıca kod değerlendirmek için tam olarak girintili satırları bağlıdır F # yazılırken faydalıdır.

Boşluk giderek göstermek için seçenekleri ayarlayın **Visual Studio > Tercihler > Metin Düzenleyicisi > işaretçileri ve bunlara Cetveller**aşağıda gösterildiği gibi. Bu seçenek olanak ayarı _zaman_ görünmez karakter gösterilecek: hiçbir zaman, seçimde veya her zaman:

 ![Görünmez karakter seçenekleri göster](media/source-editor-image3.png)

Sekmeler, boşluk ve satır sonları göstermek için seçeneği de mevcuttur:

 ![Sekmeleri ve Boşlukları Göster](media/source-editor-image4.png)

 Görünmez karakterler gri nokta, aşağıda gösterildiği gibi görüntülenir:

 ![Görüntülenen boşluk](media/source-editor-image22.png)


### <a name="ruler"></a>Cetvel

Sütun cetvel gösteren satır uzunluklarını özellikle satır uzunluğu yönergeleri içeren bir ekipte çalışırken belirlemede yararlıdır. Sütun cetvel açmak veya kapatmak için giderek açılabilir **Visual Studio > tercihleri... > Metin Düzenleyicisi > işaretçileri ve bunlara Cetveller** ve seçme (ya da seçimini) **Sütun Göster cetvel**gösterildiği gibi Aşağıda:

 ![](media/source-editor-image5.png)

 Bu, kaynak düzenleyicisinde dikey açık gri satırı olarak görüntüler.


### <a name="highlight-identifier-references"></a>Tanımlayıcı başvuruları vurgulayın

Bu seçenek etkinleştirildiğinde, bir geliştirici fare imlecini kaynak kodundaki herhangi bir simge yerleştirebilirsiniz ve Kaynak Düzenleyici o dosyadaki tüm diğer başvurular için görsel bir kılavuz sağlar. Bu giderek açık **Visual Studio > tercihleri... > Metin Düzenleyicisi > işaretçileri ve bunlara Cetveller** ve seçerek _vurgulayın tanımlayıcı başvuruları_aşağıda gösterildiği gibi:

![](media/source-editor-image6.png)

Vurgulama renk de bir atanan veya başvurulan belirten için yararlıdır. Bir şey atanırsa, kırmızıyla vurgulanır. başvurulduğunda, mavi renkte vurgulanmıştır:

![](media/source-editor-image7.png)



