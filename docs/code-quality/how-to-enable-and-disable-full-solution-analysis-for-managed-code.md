---
title: 'Nasıl yapılır: yönetilen kod için tam çözüm analizini devre | Microsoft Docs'
ms.date: 03/23/2018
ms.topic: conceptual
helpviewer_keywords:
- full solution analysis
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-code-analysis
ms.workload:
- dotnet
ms.openlocfilehash: 5221f2a97f892f272cce33b4f464a9ff223e8824
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>Nasıl yapılır: etkinleştirme ve yönetilen kod için tam çözüm analizini devre dışı

*Tam çözüm analizini* de kodda, dosyaları veya Kod Analizi sorunlarını yalnızca dosyalarında açık Visual C# veya Visual Basic çözümünüzdeki görmenize olanak sağlayan bir Visual Studio özelliği kapalı olduğu. Varsayılan olarak, tam çözüm analizini olan *etkin* Visual Basic ve *devre dışı* Visual C# için.

Tüm sorunları tüm dosyaları görmek kullanışlı olabilir, ancak ayrıca dikkat dağıtıcı olabilir. Çözümünüzü çok büyük veya çok sayıda dosya varsa, bir Visual Studio yavaşlar. Gösterilen sorunları sayısı sınırı ve Visual Studio performansı artırmak için tam çözüm analizini devre dışı bırakabilirsiniz. Bu özellik, gerekirse kolayca etkinleştirebilirsiniz.

## <a name="to-toggle-full-solution-analysis"></a>Tam çözüm analizini geçiş yapmak için

1. Açmak için **seçenekleri** Seç iletişim kutusu, Visual Studio menü çubuğunda **Araçları** > **seçenekleri**.

1. İçinde **seçenekleri** iletişim kutusunda, seçin **metin düzenleyici** > **C#** veya **temel**  >   **Gelişmiş**.

1. Seçin **tam çözüm analizini etkinleştir** onay kutusunu tam çözüm analizini etkinleştirme veya devre dışı bırakmak kutusunun işaretini kaldırın. Seçin **Tamam** tamamladığınızda.

    ![Tam çözüm analizi onay kutusunu etkinleştirin.](../code-quality/media/options-enable-full-solution-analysis.png)

## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>Sonuçlarını etkinleştirme ve tam çözüm analizini devre dışı bırakma

Aşağıdaki ekran görüntüsünde, tam çözüm analizini etkinleştirildiğinde sonuçlarını görebilirsiniz. Tüm hataları ve Kod Analizi sorunlarını *tüm* çözüm dosyalarını, dosyalar veya açık olup bağımsız olarak görünür.

![Tam çözüm analizini etkin.](../code-quality/media/fsa_enabled.png)

Aşağıdaki ekran görüntüsünde, tam çözüm analizini devre dışı bıraktıktan sonra aynı çözümden sonuçlarını gösterir. Yalnızca hataları ve Kod Analizi sorunlarını açık çözüm dosyalarında görünür **hata listesi**.

![Tam çözüm analizini devre dışı.](../code-quality/media/fsa_disabled.png)

## <a name="automatically-disable-full-solution-analysis"></a>Otomatik olarak tam çözüm analizini devre dışı bırak

Visual Studio algılarsa, 200 MB veya daha az sistem belleği için kullanılabilir, etkinleştirildiğinde, otomatik olarak tam çözüm analizini (ve bazı diğer özellikler) devre dışı bırakır. Bu gerçekleşirse, Visual Studio bazı özellikler devre dışı bildiren bir uyarı görüntülenir. Bir düğme istiyorsanız tam çözüm analizini etkinleştirme olanak sağlar.

![Uyarı metni tam çözüm analizini askıya alma](../code-quality/media/fsa_alert.png)