---
title: "İzlenecek yol: bir Windows formu kullanarak veri toplama | Microsoft Docs"
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
- data [Office development in Visual Studio], Windows Forms
- Windows Forms [Office development in Visual Studio], collecting data
- forms [Office development in Visual Studio], walkthroughs
- worksheets [Office development in Visual Studio], collecting data
ms.assetid: 40e87f7f-cfbb-4761-bf1b-d042f45f4f09
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d52a97e57701159a8ff64a106a92f181b50df66f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-collecting-data-using-a-windows-form"></a>İzlenecek Yol: Windows Formu Kullanarak Veri Toplama
  Bu kılavuz, Windows formu Microsoft Office Excel için belge düzeyi özelleştirme açmak, kullanıcıdan bilgi toplamak ve bu bilgileri çalışma sayfası hücresine yazma gösterilmiştir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Excel için belge düzeyi projesi bu kılavuzda özellikle kullansa da, izlenecek yol tarafından gösterilen kavramlar diğer Office projeleri için geçerlidir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="creating-a-new-project"></a>Yeni proje oluşturma  
 İlk adım, bir Excel çalışma kitabı projesi oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel çalışma kitabı projesi oluşturun **girdiWinFormu**seçip **bir yeni belge oluşturun** Sihirbazı'nda. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio Tasarımcısı'nda yeni Excel çalışma kitabı açılır ve ekler **girdiWinFormu** için proje **Çözüm Gezgini**.  
  
## <a name="adding-a-namedrange-control-to-the-worksheet"></a>Çalışma sayfasına NamedRange denetimi ekleme  
  
#### <a name="to-add-a-named-range-to-sheet1"></a>Adlandırılmış bir aralık Sheet1 eklemek için  
  
1.  Select hücre **A1** üzerinde `Sheet1`.  
  
2.  İçinde **adı** kutusuna **girdiFormu**.  
  
     **Adı** kutusudur sütun hemen formül çubuğuna solunda bulunan **A** çalışma sayfasının.  
  
3.  ENTER tuşuna basın.  
  
     A <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi eklenir hücre **A1**. Çalışma sayfasında görünür bir gösterge yoktur ancak **girdiFormu** görünür **adı** kutusunu (yalnızca çalışma sayfasının üstünde sol tarafta) ve **özellikleri** penceresi olduğunda Hücre **A1** seçilir.  
  
## <a name="adding-a-windows-form-to-the-project"></a>Bir Windows formunda projesine ekleniyor  
 Kullanıcıdan bilgi istemek için bir Windows Form oluşturun.  
  
#### <a name="to-add-a-windows-form"></a>Windows Form eklemek için  
  
1.  Projeyi seçin **girdiWinFormu** içinde **Çözüm Gezgini**.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Add Windows Form**.  
  
3.  Formun adı **GetInputString.vb** veya **GetInputString.cs olarak**ve ardından **Ekle**.  
  
     Yeni form tasarımcısında açar.  
  
4.  Ekleme bir <xref:System.Windows.Forms.TextBox> ve <xref:System.Windows.Forms.Button> form.  
  
5.  Düğmesini seçin, özelliği **metin** içinde **özellikleri** penceresinde ve metne dönüştürmek **Tamam**.  
  
 Ardından, kod ekleyin `ThisWorkbook.vb` veya `ThisWorkbook.cs` kullanıcının bilgileri toplamak için.  
  
## <a name="displaying-the-windows-form-and-collecting-information"></a>Windows Form görüntülemek ve bilgi toplama  
 Bir örneğini oluşturmak `GetInputString` Windows formu görüntülemek ve bir hücreye çalışma sayfasındaki kullanıcı bilgilerini yazar.  
  
#### <a name="to-display-the-form-and-collect-information"></a>Formun görüntülemek ve bilgi toplamak için  
  
1.  Sağ **ThisWorkbook.vb** veya **ThisWorkbook.cs** içinde **Çözüm Gezgini**ve ardından **görünümü kodu**.  
  
2.  İçinde <xref:Microsoft.Office.Tools.Excel.Workbook.Open> olay işleyicisi `ThisWorkbook`, form için bir değişken bildirmek için aşağıdaki kodu ekleyin `GetInputString` ve formu görüntüleyin.  
  
    > [!NOTE]  
    >  C# ' ta, olay işleyici gösterildiği gibi eklemelisiniz <xref:Microsoft.Office.Tools.Excel.Workbook.Startup> aşağıdaki olay. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingCollectingData#1](../vsto/codesnippet/CSharp/WinFormInputCS/ThisWorkbook.cs#1)]
     [!code-vb[Trin_VstcoreProgrammingCollectingData#1](../vsto/codesnippet/VisualBasic/WinFormInput/ThisWorkbook.vb#1)]  
  
3.  Adlı bir yöntem oluşturma `WriteStringToCell` adlandırılmış bir aralık metni yazar. Bu yöntem formdan çağrılır ve kullanıcının giriş geçirilir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi `formInput`, hücre **A1**.  
  
     [!code-csharp[Trin_VstcoreProgrammingCollectingData#2](../vsto/codesnippet/CSharp/WinFormInputCS/ThisWorkbook.cs#2)]
     [!code-vb[Trin_VstcoreProgrammingCollectingData#2](../vsto/codesnippet/VisualBasic/WinFormInput/ThisWorkbook.vb#2)]  
  
 Ardından, forma düğmenin click işlemek üzere kod eklemek olay.  
  
## <a name="sending-information-to-the-worksheet"></a>Çalışma sayfasına bilgileri gönderme  
  
#### <a name="to-send-information-to-the-worksheet"></a>Çalışma sayfasına bilgileri göndermek için  
  
1.  Sağ **GetInputString** içinde **Çözüm Gezgini**ve ardından **Görünüm Tasarımcısı**.  
  
2.  Düğmesini düğmesinin kod dosyasını açmak için çift <xref:System.Windows.Forms.Control.Click> olay işleyicisi eklenmiş.  
  
3.  Metin kutusunda giriş alın, işleve göndermek için olay işleyicisini kod ekleme `WriteStringToCell`ve formu kapatır.  
  
     [!code-csharp[Trin_VstcoreProgrammingCollectingData#3](../vsto/codesnippet/CSharp/WinFormInputCS/GetInputString.cs#3)]
     [!code-vb[Trin_VstcoreProgrammingCollectingData#3](../vsto/codesnippet/VisualBasic/WinFormInput/GetInputString.vb#3)]  
  
## <a name="testing"></a>Sınama  
 Projeyi şimdi çalıştırabilirsiniz. Windows Form görünür ve girişinizi çalışma sayfasında görünür.  
  
#### <a name="to-test-your-workbook"></a>Çalışma kitabınız sınamak için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Windows Form göründüğünü doğrulayın.  
  
3.  Tür **Hello World** metin kutusuna ve ardından **Tamam**.  
  
4.  Onaylayın **Hello World** hücrede görünür **A1** çalışma sayfasının.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu kılavuzda Windows formu ve bir çalışma sayfasına veri geçirme gösteren temellerini gösterir. Gerçekleştirmek isteyebileceğiniz diğer görevler şunlardır:  
  
-   Bir Excel çalışma kitabı veya Word belgesi üzerinde Windows Forms denetimleri kullanın. Daha fazla bilgi için bkz: [Office belgeleri genel bakış Windows Forms denetimleri](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
-   Belge düzeyi özelleştirme veya bir VSTO eklenti Microsoft Office uygulamasından kullanıcı arabiriminin değiştirin. Daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Word kullanımında izlenecek yollar](../vsto/walkthroughs-using-word.md)   
 [Excel Kullanarak İzlenecek Yollar](../vsto/walkthroughs-using-excel.md)  
  
  