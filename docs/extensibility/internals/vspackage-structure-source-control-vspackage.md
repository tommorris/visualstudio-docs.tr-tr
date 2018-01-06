---
title: "VSPackage yapısı (kaynak denetimi VSPackage) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, structure
- source control packages, VSPackage overview
ms.assetid: 92722be7-b397-48c3-a7a7-0b931a341961
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 168aa0f7b93d20afaa30924dc17f05e0cac465bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="vspackage-structure-source-control-vspackage"></a>VSPackage yapısı (kaynak denetimi VSPackage)
Kaynak denetimi paket SDK'sı bir VSPackage oluşturma yönergeleri izin bilgilendirilmesine kaynak denetim işlevselliği ile tümleştirmek bir kaynak denetimi uygulayan sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ortamı. Bir VSPackage genellikle isteğe bağlı yüklenen bir COM bileşeni olduğundan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) bağlı olarak, kayıt defteri girdileri paket tarafından tanıtılan Hizmetleri. Her VSPackage uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>. Bir VSPackage genellikle tarafından sunulan hizmetlerin tükettiği [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE ve bazı hizmetler kendi proffers.  
  
 Bir VSPackage menü öğelerinden bildirir ve varsayılan öğesi durumu .vsct dosyası aracılığıyla oluşturur. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE VSPackage yüklenene kadar bu menü öğelerini bu durumda görüntüler. Sonuç olarak, VSPackage'nın uyarlamasını <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi etkinleştirmek veya menü öğelerini devre dışı bırakmak için çağrılır.  
  
## <a name="source-control-package-characteristics"></a>Kaynak denetimi paket özellikleri  
 Bir kaynak denetimi VSPackage içine son derece tümleşiktir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 VSPackage semantiğini şunları içerir:  
  
-   Bir VSPackage olması uygulanacak arabirim ( `IVsPackage` arabirimi)  
  
-   UI komutu uygulaması (.vsct dosya ve uyarlamasını <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi)  
  
-   İle VSPackage kaydı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Kaynak denetimi VSPackage bunlarla diğer iletişim kurması gereken [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] varlıklar:  
  
-   Projeler  
  
-   Düzenleyiciler  
  
-   Çözümleri  
  
-   Windows  
  
-   Çalışan belge tablosu  
  
### <a name="visual-studio-environment-services-that-may-be-consumed"></a>Tüketilebilir visual Studio ortamında Hizmetleri  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 SVsRegisterScciProvider hizmeti  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>  
  
### <a name="vsip-interfaces-implemented-and-called"></a>Uygulanan ve adlı VSIP arabirimleri  
 Kaynak denetimi bir VSPackage paketidir ve bu nedenle doğrudan ile kayıtlı diğer VSPackages ile etkileşebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Kaynak denetimi işlevlerinin tüm tekliflerden sağlamak için bir kaynak denetimi VSPackage projeleri veya kabuk tarafından sağlanan arabirimleri uğraşmanız.  
  
 Her projede [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3> bir projede olarak kabul edilecek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. Ancak, bu arabirim değil özelleştirilmiş yeterli kaynak denetimi için. Kaynak altında olması beklenen projeleri uygulama Denetim <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>. Bu arabirim kaynak denetimi VSPackage karakterlerin ve bağlama bilgileri (sunucu konumu ve disk konumun altındaki bir projenin arasında bağlantı kurmak için gerekli bilgileri sağlamak için ve içeriği için bir proje sorgulamak için kullanılır Kaynak Denetimi).  
  
 VSPackage uygulayan kaynak denetimi <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, sırayla sağlayan kendileri için kaynak denetimi kaydetmek ve bunların durumunu karakterlerin almak projeleri.  
  
 Kaynak denetimi VSPackage dikkate almanız gereken arabirimleri tam bir listesi için bkz: [ilgili hizmet ve arabirimi](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarım öğeleri](../../extensibility/internals/source-control-vspackage-design-elements.md)   
 [İlgili hizmet ve arabirimi](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)