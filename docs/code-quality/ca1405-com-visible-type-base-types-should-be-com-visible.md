---
title: "CA1405: COM görünebilir tür taban türler COM görünebilir olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
helpviewer_keywords:
- CA1405
- ComVisibleTypeBaseTypesShouldBeComVisible
ms.assetid: a762ea2f-5285-4f73-bfb9-9eb10aea4290
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cceaee755af5269e266ca57e3644213e939c0ead
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="ca1405-com-visible-type-base-types-should-be-com-visible"></a>CA1405: COM görünebilir tür taban türler COM görünebilir olmalıdır
|||  
|-|-|  
|TypeName|ComVisibleTypeBaseTypesShouldBeComVisible|  
|CheckId|CA1405|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|DependsOnFix|  
  
## <a name="cause"></a>Sebep  
 Bileşen Nesne Modeli (COM) görünen türü COM görünür olmayan bir türden türetilmiş.  
  
## <a name="rule-description"></a>Kural Tanımı  
 COM görünebilir tür yeni sürümde üye eklediğinde, geçerli sürüme bağlamak COM istemcileri çiğnemekten kaçının katı yönergeleri tarafından uymanız gerekir. COM görünmez bir tür yeni üye eklediğinde bu COM sürüm oluşturma kurallarına yok varsayar. Ancak, bir COM görünür türü COM görünmez türünden ve bir sınıf arabirimi kullanıma sunan <xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName> veya <xref:System.Runtime.InteropServices.ClassInterfaceType> (varsayılan), temel türün tüm genel üyeler (bunlar özellikle COM görünmez işaretlenmiş sürece olacak yedek) com'a Temel türü bir sonraki sürümde yeni üyeler eklerse, türetilmiş bir tür sınıfı arabirimine bağlamak istediğiniz COM istemcileri kesintiye uğrayabilir. COM görünebilir türler COM istemcileri bölme olasılığını azaltmak için yalnızca COM görünebilir türler türetilmelidir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için temel türleri COM görünebilir veya türetilmiş bir tür COM görünmez yapma.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.  
  
 [!code-vb[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1405-com-visible-type-base-types-should-be-com-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.ComBaseTypes#1](../code-quality/codesnippet/CSharp/ca1405-com-visible-type-base-types-should-be-com-visible_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute?displayProperty=fullName>   
 [Yönetilmeyen Kod ile Birlikte Çalışma](/dotnet/framework/interop/index)