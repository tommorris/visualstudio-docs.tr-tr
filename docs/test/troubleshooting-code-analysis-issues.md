---
title: "Kod Analizi sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c7e44d-2780-4df5-9bcb-49e40c1152fc
caps.latest.revision: "5"
author: erickson-doug
ms.author: douge
manager: douge
ms.openlocfilehash: 3ef4a68d7b5cc8f904ea84f961083b3d7de24ef6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="troubleshooting-code-analysis-issues"></a>Kod Çözümleme Sorunlarını Giderme
Bu konu, aşağıdaki Visual Studio Kod Analizi sorunlarını ilişkin sorun giderme bilgileri içerir.  
  
-   [Bir Visual Studio 2010 kural kümesi olan önceki Visual Studio sürümlerinde yansıtılan değil değişiklikleri](#ChildRuleSetChangesInPreviousVersions)  
  
##  <a name="ChildRuleSetChangesInPreviousVersions"></a>Bir Visual Studio 2010 kural kümesi olan önceki Visual Studio sürümlerinde yansıtılan değil değişiklikleri  
 Bir kural kümesi oluşturduğunuzda [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] alt kural kümesini içeren, bir değişiklik alt kural kümesi için Kod Analizi çalıştırır, Visual Studio'nun önceki bir sürümünü kullanan bilgisayarlarda uygulanmayabilir. Bu sorunu çözmek için bir yeniden yazma alt kural kümesini içeren kural kümesi olan üst kural kümesinin zorlaması gerekir.  
  
1.  Açık üst kural kümesinde [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].  
  
2.  Ekleyerek veya kaldırarak bir kuralı gibi bir değişiklik yapın ve sonra kural kümesini kaydedin.  
  
3.  Kural kümesini yeniden açın, değişikliği geri ve kural kümesi yeniden kaydedin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama kalitesini analiz etme](../code-quality/analyzing-application-quality-by-using-code-analysis-tools.md)   
 [Yönetilen kod kalitesini analiz etme](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)   
 [Kod çözümleme kurallarını gruplandırmak için kural kullanarak ayarlar](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)