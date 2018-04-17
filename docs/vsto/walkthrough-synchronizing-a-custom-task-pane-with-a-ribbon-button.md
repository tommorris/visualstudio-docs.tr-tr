---
title: 'İzlenecek yol: özel görev bölmesini Şerit düğmesi ile eşitleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom task panes [Office development in Visual Studio], showing and hiding
- showing custom task panes
- Ribbon [Office development in Visual Studio], custom task panes
- toggle buttons [Office development in Visual Studio]
- custom task panes [Office development in Visual Studio], synchronizing with Ribbon button
- user interfaces [Office development in Visual Studio], custom task panes
- synchronization [Office development in Visual Studio], custom task panes
- task panes [Office development in Visual Studio], showing and hiding
- custom task panes [Office development in Visual Studio], creating
- hiding custom task panes
- task panes [Office development in Visual Studio], creating
- task panes [Office development in Visual Studio], synchronizing with Ribbon button
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ff3252a1ae234615cc4d4ed83a07d98a15092bee
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button"></a>İzlenecek Yol: Özel Görev Bölmesini Şerit Düğmesi ile Eşitleme
  Bu kılavuzda, kullanıcıların Gizle veya Şerit üzerindeki iki durumlu düğmeye tıklayarak görüntülemek bir özel görev bölmesi oluşturmak gösterilmiştir. Microsoft Office uygulamaları kullanıcıların özel görev bölmeleri göstermek veya gizlemek varsayılan bir yol sağlamadığından, görüntüleme ya da, özel görev bölmesini gizleme için tıklatabileceği bir düğme gibi bir kullanıcı arabirimi (UI) öğesini her zaman oluşturmanız gerekir.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Bu kılavuzda özellikle Excel kullanıyor olsa da, izlenecek yol tarafından gösterilen kavramlar yukarıda listelenen herhangi bir uygulama için uygulanabilir.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Özel görev bölmesini UI tasarlama.  
  
-   İki durumlu düğme Şerite ekleniyor.  
  
-   İki durumlu düğme birlikte özel görev bölmesini eşitleniyor.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Excel veya Microsoft [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)].  
  
## <a name="creating-the-add-in-project"></a>Eklenti projesi oluşturma  
 Bu adımda, Excel için VSTO eklenti projesindeki oluşturur.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adında bir Excel eklenti projesi oluşturun **SynchronizeTaskPaneAndRibbon**, Excel eklentisi proje şablonunu kullanarak. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] açılır **ThisAddIn.cs** veya **ThisAddIn.vb** kod dosyası ve ekler **SynchronizeTaskPaneAndRibbon** için proje **Çözüm Gezgini**.  
  
## <a name="adding-a-toggle-button-to-the-ribbon"></a>Şerit'e iki durumlu düğme ekleme  
 Office uygulaması tasarım yönergeleri kullanıcıların Office uygulama kullanıcı Arabirimi her zaman denetlemeleri biridir. Özel görev bölmesini denetlemek için kullanıcıları etkinleştirmek üzere gösterir ve görev bölmesini gizler Şerit iki durumlu düğme ekleyebilirsiniz. İki durumlu düğme oluşturmak için Ekle bir **Şerit (Görsel Tasarımcı)** proje öğesi. Tasarımcı ekleyin ve denetimleri getirin, denetim özelliklerini ayarlamak ve denetim olayları işlemek yardımcı olur. Daha fazla bilgi için bkz: [Şerit Tasarımcısı](../vsto/ribbon-designer.md).  
  
#### <a name="to-add-a-toggle-button-to-the-ribbon"></a>İki durumlu düğme Şerite eklemek için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Şerit (Görsel Tasarımcı)**.  
  
3.  Yeni Şerit adını değiştirmek **ManageTaskPaneRibbon**, tıklatıp **Ekle**.  
  
     **ManageTaskPaneRibbon.cs** veya **ManageTaskPaneRibbon.vb** dosyası Şerit Tasarımcısı'nda açılır ve varsayılan bir sekme ve grup görüntüler.  
  
4.  Şerit Tasarımcısı'nda tıklatın **group1**.  
  
5.  İçinde **özellikleri** penceresindeki ayarlayın **etiket** özelliğine **Görev Bölmesi Yöneticisi**.  
  
6.  Gelen **Office Şerit denetimleri** sekmesinde **araç**, sürükleyin bir **ToggleButton** üzerine **Görev Bölmesi Yöneticisi** grubu.  
  
7.  Tıklatın **toggleButton1**.  
  
8.  İçinde **özellikleri** penceresindeki ayarlayın **etiket** özelliğine **görev bölmesini göster**.  
  
## <a name="designing-the-user-interface-of-the-custom-task-pane"></a>Özel görev bölmesini kullanıcı arabiriminin tasarlama  
 Özel görev bölmeleri için görsel tasarımcı yoktur, ancak, istediğiniz düzene sahip bir kullanıcı denetimi tasarlayabilirsiniz. Bu kılavuzda daha sonra kullanıcı denetimi için özel görev bölmesini ekleyeceksiniz.  
  
#### <a name="to-design-the-user-interface-of-the-custom-task-pane"></a>Özel görev bölmesini kullanıcı arabiriminin tasarlamak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **kullanıcı denetimi Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, kullanıcı denetimi adını değiştirmek **TaskPaneControl**, tıklatıp **Ekle**.  
  
     Kullanıcı denetimi Tasarımcısı'nda açılır.  
  
3.  Gelen **ortak denetimler** sekmesinde **araç**, sürükleyin bir **TextBox** kullanıcı denetimi için denetim.  
  
## <a name="creating-the-custom-task-pane"></a>Özel görev bölmesi oluşturma  
 VSTO Eklenti başladığında özel görev bölmesi oluşturmak için görev bölmesinde kullanıcı denetimi Ekle <xref:Microsoft.Office.Tools.AddIn.Startup> VSTO eklentisinin olay işleyicisi. Varsayılan olarak, özel görev bölmesini görünür olmaz. Bu kılavuzda daha sonra görüntülenen veya kullanıcı Şerit'e eklenen iki durumlu düğmeye tıkladığında görev bölmesini Gizle kod ekleyeceksiniz.  
  
#### <a name="to-create-the-custom-task-pane"></a>Özel görev bölmesi oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, genişletin **Excel**.  
  
2.  Sağ **ThisAddIn.cs** veya **ThisAddIn.vb** tıklatıp **görünümü kodu**.  
  
3.  Aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Bu kod örneği bildirir `TaskPaneControl` bir üyesi olarak `ThisAddIn`.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#1](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#1)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#1)]  
  
4.  Değiştir `ThisAddIn_Startup` aşağıdaki kod ile olay işleyicisi. Bu kod ekler `TaskPaneControl` nesnesini `CustomTaskPanes` alan, ancak özel görev bölmesini görüntülemez (varsayılan olarak, <xref:Microsoft.Office.Tools.CustomTaskPane.Visible%2A> özelliği <xref:Microsoft.Office.Tools.CustomTaskPane> sınıf **false**). Visual C# kodu aynı zamanda bir olay işleyicisi ekler <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> olay.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#2](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#2)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#2)]  
  
5.  Aşağıdaki yöntemi ekleyin `ThisAddIn` sınıfı. Bu yöntem işleme <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> olay. Kullanıcının kapattığı zaman görev bölmesinde tıklatarak **Kapat** düğmesini (X), geçiş durumunu düğmesini Şerit'te bu yöntemi güncelleştirmeler.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#3](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#3)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#3](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#3)]  
  
6.  Aşağıdaki özellik ekleme `ThisAddIn` sınıfı. Bu özellik özel sunan `myCustomTaskPane1` başka sınıfların nesnesi. Bu kılavuzda daha sonra kod ekleyeceksiniz `MyRibbon` bu özelliği kullanan sınıfı.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#4](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#4)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#4](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#4)]  
  
## <a name="hiding-and-showing-the-custom-task-pane-by-using-the-toggle-button"></a>İki durumlu düğme kullanarak özel görev bölmesini gösterme ve gizleme  
 Son adım, kullanıcı Şerit üzerindeki iki durumlu düğmeye tıkladığında özel görev bölmesini gizler veya gösterir kod eklemektir.  
  
#### <a name="to-display-and-hide-the-custom-task-pane-by-using-the-toggle-button"></a>İki durumlu düğme kullanarak özel görev bölmesini gizlemek ve görüntülemek için  
  
1.  Şerit Tasarımcısı'nda çift **görev bölmesini göster** iki durumlu düğme.  
  
     Visual Studio otomatik olarak adlı bir olay işleyicisi oluşturur `toggleButton1_Click`, yürüten <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> iki durumlu düğme olayı. Visual Studio ayrıca açar **MyRibbon.cs** veya **MyRibbon.vb** Kod Düzenleyicisi'nde dosya.  
  
2.  Değiştir `toggleButton1_Click` aşağıdaki kod ile olay işleyicisi. Kullanıcı iki durumlu düğmeye tıkladığında bu kodu görüntüler veya olup iki durumlu düğmeye basıldığında veya basılı olmadığından bağlı olarak özel görev bölmesini gizler.  
  
     [!code-vb[Trin_TaskPaneRibbonSynchronize#5](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ManageTaskPaneRibbon.vb#5)]
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#5](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ManageTaskPaneRibbon.cs#5)]  
  
## <a name="testing-the-add-in"></a>Eklentiyi test etme  
 Projeyi çalıştırdığınızda, özel görev bölmesini görüntülemeden Excel açar. Kodu test etmek için Şerit'te iki durumlu düğmeye tıklayın.  
  
#### <a name="to-test-your-vsto-add-in"></a>VSTO eklentinizi sınamak için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
     Excel açıldığını onaylayın ve **eklentileri** sekmesi Şerit'te görünür.  
  
2.  Tıklatın **eklentileri** Şeritte sekmesi.  
  
3.  İçinde **Görev Bölmesi Yöneticisi** grubunda **görev bölmesini göster** iki durumlu düğme.  
  
     Görev bölmesi dönüşümlü olarak görüntülenir ve iki durumlu düğmeye tıkladığınızda gizli doğrulayın.  
  
4.  Görev bölmesi görünüyorsa tıklayın **Kapat** görev bölmesinde köşesindeki düğmesini (X).  
  
     İki durumlu düğme basılı olmadığından göründüğünü doğrulayın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Özel görev bölmeleri aşağıdaki konulardan oluşturma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Özel görev bölmesini VSTO eklenti için farklı bir uygulama oluşturun. Özel görev bölmeleri destekleyen uygulamalar hakkında daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
-   Bir uygulamayı özel görev bölmesinden otomatikleştirme. Daha fazla bilgi için bkz: [izlenecek yol: uygulamayı özel görev bölmesinden otomatikleştirme](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md).  
  
-   Outlook'ta açılmış her e-posta iletisi için bir özel görev bölmesi oluşturun. Daha fazla bilgi için bkz: [izlenecek yol: Outlook e-posta iletilerini ile birlikte özel görev bölmelerini görüntüleme](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel görev bölmeleri](../vsto/custom-task-panes.md)   
 [Nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [İzlenecek yol: uygulamayı özel görev bölmesinden otomatikleştirme](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)   
 [İzlenecek yol: Outlook'ta e-posta iletileri ile birlikte özel görev bölmelerini görüntüleme](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)   
 [Şeride Genel Bakış](../vsto/ribbon-overview.md)  
  
  