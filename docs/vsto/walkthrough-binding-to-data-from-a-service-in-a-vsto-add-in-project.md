---
title: "İzlenecek yol: Veri bağlamanın bir VSTO içinde hizmet eklenti proje | Microsoft Docs"
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
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
ms.assetid: 9b008be4-06a3-4ffc-9f02-79dd6cfe00ab
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6874dd125c692b6d853dc89cc533bf3d623aad51
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-binding-to-data-from-a-service-in-a-vsto-add-in-project"></a>İzlenecek yol: Bir VSTO eklenti projesindeki içinde hizmetinden veri bağlama
  Konak denetimleri VSTO eklentisi projelerine veri bağlayabilirsiniz. Bu kılavuz, Microsoft Office Word belgesine denetimleri ekleme, MSDN içerik hizmetinden alınan verilere denetimler bağlama ve çalışma zamanında olaylara yanıt gösterilmiştir.  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler Word 2010 uygulama düzeyi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Word.RichTextContentControl> bir belgeye çalışma zamanında denetim.  
  
-   Bağlama <xref:Microsoft.Office.Tools.Word.RichTextContentControl> bir Web hizmetinden veri denetim.  
  
-   Yanıt <xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering> olayı bir <xref:Microsoft.Office.Tools.Word.RichTextContentControl> denetim.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="creating-a-new-project"></a>Yeni proje oluşturma  
 İlk adım bir Word VSTO eklenti projesi oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir Word VSTO eklenti projesi oluşturun **MTPS Content Service**, Visual Basic veya C# kullanarak.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio açılır `ThisAddIn.vb` veya `ThisAddIn.cs` dosya ve projeye ekler **Çözüm Gezgini**.  
  
## <a name="adding-a-web-service"></a>Web hizmeti ekleme  
 Bu kılavuzda MTPS Content Service adında bir Web hizmetini kullanır. Bu Web hizmeti belirtilen bir MSDN makalesine bir XML dizesi veya düz metin biçiminde bilgi verir. Bir sonraki adımda döndürülen bilgilerin bir içerik denetimi görüntüleme gösterilmektedir.  
  
#### <a name="to-add-the-mtps-content-service-to-the-project"></a>Projeye MTPS içerik hizmeti eklemek için  
  
1.  Üzerinde **veri** menüsünde tıklatın **yeni veri kaynağı Ekle**.  
  
2.  İçinde **veri kaynağı Yapılandırma Sihirbazı**, tıklatın **hizmet**ve ardından **sonraki**.  
  
3.  İçinde **adresi** alan, şu URL'yi yazın:  
  
     **http://Services.msdn.microsoft.com/ContentServices/contentservice.asmx**  
  
4.  tıklatın **Git**.  
  
5.  İçinde **Namespace** alanında, yazın **ContentService**, tıklatıp **Tamam**.  
  
6.  İçinde **başvuru Ekleme Sihirbazı** iletişim kutusu, tıklatın **son**.  
  
## <a name="adding-a-content-control-and-binding-to-data-at-run-time"></a>İçerik denetimi ekleme ve çalışma zamanında veri bağlama  
 VSTO eklentisi projelerine ekleme ve çalışma zamanında denetimler bağlayın. Bu kılavuz için bir kullanıcı içindeki denetim tıkladığında Web hizmetinden veri almak için içerik denetimi yapılandırın.  
  
#### <a name="to-add-a-content-control-and-bind-to-data"></a>İçerik denetimi eklemek ve verilere bağlama  
  
1.  İçinde `ThisAddIn` sınıfı, MTPS Content Service'i, içerik denetimi ve veri bağlama için değişkenleri tanımlayın.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#2)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#2)]  
  
2.  Aşağıdaki yöntemi ekleyin `ThisAddIn` sınıfı. Bu yöntem, içerik denetimi etkin belgeyi başında oluşturur.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#4)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#4)]  
  
3.  Aşağıdaki yöntemi ekleyin `ThisAddIn` sınıfı. Bu yöntem oluşturmak ve Web hizmetine bir istek göndermek için gerekli olan nesneler başlatır.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#6)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#6)]  
  
4.  Bir kullanıcı içeriği içinde tıkladığında denetimleri denetlemek ve içerik denetimine veri bağlama içerikle ilgili MSDN Kitaplığı belge almak için bir olay işleyicisi oluşturun.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#5)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#5)]  
  
5.  Çağrı `AddRichTextControlAtRange` ve `InitializeServiceObjects` yöntemleri `ThisAddIn_Startup` yöntemi. C# programcıları için olay işleyici ekleyin.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#3)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#3)]  
  
## <a name="testing-the-add-in"></a>Eklentiyi test etme  
 Word ' ü açtığınızda <xref:Microsoft.Office.Tools.Word.RichTextContentControl> denetimi görünür. İçinde tıklattığınızda denetim değişiklikleri metin.  
  
#### <a name="to-test-the-vsto-add-in"></a>VSTO eklenti sınamak için  
  
1.  Tuşuna **F5**.  
  
2.  İçerik denetimi içinde'ı tıklatın.  
  
     Bilgi MTPS Content Service'ten indirilir ve içerik denetiminin içinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  