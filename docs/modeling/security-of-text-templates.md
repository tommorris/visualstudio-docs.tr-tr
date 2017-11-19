---
title: "Metin şablonlarının güvenliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, security
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: "23"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 7c99f0a519ec62a2b9946baba072b0256a78697a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="security-of-text-templates"></a>Metin Şablonlarının Güvenliği
Metin şablonları aşağıdaki güvenlik sorunları vardır:  
  
-   Metin şablonları rastgele kod eklemelerin etkilenir.  
  
-   Konak bir yönerge işlemcisi bulmak için kullandığı mekanizması güvenli değilse, kötü amaçlı bir yönerge işlemcisi çalıştırabilir.  
  
## <a name="arbitrary-code"></a>Rastgele kod  
 Şablon yazarken içinde herhangi bir kod koyabilirsiniz \<## > etiketler. Bu, bir metin şablonu içinde yürütülmesi rastgele bir kodu sağlar.  
  
 Güvenilir kaynaklardan gelen şablonları elde emin olun. Son Kullanıcılar güvenilir kaynaklardan gelen şablonları çalıştırmamayı uygulamanızın uyar emin olun.  
  
## <a name="malicious-directive-processor"></a>Kötü amaçlı yönerge işlemcisi  
 Metin şablonu altyapısı bir dönüştürme ana bilgisayar ve bir veya daha fazla yönerge işlemcileri bir çıktı dosyası şablonu metne dönüştürecek ile etkileşim kurar. Daha fazla bilgi için bkz: [metin şablonu dönüştürme süreci](../modeling/the-text-template-transformation-process.md).  
  
 Konak bir yönerge işlemcisi bulmak için kullandığı mekanizması güvenli değilse, kötü amaçlı bir yönerge işlemcisi çalıştıran riskini çalışır. Kötü amaçlı yönerge işlemcisi çalıştırmak, kod sağlayabilir `FullTrust` şablon çalıştırdığınızda modu. Özel metin şablonu dönüştürme konağı oluşturursanız, örneğin yönerge işlemcileri bulmaya altyapısı için kayıt defteri güvenli bir mekanizma kullanmanız gerekir.