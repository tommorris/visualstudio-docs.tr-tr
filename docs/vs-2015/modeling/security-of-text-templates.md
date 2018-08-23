---
title: Metin şablonlarının güvenliği | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, security
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 4ce9ccca0a144de7101e886712105315ec64fa75
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630538"
---
# <a name="security-of-text-templates"></a>Metin Şablonlarının Güvenliği
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [metin şablonlarının güvenliği](https://docs.microsoft.com/visualstudio/modeling/security-of-text-templates).  
  
Metin şablonları aşağıdaki güvenlik sorunları vardır:  
  
-   Metin şablonları, rastgele kod eklemelerin savunmasızdır.  
  
-   Konağın bir yönerge işlemcisi bulmak için kullandığı mekanizması güvenli değilse, kötü amaçlı bir yönerge işlemcisi çalıştırabilir.  
  
## <a name="arbitrary-code"></a>Rastgele kod  
 Bir şablon yazdığınızda, içinde herhangi bir kodu koyabilirsiniz \<## > etiketleri. Bu, bir metin şablonu içinde yürütülmek üzere rastgele kod sağlar.  
  
 Güvenilen kaynaklardan gelen şablonları edinmek emin olun. Uygulamanızın güvenilir kaynaklardan gelen şablonları yürütmek için son kullanıcılardan uyar emin olun.  
  
## <a name="malicious-directive-processor"></a>Kötü amaçlı bir yönerge işlemcisi  
 Metin şablonu motoru, bir dönüştürme ana bilgisayarı ve bir veya daha fazla yönerge işlemcileri bir çıktı dosyası şablonu metne dönüştürmek için ile etkileşim kurar. Daha fazla bilgi için [metin şablonu dönüştürme süreci](../modeling/the-text-template-transformation-process.md).  
  
 Konağın bir yönerge işlemcisi bulmak için kullandığı mekanizması güvenli değilse, çalışan bir kötü amaçlı bir yönerge işlemcisi riskini çalıştırır. Kötü amaçlı bir yönerge işlemcisi içinde çalışan kodu sağlayabilir `FullTrust` şablonunu çalıştırdığınızda modu. Bir özel metin şablonu dönüştürme ana bilgisayarı oluşturursanız, yönerge işlemcileri bulunacak altyapısı için kayıt defteri gibi güvenli bir mekanizma kullanmanız gerekir.



