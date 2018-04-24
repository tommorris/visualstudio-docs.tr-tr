---
title: DSL Tanımlarına Uzantılar Ekleme
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7de01ec87ca4367dcd3453c41e38c653c5184beb
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="add-extensions-to-dsl-definitions"></a>Uzantıları için DSL tanımları ekleme

DSL tanımı uzantısı, bir etki alanına özgü dil (DSL) uzantıları paketi oluşturmanıza olanak sağlar. Bir Visual Studio Tümleştirme Uzantısı'na (VSIX) bulunur, DSL uzantısı bir kullanıcının bilgisayarında DSL aynı şekilde yüklenebilir. Ek özellikler dinamik olarak etkin ve çalışma zamanında devre dışı. DSL'ler açıkça uzantısı için tasarlanmış gerekmez ve uzantıları daha sonra veya üçüncü tarafların genişletilmiş DSL değiştirmeden tasarlanabilir.

DSL uzantıları aşağıdaki özellikler içerebilir:

-   Model ve sunu öğelerin özellikleri

-   Şekilleri ve bağlayıcıları için dekoratörler

-   Sınıfları, ilişkileri, şekilleri ve bağlayıcıları

-   Doğrulama kısıtlamaları

-   Araç kutusu öğelerini ve sekmeleri

Genişletilmiş bir DSL kullanıcısı oluşturun ve ek özellikler örneklerini içeren bir modeli kaydedin. Model uygun uzantısı yüklü diğer kullanıcılar tarafından okunabilir. Uzantısı yüklü olmayan kullanıcılar ek özellikleri kullanamaz, ancak güncelleştirin ve ek özellikler kaybetmeden bir modeli kaydedin.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Ayrıca Bkz.

- [İlgili blog gönderileri](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
