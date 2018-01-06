---
title: "CA1017: Derlemeleri ComVisibleAttribute ile işaretleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 1cf713e2c177a24938c44c4577da88d8943e4fef
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: Derlemeleri ComVisibleAttribute ile işaretleme
|||  
|-|-|  
|TypeName|MarkAssembliesWithComVisible|  
|CheckId|CA1017|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir derlemeyi yok <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> özniteliğinin.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> Özniteliği COM istemcileri yönetilen kod nasıl eriştiğini belirler. İyi tasarım derlemelerin açıkça COM görünürlüğünde gösterildiğini belirler. COM görünürlüğü için tam bir derleme ayarlayın ve ardından tek tek türleri ve tür üyeleri için geçersiz kılındı. Öznitelik yoksa, derleme içeriğini COM istemcileri için görünür durumdadır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için derlemeye özniteliğini ekleyin. Derleme COM istemcileri için görünür olmasını istemiyorsanız özniteliğini uygulayın ve değerini ayarlama `false`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Derleme görünür olmasını istiyorsanız, özniteliğini uygulayın ve değerini ayarlama `true`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir derlemeye gösterir <xref:System.Runtime.InteropServices.ComVisibleAttribute> COM istemcileri için görünür olmasını engellemek için uygulanan öznitelik.  
  
 [!code-cpp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CPP/ca1017-mark-assemblies-with-comvisibleattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/VisualBasic/ca1017-mark-assemblies-with-comvisibleattribute_1.vb)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CSharp/ca1017-mark-assemblies-with-comvisibleattribute_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilmeyen kod ile birlikte çalışma](/dotnet/framework/interop/index)   
 [Birlikte Çalışma için .NET Türlerini Niteleme](/dotnet/framework/interop/qualifying-net-types-for-interoperation)