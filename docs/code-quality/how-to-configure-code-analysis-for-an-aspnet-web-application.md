---
title: "Nasıl yapılır: Visual Studio'da bir ASP.NET Web uygulaması için kod çözümlemesini yapılandırma"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.asp
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: c924a866f1bb34f41664fbf62e372b77f4d2620e
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178243"
---
# <a name="how-to-configure-code-analysis-for-an-aspnet-web-application"></a>Nasıl yapılır: Bir ASP.NET Web Uygulaması İçin Kod Çözümlemesini Yapılandırma

Visual Studio'da Kod Analizi listesinden seçebilirsiniz *kural kümeleri* uygulamak için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] web uygulaması. Varsayılan kuralı Microsoft en az önerilen kurallar kümesidir. Başka bir kural web sitesine uygulamak için kümesini seçebilirsiniz.

1. Web sitesinde seçin **Çözüm Gezgini**.

2. Üzerinde **Çözümle** menüsünde tıklatın **Web sitesi için Kod Analizi yapılandırma**.

3. Seçtiğiniz çözüm ve birden çok proje çözümü varsa, yapı, yapılandırma ve hedef işletim sisteminden seçin **yapılandırma** ve **Platform** listeler.

4. Çözümde her proje için tıklatın **kural kümesi** sütun ve ardından çalıştırmak için kuralın adını ayarlayın.

5. Varsayılan olarak, Çözümdeki tüm projeleri üzerinde kod analizini Çalıştır. Belirli bir projenin kod analizini etkinleştir veya devre dışı bırakmak için aşağıdaki adımları izleyin:

    1. Proje adına sağ tıklayın ve ardından Özellikler seçeneğine tıklayın.

    2. İşaretleyin veya temizleyin **kod çözümlemeyi etkinleştir** onay kutusu. Ayrıca kod analizini el ile seçerek çalıştırabilirsiniz **Web sitesinde kod analizini Çalıştır** gelen **Çözümle** menüsü.

6. İçinde **bu kural kümesini Çalıştır** aşağı açılan listesinde, aşağıdaki adımları izleyin:

    - Kullanmak istediğiniz bir kural kümesi seçin.

    - Seçin  **\<Gözat >** var olan bir özel kural kümesini belirlemek için listesinde değil.

    - Tanımlayan bir [özel kural kümesi](../code-quality/how-to-create-a-custom-rule-set.md).