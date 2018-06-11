---
title: 'İzlenecek yol: Eylemler bölmesinden belgeye metin ekleme'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- smart documents [Office development in Visual Studio], creating in Word
- smart documents [Office development in Visual Studio], adding controls
- actions panes [Office development in Visual Studio], creating in Word
- actions panes [Office development in Visual Studio], adding controls
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 488b885b40b4cda064ae15438822ab85725526ac
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258486"
---
# <a name="walkthrough-insert-text-into-a-document-from-an-actions-pane"></a>İzlenecek yol: Eylemler bölmesinden belgeye metin ekleme
  Bu kılavuz, Microsoft Office Word belgesinde Eylemler bölmesi oluşturmak gösterilmiştir. Eylemler bölmesinde giriş toplayan ve ardından metin belgesine göndermek iki denetimi içerir.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Windows Forms denetimlerindeki Eylemler bölmesi denetimi kullanarak bir arabirim tasarlayın.  
  
-   Uygulama açıldığında eylemler bölmesini görüntüler.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="create-the-project"></a>Projeyi oluşturma  
 İlk adım bir Word belgesi proje oluşturmaktır.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir Word belgesi proje oluşturun **My temel Eylemler bölmesi**. Sihirbazı'nda seçin **bir yeni belge oluşturun**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio tasarımcıda yeni Word belgesini açar ve ekler **My temel Eylemler bölmesi** için proje **Çözüm Gezgini**.  
  
## <a name="add-text-and-bookmarks-to-the-document"></a>Belgeye metin ve yer işaretleri ekleme  
 Eylemler bölmesinde yer işaretleri belgedeki metin gönderir. Belgeyi tasarlamak için bir temel form oluşturmak için bazı metni yazın.  
  
### <a name="to-add-text-to-your-document"></a>Metin belgenize eklemek için  
  
1.  Word belgesine aşağıdaki metni yazın:  
  
     **21 Mart 2008**  
  
     **Ad**  
  
     **Adres**  
  
     **Bu, Word temel Eylemler bölmesinde örneğidir.**  
  
 Ekleyebileceğiniz bir <xref:Microsoft.Office.Tools.Word.Bookmark> buradan sürükleyerek belgenize denetimi **araç** kullanarak veya Visual Studio'da **yer işareti** Word iletişim kutusunda.  
  
### <a name="to-add-a-bookmark-control-to-your-document"></a>Bir yer işareti denetimi belgenize eklemek için  
  
1.  Gelen **Word denetimleri** sekmesinde **araç**, sürükleyin bir <xref:Microsoft.Office.Tools.Word.Bookmark> belgenize denetimi.  
  
     **Yer işareti Denetimi Ekle** iletişim kutusu görüntülenir.  
  
2.  Word seçin **adı**olmadan paragraf işaretini seçerek ve tıklatın **Tamam**.  
  
    > [!NOTE]  
    >  Paragraf işaretlerini dışında yer işareti olmalıdır. Paragraf işaretleri belgede görünür değilse tıklatın **Araçları** menüsündeki **Microsoft Office Word Araçları** ve ardından **seçenekleri**. Tıklatın **Görünüm** sekmesini tıklatın ve seçin **paragraf işaretleri** onay kutusuna **Biçimlendirme işaretleri** bölümünü **seçenekleri** iletişim kutusu.  
  
3.  İçinde **özellikleri** penceresinde, değişiklik **adı** özelliği **Bookmark1** için **showName**.  
  
4.  Word seçin **adresi**, paragraf işaretlerini seçmeden.  
  
5.  Üzerinde **Ekle** Şerit sekmesi, **bağlantılar** grubunda **yer işareti**.  
  
6.  İçinde **yer işareti** iletişim kutusuna **showAddress** içinde **yer işareti adı** kutusuna ve tıklatın **Ekle**.  
  
## <a name="add-controls-to-the-actions-pane"></a>Eylemler bölmesine denetimleri ekleme  
 Eylemler bölmesi arabirimini tasarlamak için bir eylemler bölmesi denetimi projeye ekleyin ve sonra Eylemler bölmesinde denetimine Windows Forms denetimleri ekleyin.  
  
### <a name="to-add-an-actions-pane-control"></a>Eylemler bölmesi denetimi eklemek için  
  
1.  Seçin **My temel Eylemler bölmesi** proje **Çözüm Gezgini**.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusu, tıklatın **Eylemler bölmesi denetimi**, denetimi adlandırın **InsertTextControl'ü,** tıklatıp **Ekle**.  
  
#### <a name="to-add-windows-form-controls-to-the-actions-pane-control"></a>Eylemler bölmesi denetimine Windows Form denetimi eklemek için  
  
1.  Eylemler bölmesi denetimi tasarımcıda görünür durumda değilse, çift **InsertTextControl'ü**.  
  
2.  Gelen **ortak denetimler** sekmesinde **araç**, sürükleyin bir **etiket** Eylemler bölmesi denetimi için denetim.  
  
3.  Değişiklik **metin** etiket denetimi özelliği **adı**.  
  
4.  Ekleme bir **Textbox** Eylemler bölmesi denetimine denetlemek ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**GetName**|  
    |**Boyutu**|**130, 20**|  
  
5.  İkinci bir ekleme **etiket** Eylemler bölmesi denetimine denetlemek ve değiştirme **metin** özelliğine **adresi**.  
  
6.  İkinci bir ekleme **Textbox** Eylemler bölmesi denetimine denetlemek ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**GetAddress**|  
    |**Return kabul eder**|**TRUE**|  
    |**Çok satırlı**|**TRUE**|  
    |**Boyutu**|**130, 40**|  
  
7.  Ekleme bir **düğmesini** Eylemler bölmesi denetimine denetlemek ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**addText**|  
    |**Metin**|**Ekle**|  
  
## <a name="add-code-to-insert-text-into-the-document"></a>Belgeye metin eklemek için kodu ekleyin  
 Eylemler bölmesinde metni metin kutularından uygun ekler kod yazmayı <xref:Microsoft.Office.Tools.Word.Bookmark> denetimlerini belgede. Kullanabileceğiniz `Globals` belgede denetimleri eylemler bölmesindeki denetimlere erişmek için sınıf. Daha fazla bilgi için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
### <a name="to-insert-text-from-the-actions-pane-in-a-bookmark-in-the-document"></a>Belgesindeki bir yer işareti Eylemler bölmesinden metin eklemek için  
  
1.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> olay işleyicisi **addText** düğmesi.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#8](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/InsertTextControl.cs#8)]
     [!code-vb[Trin_VstcoreActionsPaneWord#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/InsertTextControl.vb#8)]  
  
2.  C# ' ta düğmesini tıklatın için bir olay işleyicisi eklemeniz gerekir. Bu kodu koyabilirsiniz `InsertTextControl` çağrısından sonra Oluşturucusu `IntializeComponent`. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#9](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/InsertTextControl.cs#9)]  
  
## <a name="add-code-to-show-the-actions-pane"></a>Eylemler bölmesini göstermek için kodu ekleyin  
 Eylemler bölmesini göstermek için oluşturduğunuz denetimi denetim koleksiyonuna ekleyin.  
  
### <a name="to-show-the-actions-pane"></a>Eylemler bölmesini göstermek için  
  
1.  Eylemler bölmesi denetiminin yeni bir örneğini oluşturmak `ThisDocument` sınıfı.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#10](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#10)]
     [!code-vb[Trin_VstcoreActionsPaneWord#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#10)]  
  
2.  Aşağıdaki kodu ekleyin <xref:Microsoft.Office.Tools.Word.Document.Startup> olay işleyicisi `ThisDocument`.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#11](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#11)]
     [!code-vb[Trin_VstcoreActionsPaneWord#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#11)]  
  
## <a name="test-the-application"></a>Uygulamayı test etme  
 Eylemler bölmesinde belge açılır ve düğmesine tıklandığında metin metin kutularına yazılan işaretlerine eklendiğini doğrulamak için belgenizi test edin.  
  
### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Tuşuna **F5** projeyi çalıştırın.  
  
2.  Eylemler bölmesinde görünür olduğunu doğrulayın.  
  
3.  Adınızı ve adresinizi eylemler bölmesindeki metin kutularına yazın ve tıklatın **Ekle**.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Eylemler bölmesi Excel'de oluşturun. Daha fazla bilgi için bkz: [nasıl yapılır: Excel çalışma kitaplarına Eylemler bölmesi ekleme](http://msdn.microsoft.com/en-us/62abfce6-e44f-419d-85d8-26bf59f33872).  
  
-   Eylemler bölmesindeki denetimlere veri bağlama. Daha fazla bilgi için bkz: [izlenecek yol: Word eylemler bölmesindeki denetimlere veri bağlama](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Nasıl yapılır: Word belgelerine Eylemler bölmesi ekleme veya Excel çalışma kitapları](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Nasıl yapılır: Excel çalışma kitaplarına Eylemler bölmesi ekleme](http://msdn.microsoft.com/en-us/62abfce6-e44f-419d-85d8-26bf59f33872)   
 [Nasıl yapılır: Eylemler bölmesindeki denetim düzenini yönetme](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Yer işareti denetimi](../vsto/bookmark-control.md)  
  
  