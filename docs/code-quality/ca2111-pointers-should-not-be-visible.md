---
title: "CA2111: İşaretçiler görünür olmamalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PointersShouldNotBeVisible
- CA2111
helpviewer_keywords:
- CA2111
- PointersShouldNotBeVisible
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: af31aa7a08f80467013827f971d6b823202b68a3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2111-pointers-should-not-be-visible"></a>CA2111: İşaretçiler görünür olmamalıdır
|||  
|-|-|  
|TypeName|PointersShouldNotBeVisible|  
|CheckId|CA2111|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Genel veya korumalı bir <xref:System.IntPtr?displayProperty=fullName> veya <xref:System.UIntPtr?displayProperty=fullName> alan salt okunur değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.IntPtr>ve <xref:System.UIntPtr> yönetilmeyen bellek erişmek için kullanılan işaretçi türleridir. Bir işaretçi özel, iç veya salt okunur durumda değilse, kötü amaçlı kod olası bellek rasgele konumlarda izin veren veya uygulama veya sistem hatalarına neden işaretçi değeri değiştirebilirsiniz.  
  
 İmleç alanı içeren tür güvenli erişim yapmak istiyorsanız, bkz: [CA2112: güvenli türler alanları değil kullanıma](../code-quality/ca2112-secured-types-should-not-expose-fields.md).  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 İşaretçinin salt okunur, iç veya özel yaparak güvenli hale getirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 İşaretçinin değeri güvenmeyin varsa bir uyarı bu kuraldan engelleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod ihlal ve kural karşılamak işaretçileri gösterir. Özel olmayan işaretçileri ayrıca kural ihlal bildirimi [CA1051: görünür örnek alanlarını bildirme](../code-quality/ca1051-do-not-declare-visible-instance-fields.md).  
  
 [!code-csharp[FxCop.Security.PointersArePrivate#1](../code-quality/codesnippet/CSharp/ca2111-pointers-should-not-be-visible_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2112: Güvenli türler alanları açığa çıkarmamalıdır](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA1051: görünür örnek alanlarını bildirme](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>