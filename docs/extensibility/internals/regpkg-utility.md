---
title: "RegPkg yardımcı programı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- regpkg, registration utility
- registration, regpkg utility
ms.assetid: 1683ee18-59d1-4bab-a674-dd00dd960de3
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1ca3c5d5177b7f7e865f7fffb1bcd87a78d2e8cd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="regpkg-utility"></a>RegPkg yardımcı programı
> [!NOTE]
>  Visual Studio'da paketleri kaydetmek için tercih edilen .pkgdef dosyalarını kullanarak yoludur. Bu uzantı dağıtımı için bir gereksinimdir VSIX dağıtımı için sistem kayıt defteri erişmek zorunda kalmadan sağlar. Pkgdef dosyaları kullanılarak oluşturulur [CreatePkgDef yardımcı programı](../../extensibility/internals/createpkgdef-utility.md). Visual Studio paketi dağıtımı hakkında daha fazla bilgi için bkz: [sevkiyat Visual Studio uzantıları](../../extensibility/shipping-visual-studio-extensions.md).  
  
 RegPkg.exe yardımcı programı ile VSPackage kaydeder [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve dağıtım için hazırlar. Bu yardımcı program arka planda VSPackage geliştirme sırasında kullanılır. Böylece oluşturup bir VSPackage Deneysel kovanında çalıştırın derleme işleminin bir parçası çalışır.  
  
 RegPkg sistem kayıt defteri komut dosyaları çeşitli biçimlerde oluşturabilir. Bu komut dosyalarını .msi projeleri veya Windows Installer XML araç takımı dosyaları gibi dağıtım projelerinde dahil edebilirsiniz.  
  
 RegPkg.exe genellikle \< *Visual Studio SDK yükleme yolu*> \VisualStudioIntegration\Tools\Bin\RegPkg.exe. RegPkg bu söz dizimi aşağıdaki gibidir:  
  
```  
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath  
```  
  
 /root:root  
 Belirtilen adla kayıt gerçekleştirir  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]kök dizini.  
  
 /regfile:filename  
 Kayıt defteri güncelleştiriliyor yerine .reg dosyasını oluşturur.  /Vrgfile veya /rgsfile veya /wixfile ile kullanılamaz.  
  
 /rgsfile:filename  
 Kayıt defteri güncelleştiriliyor yerine bir .rgs dosyası oluşturur.  /Vrgfile veya/regfile veya /wixfile ile kullanılamaz.  
  
 /vrgfile:filename  
 Kayıt defteri güncelleştiriliyor yerine bir .vrg dosyası oluşturur.  / Regfile veya /rgsfile veya /wixfile ile kullanılamaz.  
  
 /rgm  
 Rgs dosya yanı sıra .rgm dosyası oluşturur.  /Rgsfile ile birlikte olması gerekir.  
  
 /wixfile:filename  
 Kayıt defteri güncelleştiriliyor yerine bir Windows Installer XML araç takımı uyumlu dosyası oluşturur.  / Regfile veya /rgsfile veya /vrgfile ile kullanılamaz.  
  
 /codebase  
 Derleme yerine CodeBase kaydı zorlar.  
  
 /Assembly  
 CodeBase yerine derleme kaydı zorlar.  
  
 / kaydı  
 Bu paket kaydını siler.  Kullanılamaz  
  
 / regfile veya /vrgfile veya /rgsfile veya /wixfile.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackages](../../extensibility/internals/vspackages.md)  
 [Sorun giderme RegPkg paketi kaydı](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)