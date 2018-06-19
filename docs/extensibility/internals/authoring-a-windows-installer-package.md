---
title: Bir Windows Installer paketi geliştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- .msi files, VSPackages
- msi files, VSPackages
ms.assetid: 0ce7c21d-0d3f-47fe-a0bb-eed506e32609
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 215e1496d35059448cf11457658b7d1270b5677d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127945"
---
# <a name="authoring-a-windows-installer-package"></a>Bir Windows Installer paketi yazma
Windows Installer model veri sürücüleri. Dosyaları kopyalamak ve kayıt defteri girdileri yazmak için bir yordam komut dosyası yazmak yerine, örneğin, satırları ve sütunları, dosya ve kayıt defteri verilerini içeren veritabanı tablolarındaki yazar.  
  
## <a name="database-entries"></a>Veritabanı girişleri  
 Bir VSPackage yüklemek için bir Windows Installer paketi aşağıdaki görevleri gerçekleştirmek için veritabanı girdileri içermelidir:  
  
-   Sistem sürümlerini bulmak için arama [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (AppSearch, CompLocator, RegLocator, DrLocator ve imza dahil Windows Installer tabloları kullanarak), VSPackage destekler.  
  
-   Hiçbir desteklenen sürümü, yükleme iptal [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yüklü olduğu veya başka bir sistem gereksinimi VSPackage (LaunchCondition tablosunu kullanarak) uyulmazsa.  
  
-   VSPackage ve bağımlı dosyaları (dizin, bileşen ve dosya tabloları kullanarak) yükleyin.  
  
-   VSPackage için uygun bilgileri (kayıt defteri tablosu kullanarak) kayıt defterine ekleyin.  
  
-   VSPackage tümleştirmek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çağırarak **devenv.exe/Setup** (özel tablo kullanarak).  
  
 Daha fazla bilgi için bkz: [Windows Installer](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx).  
  
## <a name="setup-tools"></a>Kurulum Araçları  
 Üçüncü taraf kurulum araçları, çeşitli Windows Installer paketleri için bir geliştirme ortamı sağlar. İki ücretsiz araçlar şunlardır:  
  
-   InstallShield Limited Edition  
  
     Visual Studio üzerinden InstallShield sınırlı bir sürümünü elde edebilirsiniz **yeni proje** iletişim. Genişletme **diğer proje türleri** ve ardından **Kurulum ve dağıtım**. InstallShield şablonu seçin.  
  
-   Windows Installer XML Araç Takımı  
  
     Araç takımı XML kaynak dosyalarından Windows Installer paketleri oluşturur. Bir Microsoft açık kaynak projesi setidir. Yürütülebilir dosyalar ve kaynak kodu indirebilirsiniz [ http://sourceforge.net/projects/wix ](http://sourceforge.net/projects/wix).  
  
 Kolay bir şekilde entegre ticari ürünleri için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kullanarak [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], bkz: [ http://visualstudiogallery.com ](http://visualstudiogallery.com/).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Installer ile VSPackage Yükleme](../../extensibility/internals/installing-vspackages-with-windows-installer.md)