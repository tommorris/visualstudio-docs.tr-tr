---
title: 'İzlenecek yol: Program NamedRange denetimi olaylarına karşı'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, programming against events
- worksheets, changing cell values
- NamedRange control, events
- worksheets, events
- worksheets, automating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 350b0bcbae6a9d53ab706abab63556d95a6d7a8f
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258281"
---
# <a name="walkthrough-program-against-events-of-a-namedrange-control"></a>İzlenecek yol: Program NamedRange denetimi olaylarına karşı
  Bu kılavuzda nasıl ekleneceği gösterilmektedir bir <xref:Microsoft.Office.Tools.Excel.NamedRange> Microsoft Office Excel çalışma ve Visual Studio'da Office geliştirme araçlarını kullanarak olaylarına dayalı denetimi.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu gözden geçirme sırasında öğreneceksiniz nasıl yapılır:  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Excel.NamedRange> bir çalışma sayfasına denetim.  
  
-   Karşı program <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim olaylarına.  
  
-   Projenizi sınayın.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="create-the-project"></a>Projeyi oluşturma  
 Bu adımda, Visual Studio kullanarak bir Excel çalışma kitabı projesi oluşturur.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **My Named Range Events**. Olduğundan emin olun **bir yeni belge oluşturun** seçilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **My Named Range Events** için proje **Çözüm Gezgini**.  
  
## <a name="add-text-and-named-ranges-to-the-worksheet"></a>Metin ekleme ve çalışma sayfası aralıklarına adlı  
 Konak denetimleri genişletilmiş Office nesneleri olduğundan, bunları ekleyebilirsiniz aynı şekilde belgenize yerel nesne eklemek. Örneğin, bir Excel ekleyebilirsiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimini açarak çalışma sayfasına **Ekle** işaret menüsünde **adı**ve seçme **tanımla**. Ayrıca ekleyebileceğiniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> buradan sürükleyerek denetim **araç** çalışma sayfasına.  
  
 Bu adımda, iki adlandırılmış aralık denetimleri kullanarak çalışma ekleyecek **araç**ve ardından çalışma sayfasına metin ekleyin.  
  
### <a name="to-add-a-range-to-your-worksheet"></a>Çalışma için bir aralığı eklemek için  
  
1.  Doğrulayın *My adlı aralığı Events.xlsx* çalışma kitabı, Visual Studio Tasarımcısı'nda açık ile `Sheet1` görüntülenir.  
  
2.  Gelen **Excel denetimleri** sürükleme araç kutusu sekmesinde bir <xref:Microsoft.Office.Tools.Excel.NamedRange> hücre denetimine **A1** içinde `Sheet1`.  
  
     **NamedRange Denetimi Ekle** iletişim kutusu görüntülenir.  
  
3.  Doğrulayın **$A$ 1** düzenlenebilir metin kutusunda ve bu hücreyi görünür **A1** seçilir. Değilse, hücreyi tıklatın **A1** seçin.  
  
4.  **Tamam**'ı tıklatın.  
  
     Hücre **A1** adında bir aralığa dönüşür `namedRange1`. Çalışma sayfasında görünür bir gösterge yoktur ancak `namedRange1` görünür **adı** (yalnızca çalışma sayfasının sol tarafındaki üstünde bulunur) kutusunu olduğunda hücre **A1** seçilir.  
  
5.  Başka bir tane eklemek <xref:Microsoft.Office.Tools.Excel.NamedRange> hücre denetimine **B3**.  
  
6.  Doğrulayın **$B$ 3** düzenlenebilir metin kutusunda ve bu hücreyi görünür **B3** seçilir. Değilse, hücreyi tıklatın **B3** seçin.  
  
7.  **Tamam**'ı tıklatın.  
  
     Hücre **B3** adında bir aralığa dönüşür `namedRange2`.  
  
### <a name="to-add-text-to-your-worksheet"></a>Çalışma sayfasına metin ekleme  
  
1.  Hücreye **A1**, aşağıdaki metni yazın:  
  
     **Bu, NamedRange denetimi örneğidir.**  
  
2.  Hücreye **A3** (sol tarafındaki `namedRange2`), aşağıdaki metni yazın:  
  
     **Olayları:**  
  
 Aşağıdaki bölümlerde, metin ekleyen kod yazacaksınız `namedRange2` ve özelliklerini değiştirir `namedRange2` yanıt olarak Denetim <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>, <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>, ve <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> olayları `namedRange1`.  
  
## <a name="add-code-to-respond-to-the-beforedoubleclick-event"></a>BeforeDoubleClick olaya yanıt olarak kod ekleme  
  
### <a name="to-insert-text-into-namedrange2-based-on-the-beforedoubleclick-event"></a>BeforeDoubleClick olayına namedRange2 metin eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **Sheet1.vb** veya **Sheet1.cs** seçip **görünümü kodu**.  
  
2.  Kod ekleme böylece `namedRange1_BeforeDoubleClick` olay işleyicisi aşağıdaki gibi görünür:  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#24](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreHostControlsExcel#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#24)]  
  
3.  C# ' ta, adlandırılmış bir aralık için olay işleyicileri gösterildiği gibi eklemelisiniz <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> aşağıdaki olay. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#25](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#25)]  
  
## <a name="add-code-to-respond-to-the-change-event"></a>Değişiklik olaya yanıt olarak kod ekleme  
  
### <a name="to-insert-text-into-namedrange2-based-on-the-change-event"></a>Değiştirme olayı namedRange2 metin eklemek için  
  
1.  Kod ekleme böylece `NamedRange1_Change` olay işleyicisi aşağıdaki gibi görünür:  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#26](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreHostControlsExcel#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#26)]  
  
    > [!NOTE]  
    >  Excel'de bir hücreyi çift düzenleme modunda girdiğinden bir <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> olay metin için hiçbir değişiklik olmasa bile seçim aralığın dışında taşındığında ortaya çıkar.  
  
## <a name="add-code-to-respond-to-the-selectionchange-event"></a>SeçimDeğiştirme olayı yanıt olarak kod ekleme  
  
### <a name="to-insert-text-into-namedrange2-based-on-the-selectionchange-event"></a>SeçimDeğiştirme olayı namedRange2 metin eklemek için  
  
1.  Kod ekleme böylece **böylece NamedRange1_SelectionChange** olay işleyicisi aşağıdaki gibi görünür:  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#27](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#27)]
     [!code-vb[Trin_VstcoreHostControlsExcel#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#27)]  
  
    > [!NOTE]  
    >  Excel'de bir hücreyi çift aralığına taşımak için seçimi neden olduğu bir <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> olay oluştuktan önce <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick> olayı oluşur.  
  
## <a name="test-the-application"></a>Uygulamayı test etme  
 Olaylarını tanıtan metnin doğrulamak için çalışma kitabınızı sınayabilirsiniz artık bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim olaylarını ortaya çıktığında adlandırılmış başka bir aralık eklenir.  
  
### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Tuşuna **F5** projeyi çalıştırın.  
  
2.  İmleci `namedRange1`, doğrulayın metin ilgili <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> olay eklenir ve çalışma sayfasına bir açıklama eklenir.  
  
3.  İçinde çift tıklatın `namedRange1`, doğrulayın metin ilgili <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick> olayları kırmızı italik metin olarak eklenen `namedRange2`.  
  
4.  Dışında tıklatın `namedRange1` ve değişiklik olayı çıkarken oluştuğunu not metne değişiklik yapılmadı olsa bile düzenleme modunda.  
  
5.  İçindeki metni değiştirin `namedRange1`.  
  
6.  Dışında tıklatın `namedRange1`, doğrulayın metin ilgili <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> olay ile mavi metne eklenir `namedRange2`.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Bu kılavuzda olaylarına karşı programlama temelleri gösterilmektedir bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim. Sonradan gelebilecek bir görev şöyledir:  
  
-   Projeyi dağıtma. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md)   
 [NamedRange denetimi](../vsto/namedrange-control.md)   
 [Nasıl yapılır: NamedRange denetimlerinin boyutunu değiştirme](../vsto/how-to-resize-namedrange-controls.md)   
 [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md)  
  
  