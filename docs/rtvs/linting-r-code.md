---
title: Linting R kodu
description: R linting seçenekleri de dahil, Visual Studio'nun yapı içinde linting desteği ile çalışmaya nasıl.
ms.date: 01/15/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
f1_keywords:
- vs.toolsoptionspages.text_editor.r.lint
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: e5494283fdf759ddc664207d62d40f7f83993632
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
---
# <a name="linting-r-code-in-visual-studio"></a>Visual Studio'da linting R kodu

Linting olası hatalar, biçimlendirme sorunları ve diğer kod gürültü alacaklardır boşluk gibi ortaya çıkarmak üzere kod analiz eder. Linting tanımlayıcıları nasıl adlandırıldığı gibi belirli kodlama kurallarını teşvik yardımcı olur. Bu tür kuralları ekipleri ve diğer ortak durumlar içinde yardımcı olur.

R araçları için Visual Studio (RTVS) davranışını çeşitli seçenekleri bu makalede açıklanan aracılığıyla denetlenir R, yerleşik linting sağlar. Bu seçenekler bulunan **aracı > Seçenekler > Metin Düzenleyicisi > R > tüy**.

Linting varsayılan olarak devre dışıdır. Linting etkinleştirmek için ayarlanmış **tüm > etkinleştirmek tüy** seçeneği true.

Siz yazarken etkinleştirildiğinde, linting Düzenleyicisi'nde uygulanır. Sorunlar yeşil dalgalı çizgiler görüntülenir. Aşağıdaki grafikte, örneğin, RTVS kullanımı gibi altı linting sorunları belirlemiştir `=` yerine `<-` işlev bağımsız değişkenleri, geçici aralığı eksikliği atama için Pascal çalışması ve büyük tanımlayıcıları ve kullanımını kullanımını bir noktalı virgül. Bir sorun getirildiğinde, bir açıklama sağlar.

![Linting R kodu örnekleri](media/linting-01.png)

Genellikle bir proje veya dosya gereksinimlerine bağlı olarak linting seçeneklerini değiştirin. Örneğin, bir çevrimiçi indirmelere'nden örnek kodu kullanabilirsiniz `=` yerine `<-` Pascal durum tanımlayıcıları yanı sıra. Bu gibi durumlarda varsayılan linting seçenekleri bayrak çünkü kodun sık linting uyarıları gösterir. Bu kodu ile çalışırken, daha sonra her örneğinin düzeltilmesi zaman harcama yerine seçenekleri devre dışı bırakabilirsiniz.

## <a name="assignment-group"></a>Atama grubu

| Seçenek | Varsayılan değer | Linting etkisi |
| --- | --- | --- |
| Zorla \<- | `True` | Ne zaman tanımlayan `<-` ataması için kullanılmaz. |

## <a name="naming-group"></a>Grup adlandırma

Bu seçenekler farklı adlandırma kuralları kullanmak tanımlayıcıları bayrak:

| Seçenek | Varsayılan değer | Linting etkisi |
| --- | --- | --- |
| Bayrak camelCase | `False` | CamelCase kullanmak bayrakları tanımlayıcıları. |
| Bayrak uzun adları | `False` | Tanımlayıcıları bayrakları, adlandırılmış "Max adı uzunluğu" ayarı aşabilir. |
| Birden çok nokta bayrak | `True` | Birden çok nokta kullanmak bayrakları tanımlayıcıları. |
| Bayrak PascalCase | `True` | PascalCase kullanmak bayrakları tanımlayıcıları. |
| Bayrak snake_case | `False` | Alt çizgiler kullanın bayrakları tanımlayıcıları. |
| Büyük harfli bayrağı | `True` | Tümü büyük harf kullanın bayrakları tanımlayıcıları. |
| Max adı uzunluğu | 32 | "Ayar bayrağı uzun adlarla" uygulanan uzunluğu. |

## <a name="spacing-group"></a>Aralık grubu

Bunların tümü ayarlanır, bu seçenekleri `True` burada linter aralığı sorunlarını tanımlar varsayılan olarak, Denetim: önce virgüller, açma ve kapama süslü konumlar, işleçler, geçici geçici işlev adları boşluk sonra (ve () içindeki.

## <a name="statements-group"></a>İfadeleri Grup

| Seçenek | Varsayılan değer | Linting etkisi |
| --- | --- | --- |
| Birden Çok | `True` | Birden çok deyime aynı çizgi üzerinde olduğunda tanımlar. |
| Noktalı virgül | `True` | Noktalı virgül kullanımlarını tanımlar. |

## <a name="text-group"></a>Metin grubu

| Seçenek | Varsayılan değer | Linting etkisi |
| --- | --- | --- |
| Satır uzunluğu sınırı | `False` | "En fazla satır uzunluğu" seçeneğini uzun satırları linter bayraklar onaylanmadığını ayarlar. |
| En fazla satır uzunluğu | 80 | "Satır uzunluğu sınırı" seçeneği tarafından uygulanan satır uzunluğunu belirler. |

## <a name="whitespace-group"></a>Boşluk grubu

Her biri için ayarlanır, bu seçenekleri `True` burada linter boşluk sorunları tanımlar varsayılan olarak, Denetim: sekmelerinde kullanımını çift-tırnak, boş satırları izleyen ve sondaki boşluk kullanımı.