---
title: 'Nasıl yapılır: bir çözümde birden çok proje için yönetilen kod kural kümesi belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.solution
ms.assetid: 92dc3250-a010-4396-b515-f03a0b30cd2a
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 42b04eb88e6edee2d8250ac29a26f4cfe6562a29
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684364"
---
# <a name="how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution"></a>Nasıl Yapılır: Bir Çözümde Birden Çok Proje İçin Yönetilen Kod Kural Kümesi Belirtme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: belirtin yönetilen kod kural kümesi için bir çözümde birden çok proje](https://docs.microsoft.com/visualstudio/code-quality/how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution).  
  
Varsayılan olarak, Microsoft en az önerilen kurallar Kod Analizi bir çözümün tüm yönetilen projelere atanır *kural kümesi*. Proje Özellikleri iletişim kutusunda çözüm için bir çözüm atanmış olan kural kümeleri değiştirebilirsiniz.  
  
> [!NOTE]
>  Varsayılan olarak, Kod Analizi projesi bir derleme adımı olarak çalıştırılmaz. Kod Analizi bir derleme adımı olarak etkinleştirmek için bkz: [nasıl yapılır: yönetilen kod projesi için Kod Analizi yapılandırma](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md).  
  
### <a name="to-specify-a-rule-set-for-multiple-projects-in-a-managed-code--solution"></a>Yönetilen kod çözümde birden çok proje için bir kural belirtmek için  
  
1.  İçinde [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)]. [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], veya [!INCLUDE[vsPro](../includes/vspro-md.md)] çözümü açın.  
  
2.  Üzerinde **Çözümle** menüsünde tıklatın **çözüm için Kod Analizi yapılandırma**.  
  
3.  Gerekirse genişletin **ortak özellikler**ve ardından **Kod Analizi ayarları**.  
  
4.  Bir veya daha fazla proje için bir kural belirtebilirsiniz.  
  
    -   Bir kural kümesi için bir projeyi belirtmek için proje adına tıklayın.  
  
    -   Birden çok proje için bir kural belirtmek için CTRL tuşunu basılı tutun ve proje adları tıklayın.  
  
    -   Çözümdeki tüm projeleri belirtmek için SHIFT tuşunu basılı tutun ve Proje listesinde tıklayın.  
  
5.  Tıklayın **kural kümesi** alan bir proje ve kural adını ayarlayın uygulamak istediğiniz'a tıklayın.



