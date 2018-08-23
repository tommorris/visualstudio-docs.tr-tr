---
title: 'CA1900: Değer tür alanları taşınabilir olmalıdır | Microsoft Docs'
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
- CA1900
- ValueTypeFieldsShouldBePortable
helpviewer_keywords:
- ValueTypeFieldsShouldBePortable
- CA1900
ms.assetid: 1787d371-389f-4d39-b305-12b53bc0dfb9
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b0a636c1de245aa46adb0b0e43c6802dddf57810
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690010"
---
# <a name="ca1900-value-type-fields-should-be-portable"></a>CA1900: Değer tür alanları taşınabilir olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017 ile ilgili en son belgeler için bkz. [CA1900: değer tür alanları taşınabilir](https://docs.microsoft.com/visualstudio/code-quality/ca1900-value-type-fields-should-be-portable) docs.microsoft.com'da.  
  
|||  
|-|-|  
|TypeName|ValueTypeFieldsShouldBePortable|  
|CheckId|CA1900|  
|Kategori|Microsoft.Portability|  
|Yeni Değişiklik|Alan derlemesi dışında görülebilir, - kesiliyor.<br /><br /> Bölünemez - alanın derlemenin dışında görünür değilse.|  
  
## <a name="cause"></a>Sebep  
 Bu kural ile açık düzene bildirilen yapıları için 64-bit işletim sistemlerinde yönetilmeyen kod sıralandığı zaman doğru olarak hizalamayı denetler. IA-64 hizalanmamış bellek erişir ve bu ihlal düzeltilmezse süreci kilitlenecek izin vermez.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Sahip 64 bit işletim sistemlerinde Çökmelere neden olur yanlış hizalanmış alanlar içeren açık Yerleşimli yapılar.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 8 bayttan küçük olan tüm alanlar, boyutunun bir katı olan uzaklık ve 8 bayt alanlar olmalıdır veya daha fazla 8'in katı olan uzaklık olması gerekir. Başka bir çözüm `LayoutKind.Sequential` yerine `LayoutKind.Explicit`makul verilebilir.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarı yalnızca hata oluşursa atlanması.

