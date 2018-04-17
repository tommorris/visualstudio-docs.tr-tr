---
title: SharePoint çözümleri geliştirmek için gereksinimler | Microsoft Docs
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
- SharePoint development in Visual Studio, prerequisites
- SharePoint development in Visual Studio, requirements
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2cb92476d64abebb0dae24109e57940a19505cc1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="requirements-for-developing-sharepoint-solutions"></a>SharePoint Çözümleri Geliştirmek için Gereksinimler
 
Visual Studio'da bulunan SharePoint çözüm geliştirme araçları kullanmadan önce aşağıdaki önkoşulları sistemde yüklemeniz gerekir:

- C# ve/veya Visual Basic veya bir sürümü, Visual Studio uygulama yaşam döngüsü yönetimi (ALM) ile Visual Studio.

- [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 64-bit üzerinde yüklü [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] veya 64 bit [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] R2.

     veya

- [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 64-bit üzerinde yüklü [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] veya 64 bit [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] R2.

> [!NOTE]
> Yalnızca sunucu işletim sistemlerini resmi olarak SharePoint tarafından desteklendiğinden, iki istemci işletim sistemleri kullanılabilir: [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] ve [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] SP1. Daha fazla bilgi için bkz: [SharePoint Server 2010 Geliştirici iş istasyonu Yükleme Kılavuzu](http://go.microsoft.com/fwlink/?LinkID=164557).

İş verileri bağlantı (BDC) modeli proje türleri gerektiren [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] sistemde yüklü olmalıdır.

Visual Studio'da SharePoint çözümleri geliştirmek için Visual Studio ile aynı makinede SharePoint yüklemeniz gerekir. Ayrıca, SharePoint Geliştirici Araçları, yalnızca SharePoint bağımsız yapılandırmayı destekler; bir grubu (uzak) yapılandırmasını desteklemez.

> [!NOTE]
> Visual Studio'da SharePoint projeleri desteği yalnızca [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)]. Seçerseniz [!INCLUDE[net_v40_long](../sharepoint/includes/net-v40-long-md.md)] için yeni bir SharePoint projesi, bunu hala hedeflediğini [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)].

Yükleme hakkında daha fazla bilgi için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], bkz: [Visual Studio yükleme](../install/install-visual-studio.md).

## <a name="vista-and-windows-7-user-account-control-uac"></a>Vista ve Windows 7 Kullanıcı Hesabı Denetimi (UAC)

[!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] ve [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] kullanıcı hesabı denetimi (UAC) olarak bilinen bir güvenlik özelliği ekleyebilirsiniz. SharePoint çözümleri geliştirmek için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] üzerinde [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] ve [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] sistemleri UAC gerektirir, çalıştırmanız [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] bir sistem yöneticisi olarak. Masaüstünde kısayol menüsünü açın [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ve ardından **yönetici olarak çalıştır**.

Her zaman yönetici olarak çalıştırmak için masaüstü kısayolu yapılandırmak için kısayol menüsünü açın, seçin **özellikleri**, seçin **Gelişmiş** düğmesine tıklayın ve ardından **yönetici olarak çalıştır**  onay kutusu.

Daha fazla bilgi için bkz: [anlama ve Windows Vista kullanıcı hesabı denetimi yapılandırma](http://go.microsoft.com/fwlink/?LinkID=156476). ve [Windows 7 kullanıcı hesabı denetimi](http://go.microsoft.com/fwlink/?LinkId=177523).

## <a name="sharepoint-permissions-considerations"></a>SharePoint İzinleri Hakkında Önemli Noktalar

SharePoint çözümleri geliştirmek için çalıştırmak ve SharePoint çözümlerini hata ayıklamak için yeterli izinlere sahip olmalıdır. Bir SharePoint çözüm test etmeden önce gerekli izinlere sahip olduğunuzdan emin olmak için aşağıdaki adımları uygulayın:

1. Sistemde bir yönetici olarak, kullanıcı hesabını ekleyin.

2. Kullanıcı hesabınız olarak SharePoint sunucusu için bir grup yöneticisi ekleyin.

    1. SharePoint Merkezi Yönetimi'nde seçin **Grup Yöneticileri grubunu yönetin** bağlantı.

    2. Üzerinde **grup yöneticileri** sayfasında, **yeni** düğmesi.

3. Kullanıcı hesabınızı eklemek için WSS_ADMIN_WPG grubu.

## <a name="see-also"></a>Ayrıca Bkz.

[Başlarken &#40;Visual Studio'da SharePoint geliştirme&#41;](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md)