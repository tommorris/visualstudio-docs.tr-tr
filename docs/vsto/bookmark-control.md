---
title: "Yer işareti denetimi | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.Toolbox.Bookmark
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- bookmarks, controlling
- Bookmark control, data binding
- Bookmark control, events
- Bookmark control
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 38e3286d24f0591ca4ced3339118b6d0d4bfe1d7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="bookmark-control"></a>Yer İşareti Denetimi
  <xref:Microsoft.Office.Tools.Word.Bookmark> Denetimidir benzersiz bir ada sahip olayları gösterir ve verilere bağlanabilen bir yer işareti. Yer işareti yer tutucu olarak bir öğe veya Microsoft Office Word belgesi konumda işaretlemek için kullanılabilir. <xref:Microsoft.Office.Tools.Word.Bookmark> Denetim birleşimidir bir <xref:Microsoft.Office.Interop.Word.Bookmark> nesne ve <xref:Microsoft.Office.Interop.Word.Range> nesne.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Belge düzeyi projelerine eklediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> belgenize tasarım zamanında veya çalışma zamanında denetimler. VSTO eklenti projelerinde eklediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> herhangi bir açık belgeye çalışma zamanında denetimler. Daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerine yer işareti Denetimler Ekle](../vsto/how-to-add-bookmark-controls-to-word-documents.md).  
  
## <a name="binding-data-to-the-control"></a>Denetimine veri bağlama  
 A <xref:Microsoft.Office.Tools.Word.Bookmark> basit veri bağlama denetimi destekler. Yer işareti kullanarak bir veri kaynağına bağlanması gereken <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> özelliği. Varsayılan veri bağlama özelliği yer işaretinin <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> özelliği.  
  
 İlişkili veri kümesindeki veriler güncelleştirdiyseniz <xref:Microsoft.Office.Tools.Word.Bookmark> denetimi değişiklikleri yansıtır.  
  
 Belge düzeyi projelerine ayrıca veri işaretlerine kullanarak bağlayabilirsiniz **veri kaynakları** penceresi. Daha fazla bilgi için bkz: [nasıl yapılır: belgeleri nesne verileriyle doldurmak](../vsto/how-to-populate-documents-with-data-from-objects.md).  
  
## <a name="formatting"></a>Biçimlendirme  
 Uygulanabilir biçimlendirme bir <xref:Microsoft.Office.Interop.Word.Bookmark> uygulanabilir bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetim. Bu yazı tiplerini, girintileri, aralığı, numaralandırma ve stiller içerir.  
  
## <a name="assigning-text-to-the-bookmark"></a>Metin yer işaretine atama  
 Bir ek birbirinden bir <xref:Microsoft.Office.Interop.Word.Bookmark> nesne ve bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetimidir nasıl metin yer işaretine atandığında davranır. Sıfır uzunluklu metin atarsanız <xref:Microsoft.Office.Interop.Word.Bookmark>, metnin sağ tarafında yer işareti eklenir ve yer işareti sıfır uzunlukta kalır. Ancak, sıfır uzunlukta metin atarsanız <xref:Microsoft.Office.Tools.Word.Bookmark>, metin yer işaretine eklenir ve yer işaretinin uzunluğu eklenen karakterlerin toplam sayısı için genişletir.  
  
 <xref:Microsoft.Office.Tools.Word.Bookmark> Denetimi de sahip <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> özelliği. Bu farklıdır <xref:Microsoft.Office.Interop.Word.Range.Text%2A> edinilebilir özelliği <xref:Microsoft.Office.Tools.Word.Bookmark.Range%2A> özelliği bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetim veya <xref:Microsoft.Office.Interop.Word.Bookmark.Range%2A> özelliği bir <xref:Microsoft.Office.Interop.Word.Bookmark> nesnesi.  
  
|Metin özelliği|Açıklama|  
|-------------------|-----------------|  
|<xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A>|Yer işareti içindeki metni görüntülemek ve yer işareti belgede bırakmak için bu özelliği kullanın. Metin yer işaretine atamak yer işareti aralığını genişletir ve yer işareti silmez.<br /><br /> Örneğin, `Bookmark1.Text = "Hello world"` metni yer işaretine ekler ve yer işareti dokunmaz.|  
|<xref:Microsoft.Office.Interop.Word.Range.Text%2A>|Yer işareti konumundaki metni görüntülemek ve otomatik olarak yer işareti silmek için bu özelliği kullanın. Örneğin, `Bookmark1.Range.Text = "Hello world"` metni yer işaretine ekler ve yer işareti siler.|  
  
## <a name="renaming-the-control-at-design-time"></a>Tasarım zamanında denetimi yeniden adlandırma  
 Belge düzeyi projelerine sürüklediğinizde, bir <xref:Microsoft.Office.Tools.Word.Bookmark> gelen denetim **araç** belgenize, Visual Studio otomatik olarak denetim için bir ad oluşturur. Denetimin adını değiştirebilirsiniz **özellikleri** penceresi.  
  
## <a name="overlapping-controls"></a>Çakışma denetimleri  
 Yer işareti denetimi birbiriyle çakışıyor; diğer bir deyişle, aynı metnin birden fazla yer işareti tarafından paylaşılabilir. Yeni metin örtüşen yer işaretlerinden birine atadığınızda, yalnızca yeni metin içerecek ve yer işaretleri artık çakışır. Diğer yer işareti artık yalnızca örtüşen özgün yer işaretleri arasında paylaşılmayan metni içerir.  
  
 Aşağıdaki tabloda nasıl cümle "Bu örnek metindir." iki örtüşen yer işareti tarafından paylaşılır.  
  
|Yer işareti|Metin|  
|--------------|----------|  
|Çakışan yer işaretleri|[{örnek olan] metni.}|  
|Bookmark1|Bu örnek verilmiştir|  
|Bookmark2|örnek metin.|  
  
 Yeni metnin atarsanız "Yerini alır." Bookmark1, yer işaretleri artık örtüşmez ve Bookmark2 yalnızca başlangıçta Bookmark1 parçası değil metin korur.  
  
|Yer işareti|Metin|  
|--------------|----------|  
|İki ayrı yer işaretleri|[yerini almaktadır] {metin.}|  
|Bookmark1|Bu yerini alır|  
|Bookmark2|metin.|  
  
 Bir yer işareti tam olarak başka bir yer işareti içinde bulunur ve dış yer işareti metnini değiştirmek, iç yer işareti silinmez. Ancak, iç yer işaretine dış yer işareti sonuna taşınır boş bir yer işaretine dönüşür. Aşağıdaki tabloda nasıl cümle "Bu örnek metindir." başka bir yer işareti içinde yer alan bir yer işareti tarafından paylaşılır.  
  
|Yer işareti|Metin|  
|--------------|----------|  
|Çakışan yer işaretleri|[{örnek} metin budur.]|  
|Bookmark1|Bu örnek metindir.|  
|Bookmark2|örnek|  
  
 Yeni metnin atarsanız "Yerini alır." Bookmark1, yer işaretleri artık örtüşmez ve Bookmark2 Bookmark1 sonunda bulunduğu boş bir yer işaretine haline gelir.  
  
|Yer işareti|Metin|  
|--------------|----------|  
|İki ayrı yer işaretleri|[yerini alır.] {}|  
|Bookmark1|Bu yerini alır.|  
|Bookmark2|*\<Boş >*|  
  
## <a name="events"></a>Olaylar  
 Aşağıdaki olaylar kullanılabilir <xref:Microsoft.Office.Tools.Word.Bookmark> denetimi:  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.Deselected>  
  
-   <xref:System.ComponentModel.IComponent.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.Selected>  
  
-   <xref:Microsoft.Office.Tools.Word.Bookmark.SelectionChange>  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [İzlenecek yol: Yer işaretleri için kısayol menüleri oluşturma](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  