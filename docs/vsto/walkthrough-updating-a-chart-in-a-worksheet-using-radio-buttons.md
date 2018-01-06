---
title: "İzlenecek yol: radyo düğmelerini kullanarak çalışma sayfasında grafik güncelleme | Microsoft Docs"
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
- worksheets, updating using managed controls
- controls [Office development in Visual Studio], updating worksheets
- worksheets, using radio buttons
ms.assetid: cacc43a3-6d95-4a47-b943-3457d97a16f8
caps.latest.revision: "58"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 90427051f2dd3ca7a906e7b6716a33ddd538f726
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons"></a>İzlenecek Yol: Radyo Düğmelerini Kullanarak Çalışma Sayfasında Grafik Güncelleme
  Bu kılavuzda kullanıcıya hızla seçenekleri arasında geçiş yapma olanağı vermek için bir Microsoft Office Excel çalışma sayfasında radyo düğmelerini kullanarak temellerini gösterir. Bu durumda, seçenekleri grafiğinin stilini değiştirin.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Sonuç tamamlanmış bir örnek görmek için Excel bkz [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Bir çalışma sayfasına bir grup radyo düğmelerini ekleme.  
  
-   Bir seçenek belirlendiğinde, grafik stilini değiştirme.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="adding-a-chart-to-a-worksheet"></a>Çalışma sayfasına bir grafik ekleme  
 Varolan bir çalışma kitabını özelleştirir bir Excel çalışma kitabı proje oluşturabilirsiniz. Bu kılavuzda, bir çalışma kitabına bir grafik ekleyin ve sonra bu çalışma kitabında yeni bir Excel çözümünde kullanın. Bu kılavuzda veri kaynağında adlı bir çalışma sayfası olduğu **grafiği için veri**.  
  
#### <a name="to-add-the-data"></a>Veri eklemek için  
  
1.  Microsoft Excel'i açın.  
  
2.  Sağ **Sheet3** sekmesini ve ardından **yeniden adlandırma** kısayol menüsünde.  
  
3.  Sayfasına yeniden adlandırma **grafiği için veri**.  
  
4.  Aşağıdaki veri ekleme **grafiği için veri** hücre A4 olan ile üst sol köşe ve E8 sağ alt köşesindeki.  
  
    ||S1|S2|S3|S4|  
    |-|--------|--------|--------|--------|  
    |Batı|500|550|550|600|  
    |Doğu|600|625|675|700|  
    |Kuzey|450|470|490|510|  
    |Güney|800|750|775|790|  
  
 Ardından, bir grafik verileri görüntülemek için birinci çalışma sayfasına ekleyin.  
  
#### <a name="to-add-a-chart-in-excel"></a>Excel'de bir grafik eklemek için  
  
1.  Üzerinde **Ekle** sekmesinde **grafikleri** grubunda **sütun**ve ardından **tüm grafik türleri**.  
  
2.  İçinde **Grafik Ekle** iletişim kutusu, tıklatın **Tamam**.  
  
3.  Üzerinde **tasarım** sekmesinde **veri** grubunda **veri Seç**.  
  
4.  İçinde **veri kaynağı Seç** iletişim kutusu, tıklatın **Chartdata aralığı** kutusuna ve herhangi bir varsayılan seçimi temizleyin.  
  
5.  İçinde **grafiği için veri** sayfası, sol üst köşedeki E8 için sağ alt köşesindeki A4 içerir sayıları içeren hücre bloklarını seçin.  
  
6.  İçinde **veri kaynağı Seç** iletişim kutusu, tıklatın **Tamam**.  
  
7.  Grafiği yeniden konumlandırın hücreyle ekranın sağ üst köşesine hizalar **E2**.  
  
8.  C sürücüsünün dosyanızı kaydedin ve adlandırın **ExcelChart.xlsx**.  
  
9. Excel çıkın.  
  
## <a name="creating-a-new-project"></a>Yeni proje oluşturma  
 Bu adımda, temel bir Excel çalışma kitabı projesi oluşturacak **ExcelChart** çalışma kitabı.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **My Excel Chart**. Sihirbazı'nda seçin **var olan bir belgeyi kopyalama**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Tıklatın **Gözat** bu kılavuzda daha önce oluşturduğunuz çalışma kitabı ve beraberinde düğmeyi ve göz atın.  
  
3.  **Tamam**'ı tıklatın.  
  
     Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **My Excel Chart** için proje **Çözüm Gezgini**.  
  
## <a name="setting-properties-of-the-chart"></a>Grafik özelliklerini ayarlama  
 Varolan bir çalışma kitabını kullanan yeni bir Excel çalışma kitabı proje oluşturduğunuzda, ana bilgisayar denetimleri tüm adlandırılmış aralıklar, liste nesneleri ve çalışma kitabını grafiklerde için otomatik olarak oluşturulur. Adını değiştirebilirsiniz <xref:Microsoft.Office.Tools.Excel.Chart> kullanarak denetim **özellikleri** penceresi.  
  
#### <a name="to-change-the-name-of-the-chart-control"></a>Grafik denetimi adını değiştirmek için  
  
1.  Seçin <xref:Microsoft.Office.Tools.Excel.Chart> Denetim Tasarımcısı'nda ve aşağıdaki özellikleri değiştirin **özellikleri** penceresi.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**dataChart**|  
    |**HasLegend**|**false**|  
  
## <a name="adding-controls"></a>Denetimler ekleme  
 Bu çalışma radyo düğmeleri kullanıcılar hızla grafik stilini değiştirmek için bir yol sağlamak için kullanır. Ancak, özel olarak radyo düğmeleri gerekir — bir düğme seçildiğinde, aynı anda gruptaki başka bir düğmesi seçilebilir. Bir çalışma sayfasına birkaç radyo düğmeleri eklediğinizde bu davranışı varsayılan olarak gerçekleşmez.  
  
 Bu, bir kullanıcı denetimi radyo düğmeleri grubuna davranıştır eklemek için bir yol kodunuzu kullanıcı denetiminin arkasında yazın ve ardından kullanıcı denetiminin çalışma sayfasına ekleyin.  
  
#### <a name="to-add-a-user-control"></a>Bir kullanıcı denetimi eklemek için  
  
1.  Seçin **My Excel Chart** proje **Çözüm Gezgini**.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusu, tıklatın **kullanıcı denetimi**, denetimi adlandırın **ChartOptions** tıklatıp **Ekle**.  
  
#### <a name="to-add-radio-buttons-to-the-user-control"></a>Kullanıcı denetimi radyo düğmeleri eklemek için  
  
1.  Kullanıcı denetimi Tasarımcısı'nda görünür durumda değilse, çift **ChartOptions** içinde **Çözüm Gezgini**.  
  
2.  Gelen **ortak denetimler** sekmesinde **araç**, sürükleyin bir **radyo düğmesi** denetlemek için kullanıcı denetimi ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**columnChart**|  
    |**Metin**|**Sütun grafiği**|  
  
3.  Kullanıcı denetimine ikinci radyo düğmesi ekleyin ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**barChart**|  
    |**Metin**|**Çubuk grafiği**|  
  
4.  Kullanıcı denetimine üçüncü radyo düğmesini ekleyin ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**lineChart**|  
    |**Metin**|**Çizgi grafiği**|  
  
5.  Kullanıcı denetimine dördüncü radyo düğmesini ekleyin ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**areaBlockChart**|  
    |**Metin**|**Alan blok grafiği**|  
  
 Ardından, radyo düğmesine tıklandığında grafik güncellemek için kod yazma.  
  
## <a name="changing-the-chart-style-when-a-radio-button-is-selected"></a>Grafik stili olduğunda bir radyo düğmesi değiştirme seçili  
 Artık grafik stilini değiştirmek için kodu ekleyebilirsiniz. Bunu yapmak için kullanıcı denetiminde ortak olay oluşturun, seçim türünü ayarlamak için özellik ekleme ve bir olay işleyicisi oluşturun `CheckedChanged` her radyo düğmesinin olay.  
  
#### <a name="to-create-an-event-and-property-on-a-user-control"></a>Bir olay ve özellik bir kullanıcı denetimi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kullanıcı denetimi sağ tıklatın ve ardından **görünümü kodu**.  
  
2.  Kodu ekleyin `ChartOptions` sınıfı oluşturmak için bir `SelectionChanged` olay ve `Selection` özelliği.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#13](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#13)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#13)]  
  
#### <a name="to-handle-the-checkedchanged-event-of-the-radio-buttons"></a>Radyo düğmeleri CheckedChanged olayını işlemek için  
  
1.  Grafik türünü ayarlayın `CheckedChanged` olay işleyicisi `areaBlockChart` radyo düğmesinin ve olayı oluşturun.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#14](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#14)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#14)]  
  
2.  Grafik türünü ayarlayın `CheckedChanged` olay işleyicisi `barChart` radyo düğmesi.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#15](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#15)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#15](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#15)]  
  
3.  Grafik türünü ayarlayın `CheckedChanged` olay işleyicisi `columnChart` radyo düğmesi.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#16](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#16)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#16)]  
  
4.  Grafik türünü ayarlayın `CheckedChanged` olay işleyicisi `lineChart` radyo düğmesi.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#17](../vsto/codesnippet/VisualBasic/my excel chart/ChartOptions.vb#17)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#17)]  
  
5.  C# ' ta radyo düğmeleri için olay işleyicileri eklemeniz gerekir. Kod ekleyebilirsiniz `ChartOptions` çağrısı altındaki Oluşturucusu `InitializeComponent`. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/ChartOptions.cs#18)]  
  
## <a name="adding-the-user-control-to-the-worksheet"></a>Kullanıcı denetiminin çalışma sayfasına ekleme  
 Çözümü yapılandırdığınızda, yeni kullanıcı denetimi otomatik olarak eklenir **araç**. Denetimden sonra sürükleyebilirsiniz **araç** çalışma için.  
  
#### <a name="to-add-the-user-control-your-worksheet"></a>Kullanıcı denetiminin çalışma eklemek için  
  
1.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     **ChartOptions** kullanıcı denetimi eklenen **araç**.  
  
2.  İçinde **Çözüm Gezgini**, sağ **Sheet1.vb** veya **Sheet1.cs**ve ardından **Görünüm Tasarımcısı**.  
  
3.  Sürükleme **ChartOptions** gelen denetim **araç** çalışma.  
  
     Adlı yeni bir denetim `my_Excel_Chart_ChartOptions1` projenize eklenir.  
  
4.  Denetime adını değiştirmek **ChartOptions1**.  
  
## <a name="changing-the-chart-type"></a>Grafik türünü değiştirme  
 Grafik türünü değiştirmek için kullanıcı denetimi seçeneğe göre stilini ayarlar bir olay işleyicisi oluşturun.  
  
#### <a name="to-change-the-type-of-chart-that-is-displayed-in-the-worksheet"></a>Çalışma sayfasında görüntülenen grafik türünü değiştirmek için  
  
1.  Aşağıdaki olay işleyicisi ekleme `Sheet1` sınıfı.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#19](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#19)]
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#19)]  
  
2.  C# ' ta kullanıcı denetimi için bir olay işleyicisi eklemelisiniz <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> aşağıda gösterildiği gibi olay. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-cs[Trin_VstcoreProgrammingControlsExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#20)]  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Radyo düğmesini seçtiğinizde grafik doğru biçimlendirilmiş doğrulamak için çalışma kitabınızı artık test edebilirsiniz.  
  
#### <a name="to-test-your-workbook"></a>Çalışma kitabınız sınamak için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Çeşitli radyo düğmeleri seçin.  
  
3.  Grafik stilini seçimle eşleşecek şekilde değiştiğini doğrulayın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuzda radyo düğmeleri ve grafik stilleri çalışma sayfalarında kullanım temellerini gösterir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Projeyi dağıtma. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
-   Bir metin kutusunu doldurmak için düğme kullanarak. Daha fazla bilgi için bkz: [izlenecek yol: çalışma sayfasını kullanarak bir düğme metin kutusunda metin görüntüleme](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md).  
  
-   Çalışma sayfasında onay kutularını kullanarak biçimlendirmeyi değiştirme. Daha fazla bilgi için bkz: [izlenecek yol: değiştirme çalışma sayfası biçimlendirmesini kullanarak onay kutusu denetimleri](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Excel Kullanarak İzlenecek Yollar](../vsto/walkthroughs-using-excel.md)  
  
  