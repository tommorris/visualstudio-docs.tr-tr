---
title: "İzlenecek yol: CheckBox denetimlerini kullanarak çalışma sayfası biçimlendirmesini değiştirme | Microsoft Docs"
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
- worksheets, changing formatting using managed controls
- worksheets, check box controls
- controls [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 196fb88af44d12338416bc2f00f5dc955d5046e8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-changing-worksheet-formatting-using-checkbox-controls"></a>İzlenecek Yol: CheckBox Denetimlerini Kullanarak Çalışma Sayfası Biçimlendirmesini Değiştirme
  Bu kılavuzda biçimlendirmeyi değiştirmek için bir Microsoft Office Excel çalışma sayfasında onay kutuları kullanma hakkında temel bilgileri gösterir. Visual Studio'da Office geliştirme araçları oluşturmak ve kod projenize eklemek için kullanır. Sonuç tamamlanmış bir örnek görmek için Excel bkz [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu gözden geçirme sırasında öğreneceksiniz nasıl yapılır:  
  
-   Metin ve denetimleri çalışma sayfasına ekleyebilirsiniz.  
  
-   Bir seçenek belirlendiğinde, metin biçimi.  
  
-   Projenizi sınayın.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 Bu adımda, Visual Studio kullanarak bir Excel çalışma kitabı projesi oluşturacaksınız.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **My Excel biçimlendirme**. Olduğundan emin olun **bir yeni belge oluşturun** seçilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **My Excel biçimlendirme** için proje **Çözüm Gezgini**.  
  
## <a name="adding-text-and-controls-to-the-worksheet"></a>Çalışma sayfasına metin ve denetimler ekleme  
 Bu kılavuzda, üç gerekir <xref:Microsoft.Office.Tools.Excel.Controls.CheckBox> denetimleri ve bazı metinleri bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim.  
  
#### <a name="to-add-three-check-boxes"></a>Üç onay kutusunu eklemek için  
  
1.  Çalışma kitabı Visual Studio tasarımcısı ve açık olduğunu doğrulayın `Sheet1` açıktır.  
  
2.  Gelen **ortak denetimler** sekmesinde **araç**, sürükleyin bir <xref:Microsoft.Office.Tools.Excel.Controls.CheckBox> denetim ya da hücre yanına **B2** içinde **Sheet1**.  
  
3.  Gelen **Görünüm** menüsünde, select **özellikleri** penceresi.  
  
4.  Olduğundan emin olun **Checkbox1** nesne adı liste kutusunda görünür olduğundan **özellikleri** penceresinde ve aşağıdaki özellikleri değiştirin:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**applyBoldFont**|  
    |**Metin**|**Kalın**|  
  
5.  İkinci bir onay kutusu ya da hücre yanına sürükleyin **B4** ve aşağıdaki özellikleri değiştirin:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**ApplyItalicFont**|  
    |**Metin**|**İtalik**|  
  
6.  Üçüncü bir onay kutusu ya da hücre yanına sürükleyin **B6** ve aşağıdaki özellikleri değiştirin:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**applyUnderlineFont**|  
    |**Metin**|**Alt çizgi**|  
  
7.  Tüm üç onay kutusu denetimleri CTRL tuşunu basılı tutarak seçin.  
  
8.  Excel'de biçimi sekmenin Yerleştir grubunda tıklatın **Hizala**ve ardından **Sola Hizala**.  
  
     Üç onay kutusu denetimleri, seçtiğiniz ilk denetimin konumunda sol tarafındaki hizalanır.  
  
     Ardından, sürükleyin bir <xref:Microsoft.Office.Tools.Excel.NamedRange> çalışma sayfasına denetim.  
  
    > [!NOTE]  
    >  Ayrıca ekleyebileceğiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> yazarak denetim **textFont** içine **adı** kutusu.  
  
#### <a name="to-add-text-to-a-namedrange-control"></a>NamedRange denetimi için metin ekleme  
  
1.  Gelen **Excel denetimleri** sürükleme araç kutusu sekmesinde bir <xref:Microsoft.Office.Tools.Excel.NamedRange> hücre denetimine **B9**.  
  
2.  Doğrulayın **$B$ 9** düzenlenebilir metin kutusunda ve bu hücreyi görünür **B9** seçilir. Değilse, hücreyi tıklatın **B9** seçin.  
  
3.  **Tamam**'ı tıklatın.  
  
4.  Hücre **B9** adında bir aralığa dönüşür `NamedRange1`.  
  
     Çalışma sayfasında görünür bir gösterge yoktur ancak `NamedRange1` görünür **adı kutusuna** (yalnızca çalışma sayfasının üstünde sol tarafta) olduğunda hücre **B9** seçilir.  
  
5.  Olduğundan emin olun **NamedRange1** nesne adı liste kutusunda görünür olduğundan **özellikleri** penceresinde ve aşağıdaki özellikleri değiştirin:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**textFont**|  
    |**Value2**|**Bu metin biçimlendirmesini değiştirmek için bir onay kutusuna tıklayın.**|  
  
 Ardından, bir seçenek belirlendiğinde, metni biçimlendirmek için kod yazma.  
  
## <a name="formatting-the-text-when-an-option-is-selected"></a>Metin bir seçenek biçimlendirme seçili  
 Bu bölümde, böylece kullanıcı bir biçimlendirme seçeneğini seçtiğinde, çalışma sayfasındaki metin biçimi değiştirilir kod yazacaksınız.  
  
#### <a name="to-change-formatting-when-a-check-box-is-selected"></a>Bir onay kutusu seçildiğinde biçimlendirmeyi değiştirmek için seçili  
  
1.  Sağ **Sheet1**ve ardından **görünümü kodu** kısayol menüsünde.  
  
2.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi `applyBoldFont` onay kutusunu:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#7](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#7)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#7)]  
  
3.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi `applyItalicFont` onay kutusunu:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#8](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#8)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#8)]  
  
4.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi `applyUnderlineFont` onay kutusunu:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#9](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#9)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#9)]  
  
5.  C# ' ta onay kutuları için olay işleyicileri eklemelisiniz <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> aşağıda gösterildiği gibi olay. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#10)]  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Artık seçin veya bir onay kutusunu temizlediğinizde metni doğru biçimlendirildiğinden emin olmak için çalışma kitabınızı test edebilirsiniz.  
  
#### <a name="to-test-your-workbook"></a>Çalışma kitabınız sınamak için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Bir onay kutusunun işaretini kaldırın veya seçin.  
  
3.  Metni doğru şekilde biçimlendirildiğini doğrulayın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuzda onay kutularını kullanarak ve Excel çalışma sayfalarında metin biçimlendirmesini temellerini gösterir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Projeyi dağıtma. Daha fazla bilgi için bkz: [tarafından ClickOnce kullanarak Office çözümü dağıtma](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
-   Bir metin kutusunu doldurmak için düğme kullanarak. Daha fazla bilgi için bkz: [izlenecek yol: çalışma sayfasını kullanarak bir düğme metin kutusunda metin görüntüleme](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Excel kullanarak izlenecek yollar](../vsto/walkthroughs-using-excel.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Office Belgelerindeki Windows Forms Denetimleri Sınırlamaları](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  