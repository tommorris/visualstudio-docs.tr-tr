---
title: Office proje şablonlarına genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- templates [Office development in Visual Studio], about project templates
- Excel Workbook project template
- Word Template project template
- Excel [Office development in Visual Studio], project templates
- Project [Office development in Visual Studio], project templates
- project templates [Office development in Visual Studio]
- project templates, Word
- InfoPath [Office development in Visual Studio], project templates
- Excel Template project template
- project templates, 2007 Microsoft Office system
- project templates, Excel
- PowerPoint [Office development in Visual Studio], project templates
- Word [Office development in Visual Studio], Word project templates
- Office projects [Office development in Visual Studio], templates
- Excel projects in Visual Studio
- Word Document project template
- Visio [Office development in Visual Studio], project templates
- Word projects in Visual Studio
- Outlook [Office development in Visual Studio], project templates
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c8b82da48e04e9c38f16af3cdcc504f7c1fd070f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="office-project-templates-overview"></a>Office Proje Şablonlarına Genel Bakış
  Microsoft Office geliştirici araçları Visual Studio Proje şablonları Office çözümleri aşağıdaki türleri oluşturmak için şunları içerir:  
  
-   [Belge düzeyi özelleştirmeleri](#DocLevel)  
  
-   [VSTO eklentileri](#AppLevel)  
  
 Office çözümleri bu tür ayrıntılı karşılaştırması için bkz: [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 Office proje şablonları kullanılabilir **yeni proje** iletişim kutusunda **Office** düğümünün **Visual C#** ve **Visual Basic**dil düğümleri. Her şablon, derleme başvuruları ve hata ayıklama ayarları dahil olmak üzere, hedef uygulamaya uygun yapılandırmaya sahip bir proje oluşturur.  
  
 Her proje, belirli bir çözüm türü üzerinde çalışmaya başlamanızı sağlayacak dosyaları ve kodu sunar. Her bir proje için üretilen kod, başlangıç ve kapatma olayı işleyicilerini içerir. Yüklendiğinde çözümünüzü başlatmak ve kaldırıldığında çözümünüzü temizlemek için, bu olay işleyicilerine kod ekleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md) ve [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
> [!NOTE]  
>  Office geliştirme araçları Visual Studio'nun belirli sürümlerinde yer alır. Daha fazla bilgi edinmek için bkz. [Bir Bilgisayarı Office Çözümleri Geliştirmek Üzere Yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
##  <a name="DocLevel"></a> Belge düzeyi özelleştirmeleri  
 **Office** düğümünde **yeni proje** iletişim kutusu, Word ve Excel için belge düzeyi özelleştirmeleri oluşturmaya başlamanızı sağlamak için aşağıdaki proje şablonlarını sunar:  
  
-   **Word 2013 ve 2016 VSTO belgesi**  
  
-   **Word 2013 ve 2016 VSTO şablonu**  
  
-   **Excel 2013 ve 2016 VSTO çalışma kitabı**  
  
-   **Excel 2013 ve 2016 VSTO şablonu**  
  
-   **Word 2010 VSTO belgesi**  
  
-   **Word 2010 VSTO şablonu**  
  
-   **Excel 2010 VSTO çalışma kitabı**  
  
-   **Excel 2010 VSTO şablonu**  
  
 Word Belgesi ve Excel Çalışma Kitabı proje şablonları, belirli bir belgeyi veya çalışma sayfasını temel alan bir çözüm oluşturmaya başlamanızı sağlayacak kodu sunar. Bu tür çözümlerde kodunuz sadece Word veya Excel'de ilişkili belge açıksa çalışır.  
  
 Word Şablonu ve Excel Şablonu proje şablonları, Word Belgesi ve Excel Çalışma Kitabı proje şablonlarıyla aynı şekilde davranır. Bununla birlikte, Word Şablonu ve Excel Şablonu proje şablonları, kullanıcıların çözümünüzdeki özelleştirilmiş şablonun yeni yerel belge veya çalışma kitabı kopyalarını oluşturmasını kolaylaştırır. Çözümünüzdeki özellikler, kullanıcının şablondan oluşturduğu yeni belgeden kullanılabilir.  
  
> [!NOTE]  
>  Yönetilen kod uzantılarına başvuran Word şablonları genel VSTO eklentileri kullanılamaz. Şablon Word'ün Başlangıç dizininden yüklenirse, derleme çağrılmaz. Daha fazla bilgi için bkz: [Genel şablonlar sınırlamalar ve Excel eklentileri (.xla dosyaları)](#Limitations)  
  
 Bu proje türleriyle çalışmaya başlama hakkında bilgi için aşağıdaki konulara bakın:  
  
-   [Belge Düzeyi Özelleştirmelerini Programlama](../vsto/programming-document-level-customizations.md)  
  
-   [Word Çözümleri](../vsto/word-solutions.md)  
  
-   [Excel Çözümleri](../vsto/excel-solutions.md)  
  
-   [İzlenecek Yol: Word İçin İlk Belge Düzeyi Özelleştirmeyi Oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)  
  
-   [İzlenecek Yol: Excel İçin İlk Belge Düzeyi Özelleştirmeyi Oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)  
  
##  <a name="AppLevel"></a> VSTO eklentileri  
 **Office/SharePoint** düğümünde **yeni proje** sağlamak için aşağıdaki proje şablonlarını başlatılan VSTO eklentileri oluşturma iletişim kutusu sağlar.  
  
-   **Excel 2013 ve 2016 VSTO eklentisi**  
  
-   **InfoPath 2013 VSTO eklentisi**  
  
-   **Outlook 2013 ve 2016 VSTO eklentisi**  
  
-   **PowerPoint 2013 ve 2016 eklentisi**  
  
-   **Proje 2013 ve 2016 eklentisi**  
  
-   **Visio 2013 ve 2016 eklentisi**  
  
-   **Word 2013 ve 2016 eklentisi**  
  
-   **Excel 2010 Eklentisi**  
  
-   **InfoPath 2010 Eklentisi**  
  
-   **Outlook 2010 Eklentisi**  
  
-   **PowerPoint 2010 Eklentisi**  
  
-   **Project 2010 Eklentisi**  
  
-   **Visio 2010 Eklentisi**  
  
-   **Word 2010 Eklentisi**  
  
 Bu proje şablonlarından birini temel alan bir proje oluşturduğunuzda, çözümünüzdeki kod ilişkili uygulama açıldığı zaman çalışır. Belge düzeyinde projelerin aksine, kodunuz tek bir belgeyle ilişkili değildir.  
  
 Bu proje türleriyle çalışmaya başlama hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [VSTO Eklentilerini Programlamaya Başlama](../vsto/getting-started-programming-vsto-add-ins.md)  
  
-   [VSTO Eklentilerini Programlama](../vsto/programming-vsto-add-ins.md)  
  
-   [İnceleme: Excel için İlk VSTO Eklentinizi Oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)  
  
-   [İnceleme: Outlook için İlk VSTO Eklentinizi Oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)  
  
-   [İnceleme: PowerPoint için İlk VSTO Eklentinizi Oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)  
  
-   [İnceleme: Project için İlk VSTO Eklentinizi Oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)  
  
-   [İnceleme: Word için İlk VSTO Eklentinizi Oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)  
  
## <a name="document-vs-template-solutions"></a>Belge vs. Şablon çözümleri  
 Word belgesi veya Excel çalışma kitabı etrafında bir çözüm tasarladığınızda, bu belgeyi kullanıcılarınıza sunmanın en iyi yoluna karar vermelisiniz.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Bazı durumlarda her kullanıcıya belgenin bir kopyasını vermek isteyebilirsiniz. Bu durumda, çözümünüzü Excel veya Word belgesi projesi olarak oluşturun.  
  
 Diğer durumlarda, bir şablonu sunucuda kullanıma açmak isteyebilirsiniz; böylelikle her kullanıcı şablonu açıp yerel kopyasını belge olarak kaydedebilir. Bu durumda, çözümünüzü Excel veya Word şablonu projesi olarak oluşturun.  
  
## <a name="comparison"></a>Karşılaştırma  
 Aşağıdaki tabloda belgeler ile şablonlar arasındaki farklar ana hatlarıyla açıklanmıştır.  
  
|Belgeler|Şablonlar|  
|---------------|---------------|  
|Kullanıcılar, salt okunur olmadığı sürece belgeyi açıp değiştirebilir. Kaydedilen tüm değişiklikler özgün belgede tutulur.|Kullanıcılar yeni bir belge olarak yerel kopya oluşturmak üzere şablonu açabilir. Özel izinler verilmediği sürece özgün belgede değişiklik yapamazlar.|  
|Belge açıldığında, başlatır <xref:Microsoft.Office.Tools.Word.Document.Open> olay.|Açıldığında, şablon başlatır <xref:Microsoft.Office.Tools.Word.Document.New> olay.|  
  
##  <a name="Limitations"></a> Genel Şablonlar ve Excel eklentileri (.xla dosyaları) sınırlamaları  
 Belgeler, çalışma kitapları ve şablonları, genel şablonları veya Excel VSTO eklentileri (.xla dosyaları) olarak düzgün çalışmayabilir.  
  
## <a name="word-templates"></a>Word Şablonları  
 Bir Microsoft Office Word şablonunun yönetilen kod uzantıları varsa, şablonun bir genel şablon olarak iliştirilmesi veya Word'ün başlangıç dizininden yüklenmesi durumunda proje derlemesi çağrılmaz. Ayrıca belge, bir Office çözümünün parçası olan şablonun biçimini tanımaz.  
  
## <a name="excel-add-ins-xla-files"></a>Excel Eklentileri (.xla Dosyaları)  
 Bir Excel VSTO eklenti (.xla dosyası) oluşturmak için Office proje yok. Bir çalışma kitabını .xla dosyası olarak kaydetmek mümkündür, ancak bu desteklenen bir işlem değildir ve önerilmez. Yönetilen kod uzantısı olarak olan bir çalışma kitabını kaydedin, bir **Microsoft Office Excel Eklentisi (\*.xla)** dosyasını seçebileceğiniz içinde **eklentileri** başka bir çalışma kitabına uygulamak için iletişim kutusu. Bazı durumlarda, kodunuzu VSTO eklenti uygulanır, ancak böyle bir Office çözümü kullanımı desteklenmiyor sonra hedef çalışma kitabında çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Excel için belge düzeyi özelleştirme programlamasına başlama](../vsto/getting-started-programming-document-level-customizations-for-excel.md)   
 [Word için belge düzeyi özelleştirme programlamasına başlama](../vsto/getting-started-programming-document-level-customizations-for-word.md)   
 [VSTO Eklentilerini Programlamaya Başlama](../vsto/getting-started-programming-vsto-add-ins.md)  
  
  