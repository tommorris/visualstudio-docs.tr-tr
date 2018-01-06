---
title: "Excel çözümleri | Microsoft Docs"
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
- application-level add-ins [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], application-level add-ins
- Office solutions [Office development in Visual Studio], Excel
- solutions [Office development in Visual Studio], Excel
- add-ins [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], about Excel solutions
- Excel [Office development in Visual Studio]
- documents [Office development in Visual Studio], Excel
- Office documents [Office development in Visual Studio, Excel
- projects [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], document-level customizations
- user interfaces [Office development in Visual Studio], Excel
- Office development in Visual Studio, Excel solutions
- document-level customizations [Office development in Visual Studio], Excel
- Office projects [Office development in Visual Studio], Excel
ms.assetid: 34444d54-d7b6-479a-b5b7-a946267081e9
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f12823ecb3fdc8d90d9f7c3651c6e04e6b0f6635
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="excel-solutions"></a>Excel Çözümleri
  Visual Studio Proje şablonları Microsoft Office Excel için belge düzeyi özelleştirmeleri ve VSTO eklentileri oluşturmak için kullanabileceğiniz sağlar. Excel otomatikleştirmek, Excel özelliklerini genişletmek ve Excel kullanıcı arabirimini (UI) özelleştirmek için bu çözümleri kullanabilirsiniz. Belge düzeyi özelleştirmeleri ve VSTO eklentileri arasındaki farklar hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
 Bu konuda, aşağıdaki bilgiler sağlanmaktadır:  
  
-   [Excel'i otomatikleştirme](#automating).  
  
-   [Excel için belge düzeyi özelleştirmelerini geliştirme](#doclevel).  
  
-   [Excel için VSTO eklentileri geliştirme](#applevel).  
  
-   [Excel kullanıcı arabirimini özelleştirme](#UI).  
  
##  <a name="automating"></a>Excel'i otomatikleştirme  
 Excel nesne modeline Excel otomatikleştirmek için kullanabileceğiniz birçok türü ortaya çıkarır. Örneğin, program aracılığıyla grafik oluşturma, çalışma sayfaları biçimlendirmek ve aralıkları ve hücre değerlerini ayarlayın. Daha fazla bilgi için bkz: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
 Visual Studio'daki Excel çözümleri geliştirirken de kullanabilirsiniz *konak öğelerini* ve *konak denetimlerini* Çözümlerinizdeki. Excel nesne modeli, yaygın olarak kullanılan belirli nesneleri gibi genişletmek nesneleri bunlar <xref:Microsoft.Office.Interop.Excel.Worksheet> ve <xref:Microsoft.Office.Interop.Excel.Range> nesneleri. Genişletilmiş nesneler esas alan Excel nesneleri gibi davranır, ancak nesnelere ek olaylar ve veri bağlama özellikleri ekleyin. Daha fazla bilgi için bkz: [otomatikleştirme Excel genişletilmiş nesneleri kullanarak tarafından](../vsto/automating-excel-by-using-extended-objects.md).  
  
##  <a name="doclevel"></a>Excel için belge düzeyi özelleştirmelerini geliştirme  
 Microsoft Office Excel için belge düzeyi özelleştirme belirli bir çalışma kitabı ile ilişkili bir derlemeyi oluşur. Derleme, genellikle UI özelleştirerek ve Excel'i otomatikleştirme çalışma kitabını genişletir. Yalnızca ilişkili çalışma kitabını Excel'de açık olduğunda bir VSTO Excel ile ilişkili olan eklenti, özelleştirmesinde uygulamak işlevselliği kullanılabilir.  
  
 Excel için belge düzeyi özelleştirme projesi oluşturmak için Excel çalışma kitabı veya Excel Şablonu proje şablonlarını kullanın **yeni proje** Visual Studio'nun iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Belge düzeyi özelleştirmeleri çalışma hakkında daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md).  
  
### <a name="excel-customization-programming-model"></a>Excel özelleştirme programlama modeli  
 Excel için belge düzeyi projesi oluşturduğunuzda, Visual Studio çözümünüzü temelidir birkaç sınıfları oluşturur: `ThisWorkbook`, `Sheet1`, `Sheet2`, ve `Sheet3`. Bu sınıfların çözümünüzle birlikte ilişkili çalışma sayfaları ve çalışma kitabını temsil eder ve kodunuzu yazmak için bir başlangıç noktası sunar.  
  
 Bunlar hakkında daha fazla bilgi için oluşturulan sınıflar ve kullanabileceğiniz diğer özellikler bir belge düzeyi projede görmek [belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md).  
  
##  <a name="applevel"></a>Excel için VSTO eklentileri geliştirme  
 Microsoft Office Excel bir VSTO eklentisini Excel tarafından yüklenen bir derleme oluşur. Derleme, genellikle UI özelleştirerek ve Excel'i otomatikleştirme Excel genişletir. Belirli bir çalışma kitabı ile ilişkili olan bir belge düzeyi özelleştirme, bir VSTO eklenti uygulamak işlevsellik herhangi bir tek çalışma kitabına sınırlı değildir.  
  
 Excel için VSTO eklenti projesi oluşturmak için Excel çalışma kitabı veya Excel Şablonu proje şablonlarını kullanın **yeni proje** Visual Studio'nun iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 VSTO eklentileri nasıl çalıştığı hakkında genel bilgi için bkz: [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: otomatikleştirmek PowerPoint bir Excel eklenti?](http://go.microsoft.com/fwlink/?LinkID=130300).  
  
### <a name="excel-add-in-programming-model"></a>Excel eklenti programlama modeli  
 Excel VSTO eklenti projesindeki oluşturduğunuzda, Visual Studio adlı bir sınıf oluşturur `ThisAddIn`, çözümünüzün temeli. Bu sınıf, kodunuzu yazmak için bir başlangıç noktası sağlar ve Excel için VSTO eklentinizi nesne modelini de sunar.  
  
 Hakkında daha fazla bilgi için `ThisAddIn` sınıfı ve bir VSTO eklenti, kullanabileceğiniz diğer Visual Studio özellikler bkz [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
##  <a name="UI"></a>Excel kullanıcı arabirimini özelleştirme  
 Excel kullanıcı arabirimini özelleştirmek için birçok farklı yol vardır. Bazı seçenekler için tüm proje türleri kullanılabilir ve diğer seçenekleri yalnızca VSTO eklentileri ya da belge düzeyi özelleştirmeleri için kullanılabilir.  
  
### <a name="options-for-all-project-types"></a>Tüm proje türleri için seçenekleri  
 Belge düzeyi özelleştirmeleri ve VSTO eklentileri için kullanılabilir özelleştirme seçenekleri aşağıdaki tabloda listelenmektedir.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Şerit özelleştirin.|[Şeride Genel Bakış](../vsto/ribbon-overview.md)|  
|Windows Forms veya genişletilmiş Excel denetimleri belge düzeyi özelleştirmeleri için özelleştirilmiş çalışma kitabında veya herhangi bir açık çalışma kitabında VSTO eklenti için bir çalışma sayfasına ekleyin.|[Nasıl Yapılır: Office Belgelerine Windows Forms Denetimleri Ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [Nasıl Yapılır: Çalışma Sayfalarına Grafik Denetimleri Ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)<br /><br /> [Nasıl yapılır: Çalışma Sayfalarına ListObject Denetimleri Ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)<br /><br /> [Nasıl yapılır: Çalışma Sayfalarına NamedRange Denetimleri Ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)|  
  
### <a name="options-for-document-level-customizations"></a>Belge düzeyi özelleştirmeleri için seçenekleri  
 Yalnızca belge düzeyi özelleştirmeleri için özelleştirme seçenekleri aşağıdaki tabloda listelenmektedir.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Eylemler bölmesi çalışma kitabına ekleyin.|[Eylemler Bölmesine Genel Bakış](../vsto/actions-pane-overview.md)<br /><br /> [Nasıl Yapılır: Word Belgelerine veya Excel Çalışma Kitaplarına Eylemler Bölmesi Ekleme](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|Bir çalışma sayfasına XML düğümlerine eşlenmiş genişletilmiş aralık denetimleri ekleyin.|[Nasıl yapılır: Çalışma Sayfalarına XMLMappedRange Denetimleri Ekleme](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)|  
  
### <a name="options-for-vsto-add-ins"></a>VSTO eklentileri için seçenekleri  
 Aşağıdaki tabloda, yalnızca VSTO eklentileri için kullanılabilir seçenekleri listeler.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Özel görev bölmesini oluşturun.|[Özel Görev Bölmeleri](../vsto/custom-task-panes.md)|  
  
### <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Excel Nesne Modeline Genel Bakış](../vsto/excel-object-model-overview.md)|Excel nesne modeli tarafından sağlanan ana türlerine genel bakış sağlar.|  
|[Genişletilmiş Nesneleri Kullanarak Excel'i Otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)|Genişletilmiş nesneler hakkında bilgi sağlar (tarafından sağlanan [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]), Excel çözümleri kullanabilirsiniz.|  
|[Excel Çözümlerini Genelleştirme ve Yerelleştirme](../vsto/globalization-and-localization-of-excel-solutions.md)|Windows için İngilizce olmayan ayarlara sahip bilgisayarlarda çalışan Excel çözümleri için özel konular hakkında bilgi içerir.|  
|[Office Belgelerindeki Windows Forms Denetimlerine Genel Bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)|Windows Forms denetimleri Excel çalışma sayfalarına nasıl ekleyebileceğiniz açıklanmaktadır.|  
|[İzlenecek Yol: Excel İçin İlk Belge Düzeyi Özelleştirmeyi Oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)|Excel için temel bir belge düzeyi özelleştirme oluşturulacağını gösterir.|  
|[İnceleme: Excel için İlk VSTO Eklentinizi Oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)|Excel için temel bir VSTO eklenti oluşturulacağı gösterilmektedir.|  
|[İzlenecek Yol: Çalışma Zamanında VSTO Eklenti Projesindeki Çalışma Sayfasına Denetimler Ekleme](../vsto/walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project.md)|Bir Windows Forms düğme eklemek nasıl gösteren bir <xref:Microsoft.Office.Tools.Excel.NamedRange>ve <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma zamanında VSTO eklenti kullanarak.|
|[Birlikte Yazmayı ve Eklentileri Anlama](./understanding-coauthoring-and-addins.md)|Çözümlerinizi birlikte yazma uyum sağlamak için yapmanız gerekebilir ayarlamalar açıklar.|  
|[Excel 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199011)|Makaleler ve Excel çözümleri geliştirme hakkında başvuru belgeleri bağlantılar sağlar. Bu, Visual Studio kullanarak Office geliştirmeye özel değildir.|  
  
  