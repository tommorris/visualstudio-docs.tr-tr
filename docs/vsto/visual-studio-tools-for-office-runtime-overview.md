---
title: Office çalışma zamanı genel bakış için Visual Studio Araçları
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office runtime [Office development in Visual Studio], about Office runtime
- VSTOLoader.dll
- runtime loader [Office development in Visual Studio]
- Office runtime [Office development in Visual Studio], assemblies
- Office runtime [Office development in Visual Studio]
- runtime [Office development in Visual Studio], assemblies
- vstoee.dll
- Visual Studio Tools for Office runtime
- Office solutions [Office development in Visual Studio], runtime
- solutions [Office development in Visual Studio], runtime
- versions [Office development in Visual Studio], runtime
- assemblies [Office development in Visual Studio], runtime
- runtime [Office development in Visual Studio], about VSTO runtime
- solution loader [Office development in Visual Studio]
- runtime [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c0bb3c800aece9531d6fe90ba04b9c99a0b4bd69
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767809"
---
# <a name="visual-studio-tools-for-office-runtime-overview"></a>Office çalışma zamanı genel bakış için Visual Studio Araçları
  Visual Studio'da Microsoft Office geliştirici araçları kullanılarak oluşturulan çözümleri çalıştırmak için Office çalışma zamanı için Visual Studio 2010 Araçları son kullanıcı bilgisayarlarında yüklenmesi gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Office çalışma zamanı yeniden dağıtılabilir için Visual Studio araçlarını yükleme](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md). Office çalışma zamanı için Visual Studio 2010 Araçları iki ana bileşenden oluşur:  
  
-   .NET Framework için Office uzantıları. Bu bileşenler, çözümünüz ile Microsoft Office uygulaması arasındaki iletişim katmanını sağlayan yönetilen derlemelerdir. Daha fazla bilgi için bkz: [.NET Framework için Office uzantıları anlamak](#officeextensions).  
  
-   Office çözüm yükleyicisi. Bu bileşen, Office uygulamalarının çalışma zamanını ve çözümlerinizi yüklemek için kullandığı bir yönetilmeyen DLL'ler kümesidir. Daha fazla bilgi için bkz: [Office çözüm yükleyicisi anlamak](#UnmanagedLoader).  
  
 Çalışma zamanı birkaç farklı yolla yüklenebilir. Bilgisayarın yapılandırmasına bağlı olarak, çalışma zamanını yüklediğinizde farklı çalışma zamanı bileşenlerinin yüklemesi gerçekleşir. Daha fazla bilgi için bkz: [Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).  
  
##  <a name="officeextensions"></a> .NET Framework için Office uzantıları anlama  
 Office çalışma zamanı için Visual Studio 2010 Araçları, .NET Framework 3.5 için Office uzantıları içeren [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ve daha sonra. Her bir .NET Framework sürümünü hedefleyen çözümler, ilgili sürüm için uygun uzantıları kullanır.  
  
 Bu uzantılar, çözümlerinizin Office uygulamalarını otomatikleştirmek ve genişletmek için kullandığı derlemelerden oluşur. Bir Office projesi oluşturduğunuzda, Visual Studio projenin .NET Framework hedefi ve proje türü için kullanılan derlemelerin başvurularını otomatik olarak ekler. Office uzantılarında derlemeler hakkında daha fazla bilgi için bkz: [Office çalışma zamanı için Visual Studio araçlarında derlemeler](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md).  
  
### <a name="design-differences-in-the-office-extensions"></a>Office uzantıları tasarım farklılıkları  
 .NET Framework 3.5 için Office uzantılarında kullandığınız türlerin çoğu sınıflardır. Bunlar önceki sürümlerinde bulunan, aynı sınıflarıdır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Buna karşılık, Office uzantıları için kullandığınız türlerinin çoğu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya arabirimleri sonraki. Hedeflediğinizde Örneğin, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümlerde, <xref:Microsoft.Office.Tools.Excel.Worksheet> ve <xref:Microsoft.Office.Tools.Word.Document> sınıfları yerine arabirimleri türleridir.  
  
 .NET Framework 3.5 çözümünüzü hedefleyen çoğu durumda, Office çözümlerinde yazdığınız kodları aynı olup veya [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Ancak belirli özellikler, .NET Framework'ün farklı sürümlerini hedeflediğinizde farklı kod gerektirir. Daha fazla bilgi için bkz: [geçirmek Office çözümlerini .NET Framework 4 veya sonraki bir sürüme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
### <a name="interfaces-in-the-office-extensions-for-the-net-framework-4-or-later"></a>.NET Framework 4 veya sonraki Office uzantılarında arabirimleri  
 Arabirimler için Office uzantılarında çoğu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra kullanıcı kodu tarafından gerçekleştirilen amaçlanmamıştır. Doğrudan uygulayabilirsiniz yalnızca arabirimleri harfiyle başlayan adlara sahip **ı**, gibi <xref:Microsoft.Office.Tools.Excel.ISmartTagExtension>.  
  
 Harf olmayan tüm arabirimler **ı** Office çalışma zamanı için Visual Studio 2010 araçları tarafından dahili olarak uygulanır ve bu arabirimleri gelecek sürümlerde değişebilir. Bu arabirimleri uygulayan nesneler oluşturmak için tarafından sağlanan yöntemleri kullanın `Globals.Factory` projenizdeki nesnesi. Örneğin, uygulayan bir nesne almak için <xref:Microsoft.Office.Tools.Excel.SmartTag> arabirim, kullanın `Globals.Factory.CreateSmartTag` yöntemi. Hakkında daha fazla bilgi için `Globals.Factory`, bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
### <a name="enable-type-equivalence-and-embedded-types-in-projects-that-target-the-net-framework-4-or-later"></a>Tür eşdeğerliği ve katıştırılmış türlerinde .NET Framework 4 veya sonrasını hedefleyen projeler etkinleştir  
 Çünkü için Office uzantıları nesne modelini [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bağlı arabirimlerde tür bilgilerini katıştırma hem Visual C# ve Visual Basic Visual Studio'da türü eşdeğer özelliğini kullanabilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] çözümünüze . Bu özellik Office çözümleri sağlar ve [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] birbirinden sürümüne. Çözümünüzü kullanıyorsa, örneğin, <xref:Microsoft.Office.Tools.Word.Document> arabirimi katıştırılmış türünün ve sonraki sürüm çalışma zamanına ekler üyelerine <xref:Microsoft.Office.Tools.Word.Document> arabirimi, çözümünüzü sonraki çalışma zamanı sürümü ile çalışmaya. Çözümünüzü kullanmıyorsa <xref:Microsoft.Office.Tools.Word.Document> çözümünüzü sonraki çalışma zamanı sürümü ile artık çalışmayacak sonra katıştırılmış bir tür olarak arabirim.  
  
 Varsayılan olarak, tür denkliği özelliği etkinleştirilmişse, bu hedefleyen Office proje oluşturduğunuzda değil [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Bu özelliği etkinleştirmek istiyorsanız, **birlikte çalışma türlerini katıştır** özelliği projenize aşağıdaki derleme başvurularını hiçbirinin **True**:  
  
-   Microsoft.Office.Tools.dll  
  
-   Microsoft.Office.Tools.Common.dll  
  
-   Microsoft.Office.Tools.Excel.dll  
  
-   Microsoft.Office.Tools.Outlook.dll  
  
-   Microsoft.Office.Tools.Word.dll  
  
 Bu değişikliği yaptıktan sonra, projeyi oluşturduğunuzda, proje tarafından kullanılan tüm çalışma zamanı türlerine ilişkin tür bilgileri çözüm derlemesine eklenir. Çalışma zamanında çözüm tarafından başvurulan derlemeleri türü bilgileri yerine bu katıştırılmış tür bilgileri kullanılır.  
  
##  <a name="UnmanagedLoader"></a> Office çözüm yükleyicisi anlama  
 Office çalışma zamanı için Visual Studio Araçları çalışma zamanı ve Office çözümleri yüklemek için Office uygulamalarını kullanmaktadır bazı yönetilmeyen DLL dosyaları içerir. Hiçbir zaman bu DLL'ler ile doğrudan çalışmanız gerekmese de, bu DLL'lerin amaçlarını bilmeniz, Office çözümlerinin mimarisini daha iyi anlamanıza yardımcı olabilir.  
  
 Bu bileşenler yükleme işlemi sırasında nasıl kullanıldığı konusunda daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
### <a name="vstoeedll"></a>VSTOEE.dll  
 Bir kullanıcı bir belge düzeyi özelleştirme açar veya bir VSTO eklenti başlatıldığında, Office uygulamasının içine çağırır *VSTOEE.dll* yüklemek için gerekli görevleri gerçekleştirmek için [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
 *VSTOEE.dll* emin olun doğru sürümü [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] çözümü ve Office yüklü olan sürümü yüklenir. Ancak birden fazla sürümünü [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yalnızca bir örneği aynı bilgisayarda yüklü *VSTOEE.dll* aynı anda yüklenir. Bu *VSTOEE.dll* , bilgisayarda yüklü çalışma zamanı en son sürümü ile birlikte. Farklı sürümleri hakkında daha fazla bilgi için [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] , diğer çözümleri için kullanılabilmesi için bkz: [çözümleri Microsoft Office'in farklı sürümlerinde çalıştırma](../vsto/running-solutions-in-different-versions-of-microsoft-office.md).  
  
### <a name="vstoloaderdll"></a>VSTOLoader.dll  
 Sonra *VSTOEE.dll* uygun sürümünü yükler [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], *VSTOLoader.dll* çözümü derleme yükleme için gereken işlerin çoğunu gerçekleştirir. *VSTOLoader.dll* birkaç şey yapar:  
  
-   Her bir çözüm derlemesi için uygulama etki alanı oluşturur.  
  
-   Çözüm derlemesinin çalışma izni olduğunu doğrulamak için bir dizi güvenlik denetimi gerçekleştirir.  
  
-   Çözüm için gerekli .NET Framework için Office uzantıları sürümünü yükler.  
  
 *VSTOLoader.dll* de VSTO eklentileri için belirli birkaç şey yapar:  
  
-   Bunu uygulayan <xref:Extensibility.IDTExtensibility2> arabirimi. <xref:Extensibility.IDTExtensibility2> Tüm VSTO eklentileri Microsoft Office uygulamaları için uygulamalıdır bir COM arabirimidir. Bu arabirim uygulama çağırır ve VSTO eklentisi ile iletişim kurmak için yöntemleri tanımlar.  
  
-   Imanagedaddin arabirimi uygular. Bu arabirim, Office uygulamaları tarafından VSTO eklentileri yük yardımcı olmak için kullanılır. Daha fazla bilgi için bkz: [Imanagedaddin arabirimi](../vsto/imanagedaddin-interface.md).  
  
## <a name="understand-the-32-bit-and-64-bit-versions-of-the-runtime"></a>Çalışma zamanı 32-bit ve 64 bit sürümlerini anlama  
 Office çalışma zamanı için Visual Studio 2010 Araçları ayrı 64-bit ve 32-bit sürümü vardır. Çalışma zamanı'nın bu sürümlerini 64-bit ve 32-bit sürümlerinde Office çözümlerini çalıştırmak için kullanılır. Aşağıdaki tablo, çalışma zamanının hangi sürümünün her Windows ve Office birleşimi için gerekli olduğunu gösterir.  
  
|Windows sürümü|Microsoft Office sürümü|Office çalışma zamanı için Visual Studio Araçları'nın gerekli sürümü|  
|------------------------|---------------------------------|--------------------------------------------------------------------|  
|32 bit:|32 bit:|32 bit:|  
|64 bit|32 bit:|64 bit|  
|64 bit|64 bit|64 bit|  
  
 Office, gerekli sürümünü yüklediğinizde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Office ile birlikte yüklenir. Örneğin, yüklediğinizde Office 64-bit sürümü bir Windows, 64-bit sürümü 64-bit sürümü [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] de yüklenir. Yükleme hakkında daha fazla bilgi için [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Office ile bkz [Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).  
  
 Office'in 64 bit sürümü Visual Studio 2008'de 2007 Microsoft Office sistemi için proje şablonları kullanılarak oluşturulmuş Office çözümleri de çalıştırabilirsiniz. Ancak Visual Studio 2005 kullanılarak oluşturulan Office çözümlerini veya Visual Studio 2008'de Microsoft Office 2003 proje şablonları kullanılarak oluşturulan Office çözümlerini çalıştıramaz. Daha fazla bilgi için bkz: [çözümleri Microsoft Office'in farklı sürümlerinde çalıştırma](../vsto/running-solutions-in-different-versions-of-microsoft-office.md).  
  
## <a name="repair-the-visual-studio-2010-tools-for-office-runtime"></a>Office çalışma zamanı için Visual Studio 2010 Araçları onarın  
 Çalışma zamanı onarmak gerekiyorsa, açık **programlar ve Özellikler** veya **Program Ekle veya Kaldır** Denetim Masası'nda seçin **için Microsoft Visual Studio 2010 Araçları Office çalışma zamanı**programları ve ardından listesinde **kaldırma**. Çalıştırılan kurulum programı çalışma zamanını onarmanızı sağlar. Tıklatırsanız **değişiklik**, çalışma zamanı onarmak için bir seçenek verilmez.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)   
 [Office çalışma zamanı için Visual Studio araçlarındaki derlemeler](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)   
 [Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Yükseltme ve Office çözümleri geçirme](../vsto/upgrading-and-migrating-office-solutions.md)  
  
  