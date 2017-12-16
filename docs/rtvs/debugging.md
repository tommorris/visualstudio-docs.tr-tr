---
title: "R araçları ile hata ayıklama için Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: ec65639fb7549b9d824e80b702fab2b2b2e1123d
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/14/2017
---
# <a name="debugging-r-in-visual-studio"></a>Visual Studio'da R hata ayıklama

R araçları için Visual Studio (RTVS) Visual Studio tam hata ayıklama deneyimini ile entegre olur (bkz [Visual Studio'da hata ayıklamayı](../debugger/debugging-in-visual-studio.md). Bu destek, çalışan işlemlerin, inceleme ve izledikleri değişkenleri ve çağrı yığınını incelemek için ekleme kesme noktaları içerir. Bu konuda daha sonra R ve RTVS özgü hata ayıklama bu yönlerini araştırır.

Hata ayıklayıcı bir R projesini başlangıç R dosyasında diğer proje türleri ile aynıdır için başlangıç: kullanmak **hata ayıklama > hata ayıklamayı Başlat**, F5 tuşuna veya **kaynak başlangıç dosya** hata ayıklama araç çubuğunda: 

![Başlat düğmesi R için hata ayıklayıcı](media/debugger-start-button.png)

Başlangıç dosyasını değiştirmek için Çözüm Gezgini'nde bir dosyaya sağ tıklayın ve seçin **başlangıç R betiği olarak ayarlamak**.

Hata ayıklayıcı "Kaynaklar" Etkileşimli penceresinde başlatma tüm durumlarda, yükleme ve orada etkileşimli pencerenin çıkış gösterildiği gibi çalışan yani:

```output
> rtvs::debug_source("c:/proj/rproject1/rproject1/script.R")
Sourcing: c:\proj\rproject1\rproject1\script.R
Sourcing: c:\proj\rproject1\rproject1\Settings.R
```

Dikkat `rtvs::debug_source` işlev, komut dosyası kaynağı için kullanılır. Bu işlev, hata ayıklama hazırlığı kodunuzu değiştirmek RTVS gerektiği için gereklidir. Herhangi bir RTVS kaynak belirleme komutu ve bir hata ayıklayıcısı kullanarak eklendiğinde, Visual Studio otomatik olarak kullanan `rtvs::debug_source`.

Hata ayıklayıcı kullanarak doğrudan etkileşimli penceresinden el ile de ekleyebilirsiniz **R Araçlar > oturum > ekleme hata ayıklayıcı** komutu, **hata ayıklama > R etkileşimli ekleme** komut veya  **Hata ayıklayıcısını** etkileşimli pencerenin araç çubuğunda komutu. Bunu yaptıktan sonra kaynak hata ayıklamak istediğiniz dosyaları, sorumluluğundadır. El ile kaynak dosyalarını istiyorsanız, kullandığınızdan emin olun `rtvs::debug_source` ve normal `source` r komutunu

Hata ayıklayıcı ve etkileşimli pencere arasındaki bu bağlantı, arama (ve hata ayıklama) gibi şeyler kolaylaştırır farklı parametre değerleri içeren bir işlev. Örneğin, aşağıdaki işlevi kaynaklı dosyasında (oturuma yüklenmiş anlamına gelir) olduğunu varsayalım:

```R
add <- function(x, y) {
    return(x + y)
}
```

Üzerinde bir kesme noktası ayarlayın, sonra da `return` deyimi. Penceresinde girme şimdi, etkileşimli `add(4,5)` hata ayıklayıcı kesme noktasına durdurur.


## <a name="environment-browser-in-the-interactive-window"></a>Etkileşimli penceresinde ortamı tarayıcı

Hata ayıklayıcıda durduğunda, ayrıca ortamı tarayıcı isteminde durduruldu [etkileşimli pencere](interactive-repl.md). İstemi görünür `Browse[n]>` n, bir sayı.

Ortam tarayıcı özel komutlar destekler:

| Komut | Açıklama |
| --- | --- |
| n | Sonraki: çalıştırır kodda next deyimi dosya (Adımlama olarak aynı). |
| s | adımla: next deyimi işlev çağrısı ise işlevi kapsamı içine Adımlama kod dosyasında next deyimi çalıştırır. |
| F | Son: geçerli işlev kapsamı kalanını çalıştırır ve çağırana (adım ile aynı) döndürür. |
| c, devamı | devam: sonraki kesme programı çalıştırır. |
| Q | çıkar: hata ayıklama oturumu sona erer. |
| Burada | yığını göster: çağrı yığını etkileşimli penceresinde görüntüler. |
| Yardım | Yardımı Göster: kullanılabilir komutlar etkileşimli penceresinde görüntüler. |
| &lt;ifade&gt; | İfade değerlendirme *expr*. |

![Etkileşimli penceresinde ortamı tarayıcı](media/debugger-environment-browser.png)
