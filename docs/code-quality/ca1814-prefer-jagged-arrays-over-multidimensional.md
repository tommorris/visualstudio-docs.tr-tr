---
title: 'CA1814: Tercih basit dizileri çok boyutlu üzerinden | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
helpviewer_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2f87c0141b437cebce2531b5b1ec4cd983fa1822
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1814-prefer-jagged-arrays-over-multidimensional"></a>CA1814: Basit dizileri çok boyutlu dizilere tercih edin
|||  
|-|-|  
|TypeName|PreferJaggedArraysOverMultidimensional|  
|CheckId|CA1814|  
|Kategori|Microsoft.Performance|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Üye çok boyutlu bir diziye bildirildi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Basit bir dizi, öğeleri dizi olan bir dizidir. Öğeleri olan diziler bazı veri kümeler için daha az harcanmış önde gelen farklı boyutlarda olabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için basit bir dizi boyutlu bir diziye değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Çok boyutlu dizi alanı harcamamasını varsa bir uyarı bu kuraldan engelleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, basit ve çok boyutlu diziler için bildirimleri gösterir.  
  
 [!code-vb[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/VisualBasic/ca1814-prefer-jagged-arrays-over-multidimensional_1.vb)]
 [!code-csharp[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/CSharp/ca1814-prefer-jagged-arrays-over-multidimensional_1.cs)]