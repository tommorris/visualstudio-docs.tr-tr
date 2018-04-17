---
title: 'CA1724: Tür adları ad alanları eşleşmemelidir | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 39e6b539d0259f83475e3e3a685bed7ffe6a7c87
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: Tür Adları Ad Alanlarıyla Eşleşmemelidir
|||  
|-|-|  
|TypeName|TypeNamesShouldNotMatchNamespaces|  
|CheckId|CA1724|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir tür adıyla eşleşen bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ad alanı adları büyük küçük harf duyarsız bir karşılaştırma.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Tür adları tanımlanan ad alanları adlarını değil eşleşmelidir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sınıf kitaplığı. Bu kuralın ihlali kitaplığın kullanılabilirliğini azaltabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Adını eşleşmeyen bir tür adı seçin bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sınıf kitaplığı ad.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yeni geliştirme, hiçbir bilinen senaryolar ortaya burada bu kuraldan bir uyarı bastırma gerekir. Uyarı bastırma önce kullanıcılar kitaplığınızın eşleşen ada göre nasıl yanıltıcı dikkatlice düşünün. Kitaplıkları aktarma için bir uyarı bu kuraldan bastırmak gerekebilir.