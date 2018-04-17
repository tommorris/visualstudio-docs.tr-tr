---
title: Office çözüm güvenliğinde sorunu giderme | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- security [Office development in Visual Studio], troubleshooting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d7edb1826816ea4f20d66b91a7f9819ef394ce98
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshooting-office-solution-security"></a>Office Çözüm Güvenliğinde Sorunu Giderme
  Bu konu, Office çözümleri güvenliğini sağlama ile çalışırken karşılaşabileceğiniz ortak sorunları çözmek için ipuçları içerir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="trusted-solutions-cannot-be-installed-from-restricted-sites"></a>Güvenilir Çözümler Sınırlı sitelerden yüklenemez.  
 Web sitesi Internet Explorer Yasak siteler bölgesinde listeleniyorsa kullanıcılar bir web konumundan bir çözüm yükleyemezsiniz. Çözüm güvenilir bir sertifika ile imzalansa bile bu geçerlidir.  
  
 Dağıtım bildirimi URL'sini beş bölgelerinden biri kategorilere ayrılabilir:  
  
-   Bilgisayarım  
  
-   Internet  
  
-   Yerel intranet  
  
-   Güvenilen siteler  
  
-   Yasak siteler  
  
 Yasak siteler bölgesi için dağıtım bildirimi konumunu atanmışsa [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] çözümü yüklemez. Konum denir ve güvenilir, kullanıcı konumu Yasak siteler bölgesi'nden kaldırın ve çözümü yüklemek. Bölgeleri yönetme hakkında daha fazla bilgi için bkz: [yapılandırma ClickOnce Güvenilen Yayımcılar](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="solutions-cannot-be-installed-from-network-file-shares-or-web-locations-when-internet-explorer-enhanced-security-configuration-or-internet-explorer-7-is-installed"></a>Çözümleri ağ dosya paylaşımları veya Web konumlarından Internet Explorer Artırılmış Güvenlik Yapılandırması veya Internet Explorer 7 yüklü olduğunda yüklenemez.  
 Internet Explorer Artırılmış Güvenlik Yapılandırması (IEESC) Windows Server 2003 ve daha yüksek ve Internet Explorer 7 ve üzeri, kullanıcıların Internet'e göz yeteneğini önemli ölçüde kısıtlar. Kullanıcıların bir ağ dosya paylaşımı veya web konumundan Office çözümlerini yüklemeye çalışırken aşağıdaki hata iletisini alabilirsiniz: " içindağıtımbildiriminiimzalamakiçinkullanılansertifikanınçünkübuuygulamadakiözelleştirilmişişlevsellikçalışmaz*SolutionName* güvenilir değil. Yöneticinize daha fazla yardım için başvurun."  
  
 IEESC ve Internet Explorer 7 ve üzeri, dağıtım bildirimi URL'sini Internet bölgesinde kategorilere, bildirim güvenilir bir yayımcıdan bir sertifikası olmalıdır veya çözüm yüklenemez. IEESC, kullanıcıdan bir güven kararı vermesini istemek için varsayılan davranış şeklindedir.  
  
 IEESC ve Internet Explorer 7 etkisini yönetmek ve üzeri, web siteleri ve Evrensel Adlandırma Kuralı (UNC) yolları belirlemek için güven ve güvenilir güvenlik bölgeleri (Yerel intranet veya Güvenilen siteler) birine ekleyin. Bölgeleri yönetme hakkında daha fazla bilgi için bkz: [yapılandırma ClickOnce Güvenilen Yayımcılar](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office Çözümleri Güvenliğini Sağlama](../vsto/securing-office-solutions.md)  
  
  