---
title: "Office çalışma zamanı için Visual Studio araçlarında derlemeler | Microsoft Docs"
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
helpviewer_keywords: Visual Studio Tools for Office runtime, assemblies
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 22750553e714c0aa02577ee95753e7d5b2bf13f4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="assemblies-in-the-visual-studio-tools-for-office-runtime"></a>Office Çalışma Zamanı İçin Visual Studio Araçlarındaki Derlemeler
  Bir Office proje oluşturduğunuzda, Visual Studio başvuruları otomatik olarak ekler. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] proje türü ve hedef .NET Framework projenin için kullanılan derlemeler. .NET Framework 3.5 için Office uzantılarında farklı derlemeler vardır [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], ve [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Office uzantıları hakkında daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
## <a name="assemblies-in-the-office-extensions-for-the-net-framework-4-and-the-includenetv45vstoincludesnet-v45-mdmd"></a>.NET Framework 4 için Office uzantılarında derlemeler ve[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
 Aşağıdaki tabloda için Office uzantılarında dahil olan derlemeleri listeler [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ve [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Ad alanları ve bu derlemeler türlerinde ilgili belgeler için bkz: [yönetilen başvuru &#40; Visual Studio &#41; Office geliştirme](../vsto/managed-reference-office-development-in-visual-studio.md).  
  
|Derleme adı|Açıklama|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Şerit özelleştirmelerini ve akıllı etiketleri oluşturmak için türleri. **Not:** akıllı etiketler de kullanım dışı [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] ve [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].<br />-Eylemler bölmeleri belge düzeyi özelleştirmeleri ve özel görev bölmeleri içinde VSTO eklentileri oluşturma türleri.|  
|Microsoft.Office.Tools.Excel.dll|Excel projeleri ve destekleyen türler için konak denetimlerinin ve konak öğelerinin temsil eden arabirimler sağlar. Daha fazla bilgi için bkz: [otomatikleştirme Excel genişletilmiş nesneleri kullanarak tarafından](../vsto/automating-excel-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.Outlook.dll|Outlook VSTO eklentileri özel form bölgeleri oluşturmak için kullanabileceğiniz türler sağlar.|  
|Microsoft.Office.Tools.Word.dll|Word projeleri ve destekleyen türler için konak denetimlerinin ve konak öğelerinin temsil eden arabirimler sağlar. Daha fazla bilgi için bkz: [genişletilmiş nesneleri kullanarak Word otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.v4.0.Framework.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Office çalışma zamanı için Visual Studio Araçları tarafından oluşturulan özel durumlar.<br />-Form bölgeleri Outlook oluştururken kullanabileceğiniz öznitelikler.|  
|Microsoft.Office.Tools.dll|Office çalışma zamanı altyapısı için Visual Studio Araçları'nın parçası olan ve doğrudan kodunuzdan kullanılmaya yönelik değildir türler sağlar.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.dll|Aşağıdaki türlerini sağlar:<br /><br /> - <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> Özniteliği ve <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> belge düzeyi özelleştirmelerinde veri nesneleri önbelleğe almak için kullanabileceğiniz arabirimi. Daha fazla bilgi için bkz: [veri önbelleğe alma](../vsto/caching-data.md).<br />- <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> Office çözümü ClickOnce yükleyicisinin son adımı olarak ek yükleme adımlarını çalıştırmak için uygulayabileceğiniz arabirimi. Daha fazla bilgi için bkz: [tarafından ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).<br />-Office çalışma zamanı için Visual Studio Araçları tarafından oluşturulan özel durumlar.<br />-Office çalışma zamanı altyapısı için Visual Studio Araçları'nın parçası olan ve doğrudan kodunuzdan kullanılmaya yönelik değildir diğer türleri.|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll|Aşağıdaki türlerini sağlar:<br /><br /> - <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> Belgelere özelleştirilmiş derlemeleri iliştirmek ve belgelerdeki önbelleğe alınmış verilere erişmek için kullanabileceğiniz sınıfı. Daha fazla bilgi için bkz: [ServerDocument sınıfını kullanarak sunucu üzerinde belgeleri yönetme](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-Belge düzeyi özelleştirmelerinde veri hiyerarşisini temsil eden çeşitli sınıflar önbelleğe. Daha fazla bilgi için bkz: [sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md).|  
  
 Hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] aşağıdaki derlemelere de başvurur. Bu derlemeler olmayan parçası [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yeniden dağıtılabilir. Bunun yerine, çözümünüz ile dağıtılmalıdır bağımlı derlemeleri oldukları. Varsayılan olarak, projeniz için yapı çıktı klasörüne kopyalanırlar ( **kopya yerel** özelliği bu derlemeler için ayarlanmış **True**). Projenizi ClickOnce kullanarak dağıtırsanız, bu derlemeler oluşturulan pakete dahil edilir.  
  
|Derleme adı|Açıklama|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v4.0.Utilities.dll|Temel sınıflar için oluşturulan sağlar `ThisAddIn` sınıfı VSTO eklenti projeleri ve tüm projelerde oluşturulan Şerit sınıfı.|  
|Microsoft.Office.Tools.Excel.v4.0.Utilities.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Temel sınıflar için oluşturulan `ThisWorkbook` ve `Sheet` sınıflarda belge düzeyi projelerine Excel için.<br />-Excel projeleri çalışma sayfalarında kullanabileceğinizi Windows Forms denetimleri.|  
|Microsoft.Office.Tools.Outlook.v4.0.Utilities.dll|Temel sınıflar için oluşturulan sağlar `ThisAddIn` ve form bölgesi sınıflarını Outlook projeleri.|  
|Microsoft.Office.Tools.Word.v4.0.Utilities.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Temel sınıflar için oluşturulan `ThisDocument` Word için belge düzeyi projelerine sınıfı.<br />-Word projeleri belgelerinde kullanabileceğinizi Windows Forms denetimleri.|  
  
## <a name="assemblies-in-the-office-extensions-for-the-net-framework-35"></a>.NET Framework 3.5 için Office uzantılarında derlemeler  
 Aşağıdaki tabloda, .NET Framework 3.5 için Office uzantılarında bulunan derlemeleri listeler. Ad alanları ve bu derlemeler sınıflarda ilgili belgeler için Visual Studio 2008 belgelerinde şu bölüme bakın: [http://go.microsoft.com/fwlink/?LinkId=160658](http://go.microsoft.com/fwlink/?LinkId=160658).  
  
|Derleme adı|Açıklama|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v9.0.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Microsoft.Office.Tools.AddIn taban sınıfı için VSTO eklentileri.<br />-Şerit özelleştirmelerini ve akıllı etiketleri oluşturmak için sınıfları. **Not:** akıllı etiketler de kullanım dışı [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] ve [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].<br />-Eylemler bölmeleri belge düzeyi özelleştirmeleri ve özel görev bölmeleri içinde VSTO eklentileri oluşturma sınıflar.|  
|Microsoft.Office.Tools.Excel.v9.0.dll|Konak denetimlerinin ve konak öğelerinin Excel çözümleri sağlar. Daha fazla bilgi için bkz: [otomatikleştirme Excel genişletilmiş nesneleri kullanarak tarafından](../vsto/automating-excel-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.Outlook.v9.0.dll|Outlook VSTO eklentileri özel form bölgeleri oluşturmak için kullanabileceğiniz sınıflar sağlar.|  
|Microsoft.Office.Tools.Word.v9.0.dll|Konak denetimlerinin ve konak öğelerinin Word çözümleri sağlar. Daha fazla bilgi için bkz: [genişletilmiş nesneleri kullanarak Word otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.v9.0.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Veri bağlama özellikleri için belge düzeyi özelleştirmelerindeki konak kontrolleri sağlar Microsoft.VisualStudio.Tools.Office.RemoteBindableComponent sınıfı.<br />-Office çalışma zamanı altyapısı için Visual Studio Araçları'nın parçası olan ve doğrudan kodunuzdan kullanılmaya yönelik değildir diğer türleri.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v9.0.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute özniteliği ve belge düzeyi özelleştirmelerinde veri nesneleri önbelleğe almak için kullanabileceğiniz Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType arabirimi. Daha fazla bilgi için bkz: [veri önbelleğe alma](../vsto/caching-data.md).<br />-Office çalışma zamanı için Visual Studio Araçları tarafından oluşturulan özel durumlar.<br />-Office çalışma zamanı altyapısı için Visual Studio Araçları'nın parçası olan ve doğrudan kodunuzdan kullanılmaya yönelik değildir diğer türleri.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v10.0.dll|Office Çözümünü ClickOnce yükleyicisinin son adımı olarak ek yükleme adımlarını çalıştırmak için uygulayabileceğiniz Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction arabirim sağlar. Daha fazla bilgi için bkz: [Gelişmiş Office çözümü dağıtımında](http://msdn.microsoft.com/en-us/9147b6f6-849f-4cb1-b2c5-e22658d74b02).|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.v10.0.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Özelleştirme derlemeleri belgelere program aracılığıyla iliştirmek ve belgelerdeki önbelleğe alınmış verilere erişmek için kullanabileceğiniz Microsoft.VisualStudio.Tools.Applications.ServerDocument'a sınıfı. Daha fazla bilgi için bkz: [ServerDocument sınıfını kullanarak sunucu üzerinde belgeleri yönetme](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-Belge düzeyi özelleştirmelerinde veri hiyerarşisini temsil eden çeşitli sınıflar önbelleğe. Daha fazla bilgi için bkz: [sunucudaki belgelerde verilere erişme](../vsto/accessing-data-in-documents-on-the-server.md).|  
|Microsoft.VisualStudio.Tools.Office.Runtime.v10.0.dll|Aşağıdaki türlerini sağlar:<br /><br /> -Kullanıcı ekleme Office güven vermek için Liste girişlerini oluşturmak için kullanabileceğiniz Microsoft.VisualStudio.Tools.Office.Runtime.Security.AddInSecurityEntry ve Microsoft.VisualStudio.Tools.Office.Runtime.Security.UserInclusionList sınıfları .NET Framework 3.5 hedefleyen çözümler.<br />-Office çalışma zamanı altyapısı için Visual Studio Araçları'nın parçası olan ve doğrudan kodunuzdan kullanılmaya yönelik değildir diğer türleri.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Office Çalışma Zamanı Yükleme Senaryoları için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)  
  
  