---
title: Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], automating
- automation [Office development in Visual Studio], Excel
- host controls, Excel
- Excel [Office development in Visual Studio], host controls
- extended objects [Office development in Visual Studio], Excel
- host controls [Office development in Visual Studio], Excel
- automating Excel
- host items [Office development in Visual Studio], Excel
- controls [Office development in Visual Studio], Excel host controls
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 63c200a3d3a6a64dfc100cc9365f142a8dddae4c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="automating-excel-by-using-extended-objects"></a>Genişletilmiş Nesneleri Kullanarak Excel'i Otomatikleştirme
  Visual Studio'daki Excel çözümleri geliştirdiğinizde, kullanabileceğiniz *konak öğelerini* ve *konak kontrolü*Çözümlerinizdeki s. Bunlar gibi bazı yaygın olarak kullanılan nesneler Excel nesne modeli (Excel için birincil birlikte çalışma derlemesi tarafından sunulan başka bir deyişle, nesne modeli) genişleten nesnelerdir <xref:Microsoft.Office.Interop.Excel.Worksheet> ve <xref:Microsoft.Office.Interop.Excel.Range> nesneleri. Genişletilmiş nesneler esas alan Excel nesneleri gibi davranır, ancak bunlar nesnelere yeni olaylar ve veri bağlama özellikleri gibi ek özellikler ekleyin.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Konak denetimlerinin ve konak öğelerinin her iki VSTO eklenti kullanılabilir ve belge düzeyi özelleştirmeleri, bunlar kullanılabilir bağlam çözüm her tür için farklı olmasına rağmen. Daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="excel-host-items"></a>Excel konak öğeleri  
 Excel projeleri birkaç konak öğesine erişim sahibi:  
  
-   <xref:Microsoft.Office.Tools.Excel.Worksheet>. Bu konak öğesi temsil içeren projenizdeki çalışma. Ayrıca ana bilgisayar denetimleri ve Windows Forms denetimleri de dahil olmak üzere yönetilen denetimleri için kapsayıcı görevi görür ve yüzeyinde denetimler hakkında bilgi tutar. Daha fazla bilgi için bkz: [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).  
  
-   <xref:Microsoft.Office.Tools.Excel.Workbook>. Bu konak öğesi projenizdeki çalışma kitabını temsil eder ve tüm çalışma sayfaları tarafından çalışma kitabını paylaşılan bileşenleri için kapsayıcı görevi görür. Daha fazla bilgi için bkz: [çalışma kitabı konak öğesi](../vsto/workbook-host-item.md).  
  
-   <xref:Microsoft.Office.Tools.Excel.ChartSheet>. Bu konak, yalnızca bir grafik içeren ve olaylar ortaya çıkaran Excel çalışma öğesi.  
  
     Bir grafik sayfası Tasarım zamanında yeni bir sayfa olarak Microsoft Office Excel belge düzeyi özelleştirme projenizdeki eklediğinizde, Visual Studio otomatik olarak oluşturur bir <xref:Microsoft.Office.Tools.Excel.ChartSheet> konak öğesi.  
  
     Ancak bir <xref:Microsoft.Office.Tools.Excel.ChartSheet> konak öğesi Excel çalışma sayfasındaki, grafik sayfasına herhangi bir denetim ekleyemezsiniz. Diğer denetimlerin bir grafik içeren çalışma sayfası üzerinde sahip olmak istiyorsanız, bir grafik sayfası kullanmayın. Bunun yerine, bir grafik çalışma sayfasındaki katıştırılmış nesne olarak kullanarak yerleştireceğiniz <xref:Microsoft.Office.Tools.Excel.Chart> konak kontrolü. Daha fazla bilgi için bkz: [grafik denetiminin](../vsto/chart-control.md).  
  
## <a name="excel-host-controls"></a>Excel konak denetimleri  
 Excel için yardımcı denetimleri oluşturmak, düzenlemek ve çalışma kitaplarını ve çalışma otomatikleştirmek birkaç konak vardır. Bu ana bilgisayar denetimleri, olaylar ve dekiler yerel Excel nesne modelinde bulunmayan veri bağlama özellikleri sağlar.  
  
 Excel projelerinde kullanabileceğiniz ana bilgisayar denetimleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Grafik Denetimi](../vsto/chart-control.md)  
  
-   [ListObject Denetimi](../vsto/listobject-control.md)  
  
-   [NamedRange Denetimi](../vsto/namedrange-control.md)  
  
-   [XmlMappedRange Denetimi](../vsto/xmlmappedrange-control.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: ListObject denetimlerini veri ile doldurma](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına XMLMappedRange denetimleri ekleme](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: NamedRange denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-namedrange-controls.md)   
 [Nasıl yapılır: ListObject denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-listobject-controls.md)   
 [Nasıl yapılır: ListObject denetimine yeni bir satır eklendiğinde veri doğrulama](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)   
 [Nasıl yapılır: ListObject sütunlarıyla verileri eşleme](../vsto/how-to-map-listobject-columns-to-data.md)   
 [İzlenecek yol: NamedRange denetimi olaylarına karşı programlama](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  