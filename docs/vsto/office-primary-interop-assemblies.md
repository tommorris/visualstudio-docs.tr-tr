---
title: Office birincil birlikte çalışma derlemeleri | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies
- assemblies [Office development in Visual Studio], primary interop assemblies
- Office primary interop assemblies
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2ab565dfbc4fec21c646aa72b54f3694d99e6a1f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="office-primary-interop-assemblies"></a>Office Birincil Birlikte Çalışma Derlemeleri
  Bir Microsoft Office uygulamasından bir Office proje özelliklerini kullanmak için uygulama için birincil birlikte çalışma derlemesi (PIA) kullanmanız gerekir. PIA bir Microsoft Office uygulamasının COM tabanlı nesne modeli ile etkileşim kurmak yönetilen kod sağlar.  
  
 Yeni bir Office proje oluşturduğunuzda, Visual Studio projesi oluşturmak için gerekli PIA başvuruları ekler. Bazı senaryolarda (örneğin, Microsoft Office Excel için Microsoft Office Word'ün özellik projesinde kullanmak istiyorsanız) ek PIA başvuruları eklemeniz gerekebilir.  
  
 Bu konu, aşağıdaki Microsoft Office PIA Office projelerinde kullanma yönlerini açıklar:  
  
-   [Oluşturma ve çalıştırma projeler için ayrı birincil birlikte çalışma derlemeleri](#separateassemblies)  
  
-   [Tek bir projede birden çok Microsoft Office uygulamaları özelliklerini kullanma](#usingfeatures)  
  
-   [Microsoft Office uygulamaları için birincil birlikte çalışma derlemeleri tam listesi](#pialist)  
  
 Birincil birlikte çalışma derlemeleri hakkında daha fazla bilgi için bkz: [birincil birlikte çalışma derlemeleri](http://msdn.microsoft.com/en-us/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
##  <a name="separateassemblies"></a> Birincil birlikte çalışma derlemeleri oluşturma ve çalıştırma projeler için ayrı  
 Visual Studio geliştirme bilgisayarınızda PIA farklı kümesi kullanır. Derlemelerin farklı bu kümeleri aşağıdaki konumlarda bulunur:  
  
-   Program files dizini klasöründe.  
  
     Kod yazma ve projeler derlemek derlemeler bu kopyalarını kullanılır. Visual Studio bu derlemeler otomatik olarak yükler.  
  
-   Genel Derleme Önbelleği.  
  
     Bu derlemeler kopyalarını çalıştırmak veya projeleri hata ayıklama gibi bazı geliştirme görevler sırasında kullanılır. Visual Studio değil yükleyin ve bu derlemeler kaydedin; bunu kendiniz yapmanız gerekir.  
  
### <a name="primary-interop-assemblies-in-the-program-files-directory"></a>Program dosyaları içindeki birincil birlikte çalışma derlemeleri  
 Visual Studio yüklediğinizde PIA Genel Derleme Önbelleği dışında dosya sistemindeki bir konuma otomatik olarak yüklenir. Yeni bir proje oluşturduğunuzda, Visual Studio bu kopyalarını PIA başvuruları projenize otomatik olarak ekler. Visual Studio geliştirme ve projenizi derlediğinizde tür başvuruları çözümlemek için genel derleme önbelleğinde derlemeleri yerine bu PIA kopyalarını kullanır.  
  
 PIA bu kopyalarını PIA farklı sürümlerini genel derleme önbelleğinde kaydolurken oluşabilecek çeşitli geliştirme sorunlarını önlemek Visual Studio yardımcı olur.  
  
 Visual Studio geliştirme bilgisayarında aşağıdaki konumlara PIA bu kopyasını yükler:  
  
-   %ProgramFiles%\Microsoft visual Studio 12.0\Visual Studio Office\PIA\Office14 için Araçlar  
  
     (veya % ProgramFiles (x86) %\Microsoft Visual Studio 12.0\Visual Studio Tools for Office\PIA\Office14 64-bit işletim sistemlerinde)  
  
-   %ProgramFiles%\Microsoft visual Studio 12.0\Visual Studio Office\PIA\Office15 için Araçlar  
  
     (veya % ProgramFiles (x86) %\Microsoft Visual Studio 12.0\Visual Studio Tools for Office\PIA\Office15 64-bit işletim sistemlerinde)  
  
### <a name="primary-interop-assemblies-in-the-global-assembly-cache"></a>Genel derleme önbelleğinde birincil birlikte çalışma derlemeleri  
 Belirli geliştirme görevleri gerçekleştirmek için PIA yüklü ve geliştirme bilgisayarındaki genel derleme önbelleğinde kaydedilmesi gerekir. Genellikle, geliştirme bilgisayarınızda Office yüklediğinizde PIA otomatik olarak yüklenir. Daha fazla bilgi edinmek için bkz. [Bir Bilgisayarı Office Çözümleri Geliştirmek Üzere Yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
 Office PIA son kullanıcı bilgisayarlarında Office çözümlerini çalıştırmak için gerekli değildir. Daha fazla bilgi için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
##  <a name="usingfeatures"></a> Tek bir projede birden çok Microsoft Office uygulamaları özelliklerini kullanma  
 Visual Studio içindeki her Office proje şablonu, tek bir Microsoft Office uygulaması ile çalışmak üzere tasarlanmıştır. Birden çok Microsoft Office uygulamalarında özelliklerini kullanmak ya da bir uygulama ya da Visual Studio Proje yok bileşeni özellikleri kullanmak için gerekli PIA bir başvuru eklemeniz gerekir.  
  
 Çoğu durumda, Visual Studio tarafından %ProgramFiles%\Microsoft Visual Studio 12.0\Visual Studio Araçları Office\PIA\ dizini altında yüklü olan PIA başvuruları eklemeniz gerekir. Derlemeleri'nın bu sürümlerini görünür **Framework** sekmesinde **başvuru Yöneticisi** iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: hedef Office uygulamaları aracılığıyla birincil birlikte çalışma derlemeleri](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md).  
  
 Derlemeleri'nın bu sürümlerini yüklediyseniz ve Genel Derleme Önbelleği'nde PIA kayıtlı görünür **COM** sekmesinde **başvuru Yöneticisi** iletişim kutusu. Bunları kullandığınızda oluşabilecek bazı geliştirme sorunları olduğundan derlemeleri'nın bu sürümlerini başvuruları ekleme kaçınmalısınız. Genel derleme önbelleğinde PIA farklı sürümlerini kaydolduysanız, örneğin, projenize otomatik olarak en son kaydedilen derleme sürüme bağlayacaksınız — üzerinde derlemenin farklı bir sürüm belirtin olsa bile  **COM** sekmesinde **başvuru Yöneticisi** iletişim kutusu.  
  
> [!NOTE]  
>  Bunları başvuruda bulunan bir derleme eklendiğinde bazı derlemeleri projeye otomatik olarak eklenir. Örneğin, Word, Excel, Outlook, Microsoft Forms veya grafik derlemeleri başvuru eklediğinizde Office.dll ve Microsoft.Vbe.Interop.dll derlemelerine başvurular otomatik olarak eklenir.  
  
##  <a name="pialist"></a> Microsoft Office uygulamaları için birincil birlikte çalışma derlemeleri  
 Aşağıdaki tabloda kullanılabilir birincil birlikte çalışma derlemeleri listeler [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] ve [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)].  
  
|Office uygulaması veya bileşeni|Birincil birlikte çalışma derleme adı|  
|-------------------------------------|-----------------------------------|  
|Microsoft Access 14.0 Nesne Kitaplığı<br /><br /> Microsoft Access 15.0 Nesne Kitaplığı|Microsoft.Office.Interop.Access.dll|  
|Microsoft Office 14.0 Access veritabanı altyapısı Nesne Kitaplığı<br /><br /> Microsoft Office 15.0 Access veritabanı altyapısı Nesne Kitaplığı|Microsoft.Office.Interop.Access.Dao.dll|  
|Microsoft Excel 14.0 Nesne Kitaplığı<br /><br /> Microsoft Excel 15.0 Nesne Kitaplığı|Microsoft.Office.Interop.Excel.dll|  
|Microsoft Graph 14.0 Nesne Kitaplığı (grafiklerde PowerPoint, erişim ve Word tarafından kullanılır)<br /><br /> Microsoft Graph 15.0 Nesne Kitaplığı|Microsoft.Office.Interop.Graph.dll|  
|Microsoft InfoPath 2.0 tür kitaplığı (yalnızca InfoPath 2007)|Microsoft.Office.Interop.InfoPath.dll|  
|Microsoft InfoPath XML birlikte çalışma derlemesi (yalnızca InfoPath 2007)|Microsoft.Office.Interop.InfoPath.Xml.dll|  
|Microsoft Office 14.0 Nesne Kitaplığı (Paylaşılan Office işlevselliği)<br /><br /> Microsoft Office 15.0 Nesne Kitaplığı (Paylaşılan Office işlevselliği)|Office.dll|  
|Microsoft Office Outlook Görünüm Denetimi (Web sayfaları ve uygulamaları kutunuza erişmek için kullanılabilir)|Microsoft.Office.Interop.OutlookViewCtl.dll|  
|Microsoft Outlook 14.0 Nesne Kitaplığı<br /><br /> Microsoft Outlook 15.0 Nesne Kitaplığı|Microsoft.Office.Interop.Outlook.dll|  
|Microsoft PowerPoint 14.0 Nesne Kitaplığı<br /><br /> Microsoft PowerPoint 15.0 Nesne Kitaplığı|Microsoft.Office.Interop.PowerPoint.dll|  
|Microsoft Project 14.0 Nesne Kitaplığı<br /><br /> Microsoft Project 15.0 Nesne Kitaplığı|Microsoft.Office.Interop.MSProject.dll|  
|Microsoft Publisher 14.0 Nesne Kitaplığı<br /><br /> Microsoft Publisher 15.0 Nesne Kitaplığı|Microsoft.Office.Interop.Publisher.dll|  
|Microsoft SharePoint Designer 14.0 Web nesne başvurusu kitaplığı|Microsoft.Office.Interop.SharePointDesigner.dll|  
|Microsoft SharePoint Designer 14.0 sayfa nesne başvurusu kitaplığı|Microsoft.Office.Interop.SharePointDesignerPage.dll|  
|Microsoft Akıllı etiketleri 2.0 tür kitaplığı **Not:** akıllı etiketler de kullanım dışı [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] ve [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].|Microsoft.Office.Interop.SmartTag.dll|  
|Microsoft Visio 14.0 tür kitaplığı<br /><br /> Microsoft Visio 15.0 tür kitaplığı|Microsoft.Office.Interop.Visio.dll|  
|Microsoft Visio 14.0 Web türü kitaplık olarak Kaydet<br /><br /> Microsoft Visio 15.0 Web türü kitaplık olarak Kaydet|Microsoft.Office.Interop.Visio.SaveAsWeb.dll|  
|Microsoft Visio 14.0 çizim denetim tür kitaplığı<br /><br /> Microsoft Visio 15.0 çizim denetim tür kitaplığı|Microsoft.Office.Interop.VisOcx.dll|  
|Microsoft Word'ün 14.0 Nesne Kitaplığı<br /><br /> Microsoft Word'ün 15.0 Nesne Kitaplığı|Microsoft.Office.Interop.Word.dll|  
|Microsoft Visual Basic for Applications genişletilebilirliği 5.3|Microsoft.Vbe.Interop.dll|  
  
### <a name="binding-redirect-assemblies"></a>Bağlama yeniden yönlendirme derlemeler  
 Yüklediğinizde ve Genel Derleme Önbelleği (veya Office ile yeniden dağıtılabilir paketi için PIA yükleyerek) Office PIA kaydetmek bağlama yeniden yönlendirme derlemeleri genel derleme önbelleğinde da yüklenir. Bu derlemeler birincil birlikte çalışma derlemeleri doğru sürümü çalışma zamanında yüklenir sağlanmasına yardımcı olur. Örneğin, bir çözüm, başvurduğunda bir [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] derleme olan bir bilgisayarda çalışan [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] aynı birincil birlikte çalışma derlemesi sürümü, bağlama yeniden yönlendirme derleme bildirir [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] yüklemek için çalışma zamanı [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] birincil birlikte çalışma derlemesi sürümü. Daha fazla bilgi için bkz: [nasıl yapılır: etkinleştirme ve devre dışı bırakmak, bağlama otomatik yeniden yönlendirme](/dotnet/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: birincil birlikte çalışma derlemeleriyle Office uygulamalarını](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md)   
 [InfoPath çözümleri](../vsto/infopath-solutions.md)   
 [Outlook nesne modeline genel bakış](../vsto/outlook-object-model-overview.md)   
 [PowerPoint çözümleri](../vsto/powerpoint-solutions.md)   
 [Proje çözümleri](../vsto/project-solutions.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Genel başvuru &#40;Visual Studio'da Office geliştirme&#41;](../vsto/general-reference-office-development-in-visual-studio.md)  
  
  