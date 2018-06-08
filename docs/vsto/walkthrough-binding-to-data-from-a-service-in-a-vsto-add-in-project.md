---
title: 'İzlenecek yol: bir VSTO eklenti projesindeki içinde hizmet verilere bağlama'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d3c7ed095d0efe756e7a23409cd5a54f9e6dcda8
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845879"
---
# <a name="walkthrough-bind-to-data-from-a-service-in-a-vsto-add-in-project"></a>İzlenecek yol: VSTO eklenti projesindeki hizmetinden verilere bağlama
  Konak denetimleri VSTO eklentisi projelerine veri bağlayabilirsiniz. Bu kılavuz, Microsoft Office Word belgesine denetimleri ekleme, MSDN içerik hizmetinden alınan verilere denetimler bağlama ve çalışma zamanında olaylara yanıt gösterilmiştir.  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler Word 2010 uygulama düzeyi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Ekleme bir <xref:Microsoft.Office.Tools.Word.RichTextContentControl> bir belgeye çalışma zamanında denetim.  
  
-   Bağlama <xref:Microsoft.Office.Tools.Word.RichTextContentControl> bir web hizmetinden veri denetim.  
  
-   Yanıt <xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering> olayı bir <xref:Microsoft.Office.Tools.Word.RichTextContentControl> denetim.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].  
  
## <a name="create-a-new-project"></a>Yeni bir proje oluşturma  
 İlk adım bir Word VSTO eklenti projesi oluşturmaktır.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir Word VSTO eklenti projesi oluşturun **MTPS Content Service**, Visual Basic veya C# kullanarak.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio açılır `ThisAddIn.vb` veya `ThisAddIn.cs` dosya ve projeye ekler **Çözüm Gezgini**.  
  
## <a name="add-a-web-service"></a>Bir web hizmeti Ekle  
 Bu kılavuzda MTPS Content Service adında bir web hizmetini kullanır. Bu web hizmeti belirtilen bir MSDN makalesine bir XML dizesi veya düz metin biçiminde bilgi verir. Bir sonraki adımda döndürülen bilgilerin bir içerik denetimi görüntüleme gösterilmektedir.  
  
### <a name="to-add-the-mtps-content-service-to-the-project"></a>Projeye MTPS içerik hizmeti eklemek için  
  
1.  Üzerinde **veri** menüsünde tıklatın **yeni veri kaynağı Ekle**.  
  
2.  İçinde **veri kaynağı Yapılandırma Sihirbazı**, tıklatın **hizmet**ve ardından **sonraki**.  
  
3.  İçinde **adresi** alan, şu URL'yi yazın:  
  
     **http://services.msdn.microsoft.com/ContentServices/ContentService.asmx**  
  
4.  tıklatın **Git**.  
  
5.  İçinde **Namespace** alanında, yazın **ContentService**, tıklatıp **Tamam**.  
  
6.  İçinde **başvuru Ekleme Sihirbazı** iletişim kutusu, tıklatın **son**.  
  
## <a name="add-a-content-control-and-bind-to-data-at-runtime"></a>İçerik denetimi eklemek ve çalışma zamanında verilere bağlayın  
 VSTO eklentisi projelerine ekleme ve çalışma zamanında denetimler bağlayın. Bu kılavuz için bir kullanıcı içindeki denetim tıkladığında web hizmetinden veri almak için içerik denetimi yapılandırın.  
  
### <a name="to-add-a-content-control-and-bind-to-data"></a>İçerik denetimi eklemek ve verilere bağlama  
  
1.  İçinde `ThisAddIn` sınıfı, MTPS Content Service'i, içerik denetimi ve veri bağlama için değişkenleri tanımlayın.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#2)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#2)]  
  
2.  Aşağıdaki yöntemi ekleyin `ThisAddIn` sınıfı. Bu yöntem, içerik denetimi etkin belgeyi başında oluşturur.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#4)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#4](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#4)]  
  
3.  Aşağıdaki yöntemi ekleyin `ThisAddIn` sınıfı. Bu yöntem oluşturmak ve web hizmetine bir istek göndermek için gerekli olan nesneler başlatır.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#6)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#6](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#6)]  
  
4.  Bir kullanıcı içeriği içinde tıkladığında denetimleri denetlemek ve içerik denetimine veri bağlama içerikle ilgili MSDN Kitaplığı belge almak için bir olay işleyicisi oluşturun.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#5)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#5](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#5)]  
  
5.  Çağrı `AddRichTextControlAtRange` ve `InitializeServiceObjects` yöntemleri `ThisAddIn_Startup` yöntemi. C# programcıları için olay işleyici ekleyin.  
  
     [!code-csharp[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/CSharp/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.cs#3)]
     [!code-vb[Trin_WordAddIn_BindingDataToContentControl#3](../vsto/codesnippet/VisualBasic/trin_wordaddin_bindingdatatocontentcontrol/ThisAddIn.vb#3)]  
  
## <a name="test-the-add-in"></a>Eklenti test  
 Word ' ü açtığınızda <xref:Microsoft.Office.Tools.Word.RichTextContentControl> denetimi görünür. İçinde tıklattığınızda denetim değişiklikleri metin.  
  
### <a name="to-test-the-vsto-add-in"></a>VSTO eklenti sınamak için  
  
1.  Tuşuna **F5**.  
  
2.  İçerik denetimi içinde'ı tıklatın.  
  
     Bilgi MTPS Content Service'ten indirilir ve içerik denetiminin içinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  