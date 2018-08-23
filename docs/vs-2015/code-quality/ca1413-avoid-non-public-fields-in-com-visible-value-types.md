---
title: 'CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
helpviewer_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 190ca50d00d17d36eb4cab82f6062e3241b65469
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693249"
---
# <a name="ca1413-avoid-non-public-fields-in-com-visible-value-types"></a>CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının](https://docs.microsoft.com/visualstudio/code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types).  
  
TypeName | AvoidNonpublicFieldsInComVisibleValueTypes |  
| Checkıd | CA1413 |  
| Kategori | Microsoft.Interoperability|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Özel Bileşen Nesne Modeli (COM) görünür olarak işaretlenmiş bir değer türü, bir ortak olmayan örnek alan bildirir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 COM-görünür değer türlerinin ortak olmayan örnek alanları COM istemcilerine görünürdür. Alanın değil açılmamalıdır veya, istenmeyen bir tasarım veya güvenlik etkisi olmayacak bilgi içeriği gözden geçirin.  
  
 Varsayılan olarak, tüm ortak türlerin COM tarafından görülebilir Ancak, hatalı pozitif sonuçları azaltmak için bu kural türünü açıkça belirtilen COM görünürlüğünü gerektirir. Derlemeyi içeren ile işaretlenmelidir <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> kümesine `false` ve türü ile işaretlenmelidir <xref:System.Runtime.InteropServices.ComVisibleAttribute> kümesine `true`.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek ve gizli alan tutmak için bir başvuru türü için değer türü değiştirme veya kaldırma <xref:System.Runtime.InteropServices.ComVisibleAttribute> türü özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Alanın genele kabul edilebilir ise bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.  
  
 [!code-csharp[FxCop.Interoperability.NonpublicField#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.NonpublicField/cs/FxCop.Interoperability.NonpublicField.cs#1)]
 [!code-vb[FxCop.Interoperability.NonpublicField#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.NonpublicField/vb/FxCop.Interoperability.NonpublicField.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1407: COM görünebilir türler içinde statik üyelerden kaçının](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)  
  
 [CA1017: Derlemeleri ComVisibleAttribute ile işaretleyin](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilmeyen kod ile birlikte çalışma](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)   
 [Birlikte Çalışma için .NET Türlerini Niteleme](http://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)



