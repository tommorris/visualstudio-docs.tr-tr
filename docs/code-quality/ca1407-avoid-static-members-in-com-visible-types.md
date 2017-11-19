---
title: "CA1407: COM görünebilir türler içinde statik üyelerden kaçının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
helpviewer_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
ms.assetid: bebd0776-ad04-453c-bca8-8c124c2d7840
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 43240b8969026a8bbec18528230d3ca97bcb2236
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1407-avoid-static-members-in-com-visible-types"></a>CA1407: COM görünebilir türler içinde statik üyelerden kaçının
|||  
|-|-|  
|TypeName|AvoidStaticMembersInComVisibleTypes|  
|CheckId|CA1407|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Özellikle Bileşen Nesne Modeli (COM) olarak görünür olarak işaretlenmiş bir türünü içeren bir `public``static` yöntemi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 COM desteği yok `static` yöntemleri.  
  
 Bu kural yoksayar özelliği ve olay erişimcileri, İşleç aşırı yüklemesi yöntemler veya kullanarak işaretlenmiş yöntemler <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> özniteliği veya <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> özniteliği.  
  
 Varsayılan olarak, COM görünür şunlardır: derlemeleri, genel türleri, genel türlerde ortak örnek üyeleri ve ortak değer türleri tüm üyeleri.  
  
 Bu kuralın gerçekleşmesi, derleme düzeyi <xref:System.Runtime.InteropServices.ComVisibleAttribute> ayarlanmalıdır `false` ve sınıf - <xref:System.Runtime.InteropServices.ComVisibleAttribute> ayarlanması gerekir `true`, aşağıdaki kodda gösterildiği gibi.  
  
```csharp  
using System;  
using System.Runtime.InteropServices;   
  
[assembly: ComVisible(false)]   
namespace Samples  
{      
    [ComVisible(true)]  
    public class MyClass  
    {  
        public static void DoSomething()  
        {  
        }  
    }  
}  
```  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için aynı işlevselliği sağlayan örnek yöntemi kullanmak için tasarım değiştirmek `static` yöntemi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan COM istemcisi tarafından sağlanan işlevlere erişim gerektirmiyorsa gizlemek güvenlidir `static` yöntemi.  
  
## <a name="example-violation"></a>Örnek ihlali  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnekte gösterildiği bir `static` bu kuralı ihlal yöntemi.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersViolation#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_1.cs)]  
  
### <a name="comments"></a>Açıklamalar  
 Bu örnekte, **Book.FromPages** yöntemi COM'dan çağrılamaz  
  
## <a name="example-fix"></a>Örnek düzeltme  
  
### <a name="description"></a>Açıklama  
 Önceki örnekte ihlali düzeltmek için bir örnek yöntemi yöntemi değiştirebilirsiniz, ancak, bu örnekte mantıklı değildir. Açıkça uygulamak için en iyi çözümdür `ComVisible(false)` temizleyin yöntemi COM'dan görülemeyen diğer geliştiriciler yapmak için yöntemi  
  
 Aşağıdaki örnek uygular <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> yöntemi.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_2.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1017: derlemeleri ComVisibleAttribute ile işaretleme](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
 [CA1406: Visual Basic 6 istemcileri için Int64 bağımsız kaçının](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)  
  
 [CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilmeyen kod ile birlikte çalışma](/dotnet/framework/interop/index)