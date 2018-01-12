---
title: "İzlenecek yol: Outlook için ilk VSTO eklentinizi oluşturma | Microsoft Docs"
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
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- add-ins [Office development in Visual Studio], creating your first project
- Outlook [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3f92c898b6eb8ba0f143e0a2069e35c70cc6e6b2
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-your-first-vsto-add-in-for-outlook"></a>İnceleme: Outlook için İlk VSTO Eklentinizi Oluşturma
  Bu kılavuzda nasıl Microsoft Office Outlook için VSTO eklentisi oluşturulacağını gösterir. Bu tür bir çözüm içinde oluşturduğunuz özellikler uygulamanın kendisinin Outlook öğesi açık olduğu bağımsız olarak kullanılabilir. Daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Outlook VSTO eklenti projesindeki Outlook için oluşturuluyor.  
  
-   Konu ve gövde yeni bir posta iletisi, metin eklemek için Outlook nesne modelini kullanan kod yazma.  
  
-   Derleme ve test etmek için proje çalışıyor.  
  
-   VSTO eklenti artık otomatik olarak geliştirme bilgisayarınızda çalışmaması için tamamlanmış projeyi temizleme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Outlook  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
  
#### <a name="to-create-a-new-outlook-project-in-visual-studio"></a>Visual Studio'da yeni bir Outlook projesi oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Genişletilmiş altında **Office/SharePoint** düğümü, select **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde Outlook VSTO eklenti projesindeki seçin.  
  
6.  İçinde **adı** kutusuna **FirstOutlookAddIn**.  
  
7.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]oluşturur **FirstOutlookAddIn** proje ve açılır **ThisAddIn** Düzenleyicisi'nde kod dosyası.  
  
## <a name="writing-code-that-adds-text-to-each-new-mail-message"></a>Her yeni bir posta iletisi metin ekleyen kod yazma  
 Ardından, kodu ThisAddIn kod dosyasına ekleyin. Yeni kod Outlook nesne modeline metin her yeni posta iletisine eklemek için kullanır. Varsayılan olarak, aşağıdaki oluşturulmuş kodu ThisAddIn kod dosyasını içerir:  
  
-   Kısmi tanımının `ThisAddIn` sınıfı. Bu sınıf kodunuz için giriş noktası sağlar ve Outlook nesne modeline erişim sağlar. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md). Geri kalan `ThisAddIn` sınıfı değiştirmemeniz gereken gizli kod dosyasında tanımlanır.  
  
-   `ThisAddIn_Startup` Ve `ThisAddIn_Shutdown` olay işleyicileri. Bu olay işleyicileri Outlook yüklediğinde ve VSTO eklentinizi bellekten denir. Bu olay işleyicilerini VSTO eklentinizi yüklendiğinde başlatmak ve kaldırıldığında VSTO eklentinizi tarafından kullanılan kaynakları temizlemek için kullanın. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-text-to-the-subject-and-body-of-each-new-mail-message"></a>Konu ve gövde her yeni bir posta iletisi, metin ekleme  
  
1.  ThisAddIn kod dosyasında adında bir alan bildirin `inspectors` içinde `ThisAddIn` sınıfı. `inspectors` Alan geçerli Outlook örneğinde Inspector penceresi koleksiyonuna bir başvuru korur. Bu başvuru için olay işleyicisini içeren belleği boşaltmasını atık toplayıcı engeller <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> olay.  
  
     [!code-vb[Trin_OutlookAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_OutlookAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#1)]  
  
2.  Değiştir `ThisAddIn_Startup` aşağıdaki kod ile yöntemi. Bu kod bir olay işleyicisi ekler <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> olay.  
  
     [!code-vb[Trin_OutlookAddInTutorial#2](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#2)]
     [!code-csharp[Trin_OutlookAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#2)]  
  
3.  ThisAddIn kod dosyasında aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Bu kod için olay işleyicisini tanımlar <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> olay.  
  
     Kullanıcı yeni bir posta iletisi oluşturduğunda, bu olay işleyicisi konu satırı ve ileti gövdesini metin ekler.  
  
     [!code-vb[Trin_OutlookAddInTutorial#3](../vsto/codesnippet/VisualBasic/Trin_OutlookAddInTutorial/ThisAddIn.vb#3)]
     [!code-csharp[Trin_OutlookAddInTutorial#3](../vsto/codesnippet/CSharp/Trin_OutlookAddInTutorial/ThisAddIn.cs#3)]  
  
 Her yeni bir posta iletisi değiştirmek için aşağıdaki nesneler önceki kod örnekleri kullanın:  
  
-   `Application` Alanını `ThisAddIn` sınıfı. `Application` Alan döndürür bir <xref:Microsoft.Office.Interop.Outlook.Application> Outlook geçerli örneği temsil eden nesne.  
  
-   `Inspector` İçin olay işleyicisini parametresinin <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> olay. `Inspector` Parametresi bir <xref:Microsoft.Office.Interop.Outlook.Inspector> yeni bir posta iletisi Inspector penceresini gösteren nesne. Daha fazla bilgi için bkz: [Outlook çözümleri](../vsto/outlook-solutions.md).  
  
## <a name="testing-the-project"></a>Projeyi test etme  
 Yapı ve projeyi çalıştırın, metin konu satırı ve yeni bir posta iletisi gövdesi göründüğünden emin olun.  
  
#### <a name="to-test-the-project"></a>Projeyi test etmek için  
  
1.  Tuşuna **F5** oluşturun ve projenizin çalıştırın.  
  
     Projeyi derlerken kodunu projeyi derleme çıktı dosyasına dahil bütünleştirilmiş derlenir. Visual Studio ayrıca bulmak ve VSTO eklenti Outlook etkinleştirme kayıt defteri girdileri kümesini oluşturur ve VSTO eklenti çalıştırmak, geliştirici bilgisayarının güvenlik ayarlarını yapılandırır. Daha fazla bilgi için bkz: [Office çözümü oluşturma işlemine genel bakış](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md).  
  
2.  Outlook içinde yeni bir posta iletisi oluşturun.  
  
3.  Aşağıdaki metni konu satırı ve ileti gövdesi için eklendiğini doğrulayın.  
  
     **Bu metin, kod kullanarak eklendi.**  
  
4.  Outlook'u kapatın.  
  
## <a name="cleaning-up-the-project"></a>Projeyi temizleme  
 Projeyi geliştirmeyi bitirdiğinizde VSTO eklenti derlemesi, kayıt defteri girdileri ve güvenlik ayarlarını Geliştirme bilgisayarınızdan kaldırın. Aksi halde, VSTO eklenti, Outlook geliştirme bilgisayarındaki her açışınızda çalışacaktır.  
  
#### <a name="to-clean-up-your-project"></a>Projenizi temizlemek için  
  
1.  Visual Studio'da üzerinde **yapı** menüsünde tıklatın **temiz çözüm**.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bir temel VSTO eklentisi Outlook için oluşturduğunuza göre VSTO eklentileri aşağıdaki konulardan geliştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Outlook için VSTO eklentileri kullanarak gerçekleştirebileceğiniz genel programlama görevleri. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
-   Outlook nesne modelini kullanarak. Daha fazla bilgi için bkz: [Outlook çözümleri](../vsto/outlook-solutions.md).  
  
-   Kullanıcı Arabirimi, Outlook, örneğin, özel bir sekme Şerit ekleme veya kendi özel görev bölmesini oluşturarak özelleştirme. Daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
-   Derleme ve VSTO eklentileri Outlook için hata ayıklama. Daha fazla bilgi için bkz: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
-   Outlook için VSTO eklentileri dağıtma. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Outlook çözümleri](../vsto/outlook-solutions.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office Proje Şablonlarına Genel Bakış](../vsto/office-project-templates-overview.md)  
  
  