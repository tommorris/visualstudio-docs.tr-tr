---
title: "Windows Installer ile VSPackages yükleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation [Visual Studio SDK], with Windows Installer
- VSPackages, deploying
ms.assetid: 41d2c72c-0a97-4fcd-b3aa-33a8d3aa962a
caps.latest.revision: "30"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5061a52de32f699bbe234f729bb4f852ee966933
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="installing-vspackages-with-windows-installer"></a>Windows Installer ile VSPackages yükleme
İçinde VSPackage tümleştirme [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] daha fazlasını dosyaları bir kullanıcının bilgisayarına kopyalamanız gerekir. VSPackage'nın yükleyici gerekir VSPackage ve bağımlı dosyaları, yükleme ve kaydetme ve bunlara tümleştirmek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. VSPackage üzerinde bir simge görüntülemek gibi tümleştirme özellikleri yararlanabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tanıtım ekran ve hakkında iletişim kutusu.  
  
 Microsoft Windows Installer dosyaları, VSPackages dağıtmak için önerilen yoldur. Kullanımı kolay Windows Installer paketleri tarafından desteklenen tüm Windows işletim sistemi çalışabileceği [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Windows Installer temelleri](../../extensibility/internals/windows-installer-basics.md)  
 Windows Installer genel bir bakış sağlar.  
  
 [VSPackage Kurulum senaryoları](../../extensibility/internals/vspackage-setup-scenarios.md)  
 Hem sizin VSPackages yan yana yüklemesini destekleyebilmesi farklı yolları ele alır ve [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Bir Windows Installer paketi yazma](../../extensibility/internals/authoring-a-windows-installer-package.md)  
 Yükleyicileri izleyin doğru bir şekilde yüklemek ve içine VSPackages tümleştirmek için tipik adımları genel bir bakış sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Sistem gereksinimleri algılama](../../extensibility/internals/detecting-system-requirements.md)  
 Bir yükleyici nasıl algılayabilir açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve bileşenleri ve iptal VSPackage gereksinimler karşılanmazsa kurulumu.  
  
 [Bileşen Yönetimi](../../extensibility/internals/component-management.md)  
 Önceki ürün sürümleri bütünlüğünü bir yükleyici geliştirmek nasıl ele alınmaktadır.  
  
 [Yükleme dizini için VSPackage seçme](../../extensibility/internals/choosing-the-installation-directory-for-a-vspackage.md)  
 VSPackages yerini seçenekleri özetler.  
  
 [VSPackage kayıt](../../extensibility/internals/vspackage-registration.md)  
 Yükleme sırasında VSPackages nasıl kaydedildiği açıklanır ve kendi kendine kayıt neden hatalı bir uygulamadır.  
  
 [Proje türleri dağıtma](../../extensibility/internals/deploying-project-types.md)  
 Yönetilen kod projesi türleri için yeni bir proje türü toplayıcısı kullanmayı açıklar.  
  
 [Nasıl yapılır: bir yükleyici için kayıt defteri bilgilerini oluştur](../../extensibility/internals/how-to-generate-registry-information-for-an-installer.md)  
 RegPkg.exe yönetilen VSPackage için bir kayıt bildirim oluşturmak için nasıl kullanılacağını açıklar.  
  
 [Yükleme sonrasında çalışan komutlar](../../extensibility/internals/commands-that-must-be-run-after-installation.md)  
 İçine VSPackages tümleştirmek için yükleme sonrası komutların nasıl çalıştırıldığını açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Windows Installer ile VSPackage kaldırma](../../extensibility/internals/uninstalling-a-vspackage-with-windows-installer.md)  
 Kullanıcılar, VSPackage kaldırdığınızda, yükleyici gerçekleştirmeniz gereken adımlar açıklanır.  