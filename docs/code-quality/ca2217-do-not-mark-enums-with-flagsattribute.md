---
title: 'CA2217: numaralandırmaları FlagsAttribute ile işaretlemeyin | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
helpviewer_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
ms.assetid: 1b6f626c-66bf-45b0-a3e2-7c41ee9ceda7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a2cdfcf4014d00ca2d975a04a8bb81191a717e0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217: Numaralandırmaları FlagsAttribute ile işaretlemeyin
|||  
|-|-|  
|TypeName|DoNotMarkEnumsWithFlags|  
|CheckId|CA2217|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür numaralandırma işaretlenmiş <xref:System.FlagsAttribute> ve onu bir veya iki ya da başka bir birleşimini tabanların olmayan daha fazla değer sabit değerleri tanımlı.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir numaralandırma olmalıdır <xref:System.FlagsAttribute> yalnızca sabit listesinde tanımlanan her iki gücünü değerdir veya bir birleşimini tanımlı değerler mevcutsa.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için kaldırmak <xref:System.FlagsAttribute> gelen numaralandırması.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir numaralandırma ne iki gücünü ya da değerlere herhangi bir birleşimini olan 3 değeri içeren bir renk gösterir. Renk numaralandırması ile işaretlenmemiş <xref:System.FlagsAttribute>.  
  
 [!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
 [!code-csharp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
 [!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek System.FlagsAttribute ile işaretlenen gereksinimlerini karşılayan bir numaralandırma, gün, gösterir.  
  
 [!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
 [!code-csharp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
 [!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1027: Numaralandırmaları FlagsAttribute ile işaretleyin](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.FlagsAttribute?displayProperty=fullName>