---
title: 'İzlenecek yol: Excel için ilk belge düzeyi özelleştirmeyi oluşturma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, creating your first project
- Excel [Office development in Visual Studio], creating your first project
- document-level customizations [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2a63dd4eae31b99646af04ceabe76e4edb946027
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845710"
---
# <a name="walkthrough-create-your-first-document-level-customization-for-excel"></a>İzlenecek yol: Excel için ilk belge düzeyi özelleştirmeyi oluşturma
  Bu tanıtıcı kılavuz Microsoft Office Excel için belge düzeyi özelleştirme oluşturulacağını gösterir. Bu tür bir çözüm içinde oluşturduğunuz özellikler, yalnızca belirli bir çalışma kitabı açık olduğunda kullanılabilir. Belge düzeyi özelleştirme uygulama çapında değişiklik yapmak için kullanamazsınız, örneğin, herhangi bir çalışma kitabı açık olduğunda yeni bir Şerit sekmesi görüntüleme gibi.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Bir Excel çalışma kitabı projesi oluşturma.  
  
-   Visual Studio Tasarımcısı'nda barındırılan bir çalışma sayfasına metin ekleme.  
  
-   Açıldığında özelleştirilmiş çalışma sayfasına metin eklemek için Excel nesne modelini kullanan kod yazma.  
  
-   Derleme ve test etmek için proje çalışıyor.  
  
-   Gereksiz yapı dosyalarını ve güvenlik ayarlarını Geliştirme bilgisayarınızdan kaldırmak için tüm projeyi temizleniyor.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] veya [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="create-the-project"></a>Projeyi oluşturma  
  
### <a name="to-create-a-new-excel-workbook-project-in-visual-studio"></a>Visual Studio'da yeni bir Excel çalışma kitabı proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Genişletilmiş altında **Office/SharePoint** düğümü, select **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde Excel VSTO eklenti projesindeki seçin.  
  
6.  İçinde **adı** kutusuna **FirstWorkbookCustomization**.  
  
7.  **Tamam**'ı tıklatın.  
  
     **Office Proje Sihirbazı için Visual Studio Araçları** açar.  
  
8.  Seçin **bir yeni belge oluşturun**, tıklatıp **Tamam**.  
  
    -   [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] oluşturur **FirstWorkbookCustomization** proje ve aşağıdaki dosyaları projeye ekler.  
  
    -   *FirstWorkbookCustomization*.xlsx - projedeki Excel çalışma kitabını temsil eder. Çalışma sayfaları ve grafikler içerir.  
  
    -   Sheet1 (*.vb* dosya Visual Basic veya *.cs* dosya Visual C# için)-ilk çalışma kitabındaki için tasarım yüzeyi ve kod sağlayan bir çalışma. Daha fazla bilgi için bkz: [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md).  
  
    -   Sheet2 (*.vb* dosya Visual Basic veya *.cs* dosya Visual C# için)-ikinci çalışma kitabındaki için tasarım yüzeyi ve kod sağlayan bir çalışma.  
  
    -   Sheet3 (*.vb* dosya Visual Basic veya *.cs* dosya Visual C# için)-üçüncü çalışma kitabındaki için tasarım yüzeyi ve kod sağlayan bir çalışma.  
  
    -   ThisWorkbook (*.vb* dosya Visual Basic veya *.cs* dosya Visual C# için)-tasarım yüzeyi ve çalışma kitabını düzeyi özelleştirmelerinde kodu içerir. Daha fazla bilgi için bkz: [çalışma kitabı konak öğesi](../vsto/workbook-host-item.md).  
  
     Sheet1 kod dosyası Tasarımcısı'nda otomatik olarak açılır.  
  
## <a name="close-and-reopen-worksheets-in-the-designer"></a>Çalışma sayfaları Tasarımcısı'nda kapatıp yeniden yükleme  
 Projenizi geliştirirken kasıtlı olarak veya yanlışlıkla bir çalışma kitabı veya bir çalışma sayfası Tasarımcısı'nda kapatırsanız, yeniden açabilirsiniz.  
  
### <a name="to-close-and-reopen-a-worksheet-in-the-designer"></a>Tasarımcıda çalışma sayfasında kapatıp yeniden yükleme için  
  
1.  Çalışma kitabını tıklayarak kapatın **Kapat** Tasarımcısı penceresinin düğmesine (X).  
  
2.  İçinde **Çözüm Gezgini**, sağ **Sheet1** tıklayın ve kod dosyası **Görünüm Tasarımcısı**.  
  
     \- veya -  
  
     İçinde **Çözüm Gezgini**, çift **Sheet1** kod dosyası.  
  
## <a name="add-text-to-a-worksheet-in-the-designer"></a>Bir çalışma sayfasına Tasarımcısı'nda metin ekleme  
 Tasarımcıda açık çalışma sayfasını değiştirerek özelleştirmenizin kullanıcı arabirimi (UI) tasarlayabilirsiniz. Örneğin, hücrelere metin ekleyebilir, formüller uygulayabilir veya Excel denetimleri ekleyin. Tasarımcıyı kullanma hakkında daha fazla bilgi için bkz: [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
### <a name="to-add-text-to-a-worksheet-by-using-the-designer"></a>Tasarımcı kullanarak bir çalışma sayfasına metin ekleme  
  
1.  Tasarımcıda açık çalışma sayfasında hücreyi **A1**ve ardından aşağıdaki metni yazın.  
  
     **Bu metin, tasarımcıyı kullanarak eklendi.**  
  
> [!WARNING]  
>  Bu metin satırı hücreye eklerseniz **A2**, bu örnekteki diğer kod tarafından üzerine yazılacak.  
  
## <a name="add-text-to-a-worksheet-programmatically"></a>Bir çalışma sayfasına program aracılığıyla metin ekleme  
 Ardından, kodu Sheet1 kod dosyasına ekleyin. Yeni kod nesne modeli Excel çalışma kitabına metnin ikinci bir satır eklemek için kullanır. Varsayılan olarak, Sheet1 kod dosyası aşağıdaki oluşturulmuş kodu içerir:  
  
-   Kısmi tanımının `Sheet1` çalışma kitabının programlama modelini gösteren ve Excel nesne modeline erişim sağlayan sınıf. Daha fazla bilgi için [çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md) ve [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md). Geri kalan `Sheet1` sınıfı değiştirmemeniz gereken gizli kod dosyasında tanımlanır.  
  
-   `Sheet1_Startup` Ve `Sheet1_Shutdown` olay işleyicileri. Bu olay işleyicileri Excel yüklediğinde ve özelleştirmeyi bellekten denir. Bu olay işleyicilerini yüklendiğinde Eklentinizi başlatmak ve kaldırıldığında özelleştirmenizin kullandığı kaynakları temizlemek için kullanın. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
### <a name="to-add-a-second-line-of-text-to-the-worksheet-by-using-code"></a>Kod kullanarak çalışma sayfasına ikinci satırlık metin ekleme  
  
1.  İçinde **Çözüm Gezgini**, sağ **Sheet1**ve ardından **görünümü kodu**.  
  
     Visual Studio'da kod dosyasını açar.  
  
2.  Değiştir `Sheet1_Startup` aşağıdaki kod ile olay işleyicisi. Sheet1 açıldığında, bu kod çalışma sayfasına metnin ikinci bir satır ekler.  
  
     [!code-csharp[Trin_ExcelWorkbookTutorial#1](../vsto/codesnippet/CSharp/Trin_ExcelWorkbookTutorial/Sheet1.cs#1)]
     [!code-vb[Trin_ExcelWorkbookTutorial#1](../vsto/codesnippet/VisualBasic/Trin_ExcelWorkbookTutorial/Sheet1.vb#1)]  
  
## <a name="test-the-project"></a>Projeyi test  
  
### <a name="to-test-your-workbook"></a>Çalışma kitabınız sınamak için  
  
1.  Tuşuna **F5** oluşturun ve projenizin çalıştırın.  
  
     Projeyi derlerken kodu çalışma kitabı ile ilişkilendirilmiş bir derlemeyi derlenir. Visual Studio projesi için derleme çıktısı klasöründeki çalışma kitabını ve derleme bir kopyasını koyar ve çalıştırmak özelleştirmeyi etkinleştirmek için geliştirme bilgisayarınızda güvenlik ayarlarını yapılandırır. Daha fazla bilgi için bkz: [yapı Office çözümleri](../vsto/building-office-solutions.md).  
  
2.  Çalışma kitabı, aşağıdaki metni gördüğünüzü doğrulayın.  
  
     **Bu metin, tasarımcıyı kullanarak eklendi.**  
  
     **Bu metin, kod kullanarak eklendi.**  
  
3.  Çalışma kitabını kapatın.  
  
## <a name="clean-up-the-project"></a>Projeyi temizleyin  
 Projeyi geliştirmeyi bitirdiğinizde yapı çıktı klasörüne ve yapı işlemi tarafından oluşturulan güvenlik ayarlarını dosyaları kaldırmanız gerekir.  
  
### <a name="to-clean-up-the-completed-project-on-your-development-computer"></a>Geliştirme bilgisayarınızda tamamlanmış projeyi temizlemek için  
  
1.  Visual Studio'da üzerinde **yapı** menüsünde tıklatın **temiz çözüm**.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Excel için temel bir belge düzeyi özelleştirme oluşturduğunuza göre aşağıdaki konulardan özelleştirmeleri geliştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Belge düzeyi özelleştirmelerinde gerçekleştirebileceğiniz genel programlama görevleri: [Program belge düzeyi özelleştirmeleri](../vsto/programming-document-level-customizations.md).  
  
-   Excel için belge düzeyi özelleştirmelerine özel programlama görevleri: [Excel çözümleri](../vsto/excel-solutions.md).  
  
-   Excel nesne modelini kullanma: [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
-   Excel'in UI'ını özelleştirme, örneğin, göre Şerite özel bir sekme ekleme veya kendi Eylemler bölmesi oluşturma: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
-   Excel nesne modeli (örneğin, belgelerdeki yönetilen denetimleri ve Windows Forms kullanarak veriye Excel denetimi bağlama kullanarak mümkün olmayan görevleri gerçekleştirmek için Visual Studio'da Office geliştirme araçları tarafından sağlanan genişletilmiş Excel nesnelerini kullanma veri bağlama modelini): [Excel genişletilmiş nesneleri kullanarak otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md).  
  
-   Derleme ve Excel için belge düzeyi özelleştirmelerini hata ayıklama: [yapı Office çözümleri](../vsto/building-office-solutions.md).  
  
-   Excel için belge düzeyi özelleştirmelerini dağıtma: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Excel çözümleri](../vsto/excel-solutions.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md)  
  
  