---
title: "Nasıl yapılır: Eylemler bölmesindeki denetim düzenini yönetme | Microsoft Docs"
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
- actions panes [Office development in Visual Studio], control layout
- controls [Office development in Visual Studio], layout on actions panes
- smart documents [Office development in Visual Studio], control layout
ms.assetid: 857550d0-b9c0-4d2f-a947-dd955bcf2823
caps.latest.revision: "59"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 06a2488606b93040cf897ac510455b8a9ef74ce2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-control-layout-on-actions-panes"></a>Nasıl Yapılır: Eylemler Bölmesindeki Denetim Düzenini Yönetme
  Eylemler bölmesi varsayılan olarak bir belge veya çalışma sağına yerleştirilir; Ancak, sol, üstüne veya altına yerleştirilmiş. Birden çok kullanıcı denetimleri kullanıyorsanız, doğru kullanıcı denetimlerini eylemler bölmesindeki yığmak için kod yazabilirsiniz. Daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Eylemler bölmesinde dikey veya yatay olarak yerleştirildiğini üzerinde denetimlerini yığın sırasını bağlıdır.  
  
> [!NOTE]  
>  Kullanıcının Eylemler bölmesi çalışma zamanında yeniden boyutlandırırsa ile eylemler bölmesini yeniden boyutlandırmak için denetimleri ayarlayabilirsiniz. Kullanabileceğiniz <xref:System.Windows.Forms.Control.Anchor%2A> eylemler bölmesindeki denetimlere bağlantı için bir Windows Forms denetimi özelliği. Daha fazla bilgi için bkz: [nasıl yapılır: Windows formlarında denetimleri](/dotnet/framework/winforms/controls/how-to-anchor-controls-on-windows-forms).  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-set-the-stack-order-of-the-actions-pane-controls"></a>Eylemler bölmesi denetimlerinin yığın sırasını ayarlamak için  
  
1.  Birden çok kullanıcı veya iç içe geçmiş eylemler bölmesi denetimleri ile Eylemler bölmesi içeren bir Microsoft Office Word için belge düzeyi projesini açın. Daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerini ve Excel çalışma kitaplarına Eylemler bölmesi ekleme](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md).  
  
2.  Sağ **ThisDocument.vb** veya **ThisDocument.vb** içinde **Çözüm Gezgini** ve ardından **görünümü kodu**.  
  
3.  İçinde <xref:Microsoft.Office.Tools.ActionsPane.OrientationChanged> olay işleyicisi Eylemler bölmesinin Eylemler bölmesinde yönünü yatay olup olmadığını denetleyin.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#30](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#30)]
     [!code-vb[Trin_VstcoreActionsPaneWord#30](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#30)]  
  
4.  Yönlendirmeyi yatay ise, Eylemler bölmesi denetimlerini soldan yığın; Aksi takdirde, bunları üstten yığın.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#31](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#31)]
     [!code-vb[Trin_VstcoreActionsPaneWord#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#31)]  
  
5.  C# ' ta için bir olay işleyicisi eklemelisiniz `ActionsPane` için <xref:Microsoft.Office.Tools.Word.Document.Startup> olay işleyicisi. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#32](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#32)]  
  
6.  Projeyi çalıştırın ve Eylemler bölmesinde denetimler soldan sağa Eylemler bölmesi belgenin üst kısmında yerleştirilir ve Eylemler bölmesinde belge sağ tarafında yerleştirildiğinde denetimleri üstten alta Yığılmış yığılma doğrulayın.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_VstcoreActionsPaneWord#29](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#29)]
 [!code-vb[Trin_VstcoreActionsPaneWord#29](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#29)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Birden çok kullanıcı denetimleri içeren eylemler bölmesi veya iç içe geçmiş eylemler bölmesi ile Word belge düzeyi projesi denetler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Nasıl yapılır: Word belgelerini ve Excel çalışma kitaplarına Eylemler bölmesi ekleme](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Nasıl yapılır: Word belgelerini ve Excel çalışma kitaplarına Eylemler bölmesi ekleme](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [İzlenecek yol: Eylemler bölmesinden belgeye metin ekleme](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [İzlenecek Yol: Eylemler Bölmesinden Belgeye Metin Ekleme](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
  
  