---
title: "CA2114: Yöntem güvenliği türün bir üst kümesi olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ac633134b5b8037eb9e45131128b0ee0cf2887ab
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: Yöntem güvenliği türün bir üst kümesi olmalıdır
|||  
|-|-|  
|TypeName|MethodSecurityShouldBeASupersetOfType|  
|CheckId|CA2114|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bildirim temelli güvenlik türüne sahip ve yöntemlerinden biri sahip aynı güvenlik eylemi bildirimsel güvenliği ve güvenlik eylem [bağlantı talepleri](/dotnet/framework/misc/link-demands), ve türü tarafından kullanıma izinler izinler kümesini değildir yöntemi işaretlidir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir yöntemi, hem aynı eylemi için bir yöntem ve türü düzeyi bildirimsel güvenliği sahip olmamalıdır. İki denetimleri birleştirilmez; yalnızca yöntemi düzeyi talep uygulanır. Örneğin, bir tür izin talep `X`, ve yöntemlerinden birini talep izin `Y`, kod izni yok `X` yöntemi yürütülemedi.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Her iki eylemler gerekli olduğundan emin olmak için kodunuzu gözden geçirin. Her iki Eylemler gerekirse, yöntem düzeyi eylem türü düzeyinde belirtilen güvenlik içerdiğinden emin olun. Örneğin türünüz izin talep, `X`, ve kendi yöntemi izin talep gerekir `Y`, yöntem açıkça talep `X` ve `Y`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan yöntemi türü tarafından belirtilen güvenlik gerektirmiyorsa gizlemek güvenlidir. Ancak, bu normal bir senaryo değildir ve dikkatli tasarımını gözden geçirme gereksinimini gösterebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal tehlikeleri göstermek için ortam izinleri kullanır. Bu örnekte, uygulama kodu tarafından türü gerekli izni reddetmeden önce güvenli türünün bir örneğini oluşturur. Gerçek dünya tehdit senaryoda, uygulama nesnesinin bir örneği elde etmek için bir başka yolu gerektirir.  
  
 Aşağıdaki örnekte, kitaplık taleplerini yazma izni bir tür için ve bir yöntem için okuma izni.  
  
 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama kodu türü düzeyi güvenlik gereksinimleri karşılamıyor olsa bile yöntemini çağırarak kitaplığının güvenlik açığı gösterir.  
  
 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]  
  
 Bu örnek şu çıkışı üretir.  
  
 **[Tüm izinleri] Kişisel bilgi: 16/6/1964 12:00:00 AM**  
**[Yazma izni (talep türüne göre)] Kişisel bilgi: 16/6/1964 12:00:00 AM**  
**[(Yöntemi tarafından talep edilen) okuma izni yok] Kişisel bilgi erişilemedi: isteği başarısız oldu.**   
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines)   
 [Bağlantı talepleri](/dotnet/framework/misc/link-demands)   
 [Veri ve Modelleme](/dotnet/framework/data/index)