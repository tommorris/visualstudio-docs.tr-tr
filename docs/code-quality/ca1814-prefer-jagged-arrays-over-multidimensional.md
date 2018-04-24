---
title: 'CA1814: Basit dizileri çok boyutlu dizilere tercih edin'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: cedac542d003ccc89357f3a01e2f167a2471a128
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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