---
title: Taşınabilirlik uyarıları | Microsoft Docs
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
- vs.codeanalysis.PortabilityRules
helpviewer_keywords:
- portability warnings
- managed code analysis warnings, portability warnings
- warnings, portability
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 03ae0c7ea743379754eac7c40f86f26a3244f709
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692176"
---
# <a name="portability-warnings"></a>Taşınabilirlik Uyarıları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [taşınabilirlik uyarıları](https://docs.microsoft.com/visualstudio/code-quality/portability-warnings).  
  
Taşınabilirlik uyarıları, farklı işletim sistemleri arasında taşınabilirlik destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1900: Değer tür alanları taşınabilir olmalıdır](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Bu kural açık düzene özniteliği kullanılarak bildirilen yapıları için 64-bit işletim sistemlerinde yönetilmeyen kod sıralandığı zaman doğru hizalamayı denetler.|  
|[CA1901: P/Invoke bildirimleri taşınabilir olmalıdır](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|Bu kural her parametresinin boyutu ve P/Invoke dönüş değeri değerlendirir ve bunların boyutu 32-bit ve 64-bit işletim sistemlerinde yönetilmeyen kodun başvuruya doğru olduğunu doğrular.|  
|[CA1903: Yalnızca hedeflenen çerçeveden API kullanın](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|Bir üye veya tür, bir üye veya projedeki hedeflenen çerçeve ile birlikte dahil edilmemiş hizmet paketinde tanıtılmış türü kullanır.|



