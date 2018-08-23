---
title: Yönetilen kod için yönetilen minimum kurallar kural kümesi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: cca9670f65ef517a4697fc0752c65cbafbaa3b16
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692036"
---
# <a name="managed-minimun-rules-rule-set-for-managed-code"></a>Yönetilen kod için Yönetilen Minimum Kurallar kural kümesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yönetilen kod için yönetilen minimum kurallar kural kümesi](https://docs.microsoft.com/visualstudio/code-quality/managed-minimun-rules-rule-set-for-managed-code).  
  
Yönetilen Minimum kurallar potansiyel güvenlik boşluklarını, uygulama kilitlenmesi ve diğer önemli mantık ve tasarım hataları gibi kodunuzda en kritik sorunlara odaklanır. Projeleriniz için oluşturduğunuz herhangi bir özel kural kümesi bu kural kümesini içermelidir.  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|Atılabilir alanlara sahip türler atılabilir olmalıdır|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|Boş Sonlandırıcıları kaldırın|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Atılabilen alanlar atılmalıdır|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Eşittir işlecini ValueType.equals'ı geçersiz kılarak üzerinde|



