---
title: Eylemler bölmesine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- actions panes [Office development in Visual Studio], about actions panes
- actions panes [Office development in Visual Studio]
- smart documents [Office development in Visual Studio]
- user controls [Office development in Visual Studio], actions panes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 902301021a698dfd0f6e9f09b000c1e4e403e029
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="actions-pane-overview"></a>Eylemler Bölmesine Genel Bakış
  Eylemler bölmesinde bir özelleştirilebilir olduğundan **belge eylemleri** belirli Microsoft Office Word belgesine veya Microsoft Office Excel çalışma kitabına eklenmiş görev bölmesi. Bu diğer yerleşik görev bölmeleri birlikte Office görev bölmesi içinde gibi barındırılan **XML kaynağı** Excel görev bölmesinde veya **stiller ve biçimlendirme** Word görev bölmesinde. Eylemler bölmesi kullanıcı arabirimini tasarlamak için Windows Forms veya WPF denetimleri kullanabilirsiniz.  

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  

 Word veya Excel için belge düzeyi özelleştirmelerinde yalnızca eylemler bölmesi oluşturabilirsiniz. Bir VSTO eklenti Eylemler Bölmesi oluşturulamıyor. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  

> [!NOTE]  
>  Eylemler bölmesinde özel görev bölmesinden farklılık gösterir. Özel görev bölmeleri belirli bir belge uygulama ile ilişkilendirilmiş. VSTO eklentileri bazı Microsoft Office uygulamaları için özel görev bölmeleri oluşturabilirsiniz. Daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  

 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: kullanım WPF denetimleri içinde bir Excel eylemler bölmesindeki?](http://go.microsoft.com/fwlink/?LinkId=132763).  

## <a name="displaying-the-actions-pane"></a>Eylemler bölmesini görüntüleme  
 Eylemler bölmesinde tarafından temsil edilen <xref:Microsoft.Office.Tools.ActionsPane> sınıfı. Belge düzeyi projesi oluşturduğunuzda, bu sınıfın örneğini kullanarak kodunuzu kullanılabilir `ActionsPane` alanını `ThisWorkbook` (Excel için) veya `ThisDocument` projenizdeki sınıfı (Word için). Eylemler bölmesinde görüntülemek için bir Windows Forms denetimi ekleyin <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> özelliği `ActionsPane` alan. Aşağıdaki kod örneğinde adlandırılmış bir denetim ekler `actions` Eylemler bölmesine.  

 [!code-csharp[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#7)]
 [!code-vb[Trin_VstcoreActionsPaneWord#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#7)]  

 Eylemler bölmesinde, açıkça bir denetim ekleyin hemen çalışma zamanında görünür olur. Eylemler bölmesinde görüntülendikten sonra dinamik olarak ekleme veya kullanıcının eylemlerine yanıt olarak denetimlerini kaldırma. Genellikle, Eylemler bölmesinde görüntülemek üzere kod eklemek `Startup` olay işleyicisi `ThisDocument` veya `ThisWorkbook` Eylemler bölmesinde görünür olmasını sağlamak kullanıcı ilk kez açtığında belge. Ancak, yalnızca bir kullanıcının eylemi belgedeki yanıtta eylemler bölmesini görüntülemek isteyebilirsiniz. Örneğin, kod ekleme olasılığınız `Click` belgesindeki bir denetim olayı.  

### <a name="adding-multiple-controls-to-the-actions-pane"></a>Eylemler bölmesine birden çok denetim ekleme  
 Eylemler bölmesine birden çok denetim ekliyorsanız, çoğu durumda, bir kullanıcı denetimi denetimlerinde grup ve kullanıcı denetimi Ekle <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> özelliği. Bu işlem aşağıdaki adımları içerir:  

1.  Eylemler bölmesinde kullanıcı arabirimini (UI) ekleyerek oluşturun bir **Eylemler bölmesi denetimi** veya **kullanıcı denetimi** projenize öğesi. Bu öğelerin her ikisi özel bir Windows Forms içeren <xref:System.Windows.Forms.UserControl> sınıfı. **Eylemler bölmesi denetimi** ve **kullanıcı denetimi** öğeleri eşdeğer; tek fark, adıdır.  

2.  Windows Forms denetimlerine ekleme <xref:System.Windows.Forms.UserControl> Tasarımcısı'nı kullanarak ya da kod yazma.  

    > [!NOTE]  
    >  Bir WPF ekleyerek Eylemler bölmesine WPF denetimleri ekleyebilirsiniz <xref:System.Windows.Controls.UserControl> Windows Forms için <xref:System.Windows.Forms.UserControl>. Daha fazla bilgi için bkz: [Office çözümlerinde WPF denetimleri kullanarak](../vsto/using-wpf-controls-in-office-solutions.md).  

3.  Bulunan denetimleri özel bir kullanıcı denetimi örneği eklemek `ActionsPane` alanını `ThisWorkbook` (Excel için) veya `ThisDocument` projenizdeki sınıfı (Word için).  

 Bu işlem daha ayrıntılı gösteren örnekler için bkz: [nasıl yapılır: Word belgelerini ve Excel çalışma kitaplarına Eylemler bölmesi ekleme](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md).  

## <a name="hiding-the-actions-pane"></a>Eylemler bölmesini gizleme  
 Ancak <xref:Microsoft.Office.Tools.ActionsPane> sınıfına sahip bir <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> yöntemi ve <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> özelliği kaldıramazsınız Eylemler bölmesinde kullanıcı arabiriminden tüm üyeleri kullanarak <xref:Microsoft.Office.Tools.ActionsPane> sınıfının kendisini. Çağırma <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> yöntemi veya ayar <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> özelliğine **false** yalnızca; eylemler bölmesindeki denetimlere gizler görev bölmesini gizlemez.  

 Çözümünüzü görev bölmesinde gizlemek için birkaç seçeneğiniz vardır:  

-   Word'ü için ayarlama <xref:Microsoft.Office.Interop.Word.TaskPane.Visible%2A> özelliği <xref:Microsoft.Office.Interop.Word.TaskPane> belge eylemleri görev bölmesini temsil eden nesne **false**. Aşağıdaki kod örneğinde çalıştırılmak üzere tasarlanmıştır `ThisDocument` projenizdeki sınıfı.  

     [!code-csharp[Trin_VstcoreActionsPaneWord#34](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#34)]
     [!code-vb[Trin_VstcoreActionsPaneWord#34](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#34)]  

-   Excel için ayarlanan <xref:Microsoft.Office.Interop.Excel._Application.DisplayDocumentActionTaskPane%2A> özelliği <xref:Microsoft.Office.Tools.Excel.Workbook.Application%2A> nesnesini **false**. Aşağıdaki kod örneğinde çalıştırılmak üzere tasarlanmıştır `ThisWorkbook` projenizdeki sınıfı.  

     [!code-csharp[Trin_VstcoreActionsPaneExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#11)]  

-   Word veya Excel için alternatif olarak ayarlayabilirsiniz <xref:Microsoft.Office.Core.CommandBar.Visible%2A> görev bölmesini temsil eden komut çubuğunda özelliğinin **false**. Aşağıdaki kod örneğinde çalıştırılmak üzere tasarlanmıştır `ThisDocument` veya `ThisWorkbook` projenizdeki sınıfı.  

     [!code-csharp[Trin_VstcoreActionsPaneExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#9)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#9)]  

### <a name="clearing-the-actions-pane-when-the-document-is-opened"></a>Eylemler bölmesinde belge temizleme açılmış  
 Eylemler bölmesinde görünür modundayken kullanıcının belgeyi kaydederse, Eylemler bölmesinde herhangi bir denetim içeren olup olmadığına bakılmaksızın her belge açıldığında eylemler bölmesinde görünür olur. Görüntülendiğinde denetlemek istiyorsanız, çağrı <xref:Microsoft.Office.Tools.ActionsPane.Clear%2A> yöntemi `ActionsPane` alanındaki `Startup` olay işleyicisi `ThisDocument` veya `ThisWorkbook` belge açıldığında eylemler bölmesinde görünür olmamasını sağlamak için.  

### <a name="determining-when-the-actions-pane-is-closed"></a>Eylemler bölmesinde belirleme kapalı  
 Eylemler bölmesinde kapatıldığında hiçbir olayı yok. Ancak <xref:Microsoft.Office.Tools.ActionsPane> sınıfına sahip bir <xref:Microsoft.Office.Tools.ActionsPane.VisibleChanged> olayı, bu olay son kullanıcı eylemler bölmesini kapattığında oluşmaz. Eylemler bölmesindeki denetimlere çağırarak gizlidir bunun yerine, bu olay tetiklenir <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> yöntemi veya ayarlayarak <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> özelliğine **false**.  

 Son kullanıcı eylemler bölmesini kapatırsa, kullanıcı onu yeniden uygulamanın kullanıcı arabiriminde (UI) aşağıdaki yordamlardan birini gerçekleştirerek görüntüleyebilirsiniz.  

##### <a name="to-display-the-actions-pane-by-using-the-ui-of-word-or-excel"></a>Excel ve Word UI'ını kullanarak Eylemler bölmesinde görüntülemek için  

1.  Şerit'te tıklatın **Görünüm** sekmesi.  

2.  İçinde **Göster/Gizle** grubunda **belge eylemleri** iki durumlu düğme.  

## <a name="programming-actions-pane-events"></a>Eylemler bölmesi olaylarını programlama  
 Eylemler bölmesine birden çok kullanıcı denetimi ekle ve gösterme ve kullanıcı denetimleri gizleme belge olaylarına yanıt için kod yazın. Belgenize XML Şeması öğelerini eşlerseniz ekleme noktasını bir XML öğeleri içinde olduğunda, belirli kullanıcı denetimleri Eylemler bölmesinde gösterebilirsiniz. Daha fazla bilgi için bkz [nasıl yapılır: eşleme şemaları Word belgeleri içinde Visual Studio](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md) ve [nasıl yapılır: eşleme şemaları Visual Studio içindeki çalışma sayfaları](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md).  

 Ayrıca konak kontrolü, uygulama veya belge olayları dahil olmak üzere herhangi bir nesnenin olaylarına yanıt vermek amacıyla kod yazabilirsiniz. Daha fazla bilgi için bkz: [izlenecek yol: programlama karşı olayları NamedRange denetimi](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md).  

## <a name="binding-data-to-controls-on-the-actions-pane"></a>Eylemler bölmesindeki denetimlere veri bağlama  
 Eylemler bölmesindeki denetimlere Windows formlarında denetimleri aynı veri bağlama özelliklerine sahip. Veri kümeleri, türü belirtilmiş veri kümeleri ve XML gibi veri kaynaklarına denetimlerini bağlayabilirsiniz. Daha fazla bilgi için bkz: [verileri bağlama ve Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  

 Eylemler bölmesindeki denetimlere ve belge üzerinde denetimleri aynı veri kümesine bağlayabilirsiniz. Örneğin, bir ana öğe/ayrıntı ilişkisi eylemler bölmesindeki denetimlere ve çalışma sayfasındaki denetimleri arasındaki oluşturabilirsiniz. Daha fazla bilgi için bkz: [izlenecek yol: Excel eylemler bölmesindeki denetimlere veri bağlama](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md).  

## <a name="validating-data-in-actions-pane-controls"></a>Eylemler bölmesi denetimlerinde verileri doğrulama  
 Bir ileti kutusu görüntülerseniz <xref:System.Windows.Forms.Control.Validating> olay işleyicisi Eylemler bölmesinde, Olay denetimi zaman Odak denetimden ileti kutusu ikinci kez yükseltilmiş. Bu sorunu önlemek için kullanmak bir <xref:System.Windows.Forms.ErrorProvider> denetim herhangi bir doğrulama hata iletisi görüntüler.  

## <a name="user-control-stacking-order"></a>Kullanıcı denetimi sıralaması  
 Birden çok kullanıcı denetimleri kullanıyorsanız, bunu dikey veya yatay olarak mı yerleştirildiğini düzgün Eylemler bölmesinde kullanıcı denetimlerini yığmak için kod yazabilirsiniz. Kullanıcı denetimleri eylemler bölmesindeki yığınlama sırasını kullanarak ayarlayabilirsiniz <xref:Microsoft.Office.Tools.StackStyle> numaralandırması <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> özelliği. Daha fazla bilgi için bkz: [nasıl yapılır: Eylemler bölmesindeki denetim düzenini yönetme](../vsto/how-to-manage-control-layout-on-actions-panes.md)  

 <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> Özelliği aşağıdaki alabilir <xref:Microsoft.Office.Tools.StackStyle> numaralandırma değerleri.  

|Yığın stili|Tanım|  
|--------------------|----------------|  
|FromBottom|Eylemler bölmesi altından yığın.|  
|FromLeft|Eylemler bölmesinde soldan yığın.|  
|FromRight|Eylemler bölmesinde sağdan yığın.|  
|FromTop|Eylemler bölmesinde üstten yığın.|  
|Yok.|Yığma sırası tanımlanmaz; Sipariş geliştirici tarafından denetlenir.|  

 Aşağıdaki kod kümeleri <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> kullanıcı denetimlerini eylemler bölmesinin en üstünden yığmak için özellik.  

 [!code-csharp[Trin_VstcoreActionsPaneExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneExcelCS/ThisWorkbook.cs#10)]
 [!code-vb[Trin_VstcoreActionsPaneExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneExcelVB/ThisWorkbook.vb#10)]  

## <a name="anchoring-controls"></a>Denetimleri sabitleme  
 Kullanıcı çalışma zamanında eylemler bölmesinde boyutlandırırsa, denetimleri ile Eylemler bölmesinde yeniden boyutlandırabilirsiniz. Kullanabileceğiniz <xref:System.Windows.Forms.Control.Anchor%2A> eylemler bölmesindeki denetimlere bağlantı için bir Windows Forms denetimi özelliği. Ayrıca, kullanıcı denetimi üzerine Windows Forms denetimleri aynı şekilde sabitleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Windows formlarında denetimleri](/dotnet/framework/winforms/controls/how-to-anchor-controls-on-windows-forms).  

## <a name="resizing-the-actions-pane"></a>Eylemler bölmesinde yeniden boyutlandırma  
 Boyutunu doğrudan değiştiremezsiniz bir <xref:Microsoft.Office.Tools.ActionsPane> çünkü <xref:Microsoft.Office.Tools.ActionsPane> görev bölmesinde katıştırılır. Ancak, program aracılığıyla görev bölmesinde genişliğini ayarlayarak değiştirebilirsiniz <xref:Microsoft.Office.Core.CommandBar.Width%2A> özelliği <xref:Microsoft.Office.Core.CommandBar> görev bölmesini temsil eden. Yatay olarak yerleşik veya kayan olan görev bölmesinde yüksekliğini değiştirebilirsiniz.  

 Kullanıcı kendi ihtiyaçlarına göre uygun görev bölmesinin boyutunu gerekir çünkü programlı olarak görev bölmesini yeniden boyutlandırma genellikle önerilmez. Görev bölmesi genişliğini yeniden boyutlandırmak, bu görevi gerçekleştirmek için aşağıdaki kodu kullanabilirsiniz.  

 [!code-csharp[Trin_VstcoreActionsPaneWord#102](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#102)]
 [!code-vb[Trin_VstcoreActionsPaneWord#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#102)]  

## <a name="repositioning-the-actions-pane"></a>Eylemler bölmesinde yeniden konumlandırma  
 Doğrudan konumunu değiştiremezler <xref:Microsoft.Office.Tools.ActionsPane> görev bölmesinde gömülü olduğundan. Ancak, program aracılığıyla görev bölmesinde ayarlayarak taşıyabilirsiniz <xref:Microsoft.Office.Core.CommandBar.Position%2A> özelliği <xref:Microsoft.Office.Core.CommandBar> görev bölmesini temsil eden.  

 Kullanıcı kendi ihtiyaçlarına göre uygun ekrandaki görev bölmesi konumunu seçin gerekir çünkü programlı olarak görev bölmesini yeniden konumlandırma genellikle önerilmez. Görev bölmesi belirli bir konuma taşımanız gerekirse, bu görevi gerçekleştirmek için aşağıdaki kodu kullanabilirsiniz.  

 [!code-csharp[Trin_VstcoreActionsPaneWord#100](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#100)]
 [!code-vb[Trin_VstcoreActionsPaneWord#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#100)]  

> [!NOTE]  
>  Son kullanıcıların herhangi bir zamanda görev bölmesinde konumunu elle değiştirebilirsiniz. Görev bölmesi programlı olarak belirttiğiniz konumda yerleşik kalacağından emin olmak için bir yolu yoktur. Ancak, yönlendirme değişikliklerini denetle ve Eylemler bölmesindeki denetimlere doğru yöne yığılma emin olun. Daha fazla bilgi için bkz: [nasıl yapılır: Eylemler bölmesindeki denetim düzenini yönetme](../vsto/how-to-manage-control-layout-on-actions-panes.md).  

 Ayarı <xref:Microsoft.Office.Tools.ActionsPane.Top%2A> ve <xref:Microsoft.Office.Tools.ActionsPane.Left%2A> özelliklerini <xref:Microsoft.Office.Tools.ActionsPane> konumunu değiştirmez çünkü <xref:Microsoft.Office.Tools.ActionsPane> görev bölmesinde katıştırılmış nesne.  

 Görev bölmesi sabitlenmemişse ayarlayabileceğiniz <xref:Microsoft.Office.Core.CommandBar.Top%2A> ve <xref:Microsoft.Office.Core.CommandBar.Left%2A> özelliklerini <xref:Microsoft.Office.Core.CommandBar> görev bölmesini temsil eden. Aşağıdaki kod bir kilitli görev bölmesi belgenin sol üst köşesindeki taşır.  

 [!code-csharp[Trin_VstcoreActionsPaneWord#101](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#101)]
 [!code-vb[Trin_VstcoreActionsPaneWord#101](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#101)]  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde WPF denetimlerini kullanma](../vsto/using-wpf-controls-in-office-solutions.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Nasıl yapılır: Word belgelerini ve Excel çalışma kitaplarına Eylemler bölmesi ekleme](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [İzlenecek yol: Eylemler bölmesinden belgeye metin ekleme](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [İzlenecek yol: Word eylemler bölmesindeki denetimlere veri bağlama](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)   
 [İzlenecek yol: Excel eylemler bölmesindeki denetimlere veri bağlama](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md)   
 [Nasıl yapılır: Eylemler bölmesindeki denetim düzenini yönetme](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [İzlenecek Yol: Eylemler Bölmesinden Belgeye Metin Ekleme](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
