---
title: 'CA2212: servis verilen bileşenleri WebMethod ile işaretlemeyin | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca33b1dfeafa3894b3ad82fd42a04d8310d2bd50
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212: Servis verilen bileşenleri WebMethod ile işaretlemeyin
|||  
|-|-|  
|TypeName|DoNotMarkServicedComponentsWithWebMethod|  
|CheckId|CA2212|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Öğesinden devralınan bir türde bir yöntemin <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName> ile işaretlenen <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Web.Services.WebMethodAttribute> XML Web Hizmetleri içinde ASP.NET kullanılarak oluşturulan yöntemlerini uygular; yöntemi çağrılabilir uzak Web istemcilerden kolaylaştırır. Sınıf ve yöntemi ortak ve bir ASP.NET Web uygulaması olarak yürütülen olması gerekir. <xref:System.EnterpriseServices.ServicedComponent> türleri COM + uygulamaları tarafından barındırılan ve COM + hizmetlerinin kullanabilirsiniz. <xref:System.Web.Services.WebMethodAttribute> uygulanmaz <xref:System.EnterpriseServices.ServicedComponent> çünkü bunlar aynı senaryoları için tasarlanmamıştır. Özellikle, özniteliğe ekleme <xref:System.EnterpriseServices.ServicedComponent> yöntemi yapmaz yöntemi çağrılabilir uzak Web istemcilerden. Çünkü <xref:System.Web.Services.WebMethodAttribute> ve <xref:System.EnterpriseServices.ServicedComponent> yöntemine sahip çakışan davranışları ve içeriği ve işlem akışı, yöntem davranışını gereksinimleri bazı senaryolarda yanlış olacaktır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için özniteliği kaldırın <xref:System.EnterpriseServices.ServicedComponent> yöntemi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Bu öğeleri birleştirme doğru olduğu hiçbir senaryolar vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>   
 <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>