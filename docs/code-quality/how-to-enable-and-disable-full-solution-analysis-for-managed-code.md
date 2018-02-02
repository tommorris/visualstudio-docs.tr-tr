---
title: "Nasıl yapılır: yönetilen kod için tam çözüm analizini devre | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- full solution analysis
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.workload:
- dotnet
ms.openlocfilehash: 64b541093aaf1a710976c0f53a3214b5d2a47e0d
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>Nasıl yapılır: etkinleştirme ve yönetilen kod için tam çözüm analizini devre dışı

*Tam çözüm analizini* de kodda, dosyaları veya Kod Analizi sorunlarını yalnızca dosyalarında açık Visual C# veya Visual Basic çözümünüzdeki görmenize olanak sağlayan bir Visual Studio özelliği kapalı olduğu. Varsayılan olarak, tam çözüm analizini etkin için Visual Basic ve Visual C# için devre dışı.

Tüm dosyaları tüm sorunları yapamamasına yararlı olsa da, dikkat dağıtıcı olabilir. Dağıtabilirsiniz da yavaş Visual Studio aşağı çözümünüzü çok büyük veya çok sayıda dosya varsa. Gösterilen sorunları sayısı sınırı ve Visual Studio performansı artırmak için tam çözüm analizini devre dışı bırakabilirsiniz. Bu özellik, gerekirse kolayca etkinleştirebilirsiniz.

## <a name="to-toggle-full-solution-analysis"></a>Tam çözüm analizini geçiş yapmak için

1. Açmak için **seçenekleri** Seç iletişim kutusu, Visual Studio menü çubuğunda **Araçları** > **seçenekleri**.

1. İçinde **seçenekleri** iletişim kutusunda, seçin **metin düzenleyici** > **C#** veya **temel**  >   **Gelişmiş**.

1. Seçin **tam çözüm analizini etkinleştir** onay kutusunu tam çözüm analizini etkinleştirme veya devre dışı bırakmak kutusunun işaretini kaldırın. Seçin **Tamam** tamamladığınızda düğmesine tıklayın.

    ![Tam çözüm analizi onay kutusunu etkinleştirin. ] (../code-quality/media/fsa_toolsoptions.png "FSA_ToolsOptions")

## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>Sonuçlarını etkinleştirme ve tam çözüm analizini devre dışı bırakma

Aşağıdaki ekran görüntüsünde, tam çözüm analizini etkinleştirildiğinde sonuçlarını görebilirsiniz. Tüm hataları ve Kod Analizi sorunlarını *tüm* çözüm dosyalarını, dosyalar veya açık olup bağımsız olarak görünür.

![Tam çözüm analizini etkin. ] (../code-quality/media/fsa_enabled.png "FSA_Enabled")

Aşağıdaki ekran görüntüsünde, tam çözüm analizini devre dışı bıraktıktan sonra aynı çözümden sonuçlarını gösterir. Yalnızca hataları ve Kod Analizi sorunlarını dosyaları görünür çözümü hata listesinde açın.

![Tam çözüm analizini devre dışı. ] (../code-quality/media/fsa_disabled.png "FSA_Disabled")

## <a name="automatically-disabling-full-solution-analysis"></a>Otomatik olarak tam çözüm analizini devre dışı bırakma

Visual Studio algılarsa, 200MB veya daha az sistem belleği için kullanılabilir, etkinleştirildiğinde, otomatik olarak tam çözüm analizini (bazı diğer özellikler için olduğu gibi) devre dışı bırakır. Bu meydana gelirse, bu bildiren bir uyarı görüntülenir. Bir düğme, tam çözüm analizini isterseniz yeniden olanak tanır.

![Uyarı metni tam çözüm analizini askıya](../code-quality/media/fsa_alert.png "FSA_Alert")