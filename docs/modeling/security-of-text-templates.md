---
title: Metin şablonlarının güvenliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4acbe40d7229551e32f60d1503864b21840655be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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