---
title: 'CA1020: birkaç türü olan ad alanları kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a90f43735092591ad019fd2a46569e9302cf0c3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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