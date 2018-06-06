---
title: 'DA0006: Değer türleri için geçersiz kılma Equals() | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAOverrideEquals
- vs.performance.6
- vs.performance.DA0006
- vs.performance.rules.DA0006
ms.assetid: 4d85bdd6-b571-47e0-afd6-ba3764e4eed5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5e0d79b164c521bd3e0da53738d49451ff2a7af
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749989"
---
# <a name="da0006-override-equals-for-value-types"></a>DA0006: Değer türleri için Eşittir()'lerin üzerine yaz
|||  
|-|-|  
|Kural Kimliği|DA0006|  
|Kategori|.NET framework kullanımı|  
|Profiiling yöntemleri|Örnekleme|  
|İleti|Eşitse ve değer türleri üzerinde eşitlik işleci geçersiz kılar.|  
|İleti türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Equals yöntemi veya ortak değer türünün eşitlik işleçleri çağrıları profil oluşturma verileri önemli bir kısmının aynıdır. Daha verimli bir yöntem uygulayın.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Değer türleri için eşittir devralınan uyarlamasını kullanan <xref:System.Reflection> kitaplığı ve türündeki tüm alanlar içeriğini karşılaştırır. Yansıma hesaplama açısından pahalıdır ve her alan için eşitlik karşılaştırma gereksiz olabilir. Değer türü, kullanıcıların karşılaştırmak ya da örnekleri sıralama veya bunları karma tablosu anahtarları olarak kullanmak üzere bekliyorsanız, eşittir uygulamanız gerekir. İşleç aşırı yüklemesi programlama diliniz destekliyorsa, eşitlik ve eşitsizlik işleçleri uygulaması sağlamanız gerekir.  
  
 Eşittir ve eşitlik işleçleri geçersiz kılma hakkında daha fazla bilgi için bkz: [uygulama eşittir ve eşitlik işleci (==) için yönergeleri](http://go.microsoft.com/fwlink/?LinkId=177818).  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 Kod Analizi kural eşittir ve eşitlik işleçleri uygulama örneği için bkz [CA1815: geçersiz kılma eşittir ve işleç değer türlerinde eşittir](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)