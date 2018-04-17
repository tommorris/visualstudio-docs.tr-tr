---
title: 'CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
helpviewer_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e68f29fed3a1f25eb2a80b1b6acf09827e8ee18f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1413-avoid-non-public-fields-in-com-visible-value-types"></a>CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının
|||  
|-|-|  
|TypeName|AvoidNonpublicFieldsInComVisibleValueTypes|  
|CheckId|CA1413|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Özellikle Bileşen Nesne Modeli (COM) olarak görünür işaretlendiğinden bir değer türü bir ortak olmayan örnek alan bildirir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 COM-görünür değer türlerinin ortak olmayan örnek alanları COM istemcilerine görünürdür. Değil açılmamalıdır ya da, istenmeyen bir tasarım veya güvenlik etkisi olmaz bilgi alanının içeriği gözden geçirin.  
  
 Varsayılan olarak, tüm ortak değer türleri COM'a görülebilir Ancak, hatalı pozitif sonuçları azaltmak için bu kural türünü açıkça belirtilen COM görünürlüğünü gerektirir. İçeren derleme ile işaretlenmiş olmalıdır <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> kümesine `false` ve tür ile işaretlenmelidir <xref:System.Runtime.InteropServices.ComVisibleAttribute> kümesine `true`.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltin ve gizli alan tutmak için bir başvuru türü için değer türü değiştirilemiyor veya kaldırılamıyor <xref:System.Runtime.InteropServices.ComVisibleAttribute> öznitelik türü.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan genele alanının kabul edilebilir ise gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.  
  
 [!code-csharp[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/CSharp/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.cs)]
 [!code-vb[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/VisualBasic/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1407: COM görünebilir türler içinde statik üyelerden kaçının](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)  
  
 [CA1017: Derlemeleri ComVisibleAttribute ile işaretleyin](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilmeyen kod ile birlikte çalışma](/dotnet/framework/interop/index)   
 [Birlikte Çalışma için .NET Türlerini Niteleme](/dotnet/framework/interop/qualifying-net-types-for-interoperation)