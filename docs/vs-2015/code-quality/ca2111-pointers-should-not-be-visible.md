---
title: 'CA2111: İşaretçiler görünür olmamalıdır | Microsoft Docs'
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
- PointersShouldNotBeVisible
- CA2111
helpviewer_keywords:
- CA2111
- PointersShouldNotBeVisible
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 196d0f378164c2ee9109afa0fae53d79211653c7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630758"
---
# <a name="ca2111-pointers-should-not-be-visible"></a>CA2111: İşaretçiler görünür olmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2111: işaretçiler görünür olmamalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca2111-pointers-should-not-be-visible).  
  
TypeName | PointersShouldNotBeVisible |  
| Checkıd | CA2111 |  
| Kategori | Microsoft.Security|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Ortak veya korumalı bir <xref:System.IntPtr?displayProperty=fullName> veya <xref:System.UIntPtr?displayProperty=fullName> alanı salt okunur değildir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.IntPtr> ve <xref:System.UIntPtr> işaretçi türleri, yönetilmeyen bellek erişmek için kullanılır. Bir işaretçi özel, içsel veya salt okunur durumda değilse, kötü amaçlı kod işaretçinin, potansiyel olarak bellekte rastgele konumlara erişmesine izin vermek veya uygulama ya da sistem hatalarına neden değerini değiştirebilirsiniz.  
  
 İşaretçi alan içeren tür güvenli erişim yapmak istiyorsanız, bkz. [CA2112: güvenli türler alanları kullanıma](../code-quality/ca2112-secured-types-should-not-expose-fields.md).  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 İşaretçi salt okunur, iç veya özel hale getirerek güvenli hale getirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 İşaretçi değeri temel kullanmayın, bu kuraldan bir uyarıyı gizler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, ihlal ve kural karşılamak işaretçileri gösterir. Özel olmayan işaretçileri de kuralı ihlal bildirimi [CA1051: görünür örnek alanlarını bildirmeyin](../code-quality/ca1051-do-not-declare-visible-instance-fields.md).  
  
 [!code-csharp[FxCop.Security.PointersArePrivate#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.PointersArePrivate/cs/FxCop.Security.PointersArePrivate.cs#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2112: Güvenli türler alanları açığa çıkarmamalıdır](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA1051: Görünür örnek alanlarını bildirmeyin](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>



