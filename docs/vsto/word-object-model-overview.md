---
title: "Word nesne modeline genel bakış | Microsoft Docs"
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
- Word object model
- Word [Office development in Visual Studio], object model
- object models [Office development in Visual Studio], Office
- object models [Office development in Visual Studio], Word
- objects [Office development in Visual Studio], Office object models
- Office object models
ms.assetid: b66a7d9e-0a51-4ef5-8754-b2b899f9094c
caps.latest.revision: "78"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3b01307811930ec865e2b38e899318dfdd99c74a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="word-object-model-overview"></a>Word Nesne Modeline Genel Bakış
  Visual Studio'da Word çözümleri geliştirdiğinizde, Word nesne modeli ile etkileşim. Bu nesne modeli sınıfları ve Word için birincil birlikte çalışma derlemesindeki sağlanan ve içinde tanımlanan arabirimleri oluşur <xref:Microsoft.Office.Interop.Word> ad alanı.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Bu konu, Word nesne modeli kısa bir genel bakış sağlar. Burada, öğrenin tüm Word nesne modeli hakkında daha fazla kaynaklar için bkz [Word nesne modeli belgelerini kullanarak](#WordOMDocumentation).  
  
 Word nesne modeli belirli görevler gerçekleştirmek üzere kullanma hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Belgelerle Çalışma](../vsto/working-with-documents.md)  
  
-   [Belgelerde Metinle Çalışma](../vsto/working-with-text-in-documents.md)  
  
-   [Sekmelerle Çalışma](../vsto/working-with-tables.md)  
  
##  <a name="understanding"></a>Word nesne modelini anlama  
 Word ile etkileşim kurabilen nesneleri yüzlerce sağlar. Bu nesneler kullanıcı arabirimini yakından takip eden hiyerarşik olarak düzenlenir. Hiyerarşisinin en üstünde olduğu <xref:Microsoft.Office.Interop.Word.Application> nesnesi. Bu nesne Word'ün geçerli örneğini temsil eder. <xref:Microsoft.Office.Interop.Word.Application> Nesnesini içeren <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Interop.Word.Selection>, <xref:Microsoft.Office.Interop.Word.Bookmark>, ve <xref:Microsoft.Office.Interop.Word.Range> nesneleri. Bu nesnelerin her biri birçok yöntem ve ve nesnesi ile etkileşime için erişebileceği özellikler vardır.  
  
 Aşağıdaki çizimde, bu nesnelerin bir görünüm Word nesne modeli hiyerarşi içinde gösterir.  
  
 ![Word nesne modeli grafiği](../vsto/media/wrwordobjectmodel.gif "Word nesne modeli grafiği")  
  
 İlk bakışta, çakışmasına nesneler görüntülenir. Örneğin, <xref:Microsoft.Office.Interop.Word.Document> ve <xref:Microsoft.Office.Interop.Word.Selection> nesneleridir hem üyeleri <xref:Microsoft.Office.Interop.Word.Application> nesnesi, ancak <xref:Microsoft.Office.Interop.Word.Document> nesne aynı zamanda bir üyesidir <xref:Microsoft.Office.Interop.Word.Selection> nesnesi. Hem <xref:Microsoft.Office.Interop.Word.Document> ve <xref:Microsoft.Office.Interop.Word.Selection> nesneleri içeren <xref:Microsoft.Office.Interop.Word.Bookmark> ve <xref:Microsoft.Office.Interop.Word.Range> nesneleri. Aynı nesne türünü erişebilmeniz için birden çok yol olduğundan çakışma var. Örneğin, biçimlendirme uyguladığınız bir <xref:Microsoft.Office.Interop.Word.Range> nesne; ancak geçerli seçim, belirli bir paragraf, bölüm veya tüm belgeyi aralığa erişmek isteyebilir.  
  
 Aşağıdaki bölümlerde, üst düzey nesneleri ve birbirleri ile nasıl etkileşim kurduklarını kısaca açıklanmaktadır. Bu nesneler aşağıdaki beş içerir:  
  
-   Uygulama nesnesi  
  
-   Belge nesnesi  
  
-   Seçim nesnesi  
  
-   Aralık nesnesi  
  
-   Yer işareti nesnesi  
  
 Word nesne modeline ek olarak, Visual Studio'da Office projeleri sağlar *konak öğelerini* ve *konak denetimlerini* Word nesne modelindeki bazı nesneleri genişletir. Konak denetimlerinin ve konak öğelerinin bunlar genişletmek Word nesneleri gibi davranırlar, ancak aynı zamanda veri bağlama özellikleri ve fazladan olaylar gibi ek işlevlere sahiptirler. Daha fazla bilgi için bkz: [genişletilmiş nesneleri kullanarak Word otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md) ve [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
### <a name="application-object"></a>Uygulama nesnesi  
 <xref:Microsoft.Office.Interop.Word.Application> Nesnesi Word uygulamasını temsil eder ve tüm diğer nesnelerin üst. Üyeleri, genellikle bir bütün olarak Word'e uygular. Word ortamını denetlemek için onun özelliklerini ve yöntemlerini kullanabilirsiniz.  
  
 VSTO eklenti projelerinde erişebilirsiniz <xref:Microsoft.Office.Interop.Word.Application> kullanarak nesne `Application` alanını `ThisAddIn` sınıfı. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Belge düzeyi projelerine erişebilirsiniz <xref:Microsoft.Office.Interop.Word.Application> kullanarak nesne <xref:Microsoft.Office.Tools.Word.Document.Application%2A> özelliği `ThisDocument` sınıfı.  
  
### <a name="document-object"></a>Belge nesnesi  
 <xref:Microsoft.Office.Interop.Word.Document> Nesnesidir Word programlamasında. Bir belge ve tüm içeriğini temsil eder. Bir belgeyi açın veya yeni bir belge oluşturduğunuzda, yeni oluşturduğunuz <xref:Microsoft.Office.Interop.Word.Document> eklenen nesne <xref:Microsoft.Office.Interop.Word.Documents> koleksiyonu <xref:Microsoft.Office.Interop.Word.Application> nesnesi. Odaklanmış belge etkin belgeyi denir. Tarafından temsil edilen <xref:Microsoft.Office.Interop.Word._Application.ActiveDocument%2A> özelliği <xref:Microsoft.Office.Interop.Word.Application> nesnesi.  
  
 Visual Studio'da Office geliştirme araçlarını genişletme <xref:Microsoft.Office.Interop.Word.Document> sağlayarak nesne <xref:Microsoft.Office.Tools.Word.Document> türü. Bu tür bir *konak öğesi* tüm özelliklerine erişmenizi sağlayan bir <xref:Microsoft.Office.Interop.Word.Document> nesne ve ek olaylar ve yönetilen denetimler ekleme yeteneği ekler.  
  
 Belge düzeyi projesi oluşturduğunuzda, erişebilirsiniz <xref:Microsoft.Office.Tools.Word.Document> oluşturulan kullanarak üyeleri `ThisDocument` projenizdeki sınıfı. Üyeleri erişebilir <xref:Microsoft.Office.Tools.Word.Document> kullanarak ana öğe **bana** veya **bu** kodda kelimeleri `ThisDocument` kullanarak veya sınıf `Globals.ThisDocument` dışındaki koddan `ThisDocument` sınıf. Daha fazla bilgi için bkz: [belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md). Örneğin, belgede ilk paragrafa seçmek için aşağıdaki kodu kullanın.  
  
 [!code-vb[Trin_VstcoreWordAutomation#120](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#120)]
 [!code-csharp[Trin_VstcoreWordAutomation#120](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#120)]  
  
 VSTO eklenti projelerinde oluşturabileceğiniz <xref:Microsoft.Office.Tools.Word.Document> konak öğelerini çalışma zamanında. Oluşturulan konak öğesi ilgili belgeye denetim eklemek için kullanabilirsiniz. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="selection-object"></a>Seçim nesnesi  
 <xref:Microsoft.Office.Interop.Word.Selection> Nesnesi şu anda seçili alanı temsil eder. Word kullanıcı arabiriminde kalın metin gibi bir işlem gerçekleştirdiğinizde, seçin, veya bir metni vurgulamanız ve biçimlendirmeyi uygulayın. <xref:Microsoft.Office.Interop.Word.Selection> Nesne varsa her zaman bir belge. Ardından hiçbir şey seçili ise, ekleme noktasını temsil eder. Ayrıca, bir seçim bitişik olmayan birden çok metin bloklarını olabilir.  
  
### <a name="range-object"></a>Aralık nesnesi  
 <xref:Microsoft.Office.Interop.Word.Range> Nesnesi belgedeki bitişik bir alanı temsil eder ve bir başlangıç karakteri konumu ve bitiş bir karakterin tarafından tanımlanır. Tek bir sınırlı değildir <xref:Microsoft.Office.Interop.Word.Range> nesnesi. Birden çok tanımlayabilirsiniz <xref:Microsoft.Office.Interop.Word.Range> aynı belgedeki nesneleri. A <xref:Microsoft.Office.Interop.Word.Range> nesnesi aşağıdaki özelliklere sahiptir:  
  
-   Tek başına ekleme noktasını, bir metin aralığını veya tüm belgeyi oluşabilir.  
  
-   Boşluk, sekme karakterleri ve paragraf işaretleri gibi yazdırılamayan karakterler içerir.  
  
-   Geçerli seçim tarafından temsil edilen alan olabilir veya Geçerli seçimden farklı bir alanı temsil edebilir.  
  
-   Belgede, her zaman görünür bir seçim aksine görünür değil.  
  
-   Bir belgeyle kaydedilmez ve yalnızca kod çalışırken bulunmaktadır.  
  
 Bir aralık sonunda metin eklediğinizde, Word otomatik olarak eklenen metni dahil etmek için aralığı genişletir.  
  
### <a name="content-control-objects"></a>İçerik denetimi nesneleri  
 A <xref:Microsoft.Office.Interop.Word.ContentControl> giriş ve sunu metin ve diğer Word belgelerinde içerik türlerini denetlemek bir yol sağlar. A <xref:Microsoft.Office.Interop.Word.ContentControl> zengin metin denetimi, bir tarih seçici veya birleşik giriş kutusu gibi Word belgelerinde kullanım için iyileştirilmiş birçok farklı UI türlerini görüntüleyebilirsiniz. Aynı zamanda bir <xref:Microsoft.Office.Interop.Word.ContentControl> kullanıcılar belge veya şablonun bölümlerini düzenlemesini engellemek için.  
  
 Visual Studio genişletir <xref:Microsoft.Office.Interop.Word.ContentControl> birkaç farklı ana bilgisayar denetimleri nesnesine. Oysa <xref:Microsoft.Office.Interop.Word.ContentControl> nesne türlerinden herhangi birini içerik denetimleri için kullanılabilir olan farklı kullanıcı Arabirimi görüntüleyebilir, Visual Studio her içerik denetimi için farklı bir tür sağlar. Örneğin, kullanabileceğiniz bir <xref:Microsoft.Office.Tools.Word.RichTextContentControl> zengin metin denetimi veya oluşturmak için kullanabileceğiniz bir <xref:Microsoft.Office.Tools.Word.DatePickerContentControl> tarih seçici oluşturmak için. Bu ana bilgisayar denetimleri yerel gibi davranır <xref:Microsoft.Office.Interop.Word.ContentControl>, ancak ek olaylar ve veri bağlama özellikleri vardır. Daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
### <a name="bookmark-object"></a>Yer işareti nesnesi  
 <xref:Microsoft.Office.Interop.Word.Bookmark> Nesnesi başlangıç konumu ve bitiş konumu içeren bir belgede ardışık bir alanı temsil eder. Yer işaretleri bir konumda bir belge veya belgeye metin için kapsayıcı olarak işaretlemek için kullanabilirsiniz. A <xref:Microsoft.Office.Interop.Word.Bookmark> nesnesi ekleme noktası içerebilir veya tüm belge büyüklüğünde olabilir. A <xref:Microsoft.Office.Interop.Word.Bookmark> apart buradan ayarlayın aşağıdaki özelliklere sahip <xref:Microsoft.Office.Interop.Word.Range> nesnesi:  
  
-   Tasarım zamanında yer işareti adı verebilirsiniz.  
  
-   <xref:Microsoft.Office.Interop.Word.Bookmark>nesneleri belgeyle kaydedilir ve böylece kod çalışmadığında veya belge kapatıldığında silinmez.  
  
-   Yer işaretleri gizli ya da ayarlayarak görünür hale <xref:Microsoft.Office.Interop.Word.View.ShowBookmarks%2A> özelliği <xref:Microsoft.Office.Interop.Word.View> nesnesini **false** veya **doğru**.  
  
 Visual Studio genişletir <xref:Microsoft.Office.Interop.Word.Bookmark> sağlayarak nesne <xref:Microsoft.Office.Tools.Word.Bookmark> konak kontrolü. <xref:Microsoft.Office.Tools.Word.Bookmark> Konak kontrolü yerel gibi davranır <xref:Microsoft.Office.Interop.Word.Bookmark>, ancak ek olaylar ve veri bağlama özellikleri vardır. Bir Windows formunda metin kutusu denetimine veri bağlama aynı şekilde verileri bir belgedeki yer işareti denetimi bağlayabilirsiniz. Daha fazla bilgi için bkz: [yer işareti denetimi](../vsto/bookmark-control.md).  
  
##  <a name="WordOMDocumentation"></a>Word nesne modeli belgelerini kullanma  
 Word nesne modeli hakkında tam bilgi için Word birincil birlikte çalışma derlemesi (PIA) başvuru ve Visual Basic for Applications (VBA) nesne modeli başvurusu başvurabilirsiniz.  
  
### <a name="primary-interop-assembly-reference"></a>Birincil birlikte çalışma derleme başvurusu  
 Word PIA başvuru belgeleri Word için birincil birlikte çalışma derlemesindeki türler açıklanmaktadır. Bu belge aşağıdaki konumdan kullanılabilir: [Word 2010 birincil birlikte çalışma derleme başvurusu](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
 PIA ve olayları PIA nasıl uygulandığı, sınıflar ve arabirimler arasındaki fark gibi Word PIA tasarımı hakkında daha fazla bilgi için bkz: [genel bakış, sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleriiçinde](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
### <a name="vba-object-model-reference"></a>VBA nesne modeli başvurusu  
 VBA kodu gösterilen VBA nesne modeli başvurusu Word nesne modeli belgeler. Daha fazla bilgi için bkz: [Word 2010 nesne modeli başvurusu](http://go.microsoft.com/fwlink/?LinkId=199772).  
  
 Tüm nesneleri ve VBA nesne modeli başvurusu üyeleri türleri ve Word PIA üyelerine karşılık gelir. Örneğin, belge nesnesi VBA nesne modeli başvurusu için karşılık gelen <xref:Microsoft.Office.Interop.Word.Document> Word PIA nesne. VBA nesne modeli başvurusu kod örnekleri çoğu özellikleri, yöntemleri ve olayları sağlasa da, Visual C# Word kullanmak istiyorsanız, proje Visual Studio kullanarak oluşturmak veya Visual Basic bu başvurusu VBA kodu çevirme gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md)   
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Belgelerle çalışma](../vsto/working-with-documents.md)   
 [Belgelerde metinle çalışma](../vsto/working-with-text-in-documents.md)   
 [Sekmelerle çalışma](../vsto/working-with-tables.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  