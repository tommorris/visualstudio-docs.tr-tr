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
ms.openlocfilehash: 547ba6d1e58376c50d0e01ab8fd3d55f62d5a935
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693324"
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
  
 IEESC ve Internet Explorer 7 etkisini yönetmek ve üzeri, Web siteleri ve Evrensel Adlandırma Kuralı (UNC) yolları belirlemek için güven ve güvenilir güvenlik bölgeleri (Yerel intranet veya Güvenilen siteler) birine ekleyin. Bölgeleri yönetme hakkında daha fazla bilgi için bkz: [yapılandırma ClickOnce Güvenilen Yayımcılar](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office Çözümleri Güvenliğini Sağlama](../vsto/securing-office-solutions.md)  
  
  