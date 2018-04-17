---
title: 'Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ListObject control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 55d3a26f0fbf02556071dfc16d08357519b5cff9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-listobject-controls-to-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarına ListObject Denetimleri Ekleme
  Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.ListObject> Microsoft Office Excel çalışma zamanında ve belge düzeyi projelerine çalışma zamanında denetimler.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Ayrıca ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.ListObject> VSTO eklentisi projelerine çalışma zamanında denetimler.  
  
 Bu konuda aşağıdaki görevler açıklanmaktadır:  
  
-   [Tasarım zamanında ListObject denetimleri ekleme](#designtime)  
  
-   [Belge düzeyi projesindeki çalışma zamanında ListObject denetimleri ekleme](#runtimedoclevel)  
  
-   [VSTO eklenti projesindeki çalışma zamanında ListObject denetimleri ekleme](#runtimeaddin)  
  
 Hakkında daha fazla bilgi için <xref:Microsoft.Office.Tools.Excel.ListObject> denetimleri bkz [ListObject denetimi](../vsto/listobject-control.md).  
  
##  <a name="designtime"></a> Tasarım zamanında ListObject denetimleri ekleme  
 Eklemek için çeşitli yollar vardır <xref:Microsoft.Office.Tools.Excel.ListObject> tasarım zamanında belge düzeyi projesindeki çalışma sayfasına denetimler: gelen Excel'den Visual Studio içinde **araç**, gelen ve giden **veri kaynakları** penceresi.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-use-the-ribbon-in-excel"></a>Excel'de Şerit kullanma  
  
1.  Üzerinde **Ekle** sekmesinde **tabloları** grubunda **tablo**.  
  
2.  Hücrenin veya hücre, önce listesine eklemek istediğiniz seçin **Tamam**.  
  
#### <a name="to-use-the-toolbox"></a>Araç kutusunu kullanmak için  
  
1.  Gelen **Excel denetimleri** sekmesinde **araç**, sürükleyin bir <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma.  
  
     **ListObject Denetimi Ekle** iletişim kutusu görüntülenir.  
  
2.  Hücrenin veya hücre, önce listesine eklemek istediğiniz seçin **Tamam**.  
  
     Varsayılan adı tutmak istemiyorsanız adını değiştirebilirsiniz **özellikleri** penceresi.  
  
#### <a name="to-use-the-data-sources-window"></a>Veri kaynakları penceresinden kullanmak için  
  
1.  Açık **veri kaynakları** penceresi ve projeniz için bir veri kaynağı oluşturun. Daha fazla bilgi için bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).  
  
2.  Bir tablodan sürükleyin **veri kaynakları** çalışma penceresine.  
  
     Veri bağlama <xref:Microsoft.Office.Tools.Excel.ListObject> denetimi çalışma sayfasına eklenir. Daha fazla bilgi için bkz: [verileri bağlama ve Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
##  <a name="runtimedoclevel"></a> Belge düzeyi projesindeki çalışma zamanında ListObject denetimleri ekleme  
 Ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.ListObject> çalışma zamanında dinamik olarak denetim. Bu, olaylara yanıt olarak ana bilgisayar denetimleri oluşturmanıza olanak sağlar. Dinamik olarak oluşturulmuş liste nesneleri çalışma sayfasında sürdürülmez çalışma kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-listobject-control-to-a-worksheet-programmatically"></a>ListObject denetimi bir çalışma sayfasına programlı olarak eklemek için  
  
1.  İçinde <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> olay işleyicisi `Sheet1`, eklemek için aşağıdaki kodu ekleyin bir <xref:Microsoft.Office.Tools.Excel.ListObject> hücrelere denetim **A1** aracılığıyla **A4**.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#2](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#2)]
     [!code-vb[Trin_VstcoreHostControlsExcel#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#2)]  
  
##  <a name="runtimeaddin"></a> Bir VSTO eklenti projesindeki çalıştırma zamanında ListObject denetimleri ekleme  
 Ekleyebileceğiniz bir <xref:Microsoft.Office.Tools.Excel.ListObject> VSTO eklenti projesindeki herhangi bir açık çalışma sayfasına program aracılığıyla denetimine. Dinamik olarak oluşturulmuş liste nesneleri çalışma sayfasında sürdürülmez zaman çalışma kaydedildiğinde ve sonra kapatıldığında konak kontrolü olarak. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
#### <a name="to-add-a-listobject-control-to-a-worksheet-programmatically"></a>ListObject denetimi bir çalışma sayfasına programlı olarak eklemek için  
  
1.  Aşağıdaki kod açık çalışma sayfası üzerinde temel alır ve ardından ekleyen bir çalışma sayfası konak öğesi oluşturur bir <xref:Microsoft.Office.Tools.Excel.ListObject> hücrelere denetim **A1** aracılığıyla **A4**.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#8](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#8)]
     [!code-vb[Trin_Excel_Dynamic_Controls#8](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#8)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [ListObject denetimi](../vsto/listobject-control.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Nasıl yapılır: ListObject denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-listobject-controls.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  