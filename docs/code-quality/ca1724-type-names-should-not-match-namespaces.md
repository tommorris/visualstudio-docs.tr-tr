---
title: 'CA1724: Tür Adları Ad Alanlarıyla Eşleşmemelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
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
ms.openlocfilehash: c178558743ca69fb3b62eccaf8164e4b49167ad3
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547574"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: Tür Adları Ad Alanlarıyla Eşleşmemelidir
|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|Kategori|Microsoft.Naming|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir tür adıyla eşleşen bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] büyük küçük harf duyarsız bir karşılaştırma ad alanı adları.

## <a name="rule-description"></a>Kural açıklaması
 Tür adları içinde tanımlı ad alanlarının adları değil eşleşmelidir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sınıf kitaplığı. Bu kuralın ihlali kitaplığın kullanılabilirliğini azaltabilir.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Belirleyin adı eşleşmiyor bir tür adı bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sınıf kitaplığı ad alanı.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Yeni geliştirme, hiçbir bilinen senaryolar ortaya burada bu kuraldan bir uyarıyı bastırmak gerekir. Uyarının gösterilmemesi önce kitaplığınızın kullanıcılar tarafından eşleşen adı nasıl yanıltıcı dikkatlice düşünün. Kitaplıkları sevk edilmesi için bu kuraldan bir uyarıyı bastırmak gerekebilir.