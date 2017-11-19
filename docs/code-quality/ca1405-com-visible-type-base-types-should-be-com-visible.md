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
ms.openlocfilehash: 91634d5d46d63165874deded9c5ac67e7d4afa07
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Sınıf arabirimi Tanıtımı](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Yönetilmeyen kod ile birlikte çalışma](/dotnet/framework/interop/index)