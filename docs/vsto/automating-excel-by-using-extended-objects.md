---
title: Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 5a2de66896a734839c7018f48f904c79e80abcaa
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="automate-excel-by-using-etended-objects"></a>Etended nesneleri kullanarak Excel'i otomatikleştirmek
  Visual Studio'daki Excel çözümleri geliştirdiğinizde, kullanabileceğiniz *konak öğelerini* ve *konak kontrolü*Çözümlerinizdeki s. Bunlar gibi bazı yaygın olarak kullanılan nesneler Excel nesne modeli (Excel için birincil birlikte çalışma derlemesi tarafından sunulan başka bir deyişle, nesne modeli) genişleten nesnelerdir <xref:Microsoft.Office.Interop.Excel.Worksheet> ve <xref:Microsoft.Office.Interop.Excel.Range> nesneleri. Genişletilmiş nesneler esas alan Excel nesneleri gibi davranır, ancak bunlar nesnelere yeni olaylar ve veri bağlama özellikleri gibi ek özellikler ekleyin.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Konak denetimlerinin ve konak öğelerinin her iki VSTO eklenti kullanılabilir ve belge düzeyi özelleştirmeleri, bunlar kullanılabilir bağlam çözüm her tür için farklı olmasına rağmen. Daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="excel-host-items"></a>Excel konak öğeleri  
 Excel projeleri birkaç konak öğesine erişim sahibi:  
  
-   <xref:Microsoft.Office.Tools.Excel.Worksheet>. Bu konak öğesi temsil içeren projenizdeki çalışma. Ayrıca ana bilgisayar denetimleri ve Windows Forms denetimleri de dahil olmak üzere yönetilen denetimleri için kapsayıcı görevi görür ve yüzeyinde denetimler hakkında bilgi tutar. Daha fazla bilgi için bkz: [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).  
  
-   <xref:Microsoft.Office.Tools.Excel.Workbook>. Bu konak öğesi projenizdeki çalışma kitabını temsil eder ve tüm çalışma sayfaları tarafından çalışma kitabını paylaşılan bileşenleri için kapsayıcı görevi görür. Daha fazla bilgi için bkz: [çalışma kitabı konak öğesi](../vsto/workbook-host-item.md).  
  
-   <xref:Microsoft.Office.Tools.Excel.ChartSheet>. Bu konak, yalnızca bir grafik içeren ve olaylar ortaya çıkaran Excel çalışma öğesi.  
  
     Bir grafik sayfası Tasarım zamanında yeni bir sayfa olarak Microsoft Office Excel belge düzeyi özelleştirme projenizdeki eklediğinizde, Visual Studio otomatik olarak oluşturur bir <xref:Microsoft.Office.Tools.Excel.ChartSheet> konak öğesi.  
  
     Ancak bir <xref:Microsoft.Office.Tools.Excel.ChartSheet> konak öğesi Excel çalışma sayfasındaki, grafik sayfasına herhangi bir denetim ekleyemezsiniz. Diğer denetimlerin bir grafik içeren çalışma sayfası üzerinde sahip olmak istiyorsanız, bir grafik sayfası kullanmayın. Bunun yerine, bir grafik çalışma sayfasındaki katıştırılmış nesne olarak kullanarak yerleştireceğiniz <xref:Microsoft.Office.Tools.Excel.Chart> konak kontrolü. Daha fazla bilgi için bkz: [grafik denetim](../vsto/chart-control.md).  
  
## <a name="excel-host-controls"></a>Excel konak denetimleri  
 Excel için yardımcı denetimleri oluşturmak, düzenlemek ve çalışma kitaplarını ve çalışma otomatikleştirmek birkaç konak vardır. Bu ana bilgisayar denetimleri, olaylar ve dekiler yerel Excel nesne modelinde bulunmayan veri bağlama özellikleri sağlar.  
  
 Excel projelerinde kullanabileceğiniz ana bilgisayar denetimleri hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Grafik denetimi](../vsto/chart-control.md)  
  
-   [ListObject denetimi](../vsto/listobject-control.md)  
  
-   [NamedRange denetimi](../vsto/namedrange-control.md)  
  
-   [XmlMappedRange denetimi](../vsto/xmlmappedrange-control.md)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: dolgu ListObject denetimleri ile verileri](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [Nasıl yapılır: çalışma sayfalarına Grafik denetimleri ekleme](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarına XMLMappedRange denetimleri ekleme](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [Nasıl yapılır: NamedRange denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-namedrange-controls.md)   
 [Nasıl yapılır: ListObject denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-listobject-controls.md)   
 [Nasıl yapılır: ListObject denetimine yeni bir satır eklendiğinde veri doğrulama](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)   
 [Nasıl yapılır: eşleme ListObject sütunlarıyla verileri](../vsto/how-to-map-listobject-columns-to-data.md)   
 [İzlenecek yol: Program NamedRange denetimi olaylarına karşı](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında genişletme](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  