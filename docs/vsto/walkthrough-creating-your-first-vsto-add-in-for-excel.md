---
title: 'İzlenecek yol: Excel için ilk VSTO eklentinizi oluşturma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- add-ins [Office development in Visual Studio], creating your first project
- Excel [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6421df0109d68d2647cafff5713aecb297c3536d
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845814"
---
# <a name="walkthrough-create-your-first-vsto-add-in-for-excel"></a>İzlenecek yol: Excel için ilk VSTO eklentinizi oluşturma
  Bu tanıtıcı kılavuz bir uygulama düzeyi Ekle-Microsoft Office Excel için nasıl oluşturulacağını gösterir. Bu tür bir çözüm içinde oluşturduğunuz özellikler uygulamanın kendisinin çalışma kitaplarını açık olan bağımsız olarak kullanılabilir.  
  
 [!INCLUDE[appliesto_xlallapp](../vsto/includes/appliesto-xlallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Excel için Excel VSTO eklenti projesindeki oluşturuluyor.  
  
-   Kaydedildiğinde çalışma kitabına metin eklemek için Excel nesne modelini kullanan kod yazma.  
  
-   Derleme ve test etmek için proje çalışıyor.  
  
-   VSTO eklenti artık otomatik olarak geliştirme bilgisayarınızda çalışmaması için tamamlanmış projeyi temizleme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="create-the-project"></a>Projeyi oluşturma  
  
#### <a name="to-create-a-new-excel-vsto-add-in-project-in-visual-studio"></a>Visual Studio'da yeni bir Excel VSTO eklenti projesi oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Genişletilmiş altında **Office/SharePoint** düğümü, select **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde seçin **Excel 2010 Eklentisi** veya **Excel 2013 eklentisi**.  
  
6.  İçinde **adı** kutusuna **FirstExcelAddIn**.  
  
7.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] oluşturur **FirstExcelAddIn** proje ve düzenleyicide ThisAddIn kod dosyasını açar.  
  
## <a name="write-code-to-add-text-to-the-saved-workbook"></a>Kaydedilmiş çalışma kitabına metin eklemek için kod yazma  
 Ardından, kodu ThisAddIn kod dosyasına ekleyin. Yeni kod, etkin çalışma sayfasındaki ilk satırda Demirbaş metin eklemek için Excel nesne modeli kullanır. Etkin çalışma sayfasında kullanıcı çalışma kitabını kaydettiğinde, açık olan bir çalışma sayfasıdır. Varsayılan olarak, aşağıdaki oluşturulmuş kodu ThisAddIn kod dosyasını içerir:  
  
-   Kısmi tanımının `ThisAddIn` sınıfı. Bu sınıf kodunuz için giriş noktası sağlar ve Excel nesne modeline erişim sağlar. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md). Geri kalan `ThisAddIn` sınıfı değiştirmemeniz gereken gizli kod dosyasında tanımlanır.  
  
-   `ThisAddIn_Startup` Ve `ThisAddIn_Shutdown` olay işleyicileri. Bu olay işleyicileri Excel yüklediğinde ve VSTO eklentinizi bellekten denir. Bu olay işleyicilerini VSTO eklentinizi yüklendiğinde başlatmak ve kaldırıldığında, eklenti tarafından kullanılan kaynakları temizlemek için kullanın. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
### <a name="to-add-a-line-of-text-to-the-saved-workbook"></a>Metin satırının kaydedilmiş çalışma kitabına eklemek için  
  
1.  ThisAddIn kod dosyasında aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Yeni kod için olay işleyicisini tanımlar <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> bir çalışma kitabı kaydedildiğinde oluşan olayı,.  
  
     Kullanıcı bir çalışma kitabını kaydettiğinde, olay işleyicisi etkin çalışma başlangıcında yeni metin ekler.  
  
     [!code-vb[Trin_ExcelAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ExcelAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_ExcelAddInTutorial/ThisAddIn.cs#1)]  
  
2.  C# kullanıyorsanız aşağıdaki gerekli kodu eklemek `ThisAddIn_Startup` olay işleyicisi. Bu kod bağlanmak için kullanılan `Application_WorkbookBeforeSave` olay işleyicisi ile <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> olay.  
  
     [!code-csharp[Trin_ExcelAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_ExcelAddInTutorial/ThisAddIn.cs#2)]  
  
 Kaydedildiğinde çalışma kitabını değiştirmek için aşağıdaki nesneler önceki kod örnekleri kullanın:  
  
-   `Application` Alanını `ThisAddIn` sınıfı. `Application` Alan döndürür bir <xref:Microsoft.Office.Interop.Excel.Application> Excel geçerli örneği temsil eden nesne.  
  
-   `Wb` İçin olay işleyicisini parametresinin <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> olay. `Wb` Parametresi bir <xref:Microsoft.Office.Interop.Excel.Workbook> kaydedilmiş bir çalışma kitabı temsil eden nesne. Daha fazla bilgi için bkz: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
## <a name="test-the-project"></a>Projeyi test  
  
### <a name="to-test-the-project"></a>Projeyi test etmek için  
  
1.  Tuşuna **F5** oluşturun ve projenizin çalıştırın.  
  
     Projeyi derlerken kodunu projeyi derleme çıktı dosyasına dahil bütünleştirilmiş derlenir. Visual Studio da bulup VSTO eklenti Excel etkinleştirmek kayıt defteri girdileri kümesini oluşturur ve VSTO eklenti çalıştırmak, geliştirici bilgisayarının güvenlik ayarlarını yapılandırır. Daha fazla bilgi için bkz: [yapı Office çözümleri](../vsto/building-office-solutions.md).  
  
2.  Excel'de çalışma kitabını kaydedin.  
  
3.  Aşağıdaki metni çalışma kitabına eklendiğini doğrulayın.  
  
     **Bu metin, kod kullanarak eklendi.**  
  
4.  Excel'i kapatın.  
  
## <a name="clean-up-the-project"></a>Projeyi temizleyin  
 Projeyi geliştirmeyi bitirdiğinizde VSTO eklenti derlemesi, kayıt defteri girdileri ve güvenlik ayarlarını Geliştirme bilgisayarınızdan kaldırın. Aksi takdirde, VSTO eklenti Excel geliştirme bilgisayarınızda açık her zaman çalışmaya devam eder.  
  
### <a name="to-clean-up-the-completed-project-on-your-development-computer"></a>Geliştirme bilgisayarınızda tamamlanmış projeyi temizlemek için  
  
1.  Visual Studio'da üzerinde **yapı** menüsünde tıklatın **temiz çözüm**.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Excel için temel bir VSTO eklentisi oluşturduğunuza göre VSTO eklentileri aşağıdaki konulardan geliştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   VSTO eklentileri gerçekleştirebileceğiniz genel programlama görevleri: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
-   Excel VSTO eklentileri için belirli programlama görevleri: [Excel çözümleri](../vsto/excel-solutions.md).  
  
-   Excel nesne modelini kullanma: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
-   Excel kullanıcı arabirimini (UI) özelleştirme, örneğin, göre Şerite özel bir sekme ekleme veya kendi özel görev bölmesi oluşturma: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
-   Derleme ve Excel için VSTO eklentileri hata ayıklama: [yapı Office çözümleri](../vsto/building-office-solutions.md).  
  
-   Excel için VSTO eklentileri dağıtma: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Excel çözümleri](../vsto/excel-solutions.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md)  
  
  