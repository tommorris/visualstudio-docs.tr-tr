---
title: "Visual Studio için R araçları linting R koduyla | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
f1_keywords: vs.toolsoptionspages.text_editor.r.lint
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: data-science
ms.openlocfilehash: 76f4ceb040e62e4ebac46e8a791f5dac0d73aff5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="linting-r-code-in-visual-studio"></a>Visual Studio'da linting R kodu

Linting biçimlendirme sorunları ve diğer gürültü kod dosyalarında (örneğin, sahte boşluk) yanı sıra olası hatalar ortaya çıkarmak üzere kod analiz eden bir işlemdir. Linting nasıl tanımlayıcıları, takımları ve diğer ortak durumları içinde çok yararlı olduğu adlandırıldığı gibi belirli kodlama kurallarını teşvik yardımcı olur.

R araçları için Visual Studio (RTVS) davranışını çeşitli seçenekleri denetlenir R, yerleşik linting sağlar. Bu seçenekler bulunan **aracı > Seçenekler > Metin Düzenleyicisi > R > tüy**.

Linting varsayılan olarak devre dışıdır. Linting etkinleştirmek için ayarlanmış **tüm > etkinleştirmek tüy** seçeneği true. Bu konuda aşağıdaki bölümlerde, diğer tüm linting seçenekleri açıklanmaktadır:

Siz yazarken etkinleştirildiğinde, linting Düzenleyicisi'nde uygulanır. Sorunlar yeşil dalgalı çizgiler görüntülenir. Aşağıdaki grafikte, örneğin, RTVS kullanımı gibi altı linting sorunları belirlemiştir `=` yerine `<-` işlev bağımsız değişkenleri, geçici aralığı eksikliği atama için Pascal çalışması ve büyük tanımlayıcıları ve kullanımını kullanımını bir noktalı virgül. Bir sorun getirildiğinde, bir açıklama sağlar.

![Linting R kodu örnekleri](media/linting-01.png)

## <a name="assignment-group"></a>Atama grubu

| Seçenek | Varsayılan değer | Linting etkisi |
| --- | --- | --- |
| Zorla\<- | `True` | Ne zaman tanımlayan `<-` ataması için kullanılmaz. |

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