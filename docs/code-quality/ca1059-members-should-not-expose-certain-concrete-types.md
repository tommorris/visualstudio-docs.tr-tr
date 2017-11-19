---
title: "CA1059: Üyeler belli somut türleri göstermemelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1059
- MembersShouldNotExposeCertainConcreteTypes
helpviewer_keywords:
- MembersShouldNotExposeCertainConcreteTypes
- CA1059
ms.assetid: 59f61f52-8d6c-49cb-aefb-191910523a3c
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d5b8b4a50ce23a7ed50f2e608334f9b438a0b090
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1059-members-should-not-expose-certain-concrete-types"></a>CA1059: Üyeler belli somut türleri göstermemelidir
|||  
|-|-|  
|TypeName|MembersShouldNotExposeCertainConcreteTypes|  
|CheckId|CA1059|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür bir üye bir belli somut bir tür veya belli somut türleri parametrelerinden biri aracılığıyla kullanıma sunar veya dönüş değeri. Şu anda, bu kural aşağıdaki somut türleri riskini raporları:  
  
-   Öğesinden türeyen bir tür <xref:System.Xml.XmlNode?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Somut tür tam bir uygulamaya sahiptir ve bu nedenle oluşturulabilecek bir türdür. Üye yaygın kullanımına izin vermek için önerilen arabirimiyle somut türde değiştirin. Arabirimini uygulayan herhangi bir türü kabul edin veya arabirimini uygulayan bir tür beklenirken kullanılması üye sağlar.  
  
 Aşağıdaki tabloda, hedeflenen somut türleri ve bunların önerilen değişikliklerini listeler.  
  
|Somut türü|Değiştirme|  
|-------------------|-----------------|  
|<xref:System.Xml.XPath.XPathDocument>|<xref:System.Xml.XPath.IXPathNavigable?displayProperty=fullName>.<br /><br /> Arabirimi kullanarak belirli bir uygulama bir XML veri kaynağının üyeden ayrıştırır.|  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için önerilen arabirimine somut türünü değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Somut türü tarafından sağlanan belirli işlevleri gerekliyse, bu kural gelen iletiyi bastırmak güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1011: temel türleri parametre olarak geçirmeyi düşünün](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)