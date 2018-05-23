---
title: Excel çözümleri
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8e2c6e25c3acdfb4c90eb0ba74d66670be339588
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="excel-solutions"></a>Excel çözümleri
  Visual Studio Proje şablonları Microsoft Office Excel için belge düzeyi özelleştirmeleri ve VSTO eklentileri oluşturmak için kullanabileceğiniz sağlar. Excel otomatikleştirmek, Excel özelliklerini genişletmek ve Excel kullanıcı arabirimini (UI) özelleştirmek için bu çözümleri kullanabilirsiniz. Belge düzeyi özelleştirmeleri ve VSTO eklentileri arasındaki farklar hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
 Bu konuda, aşağıdaki bilgiler sağlanmaktadır:  
  
-   [Excel otomatikleştirmek](#automating).  
  
-   [Excel için belge düzeyi özelleştirmelerini geliştirme](#doclevel).  
  
-   [Excel için VSTO eklentileri geliştirmek](#applevel).  
  
-   [Excel kullanıcı arabirimini özelleştirmek](#UI).  
  
##  <a name="automating"></a> Excel otomatikleştirme  
 Excel nesne modeline Excel otomatikleştirmek için kullanabileceğiniz birçok türü ortaya çıkarır. Örneğin, program aracılığıyla grafik oluşturma, çalışma sayfaları biçimlendirmek ve aralıkları ve hücre değerlerini ayarlayın. Daha fazla bilgi için bkz: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
 Visual Studio'daki Excel çözümleri geliştirirken de kullanabilirsiniz *konak öğelerini* ve *konak denetimlerini* Çözümlerinizdeki. Excel nesne modeli, yaygın olarak kullanılan belirli nesneleri gibi genişletmek nesneleri bunlar <xref:Microsoft.Office.Interop.Excel.Worksheet> ve <xref:Microsoft.Office.Interop.Excel.Range> nesneleri. Genişletilmiş nesneler esas alan Excel nesneleri gibi davranır, ancak nesnelere ek olaylar ve veri bağlama özellikleri ekleyin. Daha fazla bilgi için bkz: [Excel genişletilmiş nesneleri kullanarak otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md).  
  
##  <a name="doclevel"></a> Excel için belge düzeyi özelleştirmelerini geliştirin  
 Microsoft Office Excel için belge düzeyi özelleştirme belirli bir çalışma kitabı ile ilişkili bir derlemeyi oluşur. Derleme, genellikle UI özelleştirerek ve Excel'i otomatikleştirme çalışma kitabını genişletir. Yalnızca ilişkili çalışma kitabını Excel'de açık olduğunda bir VSTO Excel ile ilişkili olan eklenti, özelleştirmesinde uygulamak işlevselliği kullanılabilir.  
  
 Excel için belge düzeyi özelleştirme projesi oluşturmak için Excel çalışma kitabı veya Excel Şablonu proje şablonlarını kullanın **yeni proje** Visual Studio'nun iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Belge düzeyi özelleştirmeleri çalışma hakkında daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md).  
  
### <a name="excel-customization-programming-model"></a>Excel özelleştirme programlama modeli  
 Excel için belge düzeyi projesi oluşturduğunuzda, Visual Studio çözümünüzü temelidir birkaç sınıfları oluşturur: `ThisWorkbook`, `Sheet1`, `Sheet2`, ve `Sheet3`. Bu sınıfların çözümünüzle birlikte ilişkili çalışma sayfaları ve çalışma kitabını temsil eder ve kodunuzu yazmak için bir başlangıç noktası sunar.  
  
 Bunlar hakkında daha fazla bilgi için oluşturulan sınıflar ve kullanabileceğiniz diğer özellikler bir belge düzeyi projede görmek [Program belge düzeyi özelleştirmeleri](../vsto/programming-document-level-customizations.md).  
  
##  <a name="applevel"></a> Excel için VSTO eklentileri geliştirin  
 Microsoft Office Excel bir VSTO eklentisini Excel tarafından yüklenen bir derleme oluşur. Derleme, genellikle UI özelleştirerek ve Excel'i otomatikleştirme Excel genişletir. Belirli bir çalışma kitabı ile ilişkili olan bir belge düzeyi özelleştirme, bir VSTO eklenti uygulamak işlevsellik herhangi bir tek çalışma kitabına sınırlı değildir.  
  
 Excel için VSTO eklenti projesi oluşturmak için Excel çalışma kitabı veya Excel Şablonu proje şablonlarını kullanın **yeni proje** Visual Studio'nun iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 VSTO eklentileri nasıl çalıştığı hakkında genel bilgi için bkz: [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl bir Excel eklentiden I: otomatikleştirmek PowerPoint musunuz?](http://go.microsoft.com/fwlink/?LinkID=130300).  
  
### <a name="excel-add-in-programming-model"></a>Excel eklenti programlama modeli  
 Excel VSTO eklenti projesindeki oluşturduğunuzda, Visual Studio adlı bir sınıf oluşturur `ThisAddIn`, çözümünüzün temeli. Bu sınıf, kodunuzu yazmak için bir başlangıç noktası sağlar ve Excel için VSTO eklentinizi nesne modelini de sunar.  
  
 Hakkında daha fazla bilgi için `ThisAddIn` sınıfı ve bir VSTO eklenti, kullanabileceğiniz diğer Visual Studio özellikler bkz [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
##  <a name="UI"></a> Excel kullanıcı arabirimini özelleştirme  
 Excel kullanıcı arabirimini özelleştirmek için birçok farklı yol vardır. Bazı seçenekler için tüm proje türleri kullanılabilir ve diğer seçenekleri yalnızca VSTO eklentileri ya da belge düzeyi özelleştirmeleri için kullanılabilir.  
  
### <a name="options-for-all-project-types"></a>Tüm proje türleri için seçenekleri  
 Belge düzeyi özelleştirmeleri ve VSTO eklentileri için kullanılabilir özelleştirme seçenekleri aşağıdaki tabloda listelenmektedir.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Şerit özelleştirin.|[Şerite Genel Bakış](../vsto/ribbon-overview.md)|  
|Windows Forms veya genişletilmiş Excel denetimleri belge düzeyi özelleştirmeleri için özelleştirilmiş çalışma kitabında veya herhangi bir açık çalışma kitabında VSTO eklenti için bir çalışma sayfasına ekleyin.|[Nasıl yapılır: Office belgelerine Windows forms denetimleri ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)<br /><br /> [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)<br /><br /> [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)|  
  
### <a name="options-for-document-level-customizations"></a>Belge düzeyi özelleştirmeleri için seçenekleri  
 Yalnızca belge düzeyi özelleştirmeleri için özelleştirme seçenekleri aşağıdaki tabloda listelenmektedir.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Eylemler bölmesi çalışma kitabına ekleyin.|[Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)<br /><br /> [Nasıl yapılır: Word belgelerine Eylemler bölmesi ekleme veya Excel çalışma kitapları](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|Bir çalışma sayfasına XML düğümlerine eşlenmiş genişletilmiş aralık denetimleri ekleyin.|[Nasıl yapılır: çalışma sayfalarına XMLMappedRange denetimleri ekleme](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)|  
  
### <a name="options-for-vsto-add-ins"></a>VSTO eklentileri için seçenekleri  
 Aşağıdaki tabloda, yalnızca VSTO eklentileri için kullanılabilir seçenekleri listeler.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Özel görev bölmesini oluşturun.|[Özel görev bölmeleri](../vsto/custom-task-panes.md)|  
  
### <a name="related-topics"></a>İlgili konular  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md)|Excel nesne modeli tarafından sağlanan ana türlerine genel bakış sağlar.|  
|[Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md)|Genişletilmiş nesneler hakkında bilgi sağlar (tarafından sağlanan [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]), Excel çözümleri kullanabilirsiniz.|  
|[Genelleştirme ve yerelleştirme Excel çözümleri](../vsto/globalization-and-localization-of-excel-solutions.md)|Windows için İngilizce olmayan ayarlara sahip bilgisayarlarda çalışan Excel çözümleri için özel konular hakkında bilgi içerir.|  
|[Windows Forms denetimlerindeki Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)|Windows Forms denetimleri Excel çalışma sayfalarına nasıl ekleyebileceğiniz açıklanmaktadır.|  
|[İzlenecek yol: Excel için ilk belge düzeyi özelleştirmeyi oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)|Excel için temel bir belge düzeyi özelleştirme oluşturulacağını gösterir.|  
|[İzlenecek yol: Excel için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)|Excel için temel bir VSTO eklenti oluşturulacağı gösterilmektedir.|  
|[İzlenecek yol: çalışma zamanında VSTO eklenti projesindeki çalışma sayfasına denetimler ekleme](../vsto/walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project.md)|Bir Windows Forms düğme eklemek nasıl gösteren bir <xref:Microsoft.Office.Tools.Excel.NamedRange>ve bir <xref:Microsoft.Office.Tools.Excel.ListObject> bir VSTO eklentisini kullanarak çalışma zamanında çalışma.|
|[Ortak yazma ve eklentiler anlama](./understanding-coauthoring-and-addins.md)|Çözümlerinizi birlikte yazma uyum sağlamak için yapmanız gerekebilir ayarlamalar açıklar.|  
|[Excel 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199011)|Makaleler ve Excel çözümleri geliştirme hakkında başvuru belgeleri bağlantılar sağlar. Bu, Visual Studio kullanarak Office geliştirmeye özel değildir.|  
  
  