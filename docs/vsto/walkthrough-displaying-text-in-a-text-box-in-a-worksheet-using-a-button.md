---
title: 'İzlenecek yol: düğme kullanarak çalışma sayfasındaki metin kutusunda metin görüntüleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- text [Office development in Visual Studio], displaying worksheets
- worksheets, displaying text
- text boxes, displaying text in worksheets
- text [Office development in Visual Studio], text boxes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8e9f9679f235837521b06943b1335eb6577c9408
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258447"
---
# <a name="walkthrough-display-text-in-a-text-box-in-a-worksheet-using-a-button"></a>İzlenecek yol: düğme kullanarak çalışma sayfasındaki metin kutusunda metin görüntüleme
  Bu kılavuz, Microsoft Office Excel çalışma sayfaları ve Visual Studio'da Office geliştirme araçlarını kullanarak Excel projeleri oluşturma düğmeleri ve metin kutuları kullanma temelleri gösterir. Sonuç tamamlanmış bir örnek görmek için Excel bkz [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu gözden geçirme sırasında öğreneceksiniz nasıl yapılır:  
  
-   Bir çalışma sayfasına denetimler ekleme.  
  
-   Düğme tıklatıldığında bir metin kutusu doldurun.  
  
-   Projenizi sınayın.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="create-the-project"></a>Projeyi oluşturma  
 Bu adımda, Visual Studio kullanarak bir Excel çalışma kitabı oluşturacaksınız.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **My Excel Button**. Olduğundan emin olun **bir yeni belge oluşturun** seçilir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **My Excel Button** için proje **Çözüm Gezgini**.  
  
## <a name="add-controls-to-the-worksheet"></a>Çalışma sayfasına denetimler ekleme  
 Bu kılavuzda bir düğmeyi ve bir metin kutusu ilk çalışma gerekir.  
  
### <a name="to-add-a-button-and-a-text-box"></a>Bir düğme ve bir metin kutusu eklemek için  
  
1.  Doğrulayın **My Excel Button.xlsx** çalışma kitabı, Visual Studio Tasarımcısı'nda açık ile `Sheet1` görüntülenir.  
  
2.  Gelen **ortak denetimler** sürükleme araç kutusu sekmesinde bir <xref:Microsoft.Office.Tools.Excel.Controls.TextBox> için `Sheet1`.  
  
3.  Gelen **Görünüm** menüsünde, select **Özellikler penceresini**.  
  
4.  Olduğundan emin olun **TextBox1** görünür olan **özellikleri** pencere açılan kutusu ve değişiklik **adı** özelliği metin kutusunun **görüntü metni**.  
  
5.  Sürükleme bir **düğmesini** üzerine kontrol `Sheet1` ve aşağıdaki özellikleri değiştirin:  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**E:System.Windows.Forms.Control.Click**|  
    |**Metin**|**Metin ekleme**|  
  
 Şimdi düğme tıklatıldığında çalıştırmak için kod yazın.  
  
## <a name="populate-the-text-box-when-the-button-is-clicked"></a>Düğme tıklatıldığında metin kutusunu doldurma  
 Kullanıcı düğmesi her zaman **Merhaba Dünya!** metin kutusuna eklenir.  
  
### <a name="to-write-to-the-text-box-when-the-button-is-clicked"></a>Düğmesine tıklandığında metin kutusuna yazmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **Sheet1**ve ardından **görünümü kodu** kısayol menüsünde.  
  
2.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> düğmesi olay işleyicisi:  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#11](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#11)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#11)]  
  
3.  C# ' ta bir olay işleyicisi eklemelisiniz <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> aşağıda gösterildiği gibi olay. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#12)]  
  
## <a name="test-the-application"></a>Uygulamayı test etme  
 Artık emin olmak için çalışma kitabınızı sınayabilirsiniz ileti **Merhaba Dünya!** Düğmeye tıkladığınızda metin kutusunda görüntülenir.  
  
### <a name="to-test-your-workbook"></a>Çalışma kitabınız sınamak için  
  
1.  Tuşuna **F5** projeyi çalıştırın.  
  
2.  Düğmesini tıklatın.  
  
3.  Onaylayın **Merhaba Dünya!** metin kutusunda görüntülenir.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Bu kılavuzda düğmeleri ve metin kutuları Excel çalışma sayfalarında kullanım temellerini gösterir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Projeyi dağıtma. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
-   Biçimlendirmeyi değiştirmek için onay kutularını kullanma. Daha fazla bilgi için bkz: [izlenecek yol: CheckBox denetimlerini kullanarak çalışma sayfası biçimlendirme](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Nasıl yapılır: Office belgelerine Windows Forms denetimleri ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Excel kullanarak izlenecek yollar](../vsto/walkthroughs-using-excel.md)   
 [Office belgelerindeki Windows Forms denetimleri sınırlamaları](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  