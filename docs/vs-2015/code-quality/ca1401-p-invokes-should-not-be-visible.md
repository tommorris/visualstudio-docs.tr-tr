---
title: "CA1401: P-Invoke'lar görünür olmamalıdır | Microsoft Docs"
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
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a2a69907dc37760d7d5f88d68a7443cede48136c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697153"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401: P/Invoke'lar görünür olmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1401: P-Invokes görünebilir olmamalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca1401-p-invokes-should-not-be-visible).  
  
TypeName | PInvokesShouldNotBeVisible |  
| Checkıd | CA1401 |  
| Kategori | Microsoft.Interoperability|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Ortak türde ortak veya korumalı bir yöntem olan <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> özniteliği (Ayrıca tarafından uygulanan `Declare` anahtar sözcüğünü [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).  
  
## <a name="rule-description"></a>Kural Tanımı  
 İle işaretlenmiş yöntemler <xref:System.Runtime.InteropServices.DllImportAttribute> özniteliği (veya kullanılarak tanımlanan yöntemleri `Declare` anahtar sözcüğünü [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) yönetilmeyen kod erişmek için Platform çağırma Hizmetleri kullanın. Bu tür yöntemler açıkta kalmamalıdır. Bu yöntemler özel veya iç tutarak kitaplığınızı, aksi takdirde arayamadı yönetilmeyen API'lere erişim arayanlara izin vererek güvenliği ihlal kullanılamayacağını emin olun.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için yöntemin erişim düzeyini değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bu kuralı ihlal eden bir yöntem bildirir.  
  
 [!code-csharp[FxCop.Interoperability.DllImports#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/cs/FxCop.Interoperability.DllImports.cs#1)]
 [!code-vb[FxCop.Interoperability.DllImports#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DllImports/vb/FxCop.Interoperability.DllImports.vb#1)]



