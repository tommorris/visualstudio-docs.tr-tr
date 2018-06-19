---
title: Git komutları kullanarak kod Bul
ms.date: 09/26/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 509b2107-23d1-4fb3-987f-ab99ef45b72e
helpviewer_keywords:
- code editor, go to
- code editor, go to line
- go to line
- go to
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9aca1106bb6dfa3838890e4ae5c1886875e3e357
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34447199"
---
# <a name="find-code-using-go-to-commands"></a>Git komutları kullanarak kod Bul

Visual Studio'nun **gitmek için** komutları belirtilen öğeleri hızlı bir şekilde bulmanıza yardımcı olmak için kodunuzu odaklanmış bir arama gerçekleştirin. Belirli bir satırı, türü, simge, dosya ve üye için bir basit, birleştirilmiş arabiriminden gidebilirsiniz. Bu özellik, Visual Studio 2017 ve sonraki sürümlerinde bulunmaktadır.

## <a name="how-to-use-it"></a>Nasıl kullanılacağını

Giriş        | İşlev
------------ | ---
**Klavye** | Tuşuna **Ctrl**+**T** veya **Ctrl**+**,**
**Fare**    | Seçin **Düzenle** > **Git** > **tümüne gidin**

En Üstte küçük bir pencere görüntülenir, kod düzenleyicisini sağında.

![Tüm Git penceresi](media/go-to-all.png)

Metin kutusuna yazarken, aşağı açılan listesinde metin kutusunun altındaki sonuçlar görüntülenir. Bir öğe olarak gitmek için listeden seçin.

![Git penceresi](../ide/media/vside_navigatetowindow.png)

Bir soru işareti de girebilirsiniz (**?**) ek Yardım almak için.

![Tüm Yardım'a gidin](media/go-to-all-help.png)

## <a name="filtered-searches"></a>Filtrelenmiş aramalar

Varsayılan olarak, tüm çözüm öğeleri için belirtilen öğe aranır. Bununla birlikte, belirli karakterler arama şartlarını Sunuş yapma belirli öğe türleri için kod arama kısıtlayabilirsiniz. Üzerinde düğmeleri seçerek de hızlı bir şekilde arama filtresi değiştirebilirsiniz **gitmek için** iletişim kutusu araç. Türü filtreleri değiştirmek düğmeleri sol tarafta ve arama kapsamını değiştirmek düğmeler sağ tarafta bulunur.

![Üyelerine gidin](../ide/media/vside_navigation_toolbar.png)

### <a name="filter-to-a-specific-type-of-code-element"></a>Belirli bir kod öğesi türü için filtre

Belirli türde bir kod öğesi aramanızı daraltmak için arama kutusunda bir önek belirtin veya beş filtre simgelerinden birini seçin:

önek | Simge | Kısayol | Açıklama
:----: | ---- | -------- | ---
\#     | ![Sembol simgesi](media/gotoall_symbolicon.png) | **CTRL**+**1**, **Ctrl**+**S** | Belirtilen simgeyi gidin
F      | ![Dosya simgesi](media/gotoall_fileicon.png)     | **CTRL**+**1**, **Ctrl**+**F** | Belirtilen dosyaya gidin
m      | ![Üye Simgesi](media/gotoall_membericon.png) | **CTRL**+**1**, **Ctrl**+**M** | Belirtilen üye gidin
t      | ![Tür simgesi](media/gotoall_typeicon.png)     | **CTRL**+**1**, **Ctrl**+**T** | Belirtilen türe Git
:      | ![Satır simgesi](media/gotoall_lineicon.png)     | **CTRL**+**G**         | Belirtilen satır numarasına gidin

### <a name="filter-to-a-specific-location"></a>Belirli bir konuma filtre

Belirli bir konuma aramanızı daraltmak için iki belge simgelerinden birini seçin:

Simge | Açıklama
---- | ---
![Geçerli belge](media/gotoall_currentdocument.png) | Yalnızca geçerli belgede arama
![Dış belgeleri](media/gotoall_external.png) | Proje/çözüm bulunan listelenenlere dış belge Ara

## <a name="camel-casing"></a>Ortası büyük/küçük harf

Kullanırsanız [ortası büyük/küçük harf](https://en.wikipedia.org/wiki/Camel_case) kodunuzda, yalnızca büyük harfle kod öğe adı girerek kod öğeleri daha hızlı bulabilirsiniz. Örneğin, kodunuzu adlı bir türü varsa `CredentialViewModel`, seçerek aramayı daraltabilirsiniz **türü** filtre (**t**) ve yalnızca büyük harfle adı girerek (`CVM`) içinde Git iletişim kutusu. Bu özellik, kodunuzu uzun adı varsa yararlı olabilir.

![Pencere Git büyük harfler ile arama-](../ide/media/vside_capitalsearch.png)

## <a name="settings"></a>Ayarlar

Dişli simgesini seçerek ![Dişli simgesi](media/gotoall_gear.png) Bu özellik şeklini değiştirmenize olanak sağlar:

Ayar | Açıklama
------- | ---
Önizleme sekmesini kullanın | Seçili öğeyi hemen IDE'nin Önizleme sekmesinde görüntüler
Ayrıntıları Göster    | Proje, dosya, satır ve belge açıklamaları Özet bilgilerden penceresinde görüntüle
Center penceresi   | Kod düzenleyicisinde, sağ üst yerine üst-orta bu pencereyi gitme

## <a name="see-also"></a>Ayrıca bkz.

- [Kod gidin](../ide/navigating-code.md)
- [Satıra Git iletişim kutusu](../ide/reference/go-to-line.md)
- [Tanıma ve Özet Tanıma Gitme](../ide/go-to-and-peek-definition.md)