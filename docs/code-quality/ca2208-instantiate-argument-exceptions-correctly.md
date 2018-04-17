---
title: 'CA2208: bağımsız değişken özel durumlarını doğru örnekleyin | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2208
- InstantiateArgumentExceptionsCorrectly
helpviewer_keywords:
- InstantiateArgumentExceptionsCorrectly
- CA2208
ms.assetid: e2a48939-d9fa-478c-b2f9-3bdbce07dff7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c2d42da485b7d3450c0900b85945daefba0e0d5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2208-instantiate-argument-exceptions-correctly"></a>CA2208: Bağımsız değişken özel durumlarını doğru örnekleyin
|||  
|-|-|  
|TypeName|InstantiateArgumentExceptionsCorrectly|  
|CheckId|CA2208|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Aşağıdaki durumlarda olası nedenler:  
  
-   Varsayılan (parametresiz) oluşturucu veya türeyen bir özel durum türü için bir çağrı yapılır <xref:System.ArgumentException>.  
  
-   Yanlış dize bağımsız değişken veya türeyen bir özel durum türü parametreli oluşturucuya geçirilen <xref:System.ArgumentException>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Varsayılan Oluşturucu çağırmak yerine, sağlanacak daha anlamlı bir özel durum iletisi verir Oluşturucusu aşırı birini çağırın. Özel durum iletisi, geliştirici hedef ve hata durumu ve düzeltin ya da özel durum önlemek nasıl açıkça açıklanmıştır.  
  
 Bir ve iki dize oluşturucular imzalarını <xref:System.ArgumentException> ve türetilmiş türlerini ilişkilendirilebilmesi için tutarlı olmayan `message` ve `paramName` parametreleri. Bu oluşturucular doğru dize bağımsız değişkeni ile adlandırılır emin olun. İmzaları aşağıdaki gibidir:  
  
 <xref:System.ArgumentException>(string `message`)  
  
 <xref:System.ArgumentException>(string `message`, dize `paramName`)  
  
 <xref:System.ArgumentNullException>(string `paramName`)  
  
 <xref:System.ArgumentNullException>(string `paramName`, dize `message`)  
  
 <xref:System.ArgumentOutOfRangeException>(string `paramName`)  
  
 <xref:System.ArgumentOutOfRangeException>(string `paramName`, dize `message`)  
  
 <xref:System.DuplicateWaitObjectException>(string `parameterName`)  
  
 <xref:System.DuplicateWaitObjectException>(string `parameterName`, dize `message`)  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için bir ileti, bir parametre adı veya her ikisini alan bir oluşturucu çağırın ve bağımsız değişken türü için uygun olduğundan emin olun <xref:System.ArgumentException> çağrılıyor.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan yalnızca parametreli Oluşturucusu doğru dize bağımsız değişkenlerle çağrılırsa gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yanlış ArgumentNullException türünün bir örneği başlatır bir oluşturucu gösterir.  
  
 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_1.cpp)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_1.cs)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_1.vb)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yukarıdaki ihlali oluşturucu bağımsız değişkenleri geçerek giderir.  
  
 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_2.cpp)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_2.cs)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_2.vb)]