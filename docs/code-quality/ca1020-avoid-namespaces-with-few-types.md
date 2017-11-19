---
title: "CA1020: birkaç türü olan ad alanları kaçının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c09f3fa7855f2dadfce7a22914c4a7010b84f210
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020: Birkaç türü olan ad alanlarından kaçının
|||  
|-|-|  
|TypeName|AvoidNamespacesWithFewTypes|  
|CheckId|CA1020|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Genel ad alanı dışında bir ad alanı az beş türler içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Her alanlarınızın mantıksal bir düzenleme vardır ve türleri seyrek doldurulmuş bir ad alanında geçerli bir nedeni put var olduğundan emin olun. Ad alanları, birlikte Çoğu senaryoda kullanılan türleri içermelidir. Uygulamalarını karşılıklı olarak birbirini dışlar, farklı ad alanlarında türleri bulunmalıdır. Örneğin, <xref:System.Web.UI> ad alanı, Web uygulamalarında kullanılan türler içerir ve <xref:System.Windows.Forms> ad alanı, kullanılan türleri içerir [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)]-tabanlı uygulamaları. Her iki ad kullanıcı arabirimi yönlerini kontrol türleri olsa bile bu türleri aynı uygulamada kullanmak için tasarlanmamıştır. Bu nedenle, bunlar ayrı ad alanları bulunur. Bir özellik bulunabilirliğini artırır çünkü dikkatli ad kuruluş da yararlı olabilir. Ad alanı hiyerarşisi inceleyerek kitaplığı tüketicileri bir özelliği uygulamak türleri bulabilir olmalıdır.  
  
> [!NOTE]
>  Tasarım zamanı türleri ve izinleri bu kılavuzu ile uyum sağlamak için diğer ad alanları içine birleştirilmedi. Ana, ad alanının altındaki kendi ad alanlarında bu tür aittir ve ad alanlarını bitmesi gerektiğini `.Design` ve `.Permissions`sırasıyla.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için yalnızca birkaç türlerini tek bir ad içeren ad alanları birleştirmek deneyin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Ad alanı, diğer ad türleriyle kullanılan türlerini içermiyor olduğunda bir uyarı bu kuraldan bastırmak güvenlidir.