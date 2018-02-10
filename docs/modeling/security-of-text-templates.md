---
title: "Metin şablonlarının güvenliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- text templates, security
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5c6b8d64e02562887b2bc438943fdfe7be3b2e1c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
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