---
title: "R araçları ile hata ayıklama için Visual Studio | Microsoft Docs"
description: "Visual Studio için kesme noktaları da dahil olmak üzere R tam hata ayıklama deneyimi sağlar, ekleme, yığını ve değişkenleri inceleniyor çağırın."
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 185896840be089c8a74e018e3fd66fa2816c5d76
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="debugging-r-in-visual-studio"></a>Visual Studio'da R hata ayıklama

R araçları için Visual Studio (RTVS) Visual Studio tam hata ayıklama deneyimini ile entegre olur (bkz [Visual Studio'da hata ayıklamayı](../debugger/debugging-in-visual-studio.md). Bu destek, çalışan işlemlerin, inceleme ve izledikleri değişkenleri ve çağrı yığınını incelemek için ekleme kesme noktaları içerir. Bu makalede daha sonra R ve RTVS özgü hata ayıklama bu yönlerini araştırır.

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

Hata ayıklayıcıda durduğunda, ayrıca ortamı tarayıcı isteminde durduruldu [etkileşimli pencere](interactive-repl-for-r-in-visual-studio.md). İstemi görünür `Browse[n]>` n, bir sayı.

Ortam tarayıcı özel komutlar destekler:

| Komut | Açıklama |
| --- | --- |
| n | Sonraki: çalıştırır kodda next deyimi dosya (Adımlama olarak aynı). |
| s | adımla: next deyimi işlev çağrısı ise işlevi kapsamı içine Adımlama kod dosyasında next deyimi çalıştırır. |
| f | Son: geçerli işlev kapsamı kalanını çalıştırır ve çağırana (adım ile aynı) döndürür. |
| c, devamı | devam: sonraki kesme programı çalıştırır. |
| Q | çıkar: hata ayıklama oturumu sona erer. |
| Burada | yığını göster: çağrı yığını etkileşimli penceresinde görüntüler. |
| Yardım | Yardımı Göster: kullanılabilir komutlar etkileşimli penceresinde görüntüler. |
| &lt;expr&gt; | İfade değerlendirme *expr*. |

![Etkileşimli penceresinde ortamı tarayıcı](media/debugger-environment-browser.png)
