---
title: Yer işareti denetimi | Microsoft Docs
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Bookmark
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: 68934d202fbffc162b6888ab3a45cdf0b7fd439d
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="bookmark-control"></a>Yer İşareti Denetimi
  <xref:Microsoft.Office.Tools.Word.Bookmark> Denetimidir benzersiz bir ada sahip olayları gösterir ve verilere bağlanabilen bir yer işareti. Yer işareti yer tutucu olarak bir öğe veya Microsoft Office Word belgesi konumda işaretlemek için kullanılabilir. <xref:Microsoft.Office.Tools.Word.Bookmark> Denetim birleşimidir bir <xref:Microsoft.Office.Interop.Word.Bookmark> nesne ve <xref:Microsoft.Office.Interop.Word.Range> nesne.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Belge düzeyi projelerine eklediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> belgenize tasarım zamanında veya çalışma zamanında denetimler. VSTO eklenti projelerinde eklediğiniz <xref:Microsoft.Office.Tools.Word.Bookmark> herhangi bir açık belgeye çalışma zamanında denetimler. Daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerine yer işareti Denetimler Ekle](../vsto/how-to-add-bookmark-controls-to-word-documents.md).

## <a name="binding-data-to-the-control"></a>Denetimine veri bağlama
 A <xref:Microsoft.Office.Tools.Word.Bookmark> basit veri bağlama denetimi destekler. Yer işareti kullanarak bir veri kaynağına bağlanması gereken <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> özelliği. Varsayılan veri bağlama özelliği yer işaretinin <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> özelliği.

 İlişkili veri kümesindeki veriler güncelleştirdiyseniz <xref:Microsoft.Office.Tools.Word.Bookmark> denetimini değişiklikleri gösterir.

 Belge düzeyi projelerine ayrıca veri işaretlerine kullanarak bağlayabilirsiniz **veri kaynakları** penceresi. Daha fazla bilgi için bkz: [nasıl yapılır: belgeleri nesne verileriyle doldurmak](../vsto/how-to-populate-documents-with-data-from-objects.md).

## <a name="formatting"></a>Biçimlendirme
 Uygulanabilir biçimlendirme bir <xref:Microsoft.Office.Interop.Word.Bookmark> uygulanabilir bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetim. Bu biçimlendirme yazı tiplerini, girintileri, aralığı, numaralandırma ve stiller içerir.

## <a name="assigning-text-to-the-bookmark"></a>Metin yer işaretine atama
 Bir ek birbirinden bir <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> nesne ve bir <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> denetimidir nasıl metin yer işaretine atandığında davranır. Sıfır uzunluklu metin atarsanız <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType>, metnin sağ tarafında yer işareti eklenir ve yer işareti sıfır uzunlukta kalır. Ancak, sıfır uzunlukta metin atarsanız <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType>, metin yer işaretine eklenir ve yer işaretinin uzunluğu eklenen karakterlerin toplam sayısı için genişletir.

 <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> Denetimi de sahip <xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType> özelliği. Bu özellik farklıdır <xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType> edinilebilir özelliği <xref:Microsoft.Office.Tools.Word.Bookmark.Range?displayProperty=nameWithType> özelliği bir <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> denetimi veya <xref:Microsoft.Office.Interop.Word.Bookmark.Range?displayProperty=nameWithType> özelliği bir <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> nesnesi.

|Metin özelliği|Açıklama|
|-------------------|-----------------|
|<xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType>|Yer işareti içindeki metni görüntülemek ve yer işareti belgede bırakmak için bu özelliği kullanın. Metin yer işaretine atamak yer işareti aralığını genişletir ve yer işareti silmez.<br /><br /> Örneğin, `Bookmark1.Text = "Hello world"` metni yer işaretine ekler ve yer işareti dokunmaz.|
|<xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType>|Yer işareti konumundaki metni görüntülemek ve otomatik olarak yer işareti silmek için bu özelliği kullanın. Örneğin, `Bookmark1.Range.Text = "Hello world"` metni yer işaretine ekler ve yer işareti siler.|

## <a name="renaming-the-control-at-design-time"></a>Tasarım zamanında denetimi yeniden adlandırma
 Belge düzeyi projelerine sürüklediğinizde, bir <xref:Microsoft.Office.Tools.Word.Bookmark> gelen denetim **araç** belgenize, Visual Studio otomatik olarak denetim için bir ad oluşturur. Denetimin adını değiştirebilirsiniz **özellikleri** penceresi.

## <a name="overlapping-controls"></a>Çakışma denetimleri
 Yer işareti denetimi birbiriyle çakışıyor. Aynı metnin birden fazla yer işareti tarafından paylaşılabilir. Yeni metin örtüşen yer işaretlerinden birine atadığınızda, yalnızca yeni metin içeren ve yer işaretleri artık çakışıyor. Diğer yer işareti şimdi örtüşen özgün yer işaretleri arasında paylaşılan değildi metni içerir.

 Aşağıdaki tabloda nasıl cümle "Bu örnek metindir." iki örtüşen yer işareti tarafından paylaşılan:

|Yer işareti|Metin|
|--------------|----------|
|Çakışan yer işaretleri|[{örnek olan] metni.}|
|Bookmark1|Bu örnek verilmiştir|
|Bookmark2|örnek metin.|

 Yeni metnin atarsanız "Yerini alır." Bookmark1 için yer işaretleri çakışmadığından ve başlangıçta Bookmark1 parçası olmadığı metin Bookmark2 korur.

|Yer işareti|Metin|
|--------------|----------|
|İki ayrı yer işaretleri|[yerini almaktadır] {metin.}|
|Bookmark1|Bu yerini alır|
|Bookmark2|metin.|

Başka bir yer işareti içeren bir yer işareti metnini değiştirirseniz, iç yer işareti silinmez. Ancak, iç yer işareti boş bir yer işaretine haline gelir ve dış yer işareti sonuna taşır.

Aşağıdaki tabloda nasıl cümle "Bu örnek metindir." başka bir yer işareti içinde yer alan bir yer işareti tarafından paylaşılır:

|Yer işareti|Metin|
|--------------|----------|
|Çakışan yer işaretleri|[{örnek} metin budur.]|
|Bookmark1|Bu örnek metindir.|
|Bookmark2|örnek|

 Yeni metnin atarsanız "Yerini alır." Bookmark1, yer işaretleri artık örtüşmez ve Bookmark2 Bookmark1 sonunda bulunduğu boş bir yer işaretine haline gelir.

|Yer işareti|Metin|
|--------------|----------|
|İki ayrı yer işaretleri|[yerini alır.]{}|
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

## <a name="see-also"></a>Ayrıca bkz.

- [Genişletilmiş Nesneleri Kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)
- [Nasıl Yapılır: Word Belgelerine Yer İşareti Denetimi Ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)
- [İzlenecek Yol: Yer İşaretleri İçin Kısayol Menüleri Oluşturma](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)
- [Office Çözümlerinde Verileri Denetimlere Bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Konak Denetimlerinin ve Konak Öğelerinin Programlama Sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)