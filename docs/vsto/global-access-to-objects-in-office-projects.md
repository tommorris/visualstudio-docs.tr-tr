---
title: Office projelerindeki nesnelere genel erişim | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ThisDocument_Shutdown
- ThisDocument_Startup
- Globals class, object global access
- worksheets [Office development in Visual Studio], global access
- documents [Office development in Visual Studio], global access
- event handlers [Office development in Visual Studio]
- ThisWorkbook_Startup
- application-level addins [Office development in Visual Studio]
- addins [Office development in Visual Studio], events
- workbooks [Office development in Visual Studio], global access
- ThisWorkbook_Shutdown
- document-level customizations [Office development in Visual Studio]
- Startup event
- Shutdown event
- projects [Office development in Visual Studio], global access
- Office documents [Office development in Visual Studio, global access
- ThisAddin_Startup
- events [Office development in Visual Studio]
- ThisAddIn_Shutdown
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fda3dee12cdea7442d0f92a2ba794551d76b14cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="global-access-to-objects-in-office-projects"></a>Office Projelerindeki Nesnelere Genel Erişim
  Bir Office proje oluşturduğunuzda, Visual Studio adlı bir sınıf otomatik olarak oluşturur. `Globals` projesinde. Kullanabileceğiniz `Globals` projesinde herhangi bir koddan çalışma zamanında birçok farklı proje öğesine erişmek için sınıf.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="how-to-use-the-globals-class"></a>Globals sınıfı kullanma  
 `Globals` projenizdeki belirli öğelere başvurular tutan statik bir sınıftır. Kullanarak `Globals` sınıfı, çalışma zamanında projedeki herhangi bir koddan aşağıdaki öğeleri erişebilirsiniz:  
  
-   `ThisWorkbook` Ve `Sheet` *n* Excel çalışma kitabı veya şablon projesindeki sınıfları. Bu nesneler kullanarak erişebilirsiniz `Globals.ThisWorkbook` ve `Sheet` *n* özellikleri.  
  
-   `ThisDocument` Bir Word belgesi veya şablonu projesinde sınıfı. Bu nesneyi kullanarak erişebilirsiniz `Globals.ThisDocument` özelliği.  
  
-   `ThisAddIn` VSTO eklenti projesindeki sınıfı. Bu nesneyi kullanarak erişebilirsiniz `Globals.ThisAddIn` özelliği.  
  
-   Tüm şeritler projenizdeki Şerit Tasarımcısını kullanarak özelleştirilmiş. Şerit'i kullanarak erişebilirsiniz `Globals.Ribbons` özelliği. Daha fazla bilgi için bkz: [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md).  
  
-   Outlook VSTO eklenti projesindeki tüm Outlook form bölgeleri. Form bölgeleri kullanarak erişebilirsiniz `Globals.FormRegions` özelliği. Daha fazla bilgi için bkz: [Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md).  
  
-   Hedefleyen projelerde çalışma zamanında Şerit denetimlerini oluşturmak ve ana bilgisayar olanak tanıyan bir Fabrika nesnesine öğelerini [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Bu nesneyi kullanarak erişebilirsiniz `Globals.Factory` özelliği. Bu nesne, bir aşağıdaki arabirimleri uygulayan bir sınıf örneğidir:  
  
    -   <xref:Microsoft.Office.Tools.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Excel.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Outlook.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Word.Factory>  
  
 Örneğin, kullanabileceğiniz `Globals.Sheet1` özellik metin eklemek için bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi `Sheet1` bir kullanıcı Excel için belge düzeyi projede eylemler bölmesindeki bir düğmeyi tıkladığında.  
  
 [!code-vb[Trin_VstcoreProgramming#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/Sheet1.vb#1)]
 [!code-csharp[Trin_VstcoreProgramming#1](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/Sheet1.cs#1)]  
  
## <a name="initializing-the-globals-class"></a>Globals sınıfı başlatılıyor  
 Kullanma girişiminde kod `Globals` belge veya VSTO eklenti tamamen başlatılmadan önce sınıfı bir çalışma zamanı özel durum. Örneğin, kullanarak `Globals` zaman sınıf düzeyinde bir değişkeni bildirme başarısız olabilir, çünkü `Globals` sınıfı başlatılmamış olabilir tüm Konak öğelerinin başvuruları ile bildirilen nesne örneği oluşturulmadan önce.  
  
> [!NOTE]  
>  `Globals` Sınıfı tasarım zamanında hiçbir zaman başlatılmaz, ancak denetim örnekleri tasarımcı tarafından oluşturulur. Özelliğini kullanan bir kullanıcı denetimi oluşturursanız, bunun anlamı `Globals` sınıf özelliği döndürüp döndürmediğini gelen bir kullanıcı denetimi sınıfı içinde gerekir **null** döndürülen nesne kullanmayı denemeden önce.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Belge konak öğesi](../vsto/document-host-item.md)   
 [Çalışma kitabı konak öğesi](../vsto/workbook-host-item.md)   
 [Çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md)   
 [Office Çözümlerinde Kod Yazma](../vsto/writing-code-in-office-solutions.md)  
  
  