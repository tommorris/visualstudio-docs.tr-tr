---
title: Office çözümleri geliştirmesine genel bakış (VSTO) | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies, Office
- Office development in Visual Studio, about developing solutions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f36b75b8c8c3cde4441520819ab566696d1d9066
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="office-solutions-development-overview-vsto"></a>Office Çözümleri Geliştirmesine Genel Bakış (VSTO)
  Microsoft Office ön ucu olarak çözümleri için kullanarak, size tanıdık Microsoft Office kullanıcı arabirimleri ve Word, Excel veri çözümleme özelliklerini ve Outlook e-posta yönetimi özelliklerini sözcük işleme özellikleri gibi araçları yararlanabilir . Office uygulamalarını özelleştirmek ve İş süreçlerinizi için gerek duyduğunuz belirli özellikler eklemek için Visual Studio'da çözüm geliştirebilirsiniz. Örneğin, Word düzenlenebilir veya düzenlenemez yapılan önceden var olan bölümleri çıkışı sözleşmeleri çeviren bir sözleşme oluşturucuyu kapatabilirsiniz. Excel ile farklı projeler için özelleştirilmiş bir otomatik bütçe çalışma sayfası oluşturabilirsiniz. Kullanıcılarınızın, karmaşık çözümleri web tabanlı bir mimari kullanırsanız olması çok daha pratik hale getirdiği office çözümlerini çevrimdışı da alabilir.  
  
 Bu konu, Visual Studio'da Office geliştirici araçları bulunan Office (VSTO) şablonları için Visual Studio araçları kullanarak oluşturabilirsiniz Office çözümlerinin türlerine genel bakış sağlar. Office ile geliştirme hakkında genel bilgi için bkz: [Office Geliştirici Merkezi](https://dev.office.com/).  
  
## <a name="choosing-an-office-project-type"></a>Bir Office proje türünü seçme  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] VSTO tabanlı Office geliştirme için proje şablonları aşağıdaki türlerini sağlar:  
  
-   **Belge düzeyi özelleştirmeleri** belirli bir belge ile ilişkilendirilmiş.  
  
-   **VSTO eklentileri** uygulama ile ilişkilendirilmiş.  
  
 Bu proje türleri hangisinin çözümünüz için en iyisi olduğuna karar vermek için kodunuzu çalıştırmak isteyip istemediğinizi düşünün yalnızca belirli bir belge açıksa veya mı kodunun kullanılabilir olmasını istediğiniz her uygulama çalışıyor. Proje şablonları hakkında daha fazla bilgi için bkz: [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md).  
  
 Oluşturabileceğiniz proje türleri hangi Office uygulamalarını geliştirme bilgisayarınızda yüklü olan bağlıdır. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
### <a name="document-level-customizations"></a>Belge Düzeyinde Özelleştirmeler  
 Belge düzeyi özelleştirmelerini tek bir belge, çalışma kitabı veya Microsoft Office Word veya Microsoft Office Excel şablonu ile ilişkili bir derlemeyi oluşur. İlişkili belge açıldığında derleme yüklenir. Oluşturduğunuz özelleştirmelerinde özellikleri yalnızca ilişkili belge açık olduğunda kullanılabilir. Özelleştirmeleri herhangi bir belge açık olduğunda, yeni bir menü öğesi veya Şerit sekmesi görüntüleme gibi uygulama çapında değişiklik yapamazsınız.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Belge düzeyi özelleştirmeleri oluşturmanıza yardımcı olacak araçlar içerir. Bir tasarım yüzeyi olarak özelleştirdiğiniz belge barındırılan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], sürükleyip bırakarak üzerine denetimleri belge tasarım sağlar. Diğer birçok [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Windows Forms denetimleri, sürükle ve bırak veri bağlama ve tümleşik bir hata ayıklayıcı gibi belge düzeyi projelerine özellikleri kullanılabilir.  
  
 Özelleştirmeler hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Excel İçin Belge Düzeyi Özelleştirme Programlamasına Başlama](../vsto/getting-started-programming-document-level-customizations-for-excel.md)  
  
-   [Word'de Belge Düzeyinde Özelleştirme Programlamasına Başlama](../vsto/getting-started-programming-document-level-customizations-for-word.md)  
  
-   [Belge Düzeyi Özelleştirmeler Mimarisi](../vsto/architecture-of-document-level-customizations.md)  
  
### <a name="vsto-add-ins"></a>VSTO eklentileri  
 VSTO eklentileri Microsoft Office uygulama ile ilişkilendirilen bir derlemeyi oluşur. İlişkili uygulama başlatıldığında, uygulama çalışmaya başladıktan sonra kullanıcılar ayrıca VSTO eklentileri yükleyebilir ancak genellikle, VSTO eklenti çalışır. VSTO oluşturduğunuz eklentileri özelliklerinde uygulamanın kendisinin belgeler açık olan bağımsız olarak kullanılabilir.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] VSTO eklentileri oluşturmanıza yardımcı olacak araçlar içerir. Eklenti projeleri için VSTO eklentisi temsil eden bir otomatik olarak oluşturulan sınıf içerir. Bu sınıf, özellikleri ve ana bilgisayar uygulamasının nesne modeline erişme ve VSTO eklentisi yüklenir ve kapandığında kodu çalıştırmak için kullanabileceğiniz olayları sağlar. Diğer birçok [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] VSTO eklentisi projelerine, Windows Forms ve tümleşik bir hata ayıklayıcı gibi özellikleri kullanılabilir.  
  
 VSTO eklentileri hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [VSTO Eklentilerini Programlamaya Başlama](../vsto/getting-started-programming-vsto-add-ins.md)  
  
-   [VSTO Eklentileri Mimarisi](../vsto/architecture-of-vsto-add-ins.md)  
  
## <a name="automating-office-applications-by-using-primary-interop-assemblies"></a>Birincil birlikte çalışma derlemeleri kullanarak Office uygulamalarını otomatikleştirme  
 Uygulamanın nesne modeli erişen kodu yazarak çözümünüze program aracılığıyla bir Office uygulaması özelliklerini dahil edebilirsiniz. Nesne modelleri çeşitli özellikleri ve yöntemleri aracılığıyla işlevselliği kullanıma sınıfların düzenleme ' dir. Her Office uygulaması için nesne modeli farklıdır.  
  
 Office geliştirme araçları kullanılarak oluşturulan bir çözüm bir Office uygulamasından nesne modelini kullanmak için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], uygulama için birincil birlikte çalışma derlemesi (PIA) kullanmanız gerekir. PIA yönetilen kod çözümünüzdeki Office uygulamasının COM tabanlı nesne modeli ile etkileşim için etkinleştirir.  
  
 Office yüklü ve geliştirme bilgisayarınızda genel derleme önbelleğinde kayıtlı çoğu geliştirme görevleri gerçekleştirmek için PIA olması gerekir. Daha fazla bilgi edinmek için bkz. [Bir Bilgisayarı Office Çözümleri Geliştirmek Üzere Yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md). Office PIA son kullanıcı bilgisayarlarında VSTO Office çözümlerini çalıştırmak için gerekli değildir. Daha fazla bilgi için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
 VSTO Office çözümlerinde PIA kullanma hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Office Çözümlerinde Kod Yazma](../vsto/writing-code-in-office-solutions.md)  
  
-   [Office Birincil Birlikte Çalışma Derlemeleri](../vsto/office-primary-interop-assemblies.md)  
  
## <a name="running-microsoft-vsto-office-solutions-on-end-user-computers"></a>Son kullanıcı bilgisayarlarında Microsoft VSTO Office çözümlerini çalıştırma  
 VSTO Office çözümü oluşturduğunuzda, dağıtım gereksinimleri geliştirme seçeneklerinizi nasıl etkileyebileceğini göz önünde bulundurun.  
  
### <a name="deployment-options"></a>Dağıtım seçenekleri  
 Office geliştirme araçları kullanarak oluşturduğunuz çözümleri dağıtmak için ClickOnce veya Windows Installer kullanın [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. ClickOnce dağıtımı, yüklü ve minimum kullanıcı etkileşimi ile çalıştırılan kendi kendini güncelleştirme çözümleri oluşturmanıza olanak sağlar. Windows Installer (.msi) dosyaları kolayca son kullanıcı bilgisayarlara dağıtılan, veya Systems Management Server (SMS) kullanılarak dağıtılmış. VSTO Office çözümlerini dağıtma hakkında daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
### <a name="installing-prerequisites"></a>Yükleme önkoşulları  
 Son kullanıcılar bir çözüm çalıştırmadan önce Office geliştirme araçlarını kullanarak oluşturduğunuz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], bilgisayarlarını bazı Önkoşullar yüklü olması gerekir. ClickOnce kullanarak veya bir Windows Installer dosyası oluşturarak çözümünüzü dağıtırsanız, bu Önkoşullar çözümünüzle birlikte yüklenebilir. Daha fazla bilgi için bkz [Office çözümleri önkoşulları dağıtımı için](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e) ve [nasıl yapılır: Office çözümlerini çalıştırmak için yükleme önkoşulları son kullanıcı bilgisayarlarında](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98).  
  
### <a name="security"></a>Güvenlik  
 Güvenlik VSTO Office çözümleri zorlanır için tarafından bir dizi denetim [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yükler ve çözüm yüklendiğinde duruma getirir. Bu denetimler dağıtım bildirimi konumunu Güvenilen ya da dağıtım bildirimini imzalamak için kullanılan sertifikanın güvenilir olup olmadığını doğrulamayı içerir. Daha fazla bilgi için bkz: [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken &#40;Visual Studio'da Office geliştirme&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Excel için belge düzeyi özelleştirme programlamasına başlama](../vsto/getting-started-programming-document-level-customizations-for-excel.md)   
 [Word için belge düzeyi özelleştirme programlamasına başlama](../vsto/getting-started-programming-document-level-customizations-for-word.md)   
 [VSTO Eklentilerini Programlamaya Başlama](../vsto/getting-started-programming-vsto-add-ins.md)  
  
  