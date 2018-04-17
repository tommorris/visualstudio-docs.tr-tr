---
title: 'CA1806: yöntem sonuçlarını yoksaymayın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1806
- DoNotIgnoreMethodResults
helpviewer_keywords:
- CA1806
- DoNotIgnoreMethodResults
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 90908bb85d88d939e2886f60083c0499cde2823c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1806-do-not-ignore-method-results"></a>CA1806: Yöntem sonuçlarını yoksaymayın
|||  
|-|-|  
|TypeName|DoNotIgnoreMethodResults|  
|CheckId|CA1806|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Bu uyarı için birkaç olası nedenler şunlardır:  
  
-   Yeni bir nesne oluşturulur, ancak hiç kullanılmadı.  
  
-   Oluşturur ve yeni bir dize döndüren bir yöntem olarak adlandırılır ve yeni bir dize hiçbir zaman kullanılır.  
  
-   Hiç kullanılmamış bir HRESULT veya hata kodu döndürüyor COM ya da P/Invoke yöntemi. Kural Tanımı  
  
 Gereksiz nesne oluşturma ve kullanılmayan nesnesinin ilişkili çöp toplama performansı düşebilir.  
  
 Dize değişmez ve String.ToUpper gibi yöntemleri çağırma yöntemi dizesinde örneğini değiştirmek yerine bir dize yeni bir örneğini döndürür.  
  
 HRESULT ya da hata kodu yoksayılıyor hata koşulları beklenmeyen davranışlara veya düşük kaynak koşulları yol açabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Yöntem A hiç kullanılmamış B nesnesinin yeni bir örneğini oluşturur, örnek bir bağımsız değişken olarak başka bir yönteme geçirin veya örnek bir değişkene atayın. Nesne oluşturma gereksizse kaldıramazsınız- veya -  
  
 Yöntemi A B yöntemini çağırır, ancak B yöntem yeni string örneği kullanmaz olması gerekir. Örnek bir bağımsız değişken olarak başka bir yönteme geçirin, örnek bir değişkene atayın. Veya gereksiz ise çağrı kaldırın.  
  
 -veya-  
  
 Yöntem A, B yöntemini çağırır ancak HRESULT kullanmaz veya hata kodu yöntemi döndürür. Sonuç koşullu deyimini sonucu bir değişkene atayın veya bağımsız değişken olarak başka bir yönteme geçirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Nesne oluşturma işlemi bazı amaca hizmet eder sürece bu kuraldan bir uyarı bastırma değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek arama String.Trim sonucunu yoksayar bir sınıfı gösterir.  
  
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_1.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_1.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, önceki ihlali geri çağrıldı değişken String.Trim sonucunu atayarak giderir.  
  
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_2.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_2.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_2.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek oluşturduğu bir nesne kullanmayan bir yöntemi gösterir.  
  
> [!NOTE]
>  Visual Basic'te bu ihlali yeniden oluşturulamaz.  

 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_3.cpp)]
 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_3.cs)]   
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne gereksiz oluşturulmasını kaldırarak önceki ihlali giderir.  

 [!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_4.cs)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_4.cpp)] 

<!-- Examples don't exist for the below... -->
<!--
## Example  
 The following example shows a method that ignores the error code that the native method GetShortPathName returns.  
  
## Example  
 The following example fixes the previous violation by checking the error code and throwing an exception when the call fails.  
-->