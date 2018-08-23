---
title: 'CA2212: servis verilen bileşenleri WebMethod ile işaretlemeyin | Microsoft Docs'
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
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
helpviewer_keywords:
- CA2212
- DoNotMarkServicedComponentsWithWebMethod
ms.assetid: 774bc55d-e588-48ee-8f38-c228580feca2
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7a54d18d91075b187f126845d7e0278c5e4ad65b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674565"
---
# <a name="ca2212-do-not-mark-serviced-components-with-webmethod"></a>CA2212: Servis verilen bileşenleri WebMethod ile işaretlemeyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2212: servis verilen bileşenleri WebMethod ile işaretlemeyin](https://docs.microsoft.com/visualstudio/code-quality/ca2212-do-not-mark-serviced-components-with-webmethod).  
  
TypeName | DoNotMarkServicedComponentsWithWebMethod |  
| Checkıd | CA2212 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Devralınan bir türde bir yöntemin <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName> ile işaretlenmiş <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.Web.Services.WebMethodAttribute> ASP.NET kullanarak oluşturulan bir XML Web hizmeti yöntemlerini uygular; yöntem çağrılabilir uzak Web istemcilerinden kolaylaştırır. Metot ve sınıf, genel ve bir ASP.NET Web uygulamasında yürütme olması gerekir. <xref:System.EnterpriseServices.ServicedComponent> türleri COM + uygulamaları tarafından barındırılan ve COM + Hizmetleri kullanabilir. <xref:System.Web.Services.WebMethodAttribute> uygulanmaz <xref:System.EnterpriseServices.ServicedComponent> çünkü aynı senaryolar için tasarlanmamıştır. Özellikle, öznitelik için ekleme <xref:System.EnterpriseServices.ServicedComponent> yöntemi yapmaz yöntemi çağrılabilir uzak Web istemcilerinden. Çünkü <xref:System.Web.Services.WebMethodAttribute> ve <xref:System.EnterpriseServices.ServicedComponent> yöntemine sahip çakışan davranışları ve bağlam ve işlem akışı, yöntemin davranışını gereksinimleri bazı senaryolarda yanlış olacaktır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için özniteliği kaldırın. <xref:System.EnterpriseServices.ServicedComponent> yöntemi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Bu öğeleri birleştirme doğru olduğu senaryo vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.EnterpriseServices.ServicedComponent?displayProperty=fullName>   
 <xref:System.Web.Services.WebMethodAttribute?displayProperty=fullName>



