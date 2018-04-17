---
title: Kod ölçümleri sorunlarını giderme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d8d49271d394d581349f97478a81af04b6766f4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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