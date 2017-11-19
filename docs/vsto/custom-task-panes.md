---
title: "Özel görev bölmeleri | Microsoft Docs"
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
- Office development in Visual Studio, task panes
- user interface panels [Office development in Visual Studio]
- task panes [Office development in Visual Studio]
- user interfaces [Office development in Visual Studio], custom task panes
- custom task panes [Office development in Visual Studio], creating
- task panes [Office development in Visual Studio]. multiple application windows
- custom task panes [Office development in Visual Studio], multiple application windows
- task panes [Office development in Visual Studio], creating
- application-level add-ins [Office development in Visual Studio], custom task panes
- multiple applications windows with custom task panes [Office development in Visual Studio]
- add-ins [Office development in Visual Studio], custom task panes
- custom task panes [Office development in Visual Studio]
- task panes [Office development in Visual Studio], about custom task panes
- custom task panes [Office development in Visual Studio], about custom task panes
ms.assetid: 9a415109-5333-433e-95c6-3d59ce9c4d02
caps.latest.revision: "52"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 097a4247ccc7604dd4c39b81e0f733578fc91c89
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="custom-task-panes"></a>Özel Görev Bölmeleri
  Görev bölmeleri genellikle bir tarafa bir Microsoft Office uygulamasında penceresinin yerleştirilmiş kullanıcı arabirimi bölmeleri sunulmuştur. Özel görev bölmeleri kendi görev bölmesi oluşturmak ve kullanıcıların çözümünüzün özelliklerine erişmek için tanıdık bir arabirim sağlamak için bir yol sağlar. Örneğin, arabirim belgelerini değiştirme veya bir veri kaynağından görüntülemek için kodu çalıştırma denetimlerini içerebilir.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  Özel görev bölmesi Eylemler bölmesinden farklılık gösterir. Eylemler bölmesinde Microsoft Office Word ve Microsoft Office Excel için belge düzeyi özelleştirmeleri bir parçasıdır. Daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md).  
  
## <a name="benefits-of-custom-task-panes"></a>Özel görev bölmeleri yararları  
 Özel görev bölmeleri özelliklerinizi tanıdık kullanıcı arabirimi ile tümleştirmenize olanak sağlar. Visual Studio araçları kullanarak bir özel görev bölmesi hızlı bir şekilde oluşturabilirsiniz.  
  
### <a name="familiar-user-interface"></a>Tanıdık kullanıcı arabirimi  
 Microsoft Office sistemi uygulamalarında kullanıcılarının görev bölmeleri gibi kullandıysanız zaten **stiller ve biçimlendirme** Word görev bölmesinde. Özel görev bölmeleri, Microsoft Office sistemi diğer görev bölmeleri gibi davranır. Kullanıcıların uygulama penceresinin farklı kenarlara özel görev bölmeleri sabitleyebilirsiniz veya penceresinde herhangi bir konuma özel görev bölmeleri sürükleyebilirsiniz. Bir VSTO aynı anda birden çok özel görev bölmeleri görüntüleyen eklenti oluşturabilirsiniz ve kullanıcıların her görev bölmesini ayrı ayrı kontrol edebilirsiniz.  
  
### <a name="windows-forms-support"></a>Windows Forms desteği  
 Visual Studio'da Office geliştirme araçlarını kullanarak oluşturduğunuz özel görev bölmesini kullanıcı arabiriminin Windows Forms denetimlerindeki temel alır. Özel görev bölmesini için kullanıcı arabirimi tasarlamak için tanıdık Windows Form Tasarımcısı'nı kullanabilirsiniz. Görev bölmesindeki denetimlere veri kaynağı bağlamak için Windows Forms veri bağlama desteği de kullanabilirsiniz.  
  
## <a name="creating-a-custom-task-pane"></a>Özel görev bölmesini oluşturma  
 Temel özel görev bölmesini iki adımda oluşturabilirsiniz:  
  
1.  Windows Forms denetimleri ekleyerek, özel görev bölmesini için kullanıcı arabirimi oluşturma bir <xref:System.Windows.Forms.UserControl> nesnesi.  
  
2.  Kullanıcı denetimine geçirerek özel görev bölmesini örneği <xref:Microsoft.Office.Tools.CustomTaskPaneCollection> VSTO eklentinizi nesne. Bu koleksiyonun yeni bir döndürür <xref:Microsoft.Office.Tools.CustomTaskPane> kullanıcı olaylarına yanıt vermek ve görev bölmesinde görünümünü değiştirmek için kullanabileceğiniz nesnesi.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).  
  
### <a name="creating-the-user-interface"></a>Kullanıcı arabirimi oluşturma  
 Visual Studio'da Office geliştirme araçlarını kullanarak oluşturduğunuz tüm özel görev bölmeleri içeren bir <xref:System.Windows.Forms.UserControl> nesnesi. Bu kullanıcı denetimi, özel görev bölmesi, kullanıcı arabirimi sağlar. Tasarım zamanında veya çalışma zamanında kullanıcı denetimi oluşturabilirsiniz. Tasarım zamanında kullanıcı denetimi oluşturursanız, görev bölmesi kullanıcı arabirimini oluşturmak için Windows Form Tasarımcısı'nı kullanabilirsiniz.  
  
### <a name="instantiating-the-custom-task-pane"></a>Özel görev bölmesi oluşturma  
 Özel görev bölmesini kullanıcı arabiriminin içeren bir kullanıcı denetimi oluşturduktan sonra örneği oluşturmak kullandığınız bir <xref:Microsoft.Office.Tools.CustomTaskPane>. Bunu yapmak için kullanıcı denetimini geçirin <xref:Microsoft.Office.Tools.CustomTaskPaneCollection> eklentide, VSTO birini çağırarak <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> yöntemleri. Bu koleksiyon olarak kullanıma sunulan `CustomTaskPanes` alanını `ThisAddIn` sınıfı. Aşağıdaki kod örneğinde çalıştırılmak üzere tasarlanmıştır `ThisAddIn` sınıfı.  
  
 [!code-vb[Trin_TaskPaneBasic#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#2)]
 [!code-csharp[Trin_TaskPaneBasic#2](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#2)]  
  
 <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> Yöntemleri döndürür yeni bir <xref:Microsoft.Office.Tools.CustomTaskPane> nesnesi. Görev bölmesi görünümünü değiştirme ve kullanıcı olaylarına yanıt vermek için bu nesneyi kullanabilirsiniz.  
  
### <a name="controlling-the-task-pane-in-multiple-windows"></a>Birden çok Windows görev bölmesinde denetleme  
 Özel görev bölmeleri, kullanıcıya bir belgenin veya bir öğenin görünümünü sunan bir belge çerçeve penceresi ile ilişkilendirilmiş. Yalnızca ilişkili pencere görünür olduğunda görev bölmesinde görünür olur.  
  
 Özel görev bölmesini penceresinde belirlemek için uygun kullanmak <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> görev bölmesi oluşturduğunuzda yöntemi aşırı yüklemesini:  
  
-   Görev bölmesi etkin pencere ile ilişkilendirmek için kullanın <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> yöntemi.  
  
-   Belirli bir pencere tarafından barındırılan bir belge görev bölmesini ilişkilendirmek için kullanmak <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> yöntemi.  
  
 Bazı Office uygulamaları oluşturmak veya birden fazla penceresi açık olduğunda, görev bölmesini görüntülemek ne zaman açık yönergeler gerektirir. Bu, kodunuzda görev bölmesinde uygun belgelerin veya öğelerin uygulamadaki ile görünmesini sağlamak için özel görev bölmesi örneğini nereye dikkate alınması gereken önemli kolaylaştırır. Daha fazla bilgi için bkz: [özel görev bölmeleri uygulama pencerelerini yönetme](#Managing).  
  
## <a name="accessing-the-application-from-the-task-pane"></a>Uygulama görev bölmesinden erişme  
 Uygulamayı kullanıcı denetiminden otomatikleştirmek istiyorsanız, doğrudan nesne modelini kullanarak erişebilirsiniz `Globals.ThisAddIn.Application` kodunuzda. Statik `Globals` sınıfı erişim sağlar `ThisAddIn` nesnesi. `Application` Bu nesnenin alan uygulamanın nesne modeline giriş noktasıdır.  
  
 Hakkında daha fazla bilgi için `Application` alanını `ThisAddIn` nesne için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md). Bir uygulamayı özel görev bölmesinden otomatikleştirme izlenecek yol için bkz: [izlenecek yol: uygulamayı özel görev bölmesinden otomatikleştirme](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md). Hakkında daha fazla bilgi için `Globals` sınıfı için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
## <a name="managing-the-user-interface-of-the-task-pane"></a>Görev bölmesine kullanıcı arabiriminin yönetme  
 Görev bölmesi oluşturduktan sonra özellikleri ve olayları kullanabilirsiniz <xref:Microsoft.Office.Tools.CustomTaskPane> nesne görev bölmesinde kullanıcı arabiriminin denetlemek ve kullanıcı görev bölmesini değiştirdiğinde yanıt vermek için.  
  
### <a name="making-the-custom-task-pane-visible"></a>Özel görev bölmesini görünür yapma  
 Varsayılan olarak, görev bölmesinde görünür değil. Görev bölmesi görünür hale getirmek için ayarlamalısınız <xref:Microsoft.Office.Tools.CustomTaskPane.Visible%2A> özelliğine **doğru**.  
  
 Kullanıcıların kapatabilirsiniz bir görev bölmesi herhangi bir zamanda tıklayarak **kapatmak** görev bölmesinde köşesindeki düğmesini (X). Ancak, özel görev bölmesini yeniden açmak kullanıcılar için varsayılan yolu yoktur. Bir kullanıcı özel görev bölmesini kapatırsa, görüntülemek için bir yol sağlamadıkça, kullanıcı özel görev bölmesini yeniden görüntüleyemez.  
  
 VSTO eklentinizi içinde bir özel görev bölmesi oluşturursanız, kullanıcılar görüntülemek veya özel görev bölmesi gizlemek için tıklatabileceği bir düğme gibi bir kullanıcı Arabirimi öğesi oluşturmanız gerekir. Özel görev bölmesini Şerit özelleştirme destekleyen bir Microsoft Office uygulamasında oluşturursanız, özel görev bölmesini gizler veya gösterir bir düğme ile Şerit denetim grubu ekleyebilirsiniz. Bunun nasıl yapılacağı izlenecek yol için bkz: [izlenecek yol: özel görev bölmesini Şerit düğmesi ile eşitleme](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md).  
  
 Ekleyebileceğiniz, bir özel görev bölmesini Şerit özelleştirme desteklemeyen bir Microsoft Office uygulamasında oluşturursanız, bir <xref:Microsoft.Office.Core.CommandBarButton> görüntüler veya özel görev bölmesini gizler.  
  
### <a name="modifying-the-appearance-of-the-task-pane"></a>Görev bölmesi görünümünü değiştirme  
 Özelliklerini kullanarak bir özel görev bölmesi konumunu ve boyutunu denetleyebilirsiniz <xref:Microsoft.Office.Tools.CustomTaskPane> nesnesi. Diğer birçok değişikliği özelliklerini kullanarak bir özel görev bölmesi görünümüne hale getirebilirsiniz <xref:System.Windows.Forms.UserControl> özel görev bölmesinde yer alan nesne. Örneğin, bir özel görev bölmesi için bir arka plan görüntüsü kullanarak belirtebilmeniz için <xref:System.Windows.Forms.Control.BackgroundImage%2A> kullanıcı denetimi özelliği.  
  
 Kullanarak bir özel görev bölmesinden yapabilir değişiklikler aşağıdaki tabloda listelenmektedir <xref:Microsoft.Office.Tools.CustomTaskPane> özellikleri.  
  
|Görev|Özellik|  
|----------|--------------|  
|Görev bölmesi boyutunu değiştirmek için|<xref:Microsoft.Office.Tools.CustomTaskPane.Height%2A><br /><br /> <xref:Microsoft.Office.Tools.CustomTaskPane.Width%2A>|  
|Görev bölmesi konumunu değiştirmek için|<xref:Microsoft.Office.Tools.CustomTaskPane.DockPosition%2A>|  
|Görev bölmesini gizler veya görünür yapmak için|<xref:Microsoft.Office.Tools.CustomTaskPane.Visible%2A>|  
|Kullanıcının görev bölmesi konumunu değiştirmesini engellemek için|<xref:Microsoft.Office.Tools.CustomTaskPane.DockPositionRestrict%2A>|  
  
### <a name="programming-custom-task-pane-events"></a>Özel görev bölmesi olaylarını programlama  
 VSTO kullanıcı özel görev bölmesini değiştirdiğinde yanıt eklentinizi isteyebilirsiniz. Örneğin, kullanıcı bölmesinde yönünü dikey yatay olarak değiştirirse, denetimleri yeniden konumlandırmak isteyebilirsiniz.  
  
 Aşağıdaki tabloda özel görev bölmesi kullanıcının yaptığı değişiklikler yanıt verecek şekilde işleyebilir olayları listeler.  
  
|Görev|Olay|  
|----------|-----------|  
|Kullanıcı görev bölmesi konumunu değiştirdiğinde yanıt vermek için.|<xref:Microsoft.Office.Tools.CustomTaskPane.DockPositionChanged>|  
|Yanıt olduğunda kullanıcı görev bölmesini gizler veya görünür hale getirir.|<xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged>|  
  
## <a name="cleaning-up-resources-used-by-the-task-pane"></a>Görev bölmesi tarafından kullanılan kaynakları temizleme  
 Bir özel görev bölmesini oluşturduktan sonra <xref:Microsoft.Office.Tools.CustomTaskPane> nesne VSTO eklentinizi çalıştığı sürece bellekte kalır. Kullanıcı tıkladıktan sonra bile nesne bellekte kalır **Kapat** görev bölmesinde köşesindeki düğmesini (X).  
  
 VSTO eklenti çalışırken görev bölmesi tarafından kullanılan kaynakları temizlemek için kullanmak <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Remove%2A> veya <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.RemoveAt%2A> yöntemleri. Bu yöntemler belirtilen kaldırma <xref:Microsoft.Office.Tools.CustomTaskPane> nesnesinin `CustomTaskPanes` toplama ve arama <xref:Microsoft.Office.Tools.CustomTaskPane.Dispose%2A> nesnesinin yöntemi.  
  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] VSTO Eklenti kaldırıldığında özel görev bölmesi tarafından kullanılan kaynakları otomatik olarak temizlenir. Çağırmayın <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Remove%2A> veya <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.RemoveAt%2A> yöntemleri `ThisAddIn_Shutdown` projenizdeki olay işleyicisi. Bu yöntemler özel durum oluşturacak bir <xref:System.ObjectDisposedException>, çünkü [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] tarafından kullanılan kaynakları temizler <xref:Microsoft.Office.Tools.CustomTaskPane> önce nesne `ThisAddIn_Shutdown` olarak adlandırılır. Hakkında daha fazla bilgi için `ThisAddIn_Shutdown`, bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md)  
  
##  <a name="Managing"></a>Birden çok uygulama penceresi özel görev bölmeleri yönetme  
 Belgeler ve diğer öğeleri görüntülemek için birden çok windows kullanan bir uygulamayı özel görev bölmesini oluşturduğunuzda, kullanıcı olmasını beklerken görev bölmesinde görünür olduğundan emin olmak için ek adımlar gerekir.  
  
 Özel görev bölmeleri tüm uygulamalarda, kullanıcıya bir belgenin veya bir öğenin görünümünü sunan bir belge çerçeve penceresi ile ilişkilendirilmiş. Yalnızca ilişkili pencere görünür olduğunda görev bölmesinde görünür olur. Ancak, tüm uygulamalar aynı şekilde belge çerçeve pencereleri kullanın.  
  
 Aşağıdaki uygulama gruplarını farklı geliştirme gereksinimlere sahiptir:  
  
-   [Outlook](#Outlook)  
  
-   [Word, InfoPath ve PowerPoint](#WordAndInfoPath)  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: Yönetme görev bölmeleri Word VSTO eklentileri?](http://go.microsoft.com/fwlink/?LinkId=136781).  
  
##  <a name="Outlook"></a>Outlook  
 Outlook için özel görev bölmesini oluşturduğunuzda, özel görev bölmesini belirli Explorer veya Inspector penceresi ile ilişkilidir. Gezginler bir klasörün içeriğini görüntülemek windows, ve denetçiler bir e-posta iletisi veya bir görev gibi bir öğe görüntülemek windows.  
  
 Çoklu Explorer veya Inspector windows birlikte özel görev bölmesini görüntülemek istiyorsanız, bir Explorer veya Inspector penceresi açıldığında özel görev bölmesini yeni bir örneğini oluşturmanız gerekir. Bunu yapmak için bir Explorer veya Inspector penceresi oluşturulduğunda bir olayı işlemek ve sonra görev bölmesi olay işleyicisini oluşturun. Görüntü görev bölmeleri hangi pencerenin bağlı olarak görünür veya gizlemek için Explorer veya Inspector olaylarını de işleyebilirsiniz.  
  
 Görev bölmesine bir belirli Explorer veya Inspector ile ilişkilendirmek için kullanın <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> görev bölmesi oluşturmak ve geçirmek için yöntem <xref:Microsoft.Office.Interop.Outlook.Explorer> veya <xref:Microsoft.Office.Interop.Outlook.Inspector> nesnesini *penceresi* parametresi. Özel görev bölmelerini oluşturma hakkında daha fazla bilgi için bkz: [özel görev bölmeleri genel bakış](../vsto/custom-task-panes.md).  
  
 Görev bölmesi açılır her e-posta iletisi oluşturmak nasıl izlenecek yol için bkz: [izlenecek yol: Outlook e-posta iletilerini ile birlikte özel görev bölmelerini görüntüleme](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md).  
  
### <a name="outlook-events"></a>Outlook olayları  
 Windows Explorer durumunu izlemek için aşağıdaki Explorer ilgili olayları işleyebilir:  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorersEvents_Event.NewExplorer>  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Activate>  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Close>  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Deactivate>  
  
 Inspector windows durumunu izlemek için aşağıdaki denetçisi ile ilgili olayları işleyebilir:  
  
-   <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector>  
  
-   <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_10_Event.Activate>  
  
-   <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_10_Event.Close>  
  
-   <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_10_Event.Deactivate>  
  
### <a name="preventing-multiple-instances-of-a-custom-task-pane-in-outlook"></a>Outlook içinde bir özel görev bölmesi birden çok örneğini önleme  
 Outlook windows özel görev bölmesini birden çok örneğini görüntülenmesini engellemek için açıkça özel görev bölmesinden Kaldır `CustomTaskPanes` koleksiyonu `ThisAddIn` sınıf her Pencere kapatıldığında. Çağrı <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Remove%2A> yöntemi bir pencere, gibi kapalı olduğunda bir olayda <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Close> veya <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_10_Event.Close>.  
  
 Özel görev bölmesini açıkça kaldırmazsanız, Outlook windows özel görev bölmesini birden çok örneğini görüntüleyebilir. Outlook bazen pencereleri geri dönüştürür ve bunlara bağlı herhangi bir özel görev bölmeleri başvurular geri dönüştürüldüğünde windows korumak.  
  
##  <a name="WordAndInfoPath"></a>Word, InfoPath ve PowerPoint  
 Word, InfoPath ve PowerPoint her belge farklı belge çerçeve penceresinde görüntüler. Bu uygulamalar için bir özel görev bölmesi oluşturduğunuzda, özel görev bölmesini yalnızca belirli bir belge ile ilişkilidir. Kullanıcı farklı bir belge açarsa, önceki belge yeniden görünür olana kadar özel görev bölmesini gizlenir.  
  
 Birden çok belge birlikte özel görev bölmesini görüntülemek istiyorsanız, kullanıcı yeni bir belge oluşturur veya var olan bir belgeyi açtığında özel görev bölmesini yeni bir örneğini oluşturun. Bunu yapmak için bir belge oluşturulduğunda veya açılan başlatılan olayları işlemek ve sonra görev bölmesinde olay işleyicisi oluşturun. Görüntü görev bölmeleri hangi belge bağlı olarak görünür veya gizlemek için belge olaylarını de işleyebilirsiniz.  
  
 Görev bölmesi belirli belge penceresi ile ilişkilendirmek için kullanın <xref:Microsoft.Office.Tools.CustomTaskPaneCollection.Add%2A> görev bölmesi oluşturmak ve geçirmek için yöntem bir <xref:Microsoft.Office.Interop.Word.Window> (Word için), <xref:Microsoft.Office.Interop.InfoPath.WindowObject> (InfoPath için), veya <xref:Microsoft.Office.Interop.PowerPoint.DocumentWindow> (için PowerPoint) için *penceresi*parametresi.  
  
### <a name="word-events"></a>Word olayları  
 Word'de belge pencereleri durumunu izlemek için aşağıdaki olaylar işleyebilir:  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeClose>  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen>  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.NewDocument>  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.WindowActivate>  
  
-   <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.WindowDeactivate>  
  
### <a name="infopath-events"></a>InfoPath olayları  
 Belge pencereleri InfoPath durumunu izlemek için aşağıdaki olaylar işleyebilir:  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.NewXDocument>  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowActivate>  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.WindowDeactivate>  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentBeforeClose>  
  
-   <xref:Microsoft.Office.Interop.InfoPath._ApplicationEvents_Event.XDocumentOpen>  
  
### <a name="powerpoint-events"></a>PowerPoint olayları  
 Belge pencereleri PowerPoint durumunu izlemek için aşağıdaki olaylar işleyebilir:  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.AfterNewPresentation>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.AfterPresentationOpen>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.NewPresentation>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.PresentationOpen>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.WindowActivate>  
  
-   <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.WindowDeactivate>  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [İzlenecek yol: uygulamayı özel görev bölmesinden otomatikleştirme](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)   
 [İzlenecek yol: özel görev bölmesini Şerit düğmesi ile eşitleme](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md)   
 [İzlenecek yol: Outlook'ta e-posta iletileri ile birlikte özel görev bölmelerini görüntüleme](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)  
