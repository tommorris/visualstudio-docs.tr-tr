---
title: Paylaşılan ve sürümü tutulan VSPackages arasında seçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- SxS
- side-by-side installation
- installation [Visual Studio SDK], side-by-side
ms.assetid: e3128ac3-2e92-48e9-87ab-3b6c9d80e8c9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ce7f58d664c6a186146272af16324be2fee90983
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31104627"
---
# <a name="choosing-between-shared-and-versioned-vspackages"></a>Paylaşılan ve sürümü tutulan VSPackages arasında seçme
Visual Studio farklı sürümlerini aynı bilgisayarda bulunabilir. VSPackages herhangi bir karışımını destekler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sürümleri.  
  
 VSPackages yan yana yüklemelerini iki stratejileri, paylaşılan stratejisi ya da sürümlü stratejisi ile etkinleştirebilirsiniz. Her ikisi birden fazla sürümünü varlığını uyum [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve sürümleri ilişkili [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Paylaşılan stratejinize bir VSPackage birden fazla sürümünü kullanmak için kayıtlı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Sürümü tutulan stratejinize birden çok VSPackage DLL'leri yüklenen her sürümü için bir tane [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] destek.  
  
## <a name="shared-vspackages"></a>Paylaşılan VSPackages  
 Paylaşılan VSPackage kullanarak uygun birden çok sürümlerinde aynı VSPackage kullandığınızda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Paylaşılan VSPackage uygulamak için aşağıdaki adımları izlemelisiniz:  
  
-   VSPackage birden çok sürümü ile uyumlu hale getirmek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. İki yolla bunu yaparsanız, bu nedenle kullanılabilir:  
  
    -   Yalnızca en erken sürümünün özellikleri kullanarak, VSPackage sınırlamak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] destek.  
  
    -   Sürümüne uyarlamak için VSPackage program [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çalıştığı içinde. Ardından, yeni hizmetler için sorgu başarısız olursa, VSPackage eski sürümlerinde desteklenen diğer hizmet sunabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   VSPackage uygun şekilde kaydedin. Daha fazla bilgi için bkz: [VSPackage kayıt](../extensibility/internals/vspackage-registration.md) ve [yönetilen VSPackage kayıt](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1).  
  
-   Dosya uzantılarını uygun şekilde kaydedin. Daha fazla bilgi için bkz: [yan yana dağıtımlar için dosya adı uzantılarını kaydetme](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md).  
  
-   Uygun sürümleri için VSPackage dağıtan bir yükleyici oluşturma [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [yükleme VSPackages ile Windows Installer](../extensibility/internals/installing-vspackages-with-windows-installer.md) ve [bileşen Yönetimi](../extensibility/internals/component-management.md).  
  
-   Kayıt çakışma sorunu giderir. Daha fazla bilgi için bkz: [VSPackage kayıt](../extensibility/internals/vspackage-registration.md).  
  
-   Paylaşılan ve sürümü tutulan dosyaları başvuru güvenli yüklenmesi ve kaldırılması birden çok sürümü ile izin vermek için sayım saygı emin olun. Daha fazla bilgi için bkz: [bileşen Yönetimi](../extensibility/internals/component-management.md).  
  
## <a name="versioned-vspackages"></a>Sürümü tutulan VSPackages  
 Sürümü tutulan VSPackage stratejisi altında oluşturduğunuz her sürümü için bir VSPackage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] destek. Bunun yapılması uygun sonraki sürümleri tarafından sağlanan hizmetlerin yararlanmak beklediğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], her VSPackage diğerlerini etkilemeden geliştirin. Bununla birlikte, tek bir kod tabanının veya birden çok bağımsız kod temelleri, birden çok ikili dosyaları oluşturma sürümlü stratejisi paylaşılan stratejisi'den daha fazla ilk geliştirme gerektirdiği. Her bir sürümü için ayrı bir kurulum ya da sürümleri algılar tek bir kurulum oluşturmanız gerekir çünkü Ayrıca, ek kurulum iş gerekebilecek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklenen ve, VSPackage destekler.  
  
## <a name="binary-compatibility"></a>İkili uyumluluğu  
 Genellikle, Visual Studio'nun daha yeni sürümleri çalıştırmak için Visual Studio'nun önceki sürümleri ile geliştirilen yerel kodlu VSPackages ikili uyumluluğu sağlar. Ancak, üç önemli özel durum vardır:  
  
-   Belirli bir ortak dil çalışma zamanı sürümü, VSPackage dayanır sonra hangi sürümünde belirlemelisiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çalışır.  
  
-   Bir VSPackage bir bağımlılık, başka bir VSPackage veya başka bir ürünün belirli bir özellik olabilir. Sonuç olarak, yalnızca bağımlılık burada sağlanıyorsa VSPackage çalıştırabilirsiniz.  
  
-   Bir güvenlik düzeltme tarafından bir VSPackage etkilenebilir bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hizmet paketi veya sonraki bir sürümünü [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bu gibi durumlarda bir VSPackage önceki bir sürümü ile geliştirilen [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] sürümlerinde çalışmayabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] güvenlik düzeltme ekini uygulandıktan sonra. Ancak, sonraki bir sürümü ile paketinizi yeniden derleyin ve önceki sürümlerinde de çalıştırmak sahip.  
  
 Yönetilen VSPackages bir sürümü kullanılarak oluşturulur gerekir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] hedef sürümü eşleşen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 VSPackage ikili dosyaları ikili uyumluluğu için planlama ek olarak, ayrıca çözümünü göz önünde bulundurun ve dosya biçimleri proje. Yeni bir proje türü, VSPackage oluşturur, bunu yalnızca bir sürümü ya da birden fazla sürümünü çalıştırılıp çalıştırılmayacağını karar vermelisiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [özel projeleri yükseltme](../extensibility/internals/upgrading-projects.md#upgrading-custom-projects).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Installer ile VSPackages yükleme](../extensibility/internals/installing-vspackages-with-windows-installer.md)   
 [Bileşen Yönetimi](../extensibility/internals/component-management.md)