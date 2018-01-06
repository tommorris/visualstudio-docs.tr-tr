---
title: "Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına metin arama | Microsoft Docs"
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
- worksheets, searching
- text [Office development in Visual Studio], searching in worksheets
- text searches, worksheets
ms.assetid: a6902711-fefb-450a-a76b-b1446d11c423
caps.latest.revision: "48"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 7968fe71fffb736a6e86319339f3cc7823480403
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-search-for-text-in-worksheet-ranges"></a>Nasıl yapılır: Çalışma Sayfası Aralıklarında Program Aracılığıyla Metin Arama
  <xref:Microsoft.Office.Interop.Excel.Range.Find%2A> Yöntemi <xref:Microsoft.Office.Interop.Excel.Range> nesne metin aralığı içinde arama olanak sağlar. Bu metin herhangi bir çalışma sayfası hücresinde gibi görünebilir hata dizesi de olabilir `#NULL!` veya `#VALUE!`. Hata dizeleri hakkında daha fazla bilgi için bkz: [hücre hata değerlerini](http://msdn.microsoft.com/library/office/ff839168.aspx).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Aşağıdaki örnekte adlı bir aralık arama `Fruits` ve "elmalar" sözcüğünü içeren hücrelerin yazı tipi değiştirir. Bu yordam de kullanır <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> önceden ayarlanmış kullandığı yöntem arama Aramayı yinelemek için ayarlar. Arama yapılacak hücreyi belirtin ve <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> yöntemi rest işler.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> Yöntemin arama aralığın sonuna ulaştı sonra geri arama aralığı başlangıcına sarmalar. Kodunuzu arama sonsuz bir döngüde sarma değil emin olmanız gerekir. Örnek yordamı kullanarak bunu işlemek için tek yolu gösterir <xref:Microsoft.Office.Interop.Excel.Range.Address%2A> özelliği.  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [I: kullanma bulma yöntemi bir Excel eklenti?](http://go.microsoft.com/fwlink/?LinkID=130294).  
  
### <a name="to-search-for-text-in-a-worksheet-range"></a>Bir çalışma sayfası aralıktaki metni aramak için  
  
1.  İzleme tüm aralığı, ilk bulunan aralığı ve geçerli bulunan aralığı için değişkenleri bildirin.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#58](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#58)]
     [!code-vb[Trin_VstcoreExcelAutomation#58](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#58)]  
  
2.  Sonra arama yapılacak hücre dışında tüm parametreleri belirleyerek ilk eşleşme arayın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#59](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#59)]
     [!code-vb[Trin_VstcoreExcelAutomation#59](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#59)]  
  
3.  Eşleşme vardır sürece aramaya devam edin.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#60](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#60)]
     [!code-vb[Trin_VstcoreExcelAutomation#60](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#60)]  
  
4.  İlk bulunan aralıktan karşılaştırma (`firstFind`) için **hiçbir şey**. Varsa `firstFind` bulunan aralık kod depoları hemen hiçbir değer içeriyor (`currentFind`).  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#61](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#61)]
     [!code-vb[Trin_VstcoreExcelAutomation#61](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#61)]  
  
5.  Bulunan aralığın adresi ilk bulunan aralığın adresi eşleşiyorsa döngüden çıkın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#62](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#62)]
     [!code-vb[Trin_VstcoreExcelAutomation#62](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#62)]  
  
6.  Bulunan aralığın görünümünü ayarlayın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#63](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#63)]
     [!code-vb[Trin_VstcoreExcelAutomation#63](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#63)]  
  
7.  Başka bir arama yapın.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#64](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#64)]
     [!code-vb[Trin_VstcoreExcelAutomation#64](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#64)]  
  
 Aşağıdaki örnek tam yöntemini gösterir.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_VstcoreExcelAutomation#57](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#57)]
 [!code-vb[Trin_VstcoreExcelAutomation#57](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#57)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Aralıklarla çalışma](../vsto/working-with-ranges.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki aralıklara stilleri uygulayın](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına başvuran](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  