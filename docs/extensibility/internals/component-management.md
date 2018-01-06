---
title: "Bileşen Yönetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation [Visual Studio SDK], components
- installation [Visual Studio SDK], file management
ms.assetid: 029bffa2-6841-4caa-a41a-442467e1aedc
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 398986499732a36819808b07f05f7d6b46787a94
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="component-management"></a>Bileşen Yönetimi
Windows Installer görevlerin birimler (WICs veya yalnızca bileşenleri de denir) Windows Installer bileşenleri olarak adlandırılır. Bir GUID temel birimidir, yükleme ve başvuru, Windows Installer kullanan kurulumlarını sayım her WIC tanımlar.  
  
 Bu tartışma VSPackage Yükleyicinizle oluşturmak için birkaç ürünü kullanabilmenize karşın, Windows Installer (.msi) dosyalarının kullanımını varsayar. Böylece her zaman doğru başvuru sayımı gerçekleşir Yükleyicinizle oluştururken, dosya dağıtımını doğru yönetmeniz gerekir. Sonuç olarak, ürününüzü farklı sürümlerini değil kesintiye uğratabilir veya birbiriyle yükleme karışımında bölme ve senaryoları kaldırın.  
  
 Windows Installer, başvuru sayımı bileşen düzeyinde gerçekleşir. Dikkatle kaynaklarınızı düzenleme gerekir — dosyaları, kayıt defteri girdileri ve benzeri — bileşenlere. Diğer kuruluş düzeyi vardır — modülleri, özellikleri ve ürünler gibi — farklı senaryolarda yardımcı olabilir. Daha fazla bilgi için bkz: [Windows Installer Temelleri](../../extensibility/internals/windows-installer-basics.md).  
  
## <a name="guidelines-of-authoring-setup-for-side-by-side-installation"></a>Yan yana yükleme için Kur'u yazma yönergeleri  
  
-   Yazar dosyaları ve kendi bileşenlerine sürümleri arasında paylaşılan kayıt defteri anahtarları.  
  
     Bu, bir sonraki sürümde kolayca kullanmalarını sağlar. Örneğin, genel olarak, kayıtlı tür kitaplıklarının dosya uzantıları, kayıtlı HKEY_CLASSES_ROOT ve benzeri diğer öğeler.  
  
-   Paylaşılan bileşenler ayrı birleştirme modülleri gruplandırın.  
  
     Bu, yazar tarafından ilerleyen yan için doğru yardımcı olur.  
  
-   Paylaşılan dosyaları ve kayıt defteri anahtarlarını sürümleri arasında aynı Windows Installer bileşenlerini kullanarak yükleyin.  
  
     Farklı bir bileşeni kullanırsanız, dosyaları ve kayıt defteri girdilerini bir sürümü tutulan VSPackage kaldırılır, ancak başka bir VSPackage hala yüklü durumlarda kaldırılır.  
  
-   Aynı bileşen sürümü tutulan ve paylaşılan öğelerde karışık kullanmayın.  
  
     Bunun yapılması, genel bir konum ve yalıtılmış konumlara sürümlü öğeleri için paylaşılan öğeleri yüklemek mümkün kılar.  
  
-   Sürümlü dosyalar'ın üzerine paylaşılan kayıt defteri anahtarları yok.  
  
     Bunu yaparsanız, başka bir sürümü tutulan VSPackage yüklendiğinde, paylaşılan anahtarların üzerine yazılır. İkinci sürümü kaldırdıktan sonra anahtar işaret ettiğinden kaldırılmıştır dosyasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paylaşılan ve sürümü tutulan VSPackages arasında seçme](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [VSPackage Kurulum Senaryoları](../../extensibility/internals/vspackage-setup-scenarios.md)