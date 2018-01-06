---
title: "İzlenecek yol: Outlook'ta e-posta iletileri ile birlikte özel görev bölmelerini görüntüleme | Microsoft Docs"
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
- Outlook [Office development in Visual Studio], custom task panes
- task panes [Office development in Visual Studio], displaying with e-mail messages
- displaying custom task panes in e-mail
- e-mail [Office development in Visual Studio], custom task panes displayed in
- custom task panes [Office development in Visual Studio], displaying with e-mail messages
ms.assetid: 04943967-a7ef-4876-9584-84ada427e3f3
caps.latest.revision: "59"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: c96744b433f4ad481e500420ffeab8caad3772c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook"></a>İzlenecek Yol: Outlook'ta E-Posta İletileri ile Birlikte Özel Görev Bölmelerini Görüntüleme
  Bu kılavuz, oluşturulan veya açılan her e-posta iletisi birlikte özel görev bölmesini benzersiz bir örneğini görüntülemek gösterilmiştir. Kullanıcılar, görüntüleme ya da her e-posta iletisi Şerit üzerinde bir düğmeyi kullanarak özel görev bölmesini gizleme.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Çoklu Explorer veya Inspector windows birlikte özel görev bölmesini görüntülemek için açılan her penceresi için özel görev bölmesi örneği oluşturmanız gerekir. Özel görev bölmeleri Outlook Windows davranışı hakkında daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
> [!NOTE]  
>  Bu kılavuzda kodu arkasındaki mantığı ele kolaylaştırmak için küçük bölümlerde VSTO eklenti kodu gösterir.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Özel görev bölmesini kullanıcı arabirimini (UI) tasarlama.  
  
-   Özel Şerit kullanıcı Arabirimi oluşturma.  
  
-   Özel Şerit UI'e-posta iletileri ile görüntüleme.  
  
-   Inspector pencerelerini ve özel görev bölmelerini yönetmek için bir sınıf oluşturursunuz.  
  
-   Başlatma ve VSTO eklentisi tarafından kullanılan kaynakları temizleniyor.  
  
-   Birlikte özel görev bölmesini Şerit iki durumlu düğme eşitleniyor.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)] veya Microsoft Outlook 2010.  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: kullanım görev bölmeleri Outlook'ta?](http://go.microsoft.com/fwlink/?LinkID=130309).  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 Özel görev bölmeleri VSTO eklentileri içinde uygulanır. Outlook için VSTO eklenti projesindeki oluşturarak başlayın.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Oluşturma bir **Outlook eklentisi** adlı proje **OutlookMailItemTaskPane**. Kullanım **Outlook eklentisi** proje şablonu. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]açılır **ThisAddIn.cs** veya **ThisAddIn.vb** kod dosyası ve ekler **OutlookMailItemTaskPane** için proje **Çözüm Gezgini**.  
  
## <a name="designing-the-user-interface-of-the-custom-task-pane"></a>Özel görev bölmesini kullanıcı arabiriminin tasarlama  
 Özel görev bölmeleri için görsel tasarımcı yoktur, ancak istediğiniz kullanıcı Arabirimi ile bir kullanıcı denetimi tasarlayabilirsiniz. Bu VSTO eklenti özel görev bölmesinde içeren basit bir kullanıcı Arabirimi olan bir <xref:System.Windows.Forms.TextBox> denetim. Bu kılavuzda daha sonra kullanıcı denetimi için özel görev bölmesini ekleyeceksiniz.  
  
#### <a name="to-design-the-user-interface-of-the-custom-task-pane"></a>Özel görev bölmesini kullanıcı arabiriminin tasarlamak için  
  
1.  İçinde **Çözüm Gezgini**, tıklatın **OutlookMailItemTaskPane** projesi.  
  
2.  Üzerinde **proje** menüsünde tıklatın **kullanıcı denetimi Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, kullanıcı denetimi adını değiştirmek **TaskPaneControl**ve ardından **Ekle**.  
  
     Kullanıcı denetimi Tasarımcısı'nda açılır.  
  
4.  Gelen **ortak denetimler** sekmesinde **araç**, sürükleyin bir **TextBox** kullanıcı denetimi için denetim.  
  
## <a name="designing-the-user-interface-of-the-ribbon"></a>Şerit kullanıcı arabiriminin tasarlama  
 Bu VSTO eklenti için hedeflerinden kullanıcıların her e-posta iletisinin Şerit özel görev bölmesinden görüntülemek veya gizlemek için bir yol vermektir. Kullanıcı arabirimi sağlamak için görüntüleme veya özel görev bölmesini gizleme için tıklatabileceği iki durumlu düğme görüntüler özel bir Şerit UI oluşturun.  
  
#### <a name="to-create-a-custom-ribbon-ui"></a>Özel Şerit UI oluşturmak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Şerit (Görsel Tasarımcı)**.  
  
3.  Yeni Şerit adını değiştirmek **ManageTaskPaneRibbon**, tıklatıp **Ekle**.  
  
     **ManageTaskPaneRibbon.cs** veya **ManageTaskPaneRibbon.vb** dosyası Şerit Tasarımcısı'nda açılır ve varsayılan bir sekme ve grup görüntüler.  
  
4.  Şerit Tasarımcısı'nda tıklatın **group1**.  
  
5.  İçinde **özellikleri** penceresindeki ayarlayın **etiket** özelliğine **Görev Bölmesi Yöneticisi**.  
  
6.  Gelen **Office Şerit denetimleri** sekmesinde **araç**, bir ToggleButton denetimi sürükleyin **Görev Bölmesi Yöneticisi** grubu.  
  
7.  Tıklatın **toggleButton1**.  
  
8.  İçinde **özellikleri** penceresindeki ayarlayın **etiket** özelliğine **görev bölmesini göster**.  
  
## <a name="display-the-custom-ribbon-user-interface-with-e-mail-messages"></a>Özel Şerit kullanıcı arabirimini e-posta iletileri ile görüntüleme  
 Bu kılavuzda oluşturduğunuz özel görev bölmesi, e-posta iletilerini içeren Inspector windows ile görünmesi tasarlanmıştır. Bu nedenle, yalnızca bu windows ile özel Şerit UI görüntülenecek özellikleri ayarlayın.  
  
#### <a name="to-display-the-custom-ribbon-ui-with-e-mail-messages"></a>Özel Şerit UI'e-posta iletileri ile görüntülemek için  
  
1.  Şerit Tasarımcısı'nda tıklatın **ManageTaskPaneRibbon** Şerit.  
  
2.  İçinde **özellikleri** penceresinde, aşağı açılan listeden sonraki tıklatın **RibbonType**seçip **Microsoft.Outlook.Mail.Compose** ve  **Microsoft.Outlook.Mail.Read**.  
  
## <a name="creating-a-class-to-manage-inspector-windows-and-custom-task-panes"></a>Inspector pencerelerini ve özel görev bölmeleri yönetmek için bir sınıf oluşturma  
 İçinde için VSTO eklentisi hangi özel görev bölmesini belirli e-posta iletisi ile ilişkili olduğunu bulduğu bazı durumlar vardır. Bu durumlar şunlardır:  
  
-   Kullanıcının e-posta iletisine kapattığı zaman. Bu durumda, VSTO eklenti VSTO eklenti tarafından kullanılan kaynakları doğru temizlendiğinden emin olmak için karşılık gelen özel görev bölmesini kaldırmanız gerekir.  
  
-   Kullanıcının özel görev bölmesini kapattığı zaman. Bu durumda, VSTO eklenti e-posta iletisinin Şerit üzerindeki iki durumlu düğme durumunu güncelleştirmeniz gerekir.  
  
-   Kullanıcı Şerit üzerindeki iki durumlu düğme tıkladığında. Bu durumda, VSTO eklenti Gizle veya gerekir karşılık gelen görev bölmesini görüntüler.  
  
 VSTO hangi özel görev bölmesini her açık e-posta iletisiyle ilişkili izlemek eklentiyi etkinleştirmek için çiftlerini saran özel bir sınıf oluşturun <xref:Microsoft.Office.Interop.Outlook.Inspector> ve <xref:Microsoft.Office.Tools.CustomTaskPane> nesneleri. Bu sınıf her e-posta iletisi için yeni bir özel görev bölmesi nesnesi oluşturur ve karşılık gelen e-posta iletisi kapalı olduğunda özel görev bölmesini siler.  
  
#### <a name="to-create-a-class-to-manage-inspector-windows-and-custom-task-panes"></a>Inspector pencerelerini ve özel görev bölmeleri yönetmek için bir sınıf oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **ThisAddIn.cs** veya **ThisAddIn.vb** dosya ve ardından **görünümü kodu**.  
  
2.  Aşağıdaki deyimleri dosyasının üstüne ekleyin.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#2](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#2)]
     [!code-vb[Trin_OutlookMailItemTaskPane#2](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#2)]  
  
3.  Aşağıdaki kodu ekleyin **ThisAddIn.cs** veya **ThisAddIn.vb** dışında dosya `ThisAddIn` sınıfı (Visual C# için bu kodu içine ekleyin `OutlookMailItemTaskPane` ad alanı). `InspectorWrapper` Sınıfı yönetir çifti <xref:Microsoft.Office.Interop.Outlook.Inspector> ve <xref:Microsoft.Office.Tools.CustomTaskPane> nesneleri. Aşağıdaki adımlarda bu sınıfının tanımını tamamlanır.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#3](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#3)]
     [!code-vb[Trin_OutlookMailItemTaskPane#3](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#3)]  
  
4.  Önceki adımda eklediğiniz koddan sonra aşağıdaki oluşturucuyu ekleyin. Bu oluşturucu oluşturur ve ilişkili olduğu yeni bir özel görev bölmesi başlatır <xref:Microsoft.Office.Interop.Outlook.Inspector> geçirilen nesne. C# ' ta Oluşturucusu ayrıca olay işleyicilerine iliştirir <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_Event.Close> olayı <xref:Microsoft.Office.Interop.Outlook.Inspector> nesne ve <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> olayı <xref:Microsoft.Office.Tools.CustomTaskPane> nesnesi.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#4](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#4)]
     [!code-vb[Trin_OutlookMailItemTaskPane#4](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#4)]  
  
5.  Önceki adımda eklediğiniz koddan sonra aşağıdaki yöntemi ekleyin. Bu yöntem için bir olay işleyicisidir <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> olayı <xref:Microsoft.Office.Tools.CustomTaskPane> bulunan nesne `InspectorWrapper` sınıfı. Her kullanıcı açar veya özel görev bölmesini kapatır Bu kod iki durumlu düğme durumunu güncelleştirir.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#5](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#5)]
     [!code-vb[Trin_OutlookMailItemTaskPane#5](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#5)]  
  
6.  Önceki adımda eklediğiniz koddan sonra aşağıdaki yöntemi ekleyin. Bu yöntem için bir olay işleyicisidir <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_Event.Close> olayı <xref:Microsoft.Office.Interop.Outlook.Inspector> geçerli e-posta iletisi içeren nesne. E-posta iletisi kapatıldığında olay işleyicisi kaynakları serbest bırakır. Olay işleyicisi de geçerli özel görev bölmesinden kaldırır `CustomTaskPanes` koleksiyonu. Bu, sonraki e-posta iletisi açıldığında özel görev bölmesini birden çok örneğini önlemeye yardımcı olur.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#6](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#6)]
     [!code-vb[Trin_OutlookMailItemTaskPane#6](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#6)]  
  
7.  Önceki adımda eklediğiniz koddan sonra aşağıdaki kodu ekleyin. Bu kılavuzda daha sonra bu özellik kullanıcı arabiriminde özel Şerit görüntülemek veya özel görev bölmesini gizlemek için bir yöntem çağıracaksınız.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#7](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#7)]
     [!code-vb[Trin_OutlookMailItemTaskPane#7](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#7)]  
  
## <a name="initializing-and-cleaning-up-resources-used-by-the-add-in"></a>Başlatma ve eklenti tarafından kullanılan kaynakları temizleme  
 Kodu ekleyin `ThisAddIn` sınıfı için VSTO eklentisi yüklendiğinde başlatmak ve kaldırıldığında VSTO eklenti tarafından kullanılan kaynakları temizlemek için. VSTO eklenti için bir olay işleyicisi ayarlayarak başlatır <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> olay ve tüm mevcut e-posta iletilerini bu olay işleyicisine geçirerek. VSTO Eklenti kaldırıldığında, olay işleyicisini ayırın ve VSTO eklentisi tarafından kullanılan nesneleri temizleyin.  
  
#### <a name="to-initialize-and-clean-up-resources-used-by-the-vsto-add-in"></a>Başlatmak ve VSTO eklentisi tarafından kullanılan kaynakları temizlemek için  
  
1.  İçinde **ThisAddIn.cs** veya **ThisAddIn.vb** dosya, tanımını bulun `ThisAddIn` sınıfı.  
  
2.  Aşağıdaki bildirimi ekleme `ThisAddIn` sınıfı:  
  
    -   `inspectorWrappersValue` Alanı içeren tüm <xref:Microsoft.Office.Interop.Outlook.Inspector> ve `InspectorWrapper` VSTO eklenti tarafından yönetilen nesneleri.  
  
    -   `inspectors` Alan geçerli Outlook örneğinde Inspector penceresi koleksiyonuna bir başvuru korur. Bu başvuru için olay işleyicisini içeren belleği boşaltmasını atık toplayıcı engeller <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> sonraki adımda tanımlayacağınız olay.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#8](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#8)]
     [!code-vb[Trin_OutlookMailItemTaskPane#8](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#8)]  
  
3.  Değiştir `ThisAddIn_Startup` aşağıdaki kod ile yöntemi. Bu kod bir olay işleyicisi ekler <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> olay ve geçirir var olan bütün <xref:Microsoft.Office.Interop.Outlook.Inspector> olay işleyicisine nesnesi. Outlook çalışmaya başladıktan sonra kullanıcı için VSTO eklentisi yüklerse VSTO eklenti bu bilgileri zaten açık olan tüm e-posta iletileri için özel görev bölmeleri oluşturmak için kullanır.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#9](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#9)]
     [!code-vb[Trin_OutlookMailItemTaskPane#9](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#9)]  
  
4.  Değiştir `ThisAddIn_ShutDown` aşağıdaki kod ile yöntemi. Bu kod ayırır <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> olay işleyicisi ve VSTO eklentisi tarafından kullanılan nesneleri temizler.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#10](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#10)]
     [!code-vb[Trin_OutlookMailItemTaskPane#10](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#10)]  
  
5.  Aşağıdakileri ekleyin <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> olay işleyicisine `ThisAddIn` sınıfı. Yeni <xref:Microsoft.Office.Interop.Outlook.Inspector> bir e-posta iletisini içeren yöntemi yeni bir örneğini oluşturur `InspectorWrapper` e-posta iletisi ve ilgili görev bölmesi arasındaki ilişkiyi yönetmek için nesnesi.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#11](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#11)]
     [!code-vb[Trin_OutlookMailItemTaskPane#11](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#11)]  
  
6.  Aşağıdaki özellik ekleme `ThisAddIn` sınıfı. Bu özellik özel sunan `inspectorWrappersValue` dışındaki kodu alanı `ThisAddIn` sınıfı.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#12](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#12)]
     [!code-vb[Trin_OutlookMailItemTaskPane#12](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#12)]  
  
## <a name="checkpoint"></a>Denetim noktası  
 Projenizi hatasız derlendiğinden emin olmak için yapılandırın.  
  
#### <a name="to-build-your-project"></a>Projenizi yapılandırmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **OutlookMailItemTaskPane** proje ve ardından **yapı**. Proje hatasız derlendiğinden emin olun.  
  
## <a name="synchronizing-the-ribbon-toggle-button-with-the-custom-task-pane"></a>Birlikte özel görev bölmesini Şerit iki durumlu düğme eşitleniyor  
 İki durumlu düğme içinde görev bölmesinde görünür değil ve görev bölmesinde gizli olarak basılması değil görünür basıldığında görünecektir. Düğmenin durumunu birlikte özel görev bölmesini eşitlemek için değiştirme <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> aç/kapa düğmesi olay işleyicisi.  
  
#### <a name="to-synchronize-the-custom-task-pane-with-the-toggle-button"></a>Özel görev bölmesini aç/kapa düğmesi ile eşitlemek için  
  
1.  Şerit Tasarımcısı'nda çift **görev bölmesini göster** iki durumlu düğme.  
  
     Visual Studio otomatik olarak adlı bir olay işleyicisi oluşturur `toggleButton1_Click`, yürüten <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> iki durumlu düğme olayı. Visual Studio ayrıca açar **ManageTaskPaneRibbon.cs** veya **ManageTaskPaneRibbon.vb** Kod Düzenleyicisi'nde dosya.  
  
2.  Aşağıdaki deyimleri en üst kısmına ekleyin **ManageTaskPaneRibbon.cs** veya **ManageTaskPaneRibbon.vb** dosya.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#14](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ManageTaskPaneRibbon.cs#14)]
     [!code-vb[Trin_OutlookMailItemTaskPane#14](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ManageTaskPaneRibbon.vb#14)]  
  
3.  Değiştir `toggleButton1_Click` aşağıdaki kod ile olay işleyicisi. Kullanıcı iki durumlu düğmeye tıkladığında, bu yöntem gizler veya geçerli Inspector penceresiyle ilişkili özel görev bölmesini görüntüler.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#15](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ManageTaskPaneRibbon.cs#15)]
     [!code-vb[Trin_OutlookMailItemTaskPane#15](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ManageTaskPaneRibbon.vb#15)]  
  
## <a name="testing-the-project"></a>Projeyi test etme  
 Projeyi hata ayıklama başlattığınızda, Outlook açar ve VSTO eklentisi yüklenir. VSTO eklenti açıldığında her e-posta iletisi birlikte özel görev bölmesini benzersiz bir örneğini gösterir. Kodu test etmek için birkaç yeni e-posta iletileri oluşturun.  
  
#### <a name="to-test-the-vsto-add-in"></a>VSTO eklenti sınamak için  
  
1.  F5 tuşuna basın.  
  
2.  Outlook içinde tıklatın **yeni** yeni bir e-posta iletisi oluşturmak için.  
  
3.  E-posta iletisi Şerit üzerinde tıklatın **eklentileri** sekmesini ve ardından **görev bölmesini göster** düğmesi.  
  
     Doğrulayın başlığı görev bölmesiyle **My görev bölmesi** e-posta iletisi görüntülenir.  
  
4.  Görev bölmesinde yazın **birinci görev bölmesi** metin kutusuna.  
  
5.  Görev bölmesini kapatın.  
  
     Doğrulayın durumunu **görev bölmesini göster** düğmesi değiştiğini artık basıldığında.  
  
6.  Tıklatın **görev bölmesini göster** yeniden düğmesine tıklayın.  
  
     Görev bölmesi açılır ve metin kutusunda hala dize içerdiğini doğrulayın **birinci görev bölmesi**.  
  
7.  Outlook içinde tıklatın **yeni** ikinci bir e-posta iletisi oluşturmak için.  
  
8.  E-posta iletisi Şerit üzerinde tıklatın **eklentileri** sekmesini ve ardından **görev bölmesini göster** düğmesi.  
  
     Doğrulayın başlığı görev bölmesiyle **My görev bölmesi** e-posta iletisi görüntülenir ve bu görev bölmesindeki metin kutusu boştur.  
  
9. Görev bölmesinde yazın **ikinci görev bölmesi** metin kutusuna.  
  
10. Odağı ilk e-posta iletisi değiştirin.  
  
     Bu e-posta iletisiyle ilişkili görev bölmesi hala görüntülediğini doğrulamak **birinci görev bölmesi** metin kutusuna.  
  
 Bu VSTO eklenti da daha fazla işleme Gelişmiş deneyebilirsiniz senaryoları. Örneğin, kullanarak e-postaları görüntülerken eklentinin davranışını sınayabilirsiniz **sonraki öğeye** ve **önceki öğeyi** düğmeler. VSTO eklentiyi, birden fazla e-posta iletilerini açtığınızda ve VSTO eklentisi yeniden davranışı test edebilirsiniz.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Özel görev bölmeleri aşağıdaki konulardan oluşturma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Özel görev bölmesini VSTO eklenti için farklı bir uygulama oluşturun. Özel görev bölmeleri destekleyen uygulamalar hakkında daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
-   Microsoft Office uygulamasını özel görev bölmesini kullanarak otomatik hale. Daha fazla bilgi için bkz: [izlenecek yol: uygulamayı özel görev bölmesinden otomatikleştirme](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md).  
  
-   Şerit düğmesi özel görev bölmesini görüntülemek veya gizlemek için kullanılan Excel'de oluşturun. Daha fazla bilgi için bkz: [izlenecek yol: özel görev bölmesini Şerit düğmesi ile eşitleme](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel görev bölmeleri](../vsto/custom-task-panes.md)   
 [Nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [İzlenecek yol: uygulamayı özel görev bölmesinden otomatikleştirme](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)   
 [İzlenecek yol: özel görev bölmesini Şerit düğmesi ile eşitleme](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Outlook nesne modeline genel bakış](../vsto/outlook-object-model-overview.md)   
 [Çalışma Zamanında Şeride Erişme](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  