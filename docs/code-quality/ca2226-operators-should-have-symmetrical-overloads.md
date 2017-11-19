---
title: "CA2226: İşleçler simetrik aşırı olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
helpviewer_keywords:
- OperatorsShouldHaveSymmetricalOverloads
- CA2226
ms.assetid: d202401a-ea14-4559-b15e-0ea4f5b68789
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 209741d29e3607f268fff6963723c59bc2221cb0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2226-operators-should-have-symmetrical-overloads"></a>CA2226: İşleçler simetrik aşırı yüklemelere sahip olmalıdır
|||  
|-|-|  
|TypeName|OperatorsShouldHaveSymmetricalOverloads|  
|CheckId|CA2226|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Bir tür, eşitlik ya da eşitsizlik operatörünü uygular ve ters işleci uygulamaz.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Burada eşitlik veya eşitsizlik bir türün örneklerinin için geçerlidir ve ters işleci tanımsızdır hiçbir koşullar vardır. Türleri eksi değeri kadar çevrilerek eşitlik işleci döndürerek eşitsizlik işleci genellikle uygulayın.  
  
 C# Derleyici bu kural ihlalleri için bir hata verir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için eşitlik ve eşitsizlik işleçleri uygulamak veya mevcut bir kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Türünüz ile tutarlı bir şekilde çalışmaz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1046: başvuru türlerinde eşittir işlecini aşırı yüklemeyin](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)  
  
 [CA2225: İşleç aşırı yüklemeleri adlandırılmış Alternatiflere sahiptir](../code-quality/ca2225-operator-overloads-have-named-alternates.md)  
  
 [CA2224: eşittir işlecini aşırı yüklemesi üzerinde geçersiz kılma eşittir](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)  
  
 [CA2218: gethashcode'u eşittir'i geçersiz kılarak geçersiz kılın](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)  
  
 [CA2231: ValueType.Equals geçersiz kılma üzerinde aşırı işleci eşittir.](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)