---
title: "Çalışma kitabı konak öğesi | Microsoft Docs"
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
- Excel workbooks
- Workbook host items
- host items [Office development in Visual Studio], Workbook
- workbooks, Excel
- Workbook host items, events
- workbooks
- Excel [Office development in Visual Studio], workbooks
- workbooks, events
- events [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1c1e6de8313b3e7b94ac88627ef3cdc463c92906
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="workbook-host-item"></a>Çalışma Kitabı Konak Öğesi
  <xref:Microsoft.Office.Tools.Excel.Workbook> Konak öğesi türüdür genişleten bir <xref:Microsoft.Office.Interop.Excel.Workbook> Excel için birincil birlikte çalışma derlemesinden türü. <xref:Microsoft.Office.Tools.Excel.Workbook> Konak öğesi tüm özellikleri, yöntemleri ve olayları olarak sağlayan bir <xref:Microsoft.Office.Interop.Excel.Workbook> nesnesi, ancak ayrıca ek özellikler sağlar.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Belge düzeyi projelerine bir varsayılan yok <xref:Microsoft.Office.Tools.Excel.Workbook> projenizdeki çalışma kitabını temsil eden konak öğesi. VSTO eklenti projelerinde oluşturabileceğiniz <xref:Microsoft.Office.Tools.Excel.Workbook> konak öğelerini çalışma zamanında.  
  
## <a name="understanding-the-workbook-host-item-in-document-level-projects"></a>Çalışma kitabı konak öğesi belge düzeyi projelerine anlama  
 Çalışma kitabı projenize erişmek için `ThisWorkbook` sınıfı. `ThisWorkbook` Sınıf üyelerine erişim sağlar <xref:Microsoft.Office.Tools.Excel.Workbook> çalışma kitabı açılır ya da kapalı olduğunda kodu çalıştırma gibi özelleştirme, temel görevlerini gerçekleştirmek için konak öğesi. Daha fazla bilgi için bkz: [belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md).  
  
 `ThisWorkbook` Sınıfı başlangıç projenizde kod yazma bir konum sağlar. Sınıfın tüm özellikleri, yöntemleri ve olayları olarak sağladığından <xref:Microsoft.Office.Interop.Excel.Workbook> nesne Excel için birincil birlikte çalışma derlemesindeki de kullanabilir `ThisWorkbook` Excel nesne modeline erişmek için. Daha fazla bilgi için bkz: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
 Çift **ThisWorkbook** öğesi proje **Çözüm Gezgini** çalışma kitabı tasarımcısını görüntülemek ve özelliklerini ve çalışma kitabını olayları görüntülemek için **özellikleri**penceresi.  
  
### <a name="limitations-of-the-workbook-host-item-in-document-level-projects"></a>Belge düzeyi projelerine çalışma kitabı konak öğesi sınırlamaları  
 Belge düzeyi projesi yalnızca bir tane içerebilir <xref:Microsoft.Office.Tools.Excel.Workbook> konak öğesi (diğer bir deyişle, `ThisWorkbook` sınıfı). Yeni ekleyemezsiniz <xref:Microsoft.Office.Tools.Excel.Workbook> konak öğeleri projenize tasarım zamanında ve yeni oluşturamazsınız <xref:Microsoft.Office.Tools.Excel.Workbook> konak öğelerini bir belge düzeyi özelleştirmesinde çalışma zamanında.  
  
 Çalışma zamanında yeni bir Excel çalışma kitabı oluşturursanız türü olacaktır <xref:Microsoft.Office.Interop.Excel.Workbook>. Bir konak öğesi olmadığı için herhangi bir ana bilgisayar denetimleri veya Windows Forms denetimleri içeremez. Çalışma kitaplarını çalışma zamanında oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: program aracılığıyla oluşturduğunuz yeni çalışma kitaplarını](../vsto/how-to-programmatically-create-new-workbooks.md).  
  
 <xref:Microsoft.Office.Tools.Excel.Workbook> Konak öğesi ana bilgisayar denetimleri için kapsayıcı olarak hareket değil. Bu nedenle, çalışma kitabına görünür bir denetim ekleyemezsiniz, ancak bileşenler gibi ekleyebilirsiniz bir <xref:System.Data.DataSet>, böylece bileşenleri tüm çalışma sayfaları tarafından paylaşılabilir. Belge düzeyi projede çalışma kitabına kullanılabilir bileşenler bulunabilir **bileşen** sekmesinde **veri** sekmesinde ve **tüm Windows Formları** sekmesinde  **Araç kutusu**.  
  
> [!NOTE]  
>  Visual Studio'da Office geliştirme araçları paylaşılan çalışma kitapları desteklemez.  
  
## <a name="understanding-workbook-host-items-in-vsto-add-in-projects"></a>VSTO eklentisi projelerine anlama çalışma kitabı konak öğeleri  
 VSTO eklenti projelerinde oluşturabileceğiniz bir <xref:Microsoft.Office.Tools.Excel.Workbook> Excel'de açık olan herhangi bir çalışma kitabı için çalışma zamanında konak öğesi. Oluşturulacak bir <xref:Microsoft.Office.Tools.Excel.Workbook> konak öğesi, GetVstoObject yöntemi kullanın. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  