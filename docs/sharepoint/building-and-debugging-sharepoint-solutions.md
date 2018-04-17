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
ms.openlocfilehash: f797fbf14504e2856616a0709aabba70cd639446
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="building-and-debugging-sharepoint-solutions"></a>SharePoint Çözümleri Oluşturma ve Hatalarını Ayıklama
  Genel olarak, derleme ve hata ayıklama SharePoint çözümleri oluşturma ve diğer türleri projelerinde hata ayıklama aynıdır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Bu bölümdeki konular, mevcut farkları açıklamaktadır.  
  
## <a name="project-output-for-sharepoint-solutions"></a>SharePoint çözümleri için proje çıktı  
 SharePoint çözümleri oluşturma, derlemeler ve çözüm paketi (.wsp) dosyası oluşturur. Aşağıdaki tabloda, yapılandırma sırasında bu dosyaları konumlarını gösterilmektedir.  
  
|Yapı öğesi|Çıkış klasörü|  
|----------------|-------------------|  
|Derleme, program veritabanı (PDB) ve .wsp dosyalarını.|*ProjectName*\bin\debug veya *ProjectName*\bin\release|  
|SharePoint proje öğesi dosyaları.|*ProjectName*\pkg\debug veya *ProjectName*\pkg\release|  
|Ara dosya oluşturun.|*ProjectName*\obj\debug veya *ProjectName*\obj\release|  
|Paket Ara dosyaları.|*ProjectName*\pkgobj\debug veya *ProjectName*\pkgobj\release|  
  
## <a name="building-sharepoint-solutions"></a>SharePoint çözümleri oluşturma  
 SharePoint çözümleri oluşturmak için geliştirme bilgisayarında yüklü SharePoint server'ın doğru sürümü olması gerekir. Aksi halde SharePoint çözümleri oluşturma projelerinde diğer türleri oluşturma aynıdır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: SharePoint çözümleri derleme](../sharepoint/how-to-build-sharepoint-solutions.md).  
  
## <a name="debugging-and-testing-sharepoint-solutions"></a>Hata ayıklama ve SharePoint çözümlerini test etme  
 Hata ayıklama önce [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] .wsp paket SharePoint sunucusuna kopyalar, Site ve Web kapsamlı özellikler etkinleştirir ve bazı durumlarda, proje başlatır. Diğer durumlarda, projeyi el ile açmanız gerekebilir. Daha fazla bilgi için bkz: [SharePoint çözümlerinde sorun giderme](../sharepoint/troubleshooting-sharepoint-solutions.md) ve [hata ayıklama SharePoint çözümlerini](../sharepoint/debugging-sharepoint-solutions.md).  
  
## <a name="debugging-and-verifying-sharepoint-solutions-by-using-alm-features"></a>Hata ayıklama ve ALM özelliklerini kullanarak SharePoint çözümlerini doğrulanıyor  
 Birim testi ve IntelliTrace gibi Visual Studio ALM özellikler SharePoint çözümlerinizi daha fazla doğru şekilde tam olarak belirlemenizde sorunları için etkinleştirin. Profil oluşturma bulun ve performans sorunlu alanları SharePoint çözümlerini belirlemenize olanak sağlar. Daha fazla bilgi için bkz: [doğrulama ve hata ayıklama SharePoint kodu](../sharepoint/verifying-and-debugging-sharepoint-code.md) ve [SharePoint uygulamalarını performans profili oluşturma](../sharepoint/profiling-the-performance-of-sharepoint-applications.md).  
  
## <a name="security-during-the-build-process"></a>Güvenlik Yapılandırma işlemi sırasında  
 Paket veya SharePoint çözümlerini dağıtmak için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] dosyaları SharePoint sunucusuna kopyalamak için izni olmalıdır. Çalıştırmalısınız [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] yükseltilmiş bir işlemdir ve kullanıcı SharePoint sunucusunu bir Site koleksiyonları yönetici hesabı olmalıdır. Ayrıca, projenizin korumalı bir çözüm ya da Grup çözümü olup olmadığını belirtmeniz gerekir. Daha fazla bilgi için bkz: [korumalı arasındaki farklar ve küme çözümleri](../sharepoint/differences-between-sandboxed-and-farm-solutions.md).  
  
## <a name="using-the-clean-command"></a>Temizle komutunu kullanma  
 Hata ayıklama, bir SharePoint sunucusu bir SharePoint çözüm yüklendiğinde **temiz** komutu çözümü kaldırmaz. Bunun yerine, SharePoint yapılandırma aracılığıyla özellikleri devre dışı bırakmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)   
 [Sunucu Gezgini kullanarak SharePoint bağlantılarına gözatma](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)   
 [SharePoint Çözümlerini Paketleme ve Dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  