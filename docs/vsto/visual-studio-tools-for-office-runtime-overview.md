---
title: "Office çalışma zamanı genel bakış için Visual Studio Araçları | Microsoft Docs"
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
ms.assetid: 5526a4d2-a61c-43ee-8349-dd1968e0cdb4
caps.latest.revision: "92"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 61fe29fca2feb0f19e613af62f4d9407b8d8bbff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-tools-for-office-runtime-overview"></a>Office Çalışma Zamanı İçin Visual Studio Araçlarına Genel Bakış
  Visual Studio'da Microsoft Office geliştirici araçları kullanılarak oluşturulan çözümleri çalıştırmak için Office çalışma zamanı için Visual Studio 2010 Araçları son kullanıcı bilgisayarlarında yüklenmesi gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Office çalışma zamanı yeniden dağıtılabilir için Visual Studio Araçları yükleme](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md). Office Çalışma Zamanı için Visual Studio 2010 Araçları iki ana bileşenden oluşur:  
  
-   .NET Framework için Office uzantıları. Bu bileşenler, çözümünüz ile Microsoft Office uygulaması arasındaki iletişim katmanını sağlayan yönetilen derlemelerdir. Daha fazla bilgi için bkz: [.NET Framework için Office uzantıları anlama](#officeextensions).  
  
-   Office çözüm yükleyicisi. Bu bileşen, Office uygulamalarının çalışma zamanını ve çözümlerinizi yüklemek için kullandığı bir yönetilmeyen DLL'ler kümesidir. Daha fazla bilgi için bkz: [Office çözüm yükleyicisi anlama](#UnmanagedLoader).  
  
 Çalışma zamanı birkaç farklı yolla yüklenebilir. Bilgisayarın yapılandırmasına bağlı olarak, çalışma zamanını yüklediğinizde farklı çalışma zamanı bileşenlerinin yüklemesi gerçekleşir. Daha fazla bilgi için bkz: [Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).  
  
##  <a name="officeextensions"></a>.NET Framework için Office uzantıları anlama  
 Office çalışma zamanı için Visual Studio 2010 Araçları, .NET Framework 3.5 için Office uzantıları içeren [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ve daha sonra. Her bir .NET Framework sürümünü hedefleyen çözümler, ilgili sürüm için uygun uzantıları kullanır.  
  
 Bu uzantılar, çözümlerinizin Office uygulamalarını otomatikleştirmek ve genişletmek için kullandığı derlemelerden oluşur. Bir Office projesi oluşturduğunuzda, Visual Studio projenin .NET Framework hedefi ve proje türü için kullanılan derlemelerin başvurularını otomatik olarak ekler. Office uzantılarında derlemeler hakkında daha fazla bilgi için bkz: [Office çalışma zamanı için Visual Studio araçlarında derlemeler](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md).  
  
### <a name="design-differences-in-the-office-extensions"></a>Office Uzantılarındaki Tasarım Farkları  
 .NET Framework 3.5 için Office uzantılarında kullandığınız türlerin çoğu sınıflardır. Bunlar önceki sürümlerinde bulunan, aynı sınıflarıdır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Buna karşılık, Office uzantıları için kullandığınız türlerinin çoğu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya arabirimleri sonraki. Hedeflediğinizde Örneğin, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümlerde, <xref:Microsoft.Office.Tools.Excel.Worksheet> ve <xref:Microsoft.Office.Tools.Word.Document> sınıfları yerine arabirimleri türleridir.  
  
 .NET Framework 3.5 çözümünüzü hedefleyen çoğu durumda, Office çözümlerinde yazdığınız kodları aynı olup veya [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Ancak belirli özellikler, .NET Framework'ün farklı sürümlerini hedeflediğinizde farklı kod gerektirir. Daha fazla bilgi için bkz: [geçirme Office çözümlerini .NET Framework 4 veya sonraki bir sürüme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
### <a name="interfaces-in-the-office-extensions-for-the-net-framework-4-or-later"></a>.NET Framework 4 veya sonraki Office uzantılarında arabirimleri  
 Arabirimler için Office uzantılarında çoğu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra kullanıcı kodu tarafından gerçekleştirilen amaçlanmamıştır. Doğrudan uygulayabilirsiniz yalnızca arabirimleri harfiyle başlayan adlara sahip **ı**, gibi <xref:Microsoft.Office.Tools.Excel.ISmartTagExtension>.  
  
 Harf olmayan tüm arabirimler **ı** Office çalışma zamanı ve bu arabirimleri gelecek sürümlerde değişebilir için Visual Studio 2010 araçları tarafından dahili olarak uygulanır. Bu arabirimleri uygulayan nesneler oluşturmak için projenize Globals.Factory nesne tarafından sağlanan yöntemleri kullanın. Örneğin, uygulayan bir nesne almak için <xref:Microsoft.Office.Tools.Excel.SmartTag> arabirim, Globals.Factory.CreateSmartTag yöntemi kullanın. Globals.Factory hakkında daha fazla bilgi için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
### <a name="enabling-type-equivalence-and-embedded-types-in-projects-that-target-the-net-framework-4-or-later"></a>Tür Eşdeğerliği ve katıştırılmış türlerinde .NET Framework 4 veya sonrasını hedefleyen projeler etkinleştirme  
 Çünkü için Office uzantıları nesne modelini [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bağlı arabirimlerde tür bilgilerini katıştırma hem Visual C# ve Visual Basic Visual Studio'da türü eşdeğer özelliğini kullanabilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] çözümünüze . Bu özellik Office çözümleri sağlar ve [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] birbirinden sürümüne. Çözümünüzü kullanıyorsa, örneğin, <xref:Microsoft.Office.Tools.Word.Document> arabirimi katıştırılmış türünün ve sonraki sürüm çalışma zamanına ekler üyelerine <xref:Microsoft.Office.Tools.Word.Document> arabirimi, çözümünüzü sonraki çalışma zamanı sürümü ile çalışmaya. Çözümünüzü kullanmıyorsa <xref:Microsoft.Office.Tools.Word.Document> çözümünüzü sonraki çalışma zamanı sürümü ile artık çalışmayacak sonra katıştırılmış bir tür olarak arabirim.  
  
 Varsayılan olarak, tür denkliği özelliği etkinleştirilmişse, bu hedefleyen Office proje oluşturduğunuzda değil [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Bu özelliği etkinleştirmek istiyorsanız, **birlikte çalışma türlerini katıştır** özelliği projenize aşağıdaki derleme başvurularını hiçbirinin **True**:  
  
-   Microsoft.Office.Tools.dll  
  
-   Microsoft.Office.Tools.Common.dll  
  
-   Microsoft.Office.Tools.Excel.dll  
  
-   Microsoft.Office.Tools.Outlook.dll  
  
-   Microsoft.Office.Tools.Word.dll  
  
 Bu değişikliği yaptıktan sonra, projeyi oluşturduğunuzda, proje tarafından kullanılan tüm çalışma zamanı türlerine ilişkin tür bilgileri çözüm derlemesine eklenir. Çözüm, başvurulan derlemelerdeki bilgi türü yerine, bu katıştırılmış bilgi türünü çalışma zamanında kullanılır.  
  
##  <a name="UnmanagedLoader"></a>Office çözüm yükleyicisi anlama  
 Office çalışma zamanı için Visual Studio Araçları çalışma zamanı ve Office çözümleri yüklemek için Office uygulamalarını kullanmaktadır bazı yönetilmeyen DLL dosyaları içerir. Hiçbir zaman bu DLL'ler ile doğrudan çalışmanız gerekmese de, bu DLL'lerin amaçlarını bilmeniz, Office çözümlerinin mimarisini daha iyi anlamanıza yardımcı olabilir.  
  
 Bu bileşenler yükleme işlemi sırasında nasıl kullanıldığı konusunda daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
### <a name="vstoeedll"></a>VSTOEE.dll  
 Bir kullanıcı bir belge düzeyi özelleştirme açar veya bir VSTO eklenti başlatıldığında, Office uygulama yüklemek için gerekli görevleri gerçekleştirmek için VSTOEE.dll çağırır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
 VSTOEE.dll emin olur doğru sürümü [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] çözümü ve Office yüklü olan sürümü yüklenir. Ancak birden fazla sürümünü [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yüklenebilir aynı bilgisayarda aynı anda yalnızca bir örneği VSTOEE.dll yüklenir. Bu örnek de, bilgisayarda yüklü çalışma zamanının en sürümünde yer alan VSTOEE.dll örneğidir. Farklı sürümleri hakkında daha fazla bilgi için [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] , diğer çözümleri için kullanılabilmesi için bkz: [farklı sürümleri, Microsoft Office çözümleri çalıştıran](../vsto/running-solutions-in-different-versions-of-microsoft-office.md).  
  
### <a name="vstoloaderdll"></a>VSTOLoader.dll  
 Uygun sürümünü VSTOEE.dll yüklendikten sonra [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], VSTOLoader.dll çözümü derleme yükleme için gereken işlerin çoğunu gerçekleştirir. VSTOLoader.dll çeşitli işlemler yapar:  
  
-   Her bir çözüm derlemesi için uygulama etki alanı oluşturur.  
  
-   Çözüm derlemesinin çalışma izni olduğunu doğrulamak için bir dizi güvenlik denetimi gerçekleştirir.  
  
-   Çözüm için gerekli .NET Framework için Office uzantıları sürümünü yükler.  
  
 VSTOLoader.dll ayrıca VSTO eklentileri için belirli birkaç şey yapar:  
  
-   Bunu uygulayan <xref:Extensibility.IDTExtensibility2> arabirimi. <xref:Extensibility.IDTExtensibility2>Tüm VSTO eklentileri Microsoft Office uygulamaları için uygulamalıdır bir COM arabirimidir. Bu arabirim uygulama çağırır ve VSTO eklentisi ile iletişim kurmak için yöntemleri tanımlar.  
  
-   Imanagedaddin arabirimi uygular. Bu arabirim, Office uygulamaları tarafından VSTO eklentileri yük yardımcı olmak için kullanılır. Daha fazla bilgi için bkz: [Imanagedaddin arabirimi](../vsto/imanagedaddin-interface.md).  
  
## <a name="understanding-the-32-bit-and-64-bit-versions-of-the-runtime"></a>Çalışma Zamanının 32 bit ve 64 bit Sürümlerini Anlama  
 Office Çalışma Zamanı için Visual Studio 2010 Araçları'nın ayrı 64 bit ve 32 bit sürümleri vardır. Çalışma zamanı'nın bu sürümlerini 64-bit ve 32-bit sürümlerinde Office çözümlerini çalıştırmak için kullanılır. Aşağıdaki tablo, çalışma zamanının hangi sürümünün her Windows ve Office birleşimi için gerekli olduğunu gösterir.  
  
|Windows sürümü|Microsoft Office sürümü|Office çalışma zamanı için Visual Studio Araçları'nın gerekli sürümü|  
|------------------------|---------------------------------|--------------------------------------------------------------------|  
|32 bit:|32 bit:|32 bit:|  
|64 bit|32 bit:|64 bit|  
|64 bit|64 bit|64 bit|  
  
 Office, gerekli sürümünü yüklediğinizde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Office ile birlikte yüklenir. Örneğin, yüklediğinizde Office 64-bit sürümü bir Windows, 64-bit sürümü 64-bit sürümü [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] de yüklenir. Yükleme hakkında daha fazla bilgi için [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Office ile bkz [Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).  
  
 Office'in 64 bit sürümü Visual Studio 2008'de 2007 Microsoft Office sistemi için proje şablonları kullanılarak oluşturulmuş Office çözümleri de çalıştırabilirsiniz. Ancak Visual Studio 2005 kullanılarak oluşturulan Office çözümlerini veya Visual Studio 2008'de Microsoft Office 2003 proje şablonları kullanılarak oluşturulan Office çözümlerini çalıştıramaz. Daha fazla bilgi için bkz: [farklı sürümleri, Microsoft Office çözümleri çalıştıran](../vsto/running-solutions-in-different-versions-of-microsoft-office.md).  
  
## <a name="repairing-the-visual-studio-2010-tools-for-office-runtime"></a>Office Çalışma Zamanı için Microsoft Visual Studio 2010 Araçlarını Onarma  
 Çalışma zamanı onarmak gerekiyorsa, açık **programlar ve Özellikler** veya **Program Ekle veya Kaldır** Denetim Masası'nda seçin **için Microsoft Visual Studio 2010 Araçları Office çalışma zamanı**programları ve ardından listesinde **kaldırma**. Çalıştırılan kurulum programı çalışma zamanını onarmanızı sağlar. Tıklatırsanız **değişiklik**, çalışma zamanı onarmak için bir seçenek verilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çalışma zamanı yükleme senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)   
 [Office çalışma zamanı için Visual Studio araçlarındaki derlemeler](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)   
 [Visual Studio'da Office çözümleri mimarisi](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Yükseltme ve Office çözümleri geçirme](../vsto/upgrading-and-migrating-office-solutions.md)  
  
  