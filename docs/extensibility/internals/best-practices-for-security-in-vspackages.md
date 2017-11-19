---
title: "En iyi uygulamalar VSPackages güvenliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [Visual Studio SDK]
- security best practices, VSPackages
- best practices, security
ms.assetid: 212a0504-cf6c-4e50-96b0-f2c1c575c0ff
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 770dff4b531bf4a7347cb648ca4c930b28b79bea
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="best-practices-for-security-in-vspackages"></a>VSPackages güvenlik için en iyi yöntemler
Yüklemek için [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] , bilgisayarınızda, yönetici kimlik bilgilerine sahip bir bağlamda çalıştırması gerekir. Güvenlik ve dağıtımını temel birimi bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uygulama [VSPackages](../../extensibility/internals/vspackages.md). Kullanarak bir VSPackage kaydedilmelidir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], yönetici kimlik bilgilerini de gerektirir.  
  
 Yöneticiler, kayıt defteri ve dosya sistemi yazma ve herhangi bir kod çalıştırmak için tam izinleri sahiptir. Geliştirme, dağıtma veya bir VSPackage yüklemek için bu izinleri olmalıdır.  
  
 Yüklendikten hemen sonra bir VSPackage tam güvenilir. VSPackage ile ilişkili izni nedeniyle bu yüksek düzey farkında olmadan kötü amaçlı kullanıcılardan VSPackage yüklemek mümkündür.  
  
 Kullanıcılar, yalnızca güvenilir kaynaklardan gelen VSPackages güncelleştirmesini emin olun. VSPackages geliştirme şirketler kesin adı ve oturumunu, kullanıcı o oynama güvence altına almak için engellenir. Şirketler VSPackages geliştirme, web hizmetleri ve değerlendirmek ve güvenlik sorunları düzeltmek için uzaktan yükleme gibi dış bağımlılıklarını incelemeniz gerekir.  
  
 Daha fazla bilgi için .NET Framework için güvenli kodlama yönergeleri bakın ([http://msdn.microsoft.com/library/d55zzx87.aspx](http://msdn.microsoft.com/library/d55zzx87.aspx)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eklenti güvenliği](http://msdn.microsoft.com/Library/44a5c651-6246-4310-b371-65378917c799)   
 [DDEX güvenlik](http://msdn.microsoft.com/en-us/44a52a70-5c98-450e-993d-4a3b32f69ba8)