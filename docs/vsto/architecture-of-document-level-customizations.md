---
title: "Belge düzeyi özelleştirmeler mimarisi | Microsoft Docs"
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
- VSTOLoader.dll
- formats [Office development in Visual Studio]
- file formats [Office development in Visual Studio]
- vstoee.dll
- managed code extensions [Office development in Visual Studio], definition
- document-level customizations [Office development in Visual Studio]
- AddInLoader.dll
- architecture [Office development in Visual Studio], document-level customizations
ms.assetid: bafed4d0-5ff6-457b-9974-7c90f6ecb547
caps.latest.revision: "86"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4b3e40a5a11e681f372b9cb76b43060b87ac900b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="architecture-of-document-level-customizations"></a>Belge Düzeyi Özelleştirmeler Mimarisi
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]Microsoft Office Word ve Microsoft Office Excel için belge düzeyi özelleştirmeleri oluşturmak için projeleri içerir. Bu konuda belge düzeyi özelleştirmeleri şu yönlerini açıklanmaktadır:  
  
-   [Özelleştirmeleri anlama](#UnderstandingCustomizations)  
  
-   [Özelleştirmelerin bileşenleri](#Components)  
  
-   [Microsoft Office uygulamalarıyla özelleştirmeler nasıl çalışır](#HowCustomizationsWork)  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Belge düzeyi özelleştirmeleri oluşturma hakkında daha fazla genel bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md), [Word için belge düzeyi özelleştirme programlamasına başlama](../vsto/getting-started-programming-document-level-customizations-for-word.md), ve [Excel için belge düzeyi özelleştirme programlamasına başlama](../vsto/getting-started-programming-document-level-customizations-for-excel.md).  
  
##  <a name="UnderstandingCustomizations"></a>Özelleştirmeleri anlama  
 Belge düzeyi özelleştirme oluşturmak için Visual Studio'da Office geliştirici araçlarını kullanırken belirli bir belge ile ilişkili bir yönetilen kod derleme oluşturun. Bir belge veya çalışma kitabı bağlı derlemesi ile yönetilen kod uzantılarına sahiptir kabul edilir. Daha fazla bilgi için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
 Belgeyi bir kullanıcı oturum açtığında, derleme Microsoft Office uygulaması tarafından yüklenir. Derleme yüklendikten sonra belge açıkken özelleştirme olaylara yanıt verebilir. Özelleştirme otomatikleştirmek ve belge açık olduğunda ve sınıflarda birini kullanabilirsiniz ancak uygulama genişletmek için nesne modelini de çağırabilirsiniz [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].  
  
 Derleme uygulamanın COM bileşenlerini birincil birlikte çalışma derlemesi uygulamanın üzerinden iletişim kurar. Daha fazla bilgi için bkz: [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md) ve [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 Her derleme farklı uygulama etki alanında bir kullanıcı aynı anda birden çok belge düzeyi özelleştirmeleri açarsa yüklenir. Başka bir deyişle, hatalı davranan bir çözüm diğer çözümlerin başarısız olmasına sebep olamaz. Belge düzeyi özelleştirmeleri, tek bir uygulama etki alanındaki tek bir belgenin ile çalışmak üzere tasarlanmıştır. Belge arası iletişim için tasarlanmamıştır. Uygulama etki alanları hakkında daha fazla bilgi için bkz: [uygulama etki alanları](/dotnet/framework/app-domains/application-domains).  
  
> [!NOTE]  
>  Visual Studio'da Office geliştirici araçları kullanarak oluşturduğunuz belge düzeyi özelleştirmeleri, yalnızca bir son kullanıcı tarafından uygulama başlatıldığında kullanılmak üzere tasarlanmıştır. Uygulama program aracılığıyla başladıysanız, örneğin, otomasyon, kullanarak özelleştirme beklendiği gibi çalışmayabilir.  
  
### <a name="design-time-and-run-time-experiences"></a>Tasarım zamanı ve çalışma zamanı deneyimleri  
 Belge düzeyi özelleştirmeleri mimarisini anlamak için bir çözümü tasarlama ve çözümü çalıştırmanın deneyimlerini anlamanıza yardımcı olabilir.  
  
#### <a name="design-time"></a>Tasarım Zamanı  
 Tasarım zamanı deneyimi aşağıdaki adımları içerir:  
  
1.  Belge düzeyi projede Geliştirici oluşturur [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Proje belge ve belgenin arkasında çalışan derleme içeriyor. Belge (belki de tasarımcısı tarafından oluşturulan) zaten mevcut olabilir veya yeni bir belge birlikte proje oluşturulabilir.  
  
2.  Tasarımcı — proje veya bir başkası oluşturur ya da geliştirici — için son kullanıcı belgeyi son Görünüm ve yapısını oluşturur.  
  
#### <a name="run-time"></a>Çalışma Zamanı  
 Çalışma zamanı deneyimi aşağıdaki adımları içerir:  
  
1.  Son kullanıcı bir belge veya kod uzantılarını yönettiği çalışma kitabı açılır.  
  
2.  Belge veya çalışma kitabı derlenmiş derlemeyi yükler.  
  
3.  Kullanıcı belge veya çalışma kitabını çalışırken derleme olaylara yanıt verir.  
  
#### <a name="developer-and-end-user-perspective-compared"></a>Geliştirici ve son kullanıcı açısından karşılaştırma  
 Geliştirici birincil olarak çalıştığından [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]ve son kullanıcı Word veya Excel çalıştığı, belge düzeyi özelleştirmelerini anlamanın iki yolu vardır.  
  
|Geliştirici perspektifi|Son kullanıcının perspektifi|  
|-----------------------------|----------------------------|  
|Kullanarak [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], geliştirici Word ve Excel için erişilebilir olan kod yazar.<br /><br /> Geliştirici Word veya Excel çalıştırılan yürütülebilir dosya oluşturuyor gibi görünse de işlemi gerçekte şekilde çalışır. Belge bir derlemeyle ilişkilendirilir ve bu derleme için bir işaretçi içeriyor. Belge açıldığında, Word veya Excel derlemeyi bulur ve tüm işlenmiş olaylarına yanıt olarak kodu çalıştırır.|Çözümü kullananlar yalnızca belge veya çalışma kitabı açın (veya bir şablondan yeni bir belge oluşturun) gibi diğer Microsoft Office dosyasını açar.<br /><br /> Derleme özelleştirmeleri belge veya otomatik olarak geçerli verilerle doldurma veya bilgi istemek için bir iletişim kutusu gösteren gibi çalışma kitabındaki sağlar.|  
  
### <a name="supported-document-formats-for-document-level-customizations"></a>Belge düzeyi özelleştirmeleri için desteklenen Belge biçimleri  
 Bir özelleştirme projesi oluşturduğunuzda, projede kullanmak istediğiniz belgeyi biçimi seçebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Aşağıdaki tabloda, Excel ve Word için belge düzeyi özelleştirmelerinde kullanabileceğiniz Belge biçimleri listeler.  
  
|Excel|Word|  
|-----------|----------|  
|Excel çalışma kitabı (.xlsx)<br /><br /> Excel çalışma kitabı (.xlsm) makrosu etkin<br /><br /> Excel İkili çalışma kitabı (.xlsb)<br /><br /> Excel 97-2003 çalışma kitabı (.xls)<br /><br /> Excel şablonu (.xltx)<br /><br /> Excel Makro Etkin Şablonu (.xltm)<br /><br /> Excel 97-2003 şablonu (.xlt)|Word belgesi (.docx)<br /><br /> Makro içerebilen Word belgesi (.docm)<br /><br /> Word 97-2003 belgesi (.doc)<br /><br /> Word şablonu (.dotx)<br /><br /> Word Makro Etkin Şablonu (.dotm)<br /><br /> Word 97-2003 şablonu (.dot)|  
  
 Yönetilen kod uzantıları yalnızca desteklenen biçimlerdeki belgeler için tasarlamanız gerekir. Aksi takdirde, belge uygulamada açıldığında belirli olaylar oluşmayabilir. Örneğin, <xref:Microsoft.Office.Tools.Excel.Workbook.Open> olayı Excel XML elektronik tablo biçiminde veya web sayfası (.htm; .html) biçiminde kaydedilmiş çalışma kitaplarıyla yönetilen kod uzantıları kullandığınızda oluşmaz.  
  
### <a name="support-for-word-documents-that-have-xml-file-name-extensions"></a>.Xml dosya adı uzantılarına sahip Word belgeleri için destek  
 Belge düzeyi proje şablonları aşağıdaki dosya biçimlerine bağlı projeler oluşturmanıza izin verme:  
  
-   Word XML belgesi (* xml).  
  
-   Word 2003 XML belgesi (* xml).  
  
 Bu dosya biçimlerinde özelleştirmeleri kullanmak için son kullanıcılarınız istiyorsanız, yapı ve yukarıdaki tabloda belirtilen desteklenen dosya biçimleri birini kullanan bir özelleştirme dağıtın. Özelleştirme yükledikten sonra son kullanıcıların Word XML belgesinde kaydedebilirsiniz (* xml) biçimi veya Word 2003 XML belgesi (\*xml) biçimi ve özelleştirme çalışmaya devam edecektir beklendiği gibi.  
  
##  <a name="Components"></a>Özelleştirmelerin bileşenleri  
 Ana özelleştirmesinde belge ve derleme bileşenleridir. Bu bileşenlerin yanı sıra nasıl Microsoft Office uygulamaları bulmak ve yükledikleri önemli bir rol oynar birkaç bölümden vardır.  
  
### <a name="deployment-manifest-and-application-manifest"></a>Dağıtım bildirimi ve uygulama bildirimi  
 Özelleştirmeleri belirlemek ve özelleştirme derlemesinin en güncel sürümünü yüklemek için dağıtım bildirimleri ve uygulama bildirimlerini kullanın. Dağıtım noktaları geçerli uygulama bildirimine bildirimi. Uygulama noktaları özelleştirme derleme bildirimi ve giriş noktası sınıfı (veya sınıfları) derlemede yürütmek için belirtir. Daha fazla bilgi için bkz: [uygulama ve dağıtım bildirimlerini Office çözümlerinde](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
### <a name="visual-studio-tools-for-office-runtime"></a>Office çalışma zamanı için Visual Studio Araçları  
 Visual Studio'da Office geliştirici araçları kullanılarak oluşturulan belge düzeyi özelleştirmeleri çalıştırmak için son kullanıcı bilgisayarlarında yüklü olmalıdır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yüklü. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Özelleştirme derlemesini ve ayrıca yönetilen derlemeler kümesini yük yönetilmeyen bileşenleri içerir. Bu yönetilen derlemeler özelleştirme kodunuzun konak uygulamasını otomatikleştirmek ve genişletmek için kullandığı nesne modeli sağlar.  
  
 Daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
##  <a name="HowCustomizationsWork"></a>Microsoft Office uygulamalarıyla özelleştirmeler nasıl çalışır  
 Microsoft Office Özelleştirme parçası olan bir belgeyi bir kullanıcı oturum açtığında, uygulama bulmak ve özelleştirme derlemesinin en güncel sürümünü yüklemek için belgeye bağlı dağıtım bildirimini kullanır. Dağıtım bildirimi konumunu _AssemblyLocation isimli özel belge özelliğinde depolanır. Çözümü yapılandırdığınızda bu konum tanımlayan dize özelliğe eklenir.  
  
 Dağıtım bildirim noktalarına en güncel derlemeye işaret eden uygulama bildirimi. Daha fazla bilgi için bkz: [uygulama ve dağıtım bildirimlerini Office çözümlerinde](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
 Aşağıdaki çizimde bir belge düzeyi özelleştirme temel mimarisini gösterir.  
  
 ![2007 office Özelleştirme mimarisi](../vsto/media/office07-custom.png "2007 Office Özelleştirme mimarisi")  
  
> [!NOTE]  
>  Office çözümlerinde hedef [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], konak uygulama tarafından nesne modeline çağrı PIA içine doğrudan çağırmak yerine çözüm derlemesindeki Katıştırılmış Birincil birlikte çalışma derlemesi (PIA) türü bilgileri kullanarak çözümler. Daha fazla bilgi için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="loading-process"></a>Yükleme işlemi  
 Aşağıdaki adımlar, Microsoft Office çözümü parçası olan bir belgeyi bir kullanıcı oturum açtığında gerçekleşir.  
  
1.  Microsoft Office uygulamasının yönetilen kod uzantıları belgeyle ilişkili olup olmadığını görmek için özel belge özelliklerini denetler. Daha fazla bilgi için bkz: [özel belge özelliklerine genel bakış](../vsto/custom-document-properties-overview.md).  
  
2.  Yönetilen kod uzantılarını, uygulama VSTOLoader.dll yükleyen VSTOEE.DLL'i yükler. Yönetilmeyen bunlar Office çalışma zamanı için Visual Studio 2010 Araçları yükleyicisi bileşenleri DLL'leri. Daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
3.  VSTOLoader.dll yükleyen [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] ve yönetilen kısmına başlar [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
4.  Belgeyi yerel bilgisayardan farklı bir konumdan açtıysanız [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] belgenin konumunu içinde olduğunu doğrular **Güvenilen Konumlar** listesinde **Güven Merkezi Ayarları** için o Office uygulaması. Belge konumu güvenilir bir konumda değilse, özelleştirme güvenilir değil ve yükleme işlemi burada durdurur.  
  
5.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Çözümü yükler henüz yüklü değil, en son uygulama ve dağıtım bildirimlerini indirir ve bir dizi güvenlik denetimi gerçekleştirir. Daha fazla bilgi için bkz: [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md).  
  
6.  Özelleştirme çalıştırmak için güvenilir ise [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] derleme güncelleştirmeleri denetlemek için dağıtım bildirimi ve uygulama bildirimini kullanır. Derleme yeni bir sürümü kullanılabilir durumda, çalışma zamanı derlemesi için yeni sürümü indirir [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] önbellek istemci bilgisayardaki. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
7.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Özelleştirme derlemesini yüklemek yeni bir uygulama etki alanı oluşturur.  
  
8.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Özelleştirme derlemesini uygulama etki alanına yükler.  
  
9. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Çağrıları **başlangıç** özelleştirme derlemenizde olay işleyicisi. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Özel belge özelliklerine genel bakış](../vsto/custom-document-properties-overview.md)   
 [Belge düzeyi özelleştirmelerinde önbelleğe alınan veriler](../vsto/cached-data-in-document-level-customizations.md)  
  
  