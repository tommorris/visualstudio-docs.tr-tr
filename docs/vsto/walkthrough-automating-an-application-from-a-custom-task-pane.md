---
title: "İzlenecek yol: uygulamayı özel görev bölmesinden otomatikleştirme | Microsoft Docs"
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
- task panes [Office development in Visual Studio], PowerPoint
- PowerPoint [Office development in Visual Studio], custom task panes
- automating Office applications
- custom task panes [Office development in Visual Studio], automating applications
- custom task panes [Office development in Visual Studio], PowerPoint
- task panes [Office development in Visual Studio], automating applications
ms.assetid: 77be5ab5-e330-4564-87ec-9cba564ba8f9
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8d7c349261770e6b489a793f6f4533a852c96a8e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-automating-an-application-from-a-custom-task-pane"></a>İzlenecek Yol: Uygulamayı Özel Görev Bölmesinden Otomatikleştirme
  Bu kılavuzda nasıl PowerPoint'i otomatikleştiren bir özel görev bölmesi oluşturulacağını gösterir. Özel görev bölmesini kullanıcı tıklattığında slayta tarihler ekler bir <xref:System.Windows.Forms.MonthCalendar> özel görev bölmesi üzerindeki denetim.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Bu kılavuzda PowerPoint özellikle kullansa da, izlenecek yol tarafından gösterilen kavramlar yukarıda listelenen herhangi bir uygulama için geçerlidir.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Özel görev bölmesini kullanıcı arabiriminin tasarlama.  
  
-   PowerPoint özel görev bölmesinden otomatikleştirme.  
  
-   Özel görev bölmesini PowerPoint görüntüleme.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft PowerPoint 2010 veya [!INCLUDE[PowerPoint_15_short](../vsto/includes/powerpoint-15-short-md.md)].  
  
## <a name="creating-the-add-in-project"></a>Eklenti projesi oluşturma  
 İlk adım, PowerPoint için VSTO eklenti projesindeki oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir PowerPoint VSTO eklenti projesi oluşturun **MyAddIn**, PowerPoint Eklentisi proje şablonunu kullanarak. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]açılır **ThisAddIn.cs** veya **ThisAddIn.vb** kod dosyası ve ekler **MyAddIn** için proje **Çözüm Gezgini**.  
  
## <a name="designing-the-user-interface-of-the-custom-task-pane"></a>Özel görev bölmesini kullanıcı arabiriminin tasarlama  
 Özel görev bölmeleri için görsel tasarımcı yoktur, ancak, istediğiniz düzene sahip bir kullanıcı denetimi tasarlayabilirsiniz. Bu kılavuzda daha sonra kullanıcı denetimi için özel görev bölmesini ekleyeceksiniz.  
  
#### <a name="to-design-the-user-interface-of-the-custom-task-pane"></a>Özel görev bölmesini kullanıcı arabiriminin tasarlamak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **kullanıcı denetimi Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, kullanıcı denetimi adını değiştirmek **MyUserControl**, tıklatıp **Ekle**.  
  
     Kullanıcı denetimi Tasarımcısı'nda açılır.  
  
3.  Gelen **ortak denetimler** sekmesinde **araç**, sürükleyin bir **MonthCalendar** kullanıcı denetimi için denetim.  
  
     Varsa **MonthCalendar** denetim kullanıcı denetimi tasarım yüzeyi büyükse, kullanıcı denetimi sığdırmak için yeniden boyutlandır **MonthCalendar** denetim.  
  
## <a name="automating-powerpoint-from-the-custom-task-pane"></a>PowerPoint özel görev bölmesinden otomatikleştirme  
 Seçilen tarih etkin sunu ilk Slayt üzerinde getirmek için VSTO eklentisi amacı içindir. Kullanım <xref:System.Windows.Forms.MonthCalendar.DateChanged> değiştiğinde seçilen tarihten eklemek için denetiminin olayı.  
  
#### <a name="to-automate-powerpoint-from-the-custom-task-pane"></a>Özel görev bölmesinden PowerPoint'i otomatikleştirmek için  
  
1.  Tasarımcıda çift <xref:System.Windows.Forms.MonthCalendar> denetim.  
  
     **MyUserControl.cs** veya **MyUserControl.vb** dosya açar ve bir olay işleyicisi için <xref:System.Windows.Forms.MonthCalendar.DateChanged> olay oluşturulur.  
  
2.  Aşağıdaki kodu dosyanın en üstüne ekleyin. Bu kod için diğer adlar oluşturur <xref:Microsoft.Office.Core> ve <xref:Microsoft.Office.Interop.PowerPoint> ad alanları.  
  
     [!code-csharp[Trin_TaskPaneMonthCalendar#1](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#1)]
     [!code-vb[Trin_TaskPaneMonthCalendar#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#1)]  
  
3.  Aşağıdaki kodu ekleyin `MyUserControl` sınıfı. Bu kod bildirir bir <xref:Microsoft.Office.Interop.PowerPoint.Shape> nesnesi bir üyesi olarak `MyUserControl`. Aşağıdaki adımda bunu kullanacaksınız <xref:Microsoft.Office.Interop.PowerPoint.Shape> etkin sunuya bir slayta bir metin kutusu eklemek için.  
  
     [!code-csharp[Trin_TaskPaneMonthCalendar#2](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#2)]
     [!code-vb[Trin_TaskPaneMonthCalendar#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#2)]  
  
4.  Değiştir `monthCalendar1_DateChanged` aşağıdaki kod ile olay işleyicisi. Bu kod etkin sunuya ilk slayta bir metin kutusu ekler ve ardından seçili tarih metin kutusuna ekler. Bu kodu kullanır `Globals.ThisAddIn` PowerPoint nesne modeline erişmek için nesne.  
  
     [!code-csharp[Trin_TaskPaneMonthCalendar#3](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#3)]
     [!code-vb[Trin_TaskPaneMonthCalendar#3](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#3)]  
  
5.  İçinde **Çözüm Gezgini**, sağ **MyAddIn** proje ve ardından **yapı**. Projenin hatasız oluşturulduğunu doğrulayın.  
  
## <a name="displaying-the-custom-task-pane"></a>Özel görev bölmesini görüntüleme  
 VSTO Eklenti başladığında özel görev bölmesi görüntülemek için görev bölmesinde kullanıcı denetimi Ekle <xref:Microsoft.Office.Tools.AddIn.Startup> VSTO eklentisinin olay işleyicisi.  
  
#### <a name="to-display-the-custom-task-pane"></a>Özel görev bölmesini görüntülemek için  
  
1.  İçinde **Çözüm Gezgini**, genişletin **PowerPoint**.  
  
2.  Sağ **ThisAddIn.cs** veya **ThisAddIn.vb** tıklatıp **görünümü kodu**.  
  
3.  Aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Bu kod örneklerini bildirir `MyUserControl` ve <xref:Microsoft.Office.Tools.CustomTaskPane> üyeleri olarak `ThisAddIn` sınıfı.  
  
     [!code-vb[Trin_TaskPaneMonthCalendar#4](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/ThisAddIn.vb#4)]
     [!code-csharp[Trin_TaskPaneMonthCalendar#4](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/ThisAddIn.cs#4)]  
  
4.  Değiştir `ThisAddIn_Startup` aşağıdaki kod ile olay işleyicisi. Bu kod yeni bir oluşturur <xref:Microsoft.Office.Tools.CustomTaskPane> ekleyerek `MyUserControl` nesnesine `CustomTaskPanes` koleksiyonu. Kod ayrıca görev bölmesini görüntüler.  
  
     [!code-vb[Trin_TaskPaneMonthCalendar#5](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/ThisAddIn.vb#5)]
     [!code-csharp[Trin_TaskPaneMonthCalendar#5](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/ThisAddIn.cs#5)]  
  
## <a name="testing-the-add-in"></a>Eklentiyi test etme  
 Projeyi çalıştırdığınızda PowerPoint açar ve VSTO eklentisi özel görev bölmesini görüntüler. Tıklatın <xref:System.Windows.Forms.MonthCalendar> kodu test etmek için denetim.  
  
#### <a name="to-test-your-vsto-add-in"></a>VSTO eklentinizi sınamak için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Özel görev bölmesini görünür olduğunu doğrulayın.  
  
3.  Bir tarihi tıklayın <xref:System.Windows.Forms.MonthCalendar> görev bölmesindeki denetim.  
  
     Tarih etkin sunuya ilk slayt eklenir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Özel görev bölmeleri aşağıdaki konulardan oluşturma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Özel görev bölmesini VSTO eklenti için farklı bir uygulama oluşturun. Özel görev bölmeleri destekleyen uygulamalar hakkında daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
-   Özel görev bölmesini görüntülemek veya gizlemek için kullanılan bir Şerit düğmesi oluşturun. Daha fazla bilgi için bkz: [izlenecek yol: özel görev bölmesini Şerit düğmesi ile eşitleme](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md).  
  
-   Outlook'ta açılmış her e-posta iletisi için bir özel görev bölmesi oluşturun. Daha fazla bilgi için bkz: [izlenecek yol: Outlook e-posta iletilerini ile birlikte özel görev bölmelerini görüntüleme](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel görev bölmeleri](../vsto/custom-task-panes.md)   
 [Nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [İzlenecek yol: özel görev bölmesini Şerit düğmesi ile eşitleme](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md)   
 [İzlenecek Yol: Outlook'ta E-Posta İletileri ile Birlikte Özel Görev Bölmelerini Görüntüleme](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)  
  
  