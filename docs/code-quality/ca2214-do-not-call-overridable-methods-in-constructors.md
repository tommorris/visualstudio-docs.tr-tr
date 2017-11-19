---
title: "CA2214: geçersiz kılınabilir yöntemleri oluşturucular içinde çağırmayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bbe640ac82c159b39721ddac27b9d65926c60647
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214: Geçersiz kılınabilir yöntemleri oluşturucular içinde çağırmayın
|||  
|-|-|  
|TypeName|DoNotCallOverridableMethodsInConstructors|  
|CheckId|CA2214|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Korumasız bir türde Oluşturucusu kendi sınıfında tanımlanan sanal bir yöntem çağırır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Sanal bir yöntem çağrıldığında, çalışma zamanına kadar yöntemini yürütür gerçek türü seçilmedi. Bir oluşturucu sanal bir yöntem çağırdığında yöntemi çağırır örnek oluşturucusu değil yürüttüğünü mümkündür.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için bir tür sanal yöntemleri tür oluşturucular içinde çağırmayın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Sanal bir yöntem çağrısı ortadan kaldırmak için Oluşturucusu yeniden tasarlanması gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal etkisini gösterir. Test uygulaması bir örneğini oluşturur `DerivedType`, kendi temel sınıfının neden olur (`BadlyConstructedType`) yürütmek için Oluşturucusu. `BadlyConstructedType`kişinin Oluşturucusu yanlış sanal yöntemini çağırır `DoSomething`. Çıktı gösterildiği gibi `DerivedType.DoSomething()` çalıştırır ve bu nedenle önce mu `DerivedType`'s Oluşturucusu yürütür.  
  
 [!code-csharp[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/CSharp/ca2214-do-not-call-overridable-methods-in-constructors_1.cs)]
 [!code-vb[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/VisualBasic/ca2214-do-not-call-overridable-methods-in-constructors_1.vb)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **Temel ctor çağrılıyor.**  
**Türetilen DoSomething çağrılır - başlatılan? Yok**  
**Türetilen arama ctor.**