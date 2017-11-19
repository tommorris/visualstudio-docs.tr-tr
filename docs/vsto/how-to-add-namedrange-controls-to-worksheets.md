---
title: "Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme | Microsoft Docs"
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
- ranges, adding to worksheets
- NamedRange control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
ms.assetid: da7ec48f-92cb-4fa3-b3e2-447c238d17a8
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 44aefbbce0d910efc6e92f2acb75993598f098ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-namedrange-controls-to-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarına NamedRange Denetimleri Ekleme
  Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> Microsoft Office Excel çalışma zamanında ve belge düzeyi projelerine çalışma zamanında denetimler.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Ayrıca ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> VSTO eklentisi projelerine çalışma zamanında denetimler.  
  
 Bu konuda aşağıdaki görevler açıklanmaktadır:  
  
-   [Tasarım zamanında NamedRange denetimleri ekleme](#designtime)  
  
-   [Belge düzeyi projesindeki çalışma zamanında NamedRange denetimleri ekleme](#runtimedoclevel)  
  
-   [VSTO eklenti projesindeki çalışma zamanında NamedRange denetimleri ekleme](#runtimeaddin)  
  
 Hakkında daha fazla bilgi için <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimleri bkz [NamedRange denetimi](../vsto/namedrange-control.md).  
  
##  <a name="designtime"></a>Tasarım zamanında NamedRange denetimleri ekleme  
 Eklemek için çeşitli yollar vardır <xref:Microsoft.Office.Tools.Excel.NamedRange> tasarım zamanında belge düzeyi projesindeki çalışma sayfasına denetimler: gelen Excel'den Visual Studio içinde **araç**, gelen ve giden **veri kaynakları** penceresi.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-name-box-in-excel"></a>NamedRange denetimi adı kutusuna Excel kullanarak bir çalışma sayfası eklemek için  
  
1.  Hücre veya adlandırılmış aralığın dahil etmek istediğiniz hücreleri seçin.  
  
2.  İçinde **adı kutusuna**, aralığı için bir ad yazın ve ENTER tuşuna basın.  
  
     **Adı kutusuna** sütun hemen formül çubuğundaki yanında bulunan **A** çalışma sayfasının.  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-toolbox"></a>NamedRange denetimi araç kullanarak bir çalışma sayfasına eklemek için  
  
1.  Açık **araç** tıklatıp **Excel denetimleri** sekmesi.  
  
2.  Tıklatın <xref:Microsoft.Office.Tools.Excel.NamedRange> ve bir çalışma sayfasına sürükleyin.  
  
     **Ekle adlandırılmış aralık** iletişim kutusu görüntülenir.  
  
3.  Hücre veya adlandırılmış aralığın dahil etmek istediğiniz hücreleri seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
     Denetime verilen varsayılan adı istemiyorsanız adını değiştirebilirsiniz **özellikleri** penceresi.  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-data-sources-window"></a>NamedRange denetimi veri kaynakları penceresini kullanarak bir çalışma sayfasına eklemek için  
  
1.  Açık **veri kaynakları** penceresi ve projeniz için bir veri kaynağı oluşturun. Daha fazla bilgi için bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).  
  
2.  Tek bir alandan sürükleyin **veri kaynakları** çalışma penceresine.  
  
     Veri bağlama <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi çalışma sayfasına eklenir. Daha fazla bilgi için bkz: [verileri bağlama ve Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
##  <a name="runtimedoclevel"></a>Belge düzeyi projesindeki çalışma zamanında NamedRange denetimleri ekleme  
 Ekleyebileceğiniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> program aracılığıyla çalışma zamanında denetimi. Bu, olaylara yanıt olarak ana bilgisayar denetimleri oluşturmanıza olanak sağlar. Dinamik olarak oluşturulmuş adlandırılmış aralıklar çalışma sayfasında sürdürülmez çalışma kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-programmatically"></a>NamedRange denetimi bir çalışma sayfasına programlı olarak eklemek için  
  
1.  İçinde <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> olay işleyicisi `Sheet1`, eklemek için aşağıdaki kodu ekleyin <xref:Microsoft.Office.Tools.Excel.NamedRange> hücre denetimine **A1** ve kendi <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> özelliğine`Hello world!`  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreHostControlsExcel#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#3)]  
  
##  <a name="runtimeaddin"></a>Bir VSTO eklenti projesindeki çalıştırma zamanında NamedRange denetimleri ekleme  
 Ekleyebileceğiniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> VSTO eklenti projesindeki herhangi bir açık çalışma sayfasına program aracılığıyla denetimine. Dinamik olarak oluşturulmuş adlandırılmış aralıklar çalışma sayfasında sürdürülmez çalışma kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
#### <a name="to-add-a-namedrange-control-to-a-worksheet-programmatically"></a>NamedRange denetimi bir çalışma sayfasına programlı olarak eklemek için  
  
1.  Aşağıdaki kod açık çalışma sayfası üzerinde temel alır ve ardından ekleyen bir çalışma sayfası konak öğesi oluşturur bir <xref:Microsoft.Office.Tools.Excel.NamedRange> hücre denetimine **A1** ve ayarlar kendi <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> özelliğine `Hello world`.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#7](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#7)]
     [!code-vb[Trin_Excel_Dynamic_Controls#7](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Nasıl yapılır: NamedRange denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-namedrange-controls.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  