---
title: "Windows Forms kullanma Excel çalışma sayfası denetimlerini | Microsoft Docs"
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
- Windows Forms controls [Office development in Visual Studio], Excel
- Excel [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], Window Forms controls
ms.assetid: bbda7461-0d69-4b56-8ba3-418d63ba49db
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3d80158853ec042b98f7e40feda70520af55ed32
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-windows-forms-controls-on-excel-worksheets"></a>Excel Çalışma Sayfalarında Windows Forms Denetimlerini Kullanma
  Windows formlarına denetimler ekleme aynı şekilde, Microsoft Office Excel çalışma kitaplarınızı Windows Forms denetimleri ekleyebilirsiniz. Belgelerindeki denetimler ile çalışma hakkında genel bilgi için bkz: [Office belgeleri genel bakış Windows Forms denetimleri](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="control-considerations-for-excel"></a>Excel için Denetim konuları  
 Excel'e özgü bazı noktalar vardır.  
  
### <a name="matching-control-size-to-cell-size"></a>Hücre boyutuna eşleşen denetim boyutu  
 Üst hücrenin boyutu değiştirildiğinde, otomatik olarak yeniden boyutlandırılıp denetimi ayarlayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: yeniden boyutlandırma denetimleri içinde çalışma sayfası hücreleri](../vsto/how-to-resize-controls-within-worksheet-cells.md).  
  
### <a name="adding-components-that-are-shared-by-all-worksheets"></a>Tüm çalışma sayfaları tarafından paylaşılan bileşenleri ekleme  
 Tüm çalışma sayfaları arasında gibi paylaşmak istediğiniz bileşenleri ekleyebilirsiniz bir <xref:System.Data.DataSet>, çalışma kitabı tasarımcısına çalışma sayfaları. Bileşen bileşen alanında görüntülenir.  
  
### <a name="formula-for-embedding-controls"></a>Denetimleri katıştırma için formülü  
 Excel'de denetim seçtiğinizde göreceğiniz **=EMBED("WinForms.Control.Host","")** içinde **formül çubuğu**. Bu metin gereklidir ve silinmemelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: çalışma sayfası hücreleri içinde denetimleri yeniden boyutlandırma](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [Nasıl yapılır: yazdırırken çalışma sayfası denetimlerini gizleme](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [İzlenecek yol: CheckBox denetimlerini kullanarak çalışma sayfası biçimlendirmesini değiştirme](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)   
 [İzlenecek yol: Düğme kullanarak çalışma sayfasındaki metin kutusunda metin görüntüleme](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)   
 [İzlenecek Yol: Radyo Düğmelerini Kullanarak Çalışma Sayfasında Grafik Güncelleme](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)  
  
  