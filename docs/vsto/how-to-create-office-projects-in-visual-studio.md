---
title: "Nasıl yapılır: Visual Studio'da Office projeleri oluşturma | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.SelectDocWizard.Page1
- VST.SelectDocWizard.Http
- VST.SelectDocWizard.Extension
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], creating projects
- Office applications [Office development in Visual Studio], creating
- Office projects [Office development in Visual Studio]
- projects [Office development in Visual Studio], creating
- document-level customizations [Office development in Visual Studio], creating
- application-level add-ins [Office development in Visual Studio], creating projects
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 29e84c08241bba09ab7923fa5997333f2371270d
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-create-office-projects-in-visual-studio"></a>Nasıl Yapılır: Visual Studio'da Office Projeleri Oluşturma
  Kullanabileceğiniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] VSTO eklenti ve belge düzeyi oluşturmak için Microsoft Office uygulamaları için özelleştirmeleri. Bu proje türleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-vsto-add-in-project"></a>Bir VSTO eklenti projesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni**, **proje**. Tümleşik geliştirme ortamı (IDE) kullanmak üzere ayarlanmış olup olmadığını [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] geliştirme ayarları, **dosya** menüsünde seçin **yeni**, **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
    > [!NOTE]  
    >  Office projeleri hedef [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] varsayılan olarak. Daha fazla bilgi için bkz: [.NET Framework istemci profili](/dotnet/framework/deployment/client-profile).  
  
2.  Şablonlar bölmesinde, kullanmak istediğiniz dil için düğümü genişletin **Office/SharePoint**.  
  
3.  Seçin **Office eklentileri** düğümü.  
  
4.  Proje şablonları listesinde VSTO eklenti proje şablonu seçin. Kullanılabilir VSTO eklenti proje şablonları listesi için bkz: [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md).  
  
    > [!NOTE]  
    >  Proje şablonları görünür değilse seçtiğinizde **Office eklentileri** düğümü olduğundan emin olun **.NET Framework 4** veya daha sonra iletişim kutusunun üstündeki birleşik giriş kutusu seçili olduğunda. Office proje şablonları hem .NET Framework sürümleri için görünür durumdadır.  
  
5.  İçinde **adı** proje için bir ad yazın. Varsayılan olarak, proje adı çözüm adı olarak da kullanılır.  
  
6.  İçinde **konumu** kutusunda, projeyi oluşturmak istediğiniz yolu girin. Mutlak ve Evrensel Adlandırma Kuralı (UNC) yollarını kullanabilirsiniz. HTTP, FTP veya diğer protokol yollarını kullanmayın.  
  
     Konumlar aşağıdaki biçimlere sahiptir:  
  
      * [*sürücü*\]\:  
  
      * \\\\*Sunucu*\\*paylaşımı*  
  
     Bu karakterleri konumda kullanmayın:  
  
      * Yıldız işareti (*)  
  
      * Dikey çubuk (|)  
  
      * İki nokta üst üste (:) (Sürücü harfi dışında.)  
  
      * Çift tırnak işareti (") (boşluk içeren yollar gerek kalmaz tırnak işaretleri.)  
  
      * Küçüktür (\<)  
  
      * Büyüktür (>)  
  
      * Soru işareti (?)  
  
      * Yüzde (%) işareti  
  
7. Seçin **Tamam** düğmesi.
  
    > [!NOTE]  
    >  Eklenti projeleri oluşturulduğunda daima kaydedilir. Geçici projeler olarak oluşturulamıyor. Geçici projeler hakkında daha fazla bilgi için bkz: [geçici projeler](http://msdn.microsoft.com/en-us/9cf1944c-7045-44cc-8701-7b0eb4099f2b).  
  
### <a name="to-create-a-document-level-customization-project"></a>Belge düzeyi özelleştirme projesi oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni**, **proje**. IDE'yi üzerinde Visual Basic geliştirme ayarlarını kullanmak üzere ayarlanmış olup olmadığını **dosya** menüsünde seçin **yeni**, **proje**.  
  
     **Yeni proje** iletişim kutusu görüntülenir.  
  
    > [!NOTE]  
    >  Office projeleri hedef [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] varsayılan olarak.  Daha fazla bilgi için bkz: [.NET Framework istemci profili](/dotnet/framework/deployment/client-profile).  
  
2.  Şablonlar bölmesinde, kullanmak istediğiniz dil için düğümü genişletin **Office/SharePoint**.  
  
3.  Seçin **Office eklentileri** düğümü.  
  
4.  Proje şablonları listesinde, bir belge düzeyi proje şablonu seçin. Kullanılabilir belge düzeyi proje şablonları listesi için bkz: [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md).  
  
    > [!NOTE]  
    >  Proje şablonları görünür değilse seçtiğinizde **Office eklentileri** düğümü olduğundan emin olun **.NET Framework 4** veya daha sonra iletişim kutusunun üstündeki birleşik giriş kutusu seçili olduğunda. Office proje şablonları hem .NET Framework sürümleri için görünür durumdadır.  
  
5.  İçinde **adı** proje için bir ad yazın. Varsayılan olarak, bu ad Ayrıca belge için kullanılır. Ayrıca Visual C# geliştirme ayarları veya genel geliştirme ayarlarını kullanmak için IDE'yi ayarlarsanız, konum ve çözüm adı girin.  
  
    > [!NOTE]  
    >  Yedek karakterler proje konumunun yolunu veya proje adı kullanamazsınız. Ayrıca, proje adı karakterleri çevrimdışı kullanım için çözüm dağıtmayı planlıyorsanız, HTTP protokol belirtimleri sığması gerekir.  
  
6.  Seçin **Tamam** düğmesi.  
  
     **Office Proje Sihirbazı için Visual Studio Araçları** açar.  
  
7.  Seçin **bir yeni belge oluşturun** çözüm için yeni bir belge oluşturmak veya seçmek istiyorsanız **var olan bir belgeyi kopyalama** var olan bir belgeyi özelleştirmek istiyorsanız.  
  
     Yeni bir belge oluşturursanız, adı belirtmeyin **adı** kutusunda ve belgenin biçimini kullanarak seçin **biçimi** kutusu. Kullanılabilir biçimleri hakkında daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md).  
  
     Var olan bir belgeyi kullanıyorsanız, belgede konumunu belirtin **varolan belgenin tam yolu** kutusu. Mutlak yollar ve UNC yolları kullanabilirsiniz. HTTP, FTP veya diğer Protokolü yollarını kullanmayın.  
  
     Konumlar aşağıdaki biçimlere sahiptir:  
  
    -   [*sürücü*\]\:  
  
    -   \\\\*Sunucu*\\*paylaşımı*  
  
     Bu karakterleri konumda kullanmayın:  
  
    -   Yıldız işareti (*)  
  
    -   Dikey çubuk (|)  
  
    -   İki nokta üst üste (:) (Sürücü harfi dışında.)  
  
    -   Çift tırnak işareti (") (boşluk içeren yollar gerek kalmaz tırnak işaretleri.)  
  
    -   Küçüktür (\<)  
  
    -   Büyüktür (>)  
  
    -   Soru işareti (?)  
  
    -   Yüzde (%) işareti  
  
    > [!NOTE]  
    >  Var olan bir belgeyi kullanırsanız, bir [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] proje, yalnızca içinde oluşturulur veya dönüştürülür belgeleri kullanın [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]. Benzer şekilde, var olan bir belgeyi bir Word kullanırsanız project 2010, yalnızca içinde oluşturulan veya Word 2010 dönüştürülen belgeleri kullanın. Word'ün önceki bir sürümde oluşturulmuş bir belge kullanırsanız, belirli özellikleri belgede devre dışı bırakılacak. Bu özellikleri kullanan kodu yazma çalışırsanız, projenizde hatalarla karşılaşabilirsiniz. Bir belge dönüştürmek için içinde açın [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] veya Word 2010 üzerinde **dosya** sekmesinde Şerit'te, seçin **bilgisi**, **dönüştürme**.  
  
8.  Seçin **son**.  
  
9. Proje klasöründeki ve onun alt klasörlerindeki aşağıdaki durumlarda Word'de Güven Merkezi'ndeki güvenilir konumlar listesine ekleyin:  
  
    -   .Docm dosyasını temel alan bir Word belgesi oluşturmak ve belge VBA proje içeriyor ya da Windows Forms denetimleri barındıran. Proje klasörünü güvenilir konumlar listesine ekleme, belge tasarım zamanında beklendiği gibi çalıştığından emin olun yardımcı olur.  
  
    -   .Dotx dosyasını temel alan bir Word Şablonu proje oluşturuyorsunuz. Böylece çalıştırın ve projenin hata ayıklamasını proje klasörünü güvenilir konumlar listesine eklemeniz gerekir.  
  
     Microsoft Office Online web sitesini güvenilir konumlara bir belge ekleme hakkında daha fazla bilgi için bkz: [oluşturma, kaldırma veya değiştirme dosyalarınız için güvenilir bir konumdayken](https://support.office.com/en-au/article/Create-remove-or-change-a-trusted-location-for-your-files-f5151879-25ea-4998-80a5-4208b3540a62).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md)   
 [Office çözümlerinin işbirlikçi geliştirme](../vsto/collaborative-development-of-office-solutions.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [VSTO Eklentilerini Programlamaya Başlama](../vsto/getting-started-programming-vsto-add-ins.md)  
  
  
