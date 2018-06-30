---
title: SharePoint çözümleri için güvenlik | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- security [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, security
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0b97d549a273d32b73654556bc474d39628d8faa
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120672"
---
# <a name="security-for-sharepoint-solutions"></a>SharePoint çözümleri için güvenlik
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint uygulamaları güvenliğini artırmaya yardımcı olmak için aşağıdaki özellikleri içerir.  
  
## <a name="safe-control-entries"></a>Güvenli denetim girişleri
 Her SharePoint proje öğesi oluşturulan [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] sahip bir **güvenli denetim girişleri** güvenli temsil eden özellik koleksiyonu denetler. Kendi **güvenli** alt güvenli göz önünde bulundurun denetimleri belirtmenize olanak sağlar. Daha fazla bilgi için bkz: [proje öğelerinde paketleme ve dağıtım bilgileri sağlayın](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) ve [belirtme güvenli Web Bölümleri](http://go.microsoft.com/fwlink/?LinkId=177521).  
  
## <a name="allowpartiallytrustedcallers-attribute"></a>AllowPartiallyTrustedCallers özniteliği
 Varsayılan olarak, bir paylaşılan yönetilen kod derleme tam olarak çalışma zamanı kod erişim güvenliği (CAS) sistemi tarafından güvenilir yalnızca uygulamalarına erişebilir. Tam olarak güvenilir bir derleme AllowPartiallyTrustedCallers özniteliğiyle işaretlemeyi erişmek kısmen güvenilir derlemeler sağlar.  
  
 Sistem genel derleme önbelleğine dağıtılmaz herhangi bir SharePoint çözümü AllowPartiallyTrustedCallers özniteliği eklenir ([!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]). Bu korumalı çözümler veya SharePoint uygulama Bin dizinine dağıtılan çözümleri içerir. Daha fazla bilgi için bkz: [için Microsoft .NET Framework sürüm 1 güvenlik değişiklikleri](http://go.microsoft.com/fwlink/?LinkId=177515) ve [Web Bölümleri SharePoint Foundation dağıtma](http://go.microsoft.com/fwlink/?LinkId=177509).  
  
## <a name="safe-against-script-property"></a>Komut dosyası özellik karşı güvenli
 *Komut dosyası ekleme* kötü amaçlı olabilecek kod ekleme denetimlerini veya Web sayfaları. SharePoint 2010 sitelerine komut dosyası ekleme karşı korunmasına yardımcı olmak için katkıda bulunanlar görüntüleyemez veya varsayılan Web Bölümleri veya özelliklerini düzenleyin. Bu davranış SafeAgainstScript adlı SafeControl bir öznitelik tarafından denetlenir. İçinde [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)], bu öznitelik bir proje öğesi, kullanıcının ayarlamak **güvenli denetim girişleri** alt **karşı güvenli betik**. Daha fazla bilgi için bkz: [proje öğelerinde paketleme ve dağıtım bilgileri sağlayın](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) ve [nasıl yapılır: işareti denetimleri güvenli denetim olarak](../sharepoint/how-to-mark-controls-as-safe-controls.md).  
  
## <a name="vista-and-windows-7-user-account-control"></a>Vista ve Windows 7 kullanıcı hesabı denetimi
 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] ve [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] kullanıcı hesabı denetimi (UAC) olarak bilinen bir güvenlik özelliği ekleyebilirsiniz. SharePoint çözümleri geliştirmek için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] üzerinde [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] ve [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] sistemleri UAC gerektirir, çalıştırmanız [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] bir sistem yöneticisi olarak. Gelen **Başlat** menüsünde için kısayol menüsünü açın [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ve ardından **yönetici olarak çalıştır**.  
  
 Yapılandırmak için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] her zaman yönetici olarak çalıştır, kendi kısayol menüsünü açın, seçmek için kısayol **özellikleri**, seçin **Gelişmiş** düğmesini **özellikleri**iletişim kutusunu ve ardından **yönetici olarak çalıştır** onay kutusu.  
  
 Daha fazla bilgi için bkz: [anlama ve Windows Vista kullanıcı hesabı denetimi yapılandırma](http://go.microsoft.com/fwlink/?LinkID=156476). ve [Windows 7 kullanıcı hesabı denetimi](http://go.microsoft.com/fwlink/?LinkId=177523).  
  
## <a name="sharepoint-permissions-considerations"></a>SharePoint izinlerini konuları
 SharePoint çözümleri geliştirmek için çalıştırmak ve SharePoint çözümlerini hata ayıklamak için yeterli izinlere sahip olmalıdır. Bir SharePoint çözüm test etmeden önce gerekli izinlere sahip olduğunuzdan emin olmak için aşağıdaki adımları uygulayın:  
  
1.  Sistemde bir yönetici olarak, kullanıcı hesabını ekleyin.  
  
2.  Kullanıcı hesabınız olarak SharePoint sunucusu için bir grup yöneticisi ekleyin.  
  
    1.  SharePoint 2010 Merkezi Yönetim'deki seçin **Grup Yöneticileri grubunu yönetin** bağlantı.  
  
    2.  Üzerinde **grup yöneticileri** sayfasında, **yeni** menü seçeneği  
  
3.  Kullanıcı hesabınızı eklemek için WSS_ADMIN_WPG grubu.  
  
## <a name="additional-security-resources"></a>Ek güvenlik kaynakları
 Güvenlik sorunları hakkında daha fazla bilgi için aşağıdakilere bakın.  
  
### <a name="visual-studio-security"></a>Visual Studio güvenliği
  
-   [Güvenlik ve kullanıcı izinleri](http://go.microsoft.com/fwlink/?LinkId=177503)  
  
-   [Yerel ve .NET Framework kod güvenliği](http://go.microsoft.com/fwlink/?LinkId=177504)  
  
-   [.NET Framework güvenliği](http://go.microsoft.com/fwlink/?LinkId=177502)  
  
### <a name="sharepoint-security"></a>SharePoint güvenlik
  
-   [SharePoint Foundation Yönetim ve güvenlik](http://go.microsoft.com/fwlink/?LinkId=177501)  
  
-   [SharePoint güvenlik kaynağı merkezi](http://go.microsoft.com/fwlink/?LinkId=177498)  
  
-   [SharePoint Foundation Web bölümlerini güvenliğini sağlama](http://go.microsoft.com/fwlink/?LinkId=177511)  
  
-   [İyileştirme Web uygulaması güvenliği: Tehditler ve Önlemler Kılavuzu](http://go.microsoft.com/fwlink/?LinkID=140080)  
  
### <a name="general-security"></a>Genel güvenlik
  
-   [MSDN güvenlik geliştirme yaşam döngüsü](http://go.microsoft.com/fwlink/?LinkID=147149)  
  
-   [Güvenli ASP.NET uygulamaları oluşturma: Kimlik doğrulama, yetkilendirme ve güvenli iletişim](http://go.microsoft.com/fwlink/?LinkId=177494)  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint çözümleri geliştirmek için gereksinimler](../sharepoint/requirements-for-developing-sharepoint-solutions.md)  
  
