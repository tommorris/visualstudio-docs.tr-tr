---
title: Kod Ölçümleri Sorunlarını Giderme
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: troubleshooting
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b8c5dfd9c388e8c2ab4ce83ca0c952851616835c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="troubleshooting-code-metrics-issues"></a>Kod Ölçümleri Sorunlarını Giderme
Kod ölçümleri toplarken aşağıdaki sorunlardan bazıları karşılaşabilirsiniz:

-   [Visual Studio 2010 kod karmaşıklığı hesaplamalar değişiklikleri](#Changes_in_Visual_Studio_2010_code_complexity_calculations)

##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a> Visual Studio 2010 kod karmaşıklığı hesaplamalar değişiklikleri
 Aynı işlevi için Kod Karmaşıklığı ölçüm hesaplanır, ancak [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] önceki sürümleri tarafından hesaplanan ölçüm farklı olabilir [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] aşağıdaki durumlar için:

-   Daha fazla catch blokları ya da bir işlev içeriyor. Önceki sürümlerinde [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], catch blokları hesaplamadaki dahil. İçinde [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], her catch bloğu karmaşıklığını işlevi karmaşıklığını eklenir.

-   İşlev switch (seçin durumda VB) ifadesi içermektedir. Derleyici arasındaki farklılıklar [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] ve önceki sürümleri, başarısızlığı durumları içeren bazı switch deyimleri için farklı MSIL kodu oluşturabilir.

## <a name="see-also"></a>Ayrıca Bkz.
 [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)