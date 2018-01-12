---
title: "Nasıl yapılır: çalışma kitaplarını program aracılığıyla koruma | Microsoft Docs"
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
- workbooks, passwords
- documents [Office development in Visual Studio], document protection
- workbooks, unprotecting
- document protection, removing from workbooks
- document protection, adding to workbooks
- workbooks, protecting
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1799366258786bafb3b24b5580ccf29be1d59927
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-protect-workbooks"></a>Nasıl yapılır: Çalışma Kitaplarını Program Aracılığıyla Koruma
  Böylece kullanıcılar eklenemez veya çalışma sayfalarını silme ve aynı zamanda da program aracılığıyla çalışma kitabının korumasını kaldırın, Microsoft Office Excel çalışma kitabı koruyabilirsiniz. İsteğe bağlı olarak, bir parola belirtin, (kullanıcıların sayfaları taşıyamazsınız şekilde) korumalı yapısı isterseniz ve çalışma kitabının windows korumalı isteyip istemediğinizi belirtin olup olmadığını gösterir.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Bir çalışma kitabını koruma kullanıcıların hücreleri durdurmaz. Verileri korumak için çalışma sayfaları korumanız gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: program aracılığıyla koruma çalışma sayfaları](../vsto/how-to-programmatically-protect-worksheets.md).  
  
 Aşağıdaki kod örnekleri, kullanıcıdan elde edilen parolayı içeren bir değişkeni kullanın.  
  
## <a name="protecting-a-workbook-that-is-part-of-a-document-level-customization"></a>Belge düzeyi özelleştirme parçası olan bir çalışma kitabını koruma  
  
#### <a name="to-protect-a-workbook"></a>Bir çalışma kitabını korumak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> çalışma kitabının yöntemi ve bir parola içerecek. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisWorkbook` sınıfı, bir sayfa sınıfında değil.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#10)]
     [!code-vb[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#10)]  
  
#### <a name="to-unprotect-a-workbook"></a>Bir çalışma kitabının korumasını kaldırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Workbook.Unprotect%2A> gerekiyorsa bir parola geçirerek yöntemi. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisWorkbook` sınıfı, bir sayfa sınıfında değil.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#11)]  
  
## <a name="protecting-a-workbook-by-using-an-application-level-add-in"></a>Uygulama düzeyi eklentisi kullanarak bir çalışma kitabı koruma  
  
#### <a name="to-protect-a-workbook"></a>Bir çalışma kitabını korumak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Workbook.Protect%2A> çalışma kitabının yöntemi ve bir parola içerecek. Bu kod örneği, etkin çalışma kitabının kullanır. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#6)]  
  
#### <a name="to-unprotect-a-workbook"></a>Bir çalışma kitabının korumasını kaldırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Workbook.Unprotect%2A> gerekiyorsa bir parola geçirerek etkin çalışma kitabının yöntemi. Bu örneği kullanmak için kodu çalıştırın `ThisAddIn` projenizdeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  