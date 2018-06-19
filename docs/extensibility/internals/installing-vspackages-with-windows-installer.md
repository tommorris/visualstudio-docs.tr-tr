---
title: Windows Installer ile VSPackages yükleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- installation [Visual Studio SDK], with Windows Installer
- VSPackages, deploying
ms.assetid: 41d2c72c-0a97-4fcd-b3aa-33a8d3aa962a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6fafebe0dc2bb8e13c99be8b340e7f5663a9930f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131016"
---
# <a name="installing-vspackages-with-windows-installer"></a>Windows Installer ile VSPackages yükleme
İçinde VSPackage tümleştirme [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] daha fazlasını dosyaları bir kullanıcının bilgisayarına kopyalamanız gerekir. VSPackage'nın yükleyici gerekir VSPackage ve bağımlı dosyaları, yükleme ve kaydetme ve bunlara tümleştirmek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. VSPackage üzerinde bir simge görüntülemek gibi tümleştirme özellikleri yararlanabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tanıtım ekran ve hakkında iletişim kutusu.  
  
 Microsoft Windows Installer dosyaları, VSPackages dağıtmak için önerilen yoldur. Kullanımı kolay Windows Installer paketleri tarafından desteklenen tüm Windows işletim sistemi çalışabileceği [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Temel Windows Installer Bilgileri](../../extensibility/internals/windows-installer-basics.md)  
 Windows Installer genel bir bakış sağlar.  
  
 [VSPackage Kurulum Senaryoları](../../extensibility/internals/vspackage-setup-scenarios.md)  
 Hem sizin VSPackages yan yana yüklemesini destekleyebilmesi farklı yolları ele alır ve [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Windows Installer Paketi Yazma](../../extensibility/internals/authoring-a-windows-installer-package.md)  
 Yükleyicileri izleyin doğru bir şekilde yüklemek ve içine VSPackages tümleştirmek için tipik adımları genel bir bakış sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Sistem Gereksinimlerini Algılama](../../extensibility/internals/detecting-system-requirements.md)  
 Bir yükleyici nasıl algılayabilir açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve bileşenleri ve iptal VSPackage gereksinimler karşılanmazsa kurulumu.  
  
 [Bileşen Yönetimi](../../extensibility/internals/component-management.md)  
 Önceki ürün sürümleri bütünlüğünü bir yükleyici geliştirmek nasıl ele alınmaktadır.  
  
 [VSPackage için Yükleme Dizinini Seçme](../../extensibility/internals/choosing-the-installation-directory-for-a-vspackage.md)  
 VSPackages yerini seçenekleri özetler.  
  
 [VSPackage Kaydı](../../extensibility/internals/vspackage-registration.md)  
 Yükleme sırasında VSPackages nasıl kaydedildiği açıklanır ve kendi kendine kayıt neden hatalı bir uygulamadır.  
  
 [Proje Türlerini Dağıtma](../../extensibility/internals/deploying-project-types.md)  
 Yönetilen kod projesi türleri için yeni bir proje türü toplayıcısı kullanmayı açıklar.  
  
 [Nasıl Yapılır: Bir Yükleyicinin Kayıt Defteri Bilgilerini Oluşturma](../../extensibility/internals/how-to-generate-registry-information-for-an-installer.md)  
 RegPkg.exe yönetilen VSPackage için bir kayıt bildirim oluşturmak için nasıl kullanılacağını açıklar.  
  
 [Yükleme Sonrasında çalıştırılması Gereken Komutlar](../../extensibility/internals/commands-that-must-be-run-after-installation.md)  
 İçine VSPackages tümleştirmek için yükleme sonrası komutların nasıl çalıştırıldığını açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Windows Installer ile VSPackage Kaldırma](../../extensibility/internals/uninstalling-a-vspackage-with-windows-installer.md)  
 Kullanıcılar, VSPackage kaldırdığınızda, yükleyici gerçekleştirmeniz gereken adımlar açıklanır.  