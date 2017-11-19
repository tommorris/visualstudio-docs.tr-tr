---
title: "CA1027: Numaralandırmaları FlagsAttribute ile işaretle | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MarkEnumsWithFlags
- CA1027
helpviewer_keywords:
- CA1027
- MarkEnumsWithFlags
ms.assetid: 249e882c-8cd1-4c00-a2de-7b6bdc1849ff
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3e2fa3e93b8c4673a4b50b1baa46befbc01f7f7e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1027-mark-enums-with-flagsattribute"></a>CA1027: Numaralandırmaları FlagsAttribute ile işaretle
|||  
|-|-|  
|TypeName|MarkEnumsWithFlags|  
|CheckId|CA1027|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Genel sabit listesi değerler iki tabanların veya sabit listesinde tanımlanan diğer değerleri birleşimleridir ve <xref:System.FlagsAttribute?displayProperty=fullName> özniteliği mevcut değil. Hatalı pozitif sonuçları azaltmak için bu kural bir ihlali bitişik değerlere sahip numaralandırmalar için bildirmiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir numaralandırma ilişkili adlandırılmış sabitler kümesini tanımlayan değer türüdür. Uygulama <xref:System.FlagsAttribute> adlandırılmış sabitler anlamlı birleştirilebilir, bir sabit. Örneğin, uygulamada hangi günün kaynaklar kullanılabilir izler haftanın günlerini numaralandırması göz önünde bulundurun. Her kaynak kullanılabilirliğini sahip numaralandırması kullanılarak kodlanır <xref:System.FlagsAttribute> varsa, gün, herhangi bir birleşimini temsil. Öznitelik olmadan, yalnızca bir haftanın gününü temsil edilebilir.  
  
 Combinable numaralandırmalar depolama alanları, tek tek numaralandırma değerlerinin bit alanındaki grupları olarak kabul edilir. Bu nedenle, bu tür alanları olarak da adlandırılır *bit alanları*. Bir bit alanı depolama için numaralandırma değerleri birleştirmek için koşullu Boole işleçleri kullanın. Belirli numaralandırma değeri mevcut olup olmadığını belirlemek için bir bit alanı sınamak için Boolean mantıksal işleçler kullanın. Bir bit alanı birleşik numaralandırma değerlerinin doğru depolanıp iki gücünü numaralandırmada tanımlanan her bir değeri olmalıdır. Bu nedenle olmadığı sürece, Boolean mantıksal işleçler alanda depolanan tek tek numaralandırma değerlerini ayıklayabilirsiniz olmaz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için add <xref:System.FlagsAttribute> numaralandırması için.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Numaralandırma değerlerinin combinable olmasını istemiyorsanız bu kural bir uyarıdan engelleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `DaysEnumNeedsFlags` kullanarak gereksinimlerini karşılayan bir numaralandırma <xref:System.FlagsAttribute>, yok ancak. `ColorEnumShouldNotHaveFlag` Numaralandırma iki tabanların olan bir değere sahip değil, ancak yanlış belirtir <xref:System.FlagsAttribute>. Bu kural ihlal [CA2217: numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md).  
  
 [!code-csharp[FxCop.Design.EnumFlags#1](../code-quality/codesnippet/CSharp/ca1027-mark-enums-with-flagsattribute_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2217: numaralandırmaları FlagsAttribute ile işaretlemeyin](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.FlagsAttribute?displayProperty=fullName>