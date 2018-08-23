---
title: Kod çözümleme sorunlarını giderme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
caps.latest.revision: 7
author: erickson-doug
ms.author: gewarren
manager: douge
ms.openlocfilehash: b8d17fcaec0034d2803f769cc5595416f5d56de8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689709"
---
# <a name="troubleshooting-code-analysis-issues"></a>Kod Çözümleme Sorunlarını Giderme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Kod Analizi sorunlarını giderme](https://docs.microsoft.com/visualstudio/code-quality/troubleshooting-code-analysis-issues).  
  
Bu konu aşağıdaki Visual Studio Kod Analizi sorunlarına yönelik sorun giderme bilgileri içerir.  
  
-   [Bir Visual Studio 2010 kural kümesi olan önceki Visual Studio sürümlerinde yansıtılan olmayan değişiklikler](#ChildRuleSetChangesInPreviousVersions)  
  
##  <a name="ChildRuleSetChangesInPreviousVersions"></a> Bir Visual Studio 2010 kural kümesi olan önceki Visual Studio sürümlerinde yansıtılan olmayan değişiklikler  
 Bir kural kümesi oluşturduğunuzda [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] bir alt kural kümesi içeren, bir değişiklik alt kural kümesi için Kod Analizi yürütmeleri Visual Studio'nun önceki bir sürümünü kullanan bilgisayarlarda uygulanmayabilir. Bu sorunu çözmek için bir yeniden yazma alt kural kümesini içeren kural kümesi olan üst kural kümesinin zorlaması gerekir.  
  
1.  Açık üst kural kümesinde [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].  
  
2.  Ekleme veya bir kuralı kaldırma gibi bir değişiklik yapın ve sonra kural kümesi kaydedin.  
  
3.  Kural kümesi yeniden, değişikliğini tersine çevirebilir ve kural kümesi yeniden kaydedin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama kalitesini analiz etme](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)   
 [Yönetilen kod kalitesini analiz etme](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [Kod Analizi Kurallarını Gruplandırmak için Kural Kümeleri Kullanma](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)



