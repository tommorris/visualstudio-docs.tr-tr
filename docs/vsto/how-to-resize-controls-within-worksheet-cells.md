---
title: "Nasıl yapılır: çalışma sayfası hücreleri içinde denetimleri yeniden boyutlandırma | Microsoft Docs"
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
- controls [Office development in Visual Studio], resizing
- managed controls, resizing
- worksheets, resizing
- Windows Forms controls [Office development in Visual Studio], resizing
ms.assetid: 1439db4a-e64b-4381-a6e6-605ba94db3de
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 75759b501741329808198aafbc7dd39d0994cb98
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-controls-within-worksheet-cells"></a>Nasıl Yapılır: Çalışma Sayfası Hücreleri İçinde Denetimleri Yeniden Boyutlandırma
  Sütunlara veya satırlara çalışma sayfası üzerinde yeniden boyutlandırdığınızda, hücreleri otomatik olarak içeren herhangi bir ana bilgisayar denetimleri boyutlandırıldı hücre genişliği veya yüksekliği yeniden boyutlandırın. Windows Forms denetimleri otomatik olarak varsayılan olarak yeniden boyutlandırma değil.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Tasarım zamanında denetimler eklerseniz, her denetim için seçenekleri konumlandırma ayarlamanız gerekir.  
  
 Bir Windows Forms denetimi programlı olarak ekleyin ve bir aralık bağımsız değişken sağlayın, bir hücre aralığı içinde yeniden boyutlandırıldığında denetim otomatik olarak yeniden boyutlandırır. Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="resizing-controls-at-design-time"></a>Tasarım zamanında denetimleri yeniden boyutlandırma  
  
#### <a name="to-make-controls-resize-with-cells-at-design-time"></a>Denetimleri hücrelerle tasarım zamanında yeniden boyutlandırmak için  
  
1.  Gelen **araç**, bir Windows Forms denetimini bir çalışma sayfasına sürükleyin.  
  
2.  Denetimin sağ tıklayın ve ardından **biçimi Denetim**.  
  
3.  İçinde **biçimi Denetim** iletişim kutusu, tıklatın **özellikleri** sekmesi.  
  
4.  Altında **Nesne konumlandırma**seçin **taşıyın ve hücrelerle** seçeneğini ve ardından **Tamam**.  
  
     Denetimi içeren hücreyi yeniden boyutlandırdığınızda denetimi hücre uyacak şekilde yeniden boyutlandırır.  
  
## <a name="resizing-controls-at-run-time"></a>Çalışma zamanında denetimleri yeniden boyutlandırma  
 Çalışma zamanında bir Windows Forms denetimi ekleyin ve geçirin bir <xref:Microsoft.Office.Interop.Excel.Range> aralığı içeren çalışma sayfası hücresi yeniden boyutlandırıldığında denetimin konumu denetimi otomatik olarak yeniden boyutlandırılır.  
  
#### <a name="to-make-controls-resize-with-cells-at-run-time"></a>Denetimleri hücrelerle çalışma zamanında yeniden boyutlandırmak için  
  
1.  Bir denetimi A1 aralığına ekleyin.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#5](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#5)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#5](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#5)]  
  
     Denetimi içeren hücreyi yeniden boyutlandırdığınızda denetimi hücre uyacak şekilde yeniden boyutlandırır.  
  
## <a name="resetting-control-placement"></a>Denetim yerleştirme sıfırlama  
 Yerleştirme ve ayarlayarak denetimi yeniden boyutlandırma sıfırlayabilirsiniz `Placement` aşağıdakilerden birini özelliğine <xref:Microsoft.Office.Interop.Excel.XlPlacement> değerler:  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMove>  
  
-   <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlMoveAndSize>  
  
#### <a name="to-change-the-behavior-of-a-control-so-that-it-does-not-resize-or-move-with-the-cell"></a>Böylece bırakmaz yeniden boyutlandırmak veya hücre ile taşımak için bir denetim davranışını değiştirmek için  
  
1.  Denetimin yerleşim özelliğini çağırıp değerine <xref:Microsoft.Office.Interop.Excel.XlPlacement.xlFreeFloating>.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#6](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#6)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#6)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Nasıl yapılır: Windows Forms denetimleri Office belgelerine ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Nasıl yapılır: yazdırırken çalışma sayfası denetimlerini gizleme](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Office Belgelerindeki Windows Forms Denetimleri Sınırlamaları](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  