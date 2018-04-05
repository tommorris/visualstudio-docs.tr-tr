---
title: "Nasıl yapılır: bir çözümde birden çok proje için yönetilen kod kural kümesi belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.solution
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: e0b6a2864340f87702b765f49605ebdb3aaa555c
ms.sourcegitcommit: bfa26fd7426af0d065cb2eef3d6827b5d6f7986c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2018
---
# <a name="how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution"></a>Nasıl Yapılır: Bir Çözümde Birden Çok Proje İçin Yönetilen Kod Kural Kümesi Belirtme

Varsayılan olarak, bir çözümün tüm yönetilen projeleri Microsoft Minimum önerilen kurallar Kod Analizi atanan *kural kümesi*. Çözüm için Özellikler iletişim kutusunda bir çözümün projelerine atanan kural kümeleri değiştirebilirsiniz.

> [!NOTE]
> Varsayılan olarak, proje Kod Analizi derleme adımı çalıştırılmaz. Kod çözümleme derleme adımı olarak etkinleştirmek için bkz: [nasıl yapılır: yönetilen kod projesi için Kod Analizi yapılandırma](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md).

1. Çözümü Visual Studio'da açın.

2. Üzerinde **Çözümle** menüsünde tıklatın **çözüm için Kod Analizi yapılandırma**.

3. Gerekirse, genişletin **ortak özellikleri**ve ardından **kod çözümleme ayarlarını**.

4. Bir kural kümesi için bir veya daha fazla projeleri belirtebilirsiniz.

    - Bir kural için tek bir proje kümesini belirtmek için proje adına tıklayın.

    - Bir kural için birden çok proje kümesini belirtmek için CTRL tuşunu basılı tutun ve proje adları'yi tıklatın.

    - Çözümdeki tüm projeleri belirtmek için SHIFT tuşunu basılı tutun ve Proje listesinde tıklayın.

5. Tıklatın **kural kümesi** alan bir proje ve kuralın adını ayarlayın uygulamak istediğiniz'ye tıklayın.