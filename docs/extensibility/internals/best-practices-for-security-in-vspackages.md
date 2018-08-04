---
title: Vspackage'larda güvenlik için en iyi uygulamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio SDK]
- security best practices, VSPackages
- best practices, security
ms.assetid: 212a0504-cf6c-4e50-96b0-f2c1c575c0ff
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b5b3b86736a5425640c1a87df6a3e2c6e6cec0c5
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39513354"
---
# <a name="best-practices-for-security-in-vspackages"></a>Vspackage'larda güvenlik için en iyi uygulamalar
Yüklenecek [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] bilgisayarınızda yönetici kimlik bilgilerine sahip bir bağlamda çalıştırıyor olmalısınız. Güvenliği ve dağıtımı temel birimini bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uygulama [VSPackage](../../extensibility/internals/vspackages.md). Bir VSPackage'ı kullanarak kaydedilmelidir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], gerektiren yönetici kimlik bilgileri.  
  
 Yöneticiler, kayıt defteri ve dosya sistemine yazma ve herhangi bir kodu çalıştırmak için tam izinleri vardır. Geliştirme, dağıtma veya bir VSPackage'ı yüklemek için bu izinlere sahip olmalıdır.  
  
 VSPackage yüklendikten hemen sonra tam olarak güvenilirdir. VSPackage'ı ile ilişkili izin nedeniyle bu yüksek düzeyde farkında olmadan kötü amaçlı olan bir VSPackage'ı yüklemek mümkündür.  
  
 Kullanıcılar VSPackages yalnızca güvenilir kaynaklardan gelen yükleme emin olmanız gerekir. VSPackage geliştirme şirketler kesin ad ve oturumunu, kullanıcı söz konusu oynama güvence altına almak için engellenir. VSPackage geliştirme şirketler, web hizmetleri ve değerlendirmek ve güvenlik sorunları düzeltmek için uzaktan yükleme gibi dış bağımlılıklarını incelemeniz gerekir.  
  
 Daha fazla bilgi için [güvenli kodlama yönergeleri için .NET Framework](http://msdn.microsoft.com/library/d55zzx87.aspx).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Eklenti güvenliği](http://msdn.microsoft.com/Library/44a5c651-6246-4310-b371-65378917c799)   
 [DDEX güvenlik](http://msdn.microsoft.com/en-us/44a52a70-5c98-450e-993d-4a3b32f69ba8)