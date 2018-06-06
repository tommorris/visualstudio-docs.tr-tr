---
title: Derleme ve SharePoint çözümlerini hata ayıklama | Microsoft Docs
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
- SharePoint development in Visual Studio, building and debugging
- SharePoint development in Visual Studio, debugging
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4d0bc3185b0684f96bf31cc127cd852448afe772
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765076"
---
# <a name="build-and-debug-sharepoint-solutions"></a>Derleme ve SharePoint çözümlerini hata ayıklama
  Genel olarak, derleme ve hata ayıklama SharePoint çözümleri oluşturma ve diğer türleri projelerinde hata ayıklama aynıdır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Bu bölümdeki konular, mevcut farkları açıklamaktadır.  
  
## <a name="project-output-for-sharepoint-solutions"></a>SharePoint çözümleri için proje çıktı
 SharePoint çözümleri oluşturma derlemeler ve bir çözüm paketi oluşturur (*.wsp*) dosyası. Aşağıdaki tabloda, yapılandırma sırasında bu dosyaları konumlarını gösterilmektedir.  
  
|Yapı öğesi|Çıkış klasörü|  
|----------------|-------------------|  
|Derleme, program veritabanı (*.pdb*), ve *.wsp* dosyaları.|*{ProjectName} \bin\debug* veya *{ProjectName} \bin\release*|  
|SharePoint proje öğesi dosyaları.|*{ProjectName} \pkg\debug* veya *{ProjectName} \pkg\release*|  
|Ara dosya oluşturun.|*{ProjectName} \obj\debug* veya *{ProjectName} \obj\release*|  
|Paket Ara dosyaları.|*{ProjectName} \pkgobj\debug* veya *{ProjectName} \pkgobj\release*|  
  
## <a name="build-sharepoint-solutions"></a>SharePoint çözümleri derleme
 SharePoint çözümleri oluşturmak için geliştirme bilgisayarında yüklü SharePoint server'ın doğru sürümü olması gerekir. Aksi halde SharePoint çözümleri oluşturma projelerinde diğer türleri oluşturma aynıdır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: SharePoint çözümleri derleme](../sharepoint/how-to-build-sharepoint-solutions.md).  
  
## <a name="debug-and-test-sharepoint-solutions"></a>Hata ayıklama ve SharePoint çözümlerini test etme
 Hata ayıklama önce [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] kopya *.wsp* paketi SharePoint sunucusuna Site ve Web kapsamlı özelliklerini etkinleştirir ve bazı durumlarda, proje başlatır. Diğer durumlarda, projeyi el ile açmanız gerekebilir. Daha fazla bilgi için bkz: [SharePoint çözümlerinde sorun giderme](../sharepoint/troubleshooting-sharepoint-solutions.md) ve [hata ayıklama SharePoint çözümlerini](../sharepoint/debugging-sharepoint-solutions.md).  
  
## <a name="debug-and-verify-sharepoint-solutions-by-using-alm-features"></a>Hata ayıklama ve ALM özelliklerini kullanarak SharePoint çözümlerini doğrulayın
 Birim testi ve IntelliTrace gibi Visual Studio ALM özellikler SharePoint çözümlerinizi daha fazla doğru şekilde tam olarak belirlemenizde sorunları için etkinleştirin. Profil oluşturma bulun ve performans sorunlu alanları SharePoint çözümlerini belirlemenize olanak sağlar. Daha fazla bilgi için bkz: [doğrulama ve hata ayıklama SharePoint kodu](../sharepoint/verifying-and-debugging-sharepoint-code.md) ve [SharePoint uygulamalarını performans profili oluşturma](../sharepoint/profiling-the-performance-of-sharepoint-applications.md).  
  
## <a name="security-during-the-build-process"></a>Güvenlik Yapılandırma işlemi sırasında
 Paket veya SharePoint çözümlerini dağıtmak için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] dosyaları SharePoint sunucusuna kopyalamak için izni olmalıdır. Çalıştırmalısınız [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] yükseltilmiş bir işlemdir ve kullanıcı SharePoint sunucusunu bir Site koleksiyonları yönetici hesabı olmalıdır. Ayrıca, projenizin korumalı bir çözüm ya da Grup çözümü olup olmadığını belirtmeniz gerekir. Daha fazla bilgi için bkz: [korumalı arasındaki farklar ve küme çözümleri](../sharepoint/differences-between-sandboxed-and-farm-solutions.md).  
  
## <a name="using-the-clean-command"></a>Temizle komutunu kullanma  
 Hata ayıklama, bir SharePoint sunucusu bir SharePoint çözüm yüklendiğinde **temiz** komutu çözümü kaldırmaz. Bunun yerine, SharePoint yapılandırma aracılığıyla özellikleri devre dışı bırakmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [Sunucu Gezgini kullanarak SharePoint bağlantılarına gözatma](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [SharePoint Çözümlerini Paketleme ve Dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
 