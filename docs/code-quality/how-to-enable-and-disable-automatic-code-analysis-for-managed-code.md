---
title: 'Nasıl yapılır: Yönetilen Kod İçin Otomatik Kod Çözümlemesini Etkinleştirme ve Devre Dışı Bırakma'
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3113143b07ccb6f765cd0cf1735b34be6e952c72
ms.sourcegitcommit: 6672a1e9d135d7e5cca3cceea07c6fe5a0871475
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2018
ms.locfileid: "47443551"
---
# <a name="how-to-enable-and-disable-automatic-code-analysis-for-managed-code"></a>Nasıl yapılır: yönetilen kod için otomatik kod analizini devre

Yönetilen kod projesi, her yapıdan sonra çalıştırmak için Kod Analizi yapılandırabilirsiniz. Farklı kod analizi özelliklerini her derleme yapılandırması ayarlayın, örneğin, hata ayıklama ve yayın.

## <a name="to-enable-or-disable-automatic-code-analysis"></a>Etkinleştirme veya devre dışı otomatik kod çözümlemesini

1. İçinde **Çözüm Gezgini**, projeye sağ tıklayın ve ardından **özellikleri**.

1. Proje Özellikleri iletişim kutusunda seçin **Kod Analizi** sekmesi.

1. İçinde derleme türünü belirtmeniz **yapılandırma** ve hedef platform **Platform**.

1. Etkinleştirmek veya otomatik kod analizini devre dışı bırakmak için seçin veya temizleyin **derlemede kod analizini etkinleştir** onay kutusu.

> [!NOTE]
> **Derlemede kod analizini etkinleştir** onay kutusu yalnızca statik kod analizi etkiler. Bu etkilemez [Roslyn kod Çözümleyicileri](roslyn-analyzers-overview.md), bir NuGet paketi olarak yüklü değilse derleme sırasında her zaman yürütün. Çözümleyici hataları temizlemek istiyorsanız **hata listesi**, seçerek geçerli tüm ihlalleri gizleyebilirsiniz **Çözümle** > **kod analizini Çalıştır ve etkin gösterme Sorunları** menü çubuğundaki. Daha fazla bilgi için [ihlallerini gösterme](use-roslyn-analyzers.md#suppress-violations).
