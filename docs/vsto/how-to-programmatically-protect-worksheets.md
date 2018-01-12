---
title: "Nasıl yapılır: çalışma sayfalarını program aracılığıyla koruma | Microsoft Docs"
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
- protection, adding to worksheets
- documents [Office development in Visual Studio], document protection
- document protection, adding to worksheets
- worksheets, protecting
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 94293b90add3cbb4034278b8566ecfb1d138c09e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-protect-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarını Program Aracılığıyla Koruma
  Microsoft Office Excel koruma özelliği, kullanıcıların ve kodun çalışma sayfasındaki nesneleri değiştirmesini önlemeye yardımcı olur. Koruma etkinleştirildikten sonra varsayılan olarak, tüm hücreler kilitlenir.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Belge düzeyi özelleştirmelerindeki çalışma sayfalarını Excel Tasarımcısını kullanarak koruyabilirsiniz. Aynı zamanda bir çalışma sayfasına program aracılığıyla herhangi bir proje türü çalışma zamanında koruyabilirsiniz.  
  
> [!NOTE]  
>  Windows Forms denetimleri korunan çalışma alanlarının için eklenemiyor.  
  
## <a name="using-the-designer"></a>Tasarımcı kullanarak  
  
#### <a name="to-protect-a-worksheet-in-the-designer"></a>Tasarımcıda çalışma sayfasını korumak için  
  
1.  İçinde **değişiklikleri** grubunu **gözden geçirme** sekmesini tıklatın, **sayfayı koru**.  
  
     **Sayfayı koru** iletişim kutusu görüntülenir. Bir parola ayarlayın ve isteğe bağlı olarak kullanıcıların çalışma sayfası hücreleri biçimlendir gibi ile gerçekleştirmek veya satır eklemek için izin verilen belirli eylemleri belirtin.  
  
 Ayrıca, kullanıcıların korunan çalışma sayfalarında belirli aralıkları düzenlemek de izin verebilirsiniz.  
  
#### <a name="to-allow-editing-in-specific-ranges"></a>Belirli aralıkları düzenlemeye izin vermek için  
  
1.  İçinde **değişiklikleri** grubunu **gözden geçirme** sekmesini tıklatın, **kullanıcıların aralıkları düzenlemesine izin**.  
  
     **Kullanıcıların aralıkları düzenlemesine izin** iletişim kutusu görüntülenir. Bir parola ve parola olmadan aralıkları düzenleyebilirsiniz kullanıcılar kullanarak kilidi aralıkları belirtebilirsiniz.  
  
## <a name="using-code-at-run-time"></a>Çalışma zamanında kod kullanma  
 Aşağıdaki kod (kullanıcıdan elde edilen parolayı içeren getPasswordFrom kullanarak) parolasını ayarlar ve sadece sıralamaya izin verir.  
  
#### <a name="to-protect-a-worksheet-by-using-code-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde kodu kullanarak bir çalışma sayfasını korumak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Worksheet.Protect%2A> çalışma sayfasının yöntemi. Bu örnekte adlı bir çalışma çalıştığınız varsayılır `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#27](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomation#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#27)]  
  
#### <a name="to-protect-a-worksheet-by-using-code-in-a-vsto-add-in"></a>Bir VSTO eklenti kod kullanarak bir çalışma sayfasını korumak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Worksheet.Protect%2A> etkin çalışma sayfasının yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#17](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#17](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#17)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: çalışma sayfalarından program aracılığıyla korumayı kaldırma](../vsto/how-to-programmatically-remove-protection-from-worksheets.md)   
 [Nasıl yapılır: çalışma kitaplarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-workbooks.md)   
 [Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  