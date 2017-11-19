---
title: "CA1900: Değer tür alanları taşınabilir olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1900
- ValueTypeFieldsShouldBePortable
helpviewer_keywords:
- ValueTypeFieldsShouldBePortable
- CA1900
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7f2d948d78f6b12352a3e4cfcb28aab41db3e873
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: Değer tür alanları taşınabilir olmalıdır
|||  
|-|-|  
|TypeName|ValueTypeFieldsShouldBePortable|  
|CheckId|CA1900|  
|Kategori|Microsoft.Portability|  
|Yeni Değişiklik|Alanın derleme görülebilir varsa - kesiliyor.<br /><br /> Bölünemez - alanın derleme görünür değilse.|  
  
## <a name="cause"></a>Sebep  
 Bu kural, açık düzeniyle bildirilen yapıları 64-bit işletim sistemlerinde yönetilmeyen kod için sıralanmış zaman doğru uyuşacağı denetler. IA-64 hizalanmamış bellek erişir ve bu ihlali düzeltilmezse işlemi kilitleniyor izin vermiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Yanlış hizalanmış alanları neden kilitlenme 64-bit işletim sistemlerinde içeren açık düzene sahip yapıları.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 8 bayt'tan küçük tüm alanlar boyutlarına birden fazla olan uzaklıkları ve 8 bayt alanlar olmalıdır veya daha fazla 8 birden fazla olan uzaklıkları olması gerekir. Başka bir çözüm `LayoutKind.Sequential` yerine `LayoutKind.Explicit`makul durumunda.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yalnızca hata oluşursa, bu uyarıyı atlanması.