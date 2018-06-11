---
title: Word çözümleri
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], Word
- Office projects [Office development in Visual Studio], Word
- application-level add-ins [Office development in Visual Studio], Word
- Word [Office development in Visual Studio]
- projects [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], about Word solutions
- Office solutions [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], application-level add-ins
- documents [Office development in Visual Studio], Word
- Office development in Visual Studio, Word solutions
- add-ins [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], document-level customizations
- user interfaces [Office development in Visual Studio], Word
- Office documents [Office development in Visual Studio, Word
- document-level customizations [Office development in Visual Studio], Word
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ce2c80e3d4ec62daa4774b99686ff10130834a78
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258703"
---
# <a name="word-solutions"></a>Word çözümleri
  Visual Studio Proje şablonları Microsoft Office Word için belge düzeyi özelleştirmeleri ve VSTO eklentileri oluşturmak için kullanabileceğiniz sağlar. Bu çözümler, Word otomatikleştirmek, Word özelliklerini genişletmek ve Word kullanıcı arabirimini (UI) özelleştirmek için kullanabilirsiniz. Belge düzeyi özelleştirmeleri ve VSTO eklentileri arasındaki farklar hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
 Bu konuda, aşağıdaki bilgiler sağlanmaktadır:  
  
-   [Word otomatikleştirmek](#automating).  
  
-   [Word için belge düzeyi özelleştirmeleri geliştirme](#doclevel).  
  
-   [Word için VSTO eklentileri geliştirmek](#applevel).  
  
-   [Word'ün kullanıcı arabiriminizi](#UI).  
  
##  <a name="automating"></a> Word otomatikleştirme  
 Word nesne modeli Word otomatikleştirmek için kullanabileceğiniz birçok türü ortaya çıkarır. Örneğin, size program aracılığıyla tabloları oluşturma, biçim belgeleri ve metni aralıkları ve paragrafları ayarlama. Daha fazla bilgi için bkz: [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md).  
  
 Visual Studio'da Word çözümleri geliştirirken de kullanabilirsiniz *konak öğelerini* ve *konak denetimlerini* Çözümlerinizdeki. Word nesne modeli, yaygın olarak kullanılan belirli nesneleri gibi genişletmek nesneleri bunlar <xref:Microsoft.Office.Interop.Word.Document> ve <xref:Microsoft.Office.Interop.Word.ContentControl> nesneleri. Genişletilmiş nesneler esas alan Word nesneleri gibi davranır, ancak nesnelere ek olaylar ve veri bağlama özellikleri ekleyin. Daha fazla bilgi için bkz: [otomatikleştirmek genişletilmiş nesneleri kullanarak Word'ü](../vsto/automating-word-by-using-extended-objects.md).  
  
##  <a name="doclevel"></a> Word için belge düzeyi özelleştirmeleri geliştirin  
 Microsoft Office Word için belge düzeyi özelleştirme belirli bir belge ile ilişkili bir derlemeyi oluşur. Derleme, genellikle UI özelleştirerek ve Word'ü Otomatikleştirme belge genişletir. Yalnızca ilişkili belge Word'de açık olduğunda bir VSTO Word ile ilişkili olan eklenti, özelleştirmesinde uygulamak işlevselliği kullanılabilir.  
  
 Word için belge düzeyi özelleştirme projesi oluşturmak için Word belgesine veya Word Şablonu proje şablonlarını kullanın **yeni proje** Visual Studio'nun iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Belge düzeyi özelleştirmeleri çalışma hakkında daha fazla bilgi için [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md).  
  
### <a name="word-customization-programming-model"></a>Word özelleştirme programlama modeli  
 Word için belge düzeyi projesi oluşturduğunuzda, Visual Studio adlı bir sınıf oluşturur `ThisDocument`, çözümünüzün temeli. Bu sınıf çözümünüzle ilişkilendirilmiş belgeyi temsil eder ve kodunuzu yazmak için bir başlangıç noktası sağlar.  
  
 Hakkında daha fazla bilgi için `ThisDocument` sınıfı ve bir belge düzeyi projede kullanabileceğiniz diğer özellikler bkz [Program belge düzeyi özelleştirmeleri](../vsto/programming-document-level-customizations.md).  
  
##  <a name="applevel"></a> Word için VSTO eklentileri geliştirin  
 Microsoft Office Word'ün bir VSTO eklentisi Word tarafından yüklenen bir derleme içerir. Derleme, genellikle UI özelleştirerek ve Word'ü Otomatikleştirme Word genişletir. Belirli bir belge ile ilişkili olan bir belge düzeyi özelleştirme, bir VSTO eklenti uygulamak işlevsellik herhangi bir tek belge sınırlı değildir.  
  
 Word için VSTO eklenti projesi oluşturmak için Word eklenti proje şablonlarını kullanın **yeni proje** Visual Studio'nun iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 VSTO eklentileri nasıl çalıştığı hakkında genel bilgi için bkz: [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
### <a name="word-add-in-programming-model"></a>Word eklenti programlama modeli  
 Word VSTO eklenti projesi oluşturduğunuzda, Visual Studio adlı bir sınıf oluşturur `ThisAddIn`, çözümünüzün temeli. Bu sınıf, kodunuzu yazmak için bir başlangıç noktası sağlar ve Word için VSTO eklentinizi nesne modelini de sunar.  
  
 Hakkında daha fazla bilgi için `ThisAddIn` sınıfı ve bir VSTO eklenti, kullanabileceğiniz diğer özellikler bkz [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
##  <a name="UI"></a> Word'ün kullanıcı arabirimini özelleştirme  
 Word'ün kullanıcı arabirimini özelleştirmek için birkaç farklı yolu vardır. Bazı seçenekler için tüm proje türleri kullanılabilir ve diğer seçenekleri yalnızca VSTO eklentileri ya da belge düzeyi özelleştirmeleri için kullanılabilir.  
  
### <a name="options-for-all-project-types"></a>Tüm proje türleri için seçenekleri  
 Belge düzeyi özelleştirmeleri ve VSTO eklentileri için kullanılabilir özelleştirme seçenekleri aşağıdaki tabloda listelenmektedir.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Şerit özelleştirin.|[Şerite Genel Bakış](../vsto/ribbon-overview.md)|  
|Windows Forms veya genişletilmiş Word denetimleri özelleştirilmiş belge (için belge düzeyi özelleştirmeleri için) veya herhangi bir açık belgeye (bir VSTO eklenti için) ekleyin.|[Nasıl yapılır: Office belgelerine Windows Forms denetimleri ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)<br /><br /> [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)|  
  
### <a name="options-for-document-level-customizations"></a>Belge düzeyi özelleştirmeleri için seçenekleri  
 Yalnızca belge düzeyi özelleştirmeleri için özelleştirme seçenekleri aşağıdaki tabloda listelenmektedir.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Eylemler bölmesi belgeye ekleyin.|[Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)<br /><br /> [Nasıl yapılır: Word belgelerine Eylemler bölmesi ekleme veya Excel çalışma kitapları](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|Genişletilmiş XMLNode ve XMLNodes denetimleri belge yüzeyine ekleyin.|[Nasıl yapılır: Word belgelerine XMLNode denetimleri ekleme](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)<br /><br /> [Nasıl yapılır: Word belgelerine XMLNodes denetimleri ekleme](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)|  
  
### <a name="options-for-vsto-add-ins"></a>VSTO eklentileri için seçenekleri  
 Aşağıdaki tabloda, yalnızca VSTO eklentileri için kullanılabilir seçenekleri listeler.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Özel görev bölmesini oluşturun.|[Özel görev bölmeleri](../vsto/custom-task-panes.md)|  
  
### <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)|Word nesne modeli tarafından sağlanan ana türlerine genel bakış sağlar.|  
|[Genişletilmiş nesneleri kullanarak Word otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)|Genişletilmiş nesneler hakkında bilgi sağlar (tarafından sağlanan [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]), Word çözümleri kullanabilirsiniz.|  
|[Windows Forms denetimlerindeki Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)|Windows Forms denetimleri Word belgelerine nasıl ekleyebileceğiniz açıklanmaktadır.|  
|[İzlenecek yol: Word için ilk belge düzeyi özelleştirmeyi oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)|Word için temel bir belge düzeyi özelleştirme oluşturulacağını gösterir.|  
|[İzlenecek yol: Word için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)|Temel bir VSTO eklenti Word oluşturmak gösterilmiştir.|  
|[İzlenecek yol: çalışma zamanında VSTO eklenti belgeye denetimleri ekleme](../vsto/walkthrough-adding-controls-to-a-document-at-run-time-in-a-vsto-add-in.md)|Bir Windows eklemek için düğmesini formlarının nasıl ve gösterir <xref:Microsoft.Office.Tools.Word.RichTextContentControl> bir belgeye çalışma zamanında VSTO eklenti kullanarak.|  
|[Word 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199020)|Makaleler ve başvuru belgeleri (Visual Studio kullanarak Office geliştirmeye özgü olmayan) geliştirme Word çözümleri hakkında bağlantılar sağlar.|  
  
  