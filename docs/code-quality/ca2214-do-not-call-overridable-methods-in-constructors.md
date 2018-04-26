---
title: 'CA2214: Geçersiz kılınabilir yöntemleri oluşturucular içinde çağırmayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5ebcd4164f9db28d4cb1f150ee3a4bb21b21cde
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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

 **Temel ctor çağrılıyor. ** 
 **Türetilmiş DoSomething çağrılır - başlatılan? Hayır**
**arama ctor türetilmiş.**