---
title: 'CA1303: Harfleri yerelleştirilmiş parametreler olarak göndermeyin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b9c20d0c11711f3736f29498f9519f07163e7cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303: Harfleri yerelleştirilmiş parametreler olarak göndermeyin
|||
|-|-|
|TypeName|DoNotPassLiteralsAsLocalizedParameters|
|CheckId|CA1303|
|Kategori|Microsoft.Globalization|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Bir yöntem bir dize sabit değeri parametre olarak Oluşturucusu veya yönteminde geçirir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sınıf kitaplığı ve dize yerelleştirilebilir olmalıdır.

 Bu uyarı, hazır bir dize parametresi ya da özelliği için bir değer olarak geçirilir ve bir veya daha fazla aşağıdaki durumlarda doğru olduğunda ortaya çıkar:

-   <xref:System.ComponentModel.LocalizableAttribute> Parametresi ya da özelliğin özniteliği true.

-   Parametresi veya özellik adı "Metin", "İletisi" veya "Resim yazısı" içerir.

-   Console.Write veya Console.WriteLine yönteme geçirilen dize parametresi "value" veya "biçim" adıdır.

## <a name="rule-description"></a>Kural Tanımı
 Kaynak kodunda katıştırılmış dize değişmez değerleri yerelleştirme zordur.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için dize sabit değeri bir örneği üzerinden alınan bir dizeyi yerine <xref:System.Resources.ResourceManager> sınıfı.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Kod kitaplığı değil yerelleştirilmiş veya dize son kullanıcı ya da kod kitaplığı kullanarak bir geliştirici açık değilse bir uyarı bu kuraldan gizlemek güvenlidir.

 Kullanıcılar ya da parametre veya adlı özellik yeniden adlandırma ya da bu öğeleri koşullu olarak işaretleme yerelleştirilmiş dizeleri geçirilmemelidir yöntemleri karşı gürültü ortadan kaldırabilirsiniz.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, iki bağımsız değişkenlerinin birini aralık dışında olduğunda aykırı bir yöntemi gösterir. İlk bağımsız değişkeni için özel durum Oluşturucusu bu kuralı ihlal sabit değerli bir dize geçirilir. İkinci bağımsız değişkeni için Oluşturucusu üzerinden alınan bir dizeyi doğru geçirilen bir <xref:System.Resources.ResourceManager>.

 [!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
 [!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
 [!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Masaüstü Uygulamalarındaki Kaynaklar](/dotnet/framework/resources/index)