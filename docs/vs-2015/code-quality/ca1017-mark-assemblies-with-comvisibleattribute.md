---
title: 'CA1017: Derlemeleri ComVisibleAttribute ile işaretleme | Microsoft Docs'
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
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7e6ed67cd3b849421e82a7ac2fb83d546d1f2d26
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632303"
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: Derlemeleri ComVisibleAttribute ile işaretleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1017: derlemeleri ComVisibleAttribute ile işaretleyin](https://docs.microsoft.com/visualstudio/code-quality/ca1017-mark-assemblies-with-comvisibleattribute).  
  
TypeName | MarkAssembliesWithComVisible |  
| Checkıd | CA1017 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Bir derleme olmayan <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> özniteliğinin.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> Özniteliği COM istemcilerinin yönetilen kod nasıl eriştiğini belirler. İyi tasarım derlemelerin açıkça COM görünürlüğünde gösterildiğini belirler. COM görünürlüğü tüm bir derleme için ayarlanabilir ve sonra bireysel tür ve tür üyeleri için geçersiz kılındı. Öznitelik yoksa derleme içeriği COM istemcilerine görülebilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için özniteliği derlemeye ekleyin. Derlemenin COM istemcilerine görünür olmasını istemiyorsanız özniteliğini uygulayın ve değerini ayarlamak `false`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Derleme görünür olmasını istiyorsanız, özniteliğini uygulayın ve değerini ayarlamak `true`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir derlemeye gösterir <xref:System.Runtime.InteropServices.ComVisibleAttribute> COM istemcilerine görünür olmasını engellemek için uygulanan bir öznitelik.  
  
 [!code-cpp[FxCop.Design.AssembliesCom#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/cpp/FxCop.Design.AssembliesCom.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/cs/FxCop.Design.AssembliesCom.cs#1)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/vb/FxCop.Design.AssembliesCom.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilmeyen kod ile birlikte çalışma](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)   
 [Birlikte Çalışma için .NET Türlerini Niteleme](http://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)



