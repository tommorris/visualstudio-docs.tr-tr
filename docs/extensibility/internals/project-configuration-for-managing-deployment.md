---
title: Yapılandırma dağıtımını yönetmek için proje | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project configurations, managing deployment
- projects [Visual Studio SDK], configuration for managing deployment
ms.assetid: bd5940d9-d94d-4944-beda-4ec1ab2bbde5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 723edd078636eb324fc2d5dfca2ae81ef3249a43
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132267"
---
# <a name="project-configuration-for-managing-deployment"></a>Dağıtım yönetmek için proje yapılandırması
Dağıtım fiziksel olarak hata ayıklama ve yükleme için beklenen konuma derleme işleminden çıkış öğeleri taşıma işlemidir. Örneğin, bir Web uygulaması yerel makine üzerinde oluşturulmuş ve sunucuda yerleştirilir.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projeleri dağıtımda yer alan, iki yolla destekler:  
  
-   Dağıtım işlemi konu.  
  
-   Dağıtım işlemi Yöneticisi olarak.  
  
 Çözümleri dağıtılmadan önce dağıtım seçeneklerini yapılandırmak için bir dağıtım projesi eklemeniz gerekir. Dağıtma proje zaten mevcut değilse seçtiğinizde aşağıdakilerden oluşturmak isteyip istemediğiniz sorulur **çözümü Dağıt** gelen **yapı** menüsü veya çözüme sağ tıklayın. Tıklatarak **Evet** açılır **Yeni Proje Ekle** iletişim kutusuyla **uzaktan Dağıtma Sihirbazı'nı** seçili projesi.  
  
 Uzaktan Dağıtma Sihirbazı'nı, tür bir uygulama (Windows veya Web), dahil etmek için proje çıktı grupları, dahil etmek istediğiniz ek dosyalardan ve dağıtmak istediğiniz uzak bilgisayarı için ister. Sihirbazın son sayfasında seçilen seçenekleri özetini görüntüler.  
  
 Dağıtım işlemi konu olan projeler için alternatif bir ortam taşınmalıdır çıktı öğeleri üretir. Bu öğe için bir parametre olarak açıklanmıştır çıkış <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> , birincil grup çıkışları projelerine izin vermek ise amaçla arabirimi. Uygulamasına yönelik ilgili daha fazla bilgi için `IVsProjectCfg2`, bkz: [çıktı için proje yapılandırması](../../extensibility/internals/project-configuration-for-output.md).  
  
 Dağıtım işlemi yönetmek, dağıtım projeleri Dağıt komutu etkinleştirmek ve bu komut seçildiğinde yanıt. Dağıtım projeleri uygulamak <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> çağrı yapmak ve dağıtım gerçekleştirmek için arabirim <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployStatusCallback> rapor arabirimine durum olaylarını dağıtın.  
  
 Yapılandırmaları yapı ya da dağıtım işlemlerini etkileyen bağımlılıkları belirtebilirsiniz. Oluşturma veya dağıtma yerleşik veya önce veya sonra yapılandırmaları kendilerini yerleşik veya dağıtılan dağıtılan projeleri bağımlılıklardır. Projeler arasında derleme bağımlılıkları ile açıklanmıştır <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildDependency> arabirim ve bağımlılıkları ile dağıtma <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployDependency> arabirimi. Daha fazla bilgi için bkz: [proje yapılandırması oluşturmak için](../../extensibility/internals/project-configuration-for-building.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılandırma seçenekleri yönetme](../../extensibility/internals/managing-configuration-options.md)   
 [Proje yapılandırması oluşturmak için](../../extensibility/internals/project-configuration-for-building.md)   
 [Çıkış için Proje Yapılandırması](../../extensibility/internals/project-configuration-for-output.md)