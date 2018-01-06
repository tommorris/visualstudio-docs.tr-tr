---
title: "CA1724: Tür adları ad alanları eşleşmemelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f138958ce2dc83b7d258fbdb16986841e92d3484
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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