---
title: "Office çözümleri güvenliğini sağlama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, security
- Office applications [Office development in Visual Studio], security
- security [Office development in Visual Studio]
ms.assetid: af840916-dda4-4e52-b536-802ebcab30ca
caps.latest.revision: "78"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 50960f95b317f389cfe9f99154e51a5103b419d3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="securing-office-solutions"></a>Office Çözümleri Güvenliğini Sağlama
  Office çözümleri için güvenlik modeli birçok teknoloji içerir: [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)], Microsoft Office ve Internet Explorer Yasak siteler bölgesi Güven Merkezi. Aşağıdaki bölümlerde, farklı güvenlik özelliklerinin nasıl çalıştığı açıklanmaktadır:  
  
-   [Office çözümlerine güven verme](#GrantingTrustToSolutions)  
  
-   [Belgelere güven verme](#GrantingTrustToDocuments)  
  
-   [Windows Installer kullanırken, güven verme](#GrantingTrustWindowsInstaller)  
  
-   [Office çözümleri için belirli güvenlik konuları](#Security)  
  
-   [Güvenlik geliştirme sırasında](#SecurityDuringDeployment)  
  
-   [Office çalışma zamanı için Visual Studio Araçları](#VisualStudioToolsForOfficeRuntime)  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
##  <a name="GrantingTrustToSolutions"></a>Office çözümlerine güven verme  
 Office çözümlerine güven üzerinde aşağıdaki bulgu göre Office çözümü güvenmeyi her son kullanıcının güvenlik ilkesini değiştirmek anlamına gelir:  
  
-   Uygulama bildirimini imzalamak için kullanılan sertifika.  
  
-   Dağıtım bildirimi URL'si.  
  
 Daha fazla bilgi için bkz: [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md).  
  
##  <a name="GrantingTrustToDocuments"></a>Belgelere güven verme  
 Belge düzeyi özelleştirme belge güvenilir bir konum olarak belirlenmiş bir dizinde olması gerekir. Daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
##  <a name="GrantingTrustWindowsInstaller"></a>Windows Installer kullanırken, güven verme  
 Office çözümleri yönetici hakları gerektiren Program dosyaları dizine yüklemek üzere bir MSI dosyası oluşturmak için Windows Installer'ı kullanabilirsiniz. Office çözümleri Program Files dizininde için Office çalışma zamanı için Visual Studio 2010 Araçları güvenilir olması için bu Office çözümleri göz önünde bulundurur ve ClickOnce güven istemi göstermez.  
  
##  <a name="Security"></a>Office çözümleri için belirli güvenlik konuları  
 Tarafından sağlanan güvenlik özellikleri [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], ve Microsoft Office Office çözümlerindeki olası güvenlik tehditlerini çeşitli karşı korumaya yardımcı olabilir. Daha fazla bilgi için bkz: [Office çözümleri için belirli güvenlik konuları](../vsto/specific-security-considerations-for-office-solutions.md).  
  
##  <a name="SecurityDuringDeployment"></a>Güvenlik geliştirme sırasında  
 Geliştirme sürecini kolaylaştırmak için Visual Studio çalıştırmak ve çözümünüzü bilgisayarınızdaki bir projeyi derleme her zaman hata ayıklamak için gerekli olan güvenlik ilkesini ayarlar. Bazı senaryolarda projeyi geliştirmek için ek güvenlik adımlar gerekebilir.  
  
### <a name="document-level-solutions"></a>Belge düzeyi çözümleri  
 Aşağıdaki proje türlerini geliştiriyorsanız, bir belgenin tam yolu Microsoft Office uygulamasında güvenilir konumlar listesine eklenmesi gerekir:  
  
-   Belge düzeyi gibi bir ağ dosya paylaşımında bulunan çözümleri  *\\\servername\sharename*.  
  
-   .Doc veya .docm dosyaları kullanan Word için belge düzeyi çözümleri.  
  
 Belge konumu güvenilir konumları listesine Ekle veya özel olarak hata ayıklama dahil oluşturmak ve bunları klasörleri olduğunda alt dizinleri içerir. Daha fazla bilgi için Microsoft Office Online Yardım makalesine bakın [oluşturma, kaldırma veya değiştirme dosyalarınız için güvenilir bir konumdayken](https://support.office.com/en-au/article/Create-remove-or-change-a-trusted-location-for-your-files-f5151879-25ea-4998-80a5-4208b3540a62).  
  
### <a name="temporary-certificates"></a>Geçici Sertifikalar  
 Bir imzalama sertifikası zaten yoksa, visual Studio geçici bir sertifika oluşturur. Bu geçici bir sertifika yalnızca geliştirme sırasında kullanmak ve dağıtım için resmi bir sertifika satın alın.  
  
 Office projesini ilk kez yapılandırıldıktan sonra geçici bir sertifika oluşturulur. Proje sertifika eklendiğinde değiştirilmiş olarak işaretlendiği için F5 ' e bir sonraki basışınızda projeyi yeniden oluşturulur.  
  
 Olabilir birçok geçici sertifikalar bir süre sonra geçici sertifikalar bazen temizlemelidir şekilde.  
  
##  <a name="VisualStudioToolsForOfficeRuntime"></a>Office çalışma zamanı için Visual Studio Araçları  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Yayımcı ve bir özelleştirmeye verilen izinleri kimliğini doğrulamak için özelliklere sahiptir. Bir dizi güvenlik denetimleri bu izinleri doğrular.  
  
### <a name="security-during-customization-loading"></a>Özelleştirme yüklendiği sırada güvenlik  
 Belge düzeyi özelleştirme yüklendiğinde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] her zaman belgenin güvenilir konumlar listesinde olup olmadığını denetler. Ayrıca, çalışma zamanı çözümün uygulama bildiriminde FullTrust istekleri olup olmadığını denetler. Özelleştirme yüklenirken ek güvenlik denetimleri gerçekleştirir.  
  
### <a name="sequence-of-security-checks-during-installation"></a>Güvenlik denetimlerini yükleme sırasında bir dizi  
 Office çözümünü yüklü veya güncelleştirildiğinde, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] bir güven karar vermek için belirli bir sırada bir dizi güvenlik denetimleri gerçekleştirir. Bir çözüm yüklü veya yalnızca çalışma zamanı çözüm güvenilir olduğunu belirlerse güncelleştirildi.  
  
 Yükleme işlemi dört yöntemden birini kullanarak başlatabilirsiniz: Kurulum programını çalıştırarak, dağıtım bildirimi açarak, Microsoft Office uygulama ana bilgisayarı açarak veya VSTOInstaller.exe çalıştırarak.  
  
 İlk güvenlik denetimi yalnızca belge düzeyi çözümleri için geçerlidir. Belge düzeyi çözümü belgenin güvenilir bir konumda olması gerekir. Belge bir uzak ağ dosya paylaşımında bulunan veya .doc veya .docm dosya adı uzantısı varsa, belgenin konumu güvenilir konumlar listesine eklenmesi gerekir. Daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
 ![VSTO güvenliği - Microsoft Office'ten yükleme](../vsto/media/host-install.png "VSTO güvenliği - Microsoft Office'ten yükleme")  
  
 Güvenlik denetimlerini sonraki kümesi olan [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ve ClickOnce. Bu denetimleri geçirmek için Office çözümleri FullTrust izinlerini istemeniz gerekir, güvenilmeyen yayımcı listesinde olmayan bir sertifika ile oturum açmanız ve Internet Explorer kısıtlı bölgede değil bir konumda olabilir. Sertifika güvenilir yayımcı listesinde ise, çözüm hemen yüklenir. Aksi takdirde, biri de, başarısız olmadıysa, çözüm denetimleri son kümesine devam eder.  
  
 ![Çözümleri yüklemek için VSTO güvenliği](../vsto/media/installing.png "VSTO güvenlik çözümleri yüklemek için")  
  
 Varsa [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] güven istemi izin verilir ve çözüm güven henüz verilmemiş, çalışma zamanı güven kararının son kullanıcı tarafından yapılmasına izin verir. Kullanıcı çözümlerine güven verirse bir girdi kullanıcı ekleme listesine eklenir. Kullanıcı ekleme listesindeki tüm çözümleri tam güvene sahip ve yüklenebilir ve çalıştırın.  
  
 Windows Installer (MSI) Program dosyaları dizinine kullanarak Office çözümü yüklüyse, Visual Studio 2010'dan başlayarak, ekleme listesi atlanır. Daha fazla bilgi için bkz: [güvenen Office çözümleri ekleme listeleri kullanarak tarafından](../vsto/trusting-office-solutions-by-using-inclusion-lists.md).  
  
 ![VSTO güvenliği - yüklemek için Kurulum programını kullanarak](../vsto/media/setup-vstoinstaller.png "VSTO güvenliği - yüklemek için Kurulum programını kullanma")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerine güven verme](../vsto/granting-trust-to-office-solutions.md)   
 [Belgelere güven verme](../vsto/granting-trust-to-documents.md)   
 [Ekleme listelerini kullanarak Office çözümlerine güvenme](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)   
 [Nasıl yapılır: ekleme listesi güvenliğini yapılandırma](../vsto/how-to-configure-inclusion-list-security.md)   
 [Nasıl yapılır: Office çözümlerini imzalama](../vsto/how-to-sign-office-solutions.md)   
 [Office çözüm güvenliğinde sorunu giderme](../vsto/troubleshooting-office-solution-security.md)   
 [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)   
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Başvurusu](/visualstudio/deployment/clickonce-reference)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)  
  
  