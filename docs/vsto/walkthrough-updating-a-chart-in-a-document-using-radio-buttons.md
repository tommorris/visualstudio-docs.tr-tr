---
title: 'İzlenecek yol: radyo düğmelerini kullanarak belgede grafik güncelleştir'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], updating using controls
- controls [Office development in Visual Studio], updating documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a72a5cb07f39f8d2acaec59e5da5a66a30293453
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258226"
---
# <a name="walkthrough-update-a-chart-in-a-document-using-radio-buttons"></a>İzlenecek yol: radyo düğmelerini kullanarak belgede grafik güncelleştir
  Bu anlatımda radyo düğmeleri Microsoft Office Word için belge düzeyi özelleştirmelerinde kullanıcıların belgede grafik türlerini seçmek için seçenek sunmak amacıyla nasıl kullanılacağı gösterilir.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Grafik belge düzeyi projesindeki belgeye çalışma zamanında ekleme.  
  
-   Bir kullanıcı denetimi ekleyerek radyo düğmelerini gruplandırma.  
  
-   Bir seçenek belirlendiğinde, grafik stilini değiştirme.  
  
 Sonuç tamamlanmış bir örnek görmek için Word denetimleri örneğine bakın [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="create-the-project"></a>Projeyi oluşturma  
 İlk adım bir Word belgesi proje oluşturmaktır.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir Word belgesi proje oluşturun **My grafik seçenekleri**. Sihirbazı'nda seçin **bir yeni belge oluşturun**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio tasarımcıda yeni Word belgesini açar ve ekler **My grafik seçenekleri** için proje **Çözüm Gezgini**.  
  
## <a name="add-a-chart-to-the-document"></a>Belgeye bir grafik ekleyin  
  
### <a name="to-add-a-chart"></a>Grafik eklemek için  
  
1.  Şerit üzerindeki Visual Studio tasarımcısında Word belgesinde tıklatın **Ekle** sekmesi.  
  
2.  İçinde **metin** grubunda **Nesne Ekle** açılan düğmesine ve tıklatın **nesne**.  
  
     **Nesne** iletişim kutusu açılır.  
  
3.  İçinde **nesne türü** listesini **Yeni Oluştur** sekmesine **Microsoft Graph grafiği** ve ardından **Tamam**.  
  
     Bir grafik ekleme noktasına belgeye eklenir ve **veri** penceresi bazı varsayılan verilerle birlikte görüntülenir.  
  
4.  Kapat **veri** penceresi grafikteki varsayılan değerleri kabul edin ve odağı grafikten taşımak için belge içindeki'ı tıklatın.  
  
5.  Grafiğin sağ tıklayın ve ardından **biçimi nesne**.  
  
6.  Üzerinde **düzeni** sekmesinde **biçimi nesne** iletişim kutusunda **kare** tıklatıp **Tamam**.  
  
## <a name="add-a-user-control-to-the-project"></a>Projeye bir kullanıcı denetimi Ekle  
 Varsayılan bir belge radyo düğmeleri birbirini dışlamaz. Bunları doğru bunları bir kullanıcı denetimi ekleyerek ve ardından seçimi denetlemek için kod yazma işlev yapabilirsiniz.  
  
### <a name="to-add-a-user-control"></a>Bir kullanıcı denetimi eklemek için  
  
1.  Seçin **My grafik seçenekleri** proje **Çözüm Gezgini**.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusu, tıklatın **kullanıcı denetimi**, denetimi adlandırın **ChartOptions** tıklatıp **Ekle**.  
  
### <a name="to-add-windows-form-controls-to-the-user-control"></a>Kullanıcı denetimine Windows Form denetimi eklemek için  
  
1.  Kullanıcı denetimi Tasarımcısı'nda görünür durumda değilse, çift **ChartOptions** içinde **Çözüm Gezgini**.  
  
2.  Gelen **ortak denetimler** sekmesinde **araç**, ilk sürükleyin **radyo düğmesi** denetlemek için kullanıcı denetimi ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**columnChart**|  
    |**Metin**|**Sütun grafiği**|  
  
3.  İkinci bir ekleme **radyo düğmesi** kullanıcıya denetlemek ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**barChart**|  
    |**Metin**|**Çubuk grafiği**|  
  
4.  Bir üçüncü ekleyin **radyo düğmesi** kullanıcıya denetlemek ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**lineChart**|  
    |**Metin**|**Çizgi grafiği**|  
  
5.  Dördüncü eklemek **radyo düğmesi** kullanıcıya denetlemek ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**areaBlockChart**|  
    |**Metin**|**Alan blok grafiği**|  
  
## <a name="add-references"></a>Başvuruları ekleme  
 Bir belge kullanıcı denetiminden grafik erişmek için bir başvuru içermelidir `Microsoft.Office.Interop.Graph` projenizdeki derleme.  
  
### <a name="to-add-a-reference-to-the-microsoftofficeinteropgraph-assembly"></a>Microsoft.Office.Interop.Graph derlemesine başvuru eklemek için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Başvuru Ekle**.  
  
     **Başvuru Ekle** iletişim kutusu görüntülenir.  
  
2.  Üzerinde **.NET** sekmesine **Microsoft.Office.Interop.Graph** tıklatıp **Tamam**. Derleme sürümünü 14.0.0.0 seçin.  
  
## <a name="change-the-chart-style-when-a-radio-button-is-selected"></a>Radyo düğmesi seçildiğinde grafik stilini değiştirme  
 Düzgün çalışması, bir ortak olay kullanıcı denetimi oluşturma düğmeleri yapmak için Seçim türünü ayarlamak için özellik ekleme ve için bir yordam oluşturma `CheckedChanged` her radyo düğmesinin olay.  
  
### <a name="to-create-an-event-and-property-on-a-user-control"></a>Bir olay ve özellik bir kullanıcı denetimi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, kullanıcı denetimi sağ tıklatın ve ardından **görünümü kodu**.  
  
2.  Oluşturmak için kodu ekleyin bir `SelectionChanged` olay ve `Selection` özelliğine `ChartOptions` sınıfı.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#9](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#9)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#9](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#9)]  
  
### <a name="to-handle-the-checkedchange-event-of-the-radio-buttons"></a>Radyo düğmeleri CheckedChange olayını işlemek için  
  
1.  Grafik türünü ayarlayın `CheckedChanged` olay işleyicisi `areaBlockChart` radyo düğmesinin ve olayı oluşturun.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#10](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#10)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#10](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#10)]  
  
2.  Grafik türünü ayarlayın `CheckedChanged` olay işleyicisi `barChart` radyo düğmesi.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#11](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#11)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#11](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#11)]  
  
3.  Grafik türünü ayarlayın `CheckedChanged` olay işleyicisi `columnChart` radyo düğmesi.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#12](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#12)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#12](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#12)]  
  
4.  Grafik türünü ayarlayın `CheckedChanged` olay işleyicisi `lineChart` radyo düğmesi.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#13](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#13)]
     [!code-vb[Trin_VstcoreProgrammingControlsWord#13](../vsto/codesnippet/VisualBasic/my chart options/ChartOptions.vb#13)]  
  
5.  C# ' ta radyo düğmeleri için olay işleyicileri eklemeniz gerekir. Kod ekleyebilirsiniz `ChartOptions` çağrısı altındaki Oluşturucusu `InitializeComponent`. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#14](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ChartOptions.cs#14)]  
  
## <a name="add-the-user-control-to-the-document"></a>Belgeye kullanıcı denetimi Ekle  
 Çözümü yapılandırdığınızda, yeni kullanıcı denetimi otomatik olarak eklenir **araç**. Denetimden sonra sürükleyebilirsiniz **araç** belgenize.  
  
### <a name="to-add-the-user-control-your-document"></a>Kullanıcı denetimi belgenizi eklemek için  
  
1.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     **ChartOptions** kullanıcı denetimi eklenen **araç**.  
  
2.  İçinde **Çözüm Gezgini**, sağ **ThisDocument.vb** veya **ThisDocument.vb**ve ardından **Görünüm Tasarımcısı**.  
  
3.  Sürükleme `ChartOptions` gelen denetim **araç** belge.  
  
     İçinde **özellikleri** penceresinde, belgeye eklediğiniz yeni denetim adı `ChartOptions1`.  
  
## <a name="change-the-chart-type"></a>Grafik türünü değiştir  
 Grafik türünü, kullanıcı denetimi belirlediğiniz seçeneğe göre değiştirmek için bir olay işleyicisi oluşturun.  
  
### <a name="to-change-the-type-of-chart-that-is-displayed-in-the-document"></a>Belgede görüntülenen grafik türünü değiştirmek için  
  
1.  Aşağıdaki olay işleyicisi ekleme `ThisDocument` sınıfı.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#15](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#15)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#15](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#15)]  
  
2.  C# ' ta kullanıcı denetimi için bir olay işleyicisi eklemelisiniz <xref:Microsoft.Office.Tools.Word.Document.Startup> olay.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#16](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#16)]  
  
## <a name="test-the-application"></a>Uygulamayı test etme  
 Radyo düğmesini seçtiğinizde grafik stilini doğru güncelleştirildiğinden emin olmak için belgenizi artık test edebilirsiniz.  
  
### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Tuşuna **F5** projeyi çalıştırın.  
  
2.  Çeşitli radyo düğmeleri seçin.  
  
3.  Grafik stilini seçimle eşleşecek şekilde değiştiğini doğrulayın.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Bir metin kutusunu doldurmak için düğme kullanarak. Daha fazla bilgi için bkz: [izlenecek yol: bir belgeyi bir düğme kullanarak metin kutusunda metin görüntüleme](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md).  
  
-   Açılan kutudan bir stil seçerek biçimlendirme değiştirin. Daha fazla bilgi için bkz: [izlenecek yol: CheckBox denetimlerini kullanarak belge değişikliği biçimlendirme](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Word'ü kullanarak izlenecek yollar](../vsto/walkthroughs-using-word.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Office belgelerindeki Windows Forms denetimleri sınırlamaları](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  