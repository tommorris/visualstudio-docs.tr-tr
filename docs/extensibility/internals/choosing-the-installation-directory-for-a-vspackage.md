---
title: "Yükleme dizini için VSPackage seçme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: VSPackages, installation directory
ms.assetid: 01fbbb5b-f747-446c-afe0-2a081626a945
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3462104e100ab672373f30dcd8228bc064746f2d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="choosing-the-installation-directory-for-a-vspackage"></a>Yükleme dizini için VSPackage seçme
Bir kullanıcının dosya sisteminde bir VSPackage ve Tamamlayıcı dosyaları olmalıdır. Konumu olup VSPackage yönetilen veya yönetilmeyen, yan yana sürüm oluşturma düzeni ve kullanıcı seçeneği bağlıdır.  
  
## <a name="unmanaged-vspackages"></a>Yönetilmeyen VSPackages  
 Bir yönetilmeyen VSPackage herhangi bir konuma yüklenebilir bir COM sunucusudur. Kayıt bilgileri doğru bir şekilde konumuna yansıtır gerekir. Yükleyici kullanıcı arabirimi (UI) Programfılesfolder Windows Installer özelliği bir alt dizini olarak varsayılan konumunu sağlamalıdır. Örneğin:  
  
 [Programfılesfolder] MyCompany\MyVSPackageProduct\V1.0\  
  
 Kullanıcı, bir küçük önyükleme bölümü tutmak kullanıcılar uyum sağlamak için varsayılan dizini değiştirin ve başka bir birimde uygulamaları ve araçları yüklemek tercih ettiğiniz için izin verilmelidir.  
  
 Yan yana düzeninizi sürümlü VSPackage kullanıyorsa, alt dizinleri farklı sürümlerini depolamak için kullanabilirsiniz. Örneğin:  
  
 [Programfılesfolder] MyCompany\MyVSPackageProduct\V1.0\2002\  
  
 [Programfılesfolder] MyCompany\MyVSPackageProduct\V1.0\2003\  
  
 [Programfılesfolder] MyCompany\MyVSPackageProduct\V1.0\2005\  
  
## <a name="managed-vspackages"></a>Yönetilen VSPackages  
 Yönetilen VSPackages herhangi bir konuma da yüklenebilir. Ancak, Genel Derleme Önbelleği (GAC) derleme yükleme süreleri azaltmak için her zaman yüklemeden düşünmelisiniz. Yönetilen VSPackages her zaman tanımlayıcı adlı derlemeler olduğundan, GAC'de yükleme kendi sağlam ad imzası doğrulama yalnızca yükleme sırasında geçen anlamına gelir. Tanımlayıcı adlı derlemeler dosya sistemindeki başka bir yerde yüklü yüklenen her zaman doğrulanmış kendi imzalarına sahip olmalıdır. GAC içinde yönetilen VSPackages yüklediğinizde regpkg aracın kullanın **/assembly** derleme güçlü adına işaret eden kayıt defteri girdileri yazmak için anahtar.  
  
 GAC dışında bir konumda yönetilen VSPackages yüklerseniz, yönetilmeyen VSPackages için dizin hiyerarşileri seçmek için verilen önceki önerileri izleyin. Regpkg aracın kullanmak **/ codebase** VSPackage derleme yola işaret eden kayıt defteri girdileri yazmak için anahtar.  
  
 Daha fazla bilgi için bkz: [kaydetme ve kaydını kaldırma VSPackages](../../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="satellite-dlls"></a>Uydu DLL'leri  
 Kurala göre VSPackage Uydu DLL'leri — belirli bir yerel ayar için kaynakları içeren — VSPackage dizinin alt dizinlerinde bulunur. Alt dizinleri yerel ayar kimliği (LCID) değerine karşılık gelir.  
  
 [VSPackages yönetme](../../extensibility/managing-vspackages.md) kayıt defteri girdileri where kontrol gösterir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] gerçekten VSPackage'nın arar DLL uydu. Ancak, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aşağıdaki sırayla bir LCID değeri için adlı bir alt uydu DLL yüklemeyi dener:  
  
1.  Varsayılan LCID (VS LCID örneğin \1033 İngilizce için)  
  
2.  Varsayılan alt dili ile varsayılan LCID.  
  
3.  Sistem varsayılan LCID.  
  
4.  Varsayılan alt dili ile sistem varsayılan LCID.  
  
5.  ABD İngilizce (. \1033 veya. \0x409).  
  
 VSPackage DLL kaynakları ve ona SatelliteDll\DllName kayıt defteri giriş noktaları içeriyorsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yukarıdaki sırayla yüklemeye çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paylaşılan ve sürümü tutulan VSPackages arasında seçme](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [VSPackages yönetme](../../extensibility/managing-vspackages.md)   
 [Yönetilen paketi kaydı](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)