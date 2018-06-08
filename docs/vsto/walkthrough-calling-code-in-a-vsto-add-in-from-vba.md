---
title: "İzlenecek yol: çağrı VBA'dan kod bir VSTO eklenti"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA [Office development in Visual Studio], calling code in application-level add-ins
- application-level add-ins [Office development in Visual Studio], calling code from other solutions
- Video How tos, Office development in Visual Studio
- calling add-in code
- add-ins [Office development in Visual Studio], calling code from other solutions
- interoperability [Office development in Visual Studio]
- calling code from VBA
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1349facda26418907f039c80c7742d3c456437af
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845723"
---
# <a name="walkthrough-call-code-in-a-vsto-add-in-from-vba"></a>İzlenecek yol: çağrı VBA'dan kod bir VSTO eklenti
  Bu kılavuz, nesneyi VSTO eklenti Visual Basic for Applications (VBA) ve COM VSTO eklentileri için dahil diğer Microsoft Office çözümleri için kullanıma gösterilmiştir.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Bu kılavuzda özellikle Excel kullanıyor olsa da, izlenecek yol tarafından gösterilen kavramlar Visual Studio tarafından sağlanan tüm VSTO eklenti proje şablonu için uygulanabilir.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Diğer Office Çözümlerinden verilebilen bir sınıf tanımlama.  
  
-   Diğer Office çözümlerine sınıfı gösterme.  
  
-   VBA kodundan sınıfının yöntemini çağırma.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Excel  
  
## <a name="create-the-vsto-add-in-project"></a>VSTO eklenti projesi oluşturma  
 İlk adım, Excel için VSTO eklenti projesi oluşturmaktır.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı Excel VSTO eklenti projesindeki oluşturun **ExcelImportData**, Excel VSTO eklenti proje şablonunu kullanarak. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] açılır **ThisAddIn.cs** veya **ThisAddIn.vb** kod dosyası ve ekler **ExcelImportData** için proje **Çözüm Gezgini**.  
  
## <a name="define-a-class-that-you-can-expose-to-other-office-solutions"></a>Diğer Office Çözümlerinden kullanıma sunmak bir sınıf tanımlama  
 Çağırmak için bu kılavuzun amacı olan `ImportData` adlı bir sınıf yöntemi `AddInUtilities` VSTO eklentinizi VBA kodundan içinde. Bu yöntem etkin çalışma sayfasının A1 hücresine bir dize yazar.  
  
 Kullanıma sunmak için `AddInUtilities` sınıfı diğer Office Çözümlerinden sınıfı ortak ve COM görünür olmalısınız Ayrıca kullanıma gerekir [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) sınıfında arabirimi. Aşağıdaki yordamda kodu bu gereksinimleri sağlamanın bir yolu gösterir. Daha fazla bilgi için bkz: [VSTO eklentileri diğer Office Çözümlerinden gelen çağırma kodda](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
### <a name="to-define-a-class-that-you-can-expose-to-other-office-solutions"></a>Diğer Office Çözümlerinden kullanıma sunmak bir sınıf tanımlamak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **sınıfı Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, yeni sınıf adını değiştirmek **AddInUtilities**, tıklatıp **Ekle**.  
  
     **AddInUtilities.cs** veya **AddInUtilities.vb** dosyasını Kod Düzenleyicisi'nde açar.  
  
3.  Aşağıdaki deyimleri dosyasının üstüne ekleyin.  
  
     [!code-csharp[Trin_AddInInteropWalkthrough#2](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/AddInUtilities.cs#2)]
     [!code-vb[Trin_AddInInteropWalkthrough#2](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/AddInUtilities.vb#2)]  
  
4.  Değiştir `AddInUtilities` aşağıdaki kodla sınıfı.  
  
     [!code-csharp[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/AddInUtilities.cs#3)]
     [!code-vb[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/AddInUtilities.vb#3)]  
  
     Bu kod yapar `AddInUtilities` COM görünür sınıfı ve ekler `ImportData` sınıfına yöntemi. Kullanıma sunmak için [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) arabirimi, `AddInUtilities` sınıfı ayrıca sahip <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliği ve uygulayan COM'a görünür bir arabirimi  
  
## <a name="expose-the-class-to-other-office-solutions"></a>Diğer Office çözümlerine sınıfı  
 Kullanıma sunmak için `AddInUtilities` sınıfı diğer Office Çözümlerinden, geçersiz kılma <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> yönteminde `ThisAddIn` sınıfı. Geçersiz kılmada örneği dönmek `AddInUtilities` sınıfı.  
  
### <a name="to-expose-the-addinutilities-class-to-other-office-solutions"></a>Diğer Office çözümlerine AddInUtilities sınıfı kullanıma sunmak için  
  
1.  İçinde **Çözüm Gezgini**, genişletin **Excel**.  
  
2.  Sağ **ThisAddIn.cs** veya **ThisAddIn.vb**ve ardından **görünümü kodu**.  
  
3.  Aşağıdaki kodu ekleyin `ThisAddIn` sınıfı.  
  
     [!code-csharp[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/ThisAddIn.cs#1)]
     [!code-vb[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/ThisAddIn.vb#1)]  
  
4.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
     Çözümünüzün hatasız oluşturulduğunu doğrulayın.  
  
## <a name="test-the-vsto-add-in"></a>VSTO eklentisinin test  
 Çağırabilirsiniz `AddInUtilities` Office çözümleri birkaç farklı türde bir sınıftan. Bu kılavuzda, bir Excel çalışma kitabında VBA kodu kullanır. Office çözümleri de kullanabilir diğer türleri hakkında daha fazla bilgi için bkz: [çağrısı kod VSTO eklentileri diğer Office Çözümlerinden](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
### <a name="to-test-your-vsto-add-in"></a>VSTO eklentinizi sınamak için  
  
1.  Tuşuna **F5** projeyi çalıştırın.  
  
2.  Excel'de etkin çalışma kitabının bir etkin çalışma kitabı (*.xlsm) olarak kaydedin. Masaüstü gibi uygun bir konuma kaydedin.  
  
3.  Şerit'te tıklatın **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  İçinde **kod** grubunda **Visual Basic**.  
  
     Visual Basic Düzenleyicisi'ni açar.  
  
5.  İçinde **proje** penceresinde çift **ThisWorkbook**.  
  
     İçin kod dosyası `ThisWorkbook` nesnesini açar.  
  
6.  Aşağıdaki VBA kodu kod dosyasına ekleyin. Bu kod ilk temsil eden bir COMAddIn nesnesi alır **ExcelImportData** VSTO eklenti. Ardından, kod çağırmak için COMAddIn nesnesinin nesne özelliğini kullanır `ImportData` yöntemi.  
  
    ```vb  
    Sub CallVSTOMethod()  
        Dim addIn As COMAddIn  
        Dim automationObject As Object  
        Set addIn = Application.COMAddIns("ExcelImportData")  
        Set automationObject = addIn.Object  
        automationObject.ImportData  
    End Sub  
    ```  
  
7.  Tuşuna **F5**.  
  
8.  Doğrulayın yeni bir **içe aktarılan verilerin** sayfası çalışma kitabına eklendi. Ayrıca, A1 hücresinin dize içerdiğini doğrulayın **verilerimi budur**.  
  
9. Excel çıkın.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 VSTO eklentileri aşağıdaki konulardan programlama hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Kullanım `ThisAddIn` konak uygulamasını otomatikleştirmek ve VSTO eklenti projesindeki diğer görevleri gerçekleştirmek için sınıf. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
-   Bir VSTO eklenti özel görev bölmesini oluşturun. Daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md) ve [nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).  
  
-   Bir VSTO eklentisinin Şeritte özelleştirin. Daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md) ve [nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [VSTO eklentileri diğer Office Çözümlerinden kodu çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [Office çözümleri geliştirmek](../vsto/developing-office-solutions.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Genişletilebilirlik arabirimlerini kullanarak kullanıcı Arabirimi özelliklerini özelleştirme](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md)  
  
  