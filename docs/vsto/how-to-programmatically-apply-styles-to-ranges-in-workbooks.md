---
title: 'Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki aralıklara stilleri uygulayın'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, styles
- styles, workbook ranges
- workbooks, styles
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d1fd06384febf4e886c28bd4811d10413e0eeb54
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256646"
---
# <a name="how-to-programmatically-apply-styles-to-ranges-in-workbooks"></a>Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki aralıklara stilleri uygulayın
  Çalışma kitaplarında bulunan bölgelere adlandırılmış stiller uygulayabilirsiniz. Excel bir dizi önceden tanımlanmış stil sağlar.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 **Hücreleri Biçimlendir** hücreleri biçimlendirmek için kullanabileceğiniz tüm seçenekler iletişim kutusu görüntüler ve bu seçeneklerin her biri kodunuzdan kullanılabilir. Excel'de bu iletişim kutusunu görüntülemek için tıklatın **hücreleri** üzerinde **biçimi** menüsü.  
  
## <a name="to-apply-a-style-to-a-named-range-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde adlandırılmış bir aralık bir stil uygulamak için  
  
1.  Yeni bir stil oluşturun ve özniteliklerini ayarlayın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#53](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#53)]
     [!code-vb[Trin_VstcoreExcelAutomation#53](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#53)]  
  
2.  Oluşturma bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetlemek, metin atayın ve sonra yeni stili uygulayın. Bu kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#54](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#54)]
     [!code-vb[Trin_VstcoreExcelAutomation#54](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#54)]  
  
## <a name="to-clear-a-style-from-a-named-range-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde adlandırılmış bir aralık'nden bir stil temizlemek için  
  
1.  Normal stili aralığa uygular. Bu kod sayfa sınıfında değil yerleştirilmelidir `ThisWorkbook` sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#55](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#55)]
     [!code-vb[Trin_VstcoreExcelAutomation#55](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#55)]  
  
## <a name="to-apply-a-style-to-a-named-range-in-a-vsto-add-in"></a>Bir VSTO eklentisi adlandırılmış aralıkta bir stil uygulamak için  
  
1.  Yeni bir stil oluşturun ve özniteliklerini ayarlayın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#28](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#28](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#28)]  
  
2.  Oluşturma bir <xref:Microsoft.Office.Interop.Excel.Range>metin atayın ve sonra yeni stili uygulayın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#29](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#29)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#29](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#29)]  
  
## <a name="to-clear-a-style-from-a-named-range-in-an-vsto-add-in"></a>Bir VSTO eklenti adlandırılmış aralıkta'nden bir stil temizlemek için  
  
1.  Normal stili aralığa uygular.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#56](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#56)]
     [!code-vb[Trin_VstcoreExcelAutomation#56](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#56)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Aralıkları ile çalışma](../vsto/working-with-ranges.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  