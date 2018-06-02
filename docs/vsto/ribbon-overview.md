---
title: Şerite Genel Bakış
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, multiple Ribbons
- Ribbon [Office development in Visual Studio], about Ribbon
- toolbars [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], multiple Ribbons
- toolbars [Office development in Visual Studio]
- custom Ribbon, multiple Ribbons
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6f78f55f1f36f23331a9e27228c0afa567429e30
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34693026"
---
# <a name="ribbon-overview"></a>Şerite Genel Bakış
  Şerit, böylece daha kolay bulmak için ilgili komutları düzenlemek için bir yoldur. Şerit üzerindeki denetimleri olarak komutlar görüntülenir. Denetimleri içine düzenlenir *grupları* bir uygulama penceresinin üst kenarında yatay bir bant boyunca. İlgili gruplar sekmelerinde düzenlenir.  
  
 Microsoft Office sistemi önceki sürümlerinde menüleri ve araç çubuklarını aracılığıyla erişim özelliklerin çoğunu artık Şerit kullanarak erişilebilir. Daha fazla bilgi için teknik makalesine bakın [2007 Microsoft Office sistemi için kullanıcı arabirimi Geliştirici bakış](http://go.microsoft.com/fwlink/?LinkID=70860).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="customize-the-microsoft-office-ribbon"></a>Microsoft Office Şerit özelleştirme  
 Şerit özelleştirmek için aşağıdaki Şerit öğelerden birini Office projenize ekleyin:  
  
-   **Şerit (Görsel Tasarımcı)**  
  
-   **Şerit (XML)**  
  
 Örneğin, Excel Şerit özelleştirmek için bir Excel VSTO eklenti projesine bir Şerit öğesi ekleyin.  
  
### <a name="ribbon-visual-designer-item"></a>Şerit (Görsel Tasarımcı) öğesi  
 **Şerit (Görsel Tasarımcı)** öğesi özel bir Şerit tasarlayıp kolaylaştıran gelişmiş araçlar sağlar. Kullanım **Şerit (Görsel Tasarımcı)** Şerit aşağıdaki yollarla özelleştirmek için öğesi:  
  
-   Özel veya yerleşik sekmeler Şerite ekleyin.  
  
-   Özel gruplar için özel veya yerleşik bir sekme ekleyin.  
  
    > [!NOTE]  
    >  Yerleşik sekme veya grup zaten bir Microsoft Office uygulamasından Şerit'te biridir. Örneğin, **veri** sekme, yerleşik bir sekmeyi Excel'de kullanılabilir. **Bağlantıları** grup yerleşik bir gruptur üzerinde **veri** sekmesi.  
  
-   Özel denetimler özel bir gruba ekleyin.  
  
-   Özel denetimler Backstage görünümüne ekleyin.  
  
 Kullanarak bir Şerit özelleştirme hakkında daha fazla bilgi için **Şerit (Görsel Tasarımcı)** öğesi için bkz: [Şerit Tasarımcısı](../vsto/ribbon-designer.md).  
  
### <a name="ribbon-xml-item"></a>Şerit (XML) öğesi  
 Kullanım **Şerit (XML)** tarafından desteklenmeyen bir yolla Şerit'özelleştirmek istiyorsanız öğesi **Şerit (Görsel Tasarımcı)** öğesi. Kullanım **Şerit (XML)** Şerit aşağıdaki yollarla özelleştirmek için öğesi:  
  
-   Ekleme *yerleşik* bir özel veya yerleşik sekmelere gruplarına.  
  
-   Yerleşik denetimleri özel bir gruba ekleyin.  
  
-   Olay işleyicileri yerleşik denetimlerin geçersiz kılmak için özel kod ekleyin.  
  
-   Hızlı Erişim Araç çubuğunu özelleştirme.  
  
-   Şerit özelleştirme VSTO yetkili bir kimlik kullanarak eklenti arasında paylaşma  
  
 Kullanarak Şerit özelleştirme hakkında daha fazla bilgi için **Şerit (XML)** öğesi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
## <a name="export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml"></a>Şerit Şerit Tasarımcısından Şerit XML'ine verebilir.  
 Şerit Tasarımcısını kullanarak bir Şerit oluşturun ve ardından Şeriti şekillerde özelleştirmek istediğiniz karar verirseniz, **Şerit (Görsel Tasarımcı)** öğesi desteklemez, Şerit XML dosyasına verebilirsiniz.  
  
 Visual Studio otomatik olarak oluşturur bir **Şerit (XML)** öğesi ve Şerit üzerindeki her denetim için Şerit XML dosyası öğeleri ve öznitelikleri ile doldurur.  
  
 Tüm bulunan özellikler **özellikleri** Şerit Tasarımcısı penceresinin Şerit XML dosyasına aktarılır.  Örneğin, Visual Studio değeri vermez **görüntü** veya **metin** özelliği. Bir geri çağırma yöntemi bir görüntü atayın veya metin denetimi ayarlamak için dışarı aktarılan proje Şerit kod dosyasında oluşturmalısınız olmasıdır. Visual Studio dışa aktarma işleminin bir parçası geri arama yöntemleri otomatik olarak oluşturmaz.  
  
 Ayrıca, tüm değişmeden varsayılan özellik değerleri sonuçta elde edilen Şerit XML dosyasında görünmez.  
  
 Şerit XML dışarı aktarma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Şerit Tasarımcısından Şerit XML'ine Şerit Dışarı](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md).  
  
### <a name="update-the-code"></a>Kodunu güncelleştirin  
 Yeni bir Şerit kod dosyası eklenen **Çözüm Gezgini**. Bu dosya Şerit XML sınıfını içerir. Geri arama yöntemleri oluşturmalısınız `Ribbon Callbacks` bir düğmeye tıklanması gibi kullanıcı eylemlerini işlemek için bu sınıfın bölgesi. Bu geri çağırma yöntemleri için olay işleyicilerini kodunuzu taşıyın ve Şerit genişletilebilirlik (RibbonX) programlama modeli çalışmak için kodu değiştirin. Daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
 Kod ayrıca eklemelisiniz `ThisAddIn`, `ThisWorkbook`, veya `ThisDocument` geçersiz kılmaları sınıf `CreateRibbonExtensibilityObject` yöntemi Şerit XML sınıfını döndüren Office uygulaması.  
  
 Daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
## <a name="add-multiple-ribbon-items-to-a-project"></a>Birden çok Şerit öğesi için bir proje ekleyin  
 Tek bir projeye birden çok Şerit öğesi ekleyebilirsiniz. Bu, aşağıdaki iki görevden birini gerçekleştirmek istiyorsanız yararlıdır:  
  
-   Outlook için Şerit oluşturma *denetçiler*. Daha fazla bilgi için bkz: [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md).  
  
    > [!NOTE]  
    >  Bir denetleyici kullanıcıların e-posta iletisine oluşturma gibi belirli görevleri gerçekleştirdiğinizde, açılan bir penceredir.  
  
-   Çalışma zamanında görüntülemek için hangi Şerit'i seçin.  
  
### <a name="select-which-ribbons-to-display-at-runtime"></a>Çalışma zamanında görüntülemek için hangi Şerit seçin  
 Bir proje birden çok Şerit içerdiğinden, çalışma zamanında görüntülemek üzere hangi Şerit seçebilirsiniz.  
  
 Çalışma zamanında görüntülemek üzere bir Şerit seçmek için geçersiz kılma `CreateRibbonExtensibilityObject` yönteminde `ThisAddin`, `ThisWorkbook`, veya `ThisDocument` projenizi ve return görüntülemek istediğiniz Şerit sınıfı. Aşağıdaki örnek adlı bir alanın değerini denetler `myCondition` ve uygun Şerit döndürür.  
  
> [!NOTE]  
>  Bu örnekte kullanılan sözdizimi kullanılarak oluşturulmuş bir Şerit döndürür **Şerit (Görsel Tasarımcı)** öğesi. Sözdizimi kullanılarak oluşturulan bir Şerit döndürmek için bir **Şerit (XML)** öğesi biraz farklıdır. Döndürme hakkında daha fazla bilgi için bir **Şerit (XML)** öğesi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
 Aşağıdaki kodu ekleyin:  
  
 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/VisualBasic/trin_Ribbon_choose_Ribbon_4/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/CSharp/trin_Ribbon_choose_Ribbon_4/ThisWorkbook.cs#1)]  
  
### <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)|Microsoft Office uygulamasının şeridini özelleştirmek için ekleyin gösterilmiştir bir **Şerit (Görsel Tasarımcı)** veya **Şerit (XML)** Office proje öğesi.|  
|[Şerit Tasarımcısı](../vsto/ribbon-designer.md)|Microsoft Office uygulama Şerite özel sekmeler, gruplar ve denetimler eklemek için Şerit Tasarımcısı nasıl kullanabileceğinizi açıklar.|  
|[İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)|Şerit Tasarımcısını kullanarak özel bir Şerit sekmesi oluşturulacağını gösterir. Ekleme ve özel sekmesindeki denetimleri konumlandırmak için Şerit Tasarımcısını kullanabilirsiniz.|  
|[Şerit nesne modeline genel bakış](../vsto/ribbon-object-model-overview.md)|Almak ve Şerit denetimlerini çalışma zamanında ayarlamak için kullanabileceğiniz kesin türü belirtilmiş nesne modeline genel bakış sağlar.|  
|[İzlenecek yol: çalışma zamanında Şerit denetimlerini güncelleştirme](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)|Şerit nesne modeline Şerit Office uygulamasına yüklendikten sonra bir Şerit denetimlerini güncellemek için nasıl kullanılacağını gösterir.|  
|[Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md)|Microsoft Office Outlook Şeritte özelleştirmek için yönergeler sağlanmaktadır.|  
|[InfoPath için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-infopath.md)|Microsoft Office InfoPath Şeritte özelleştirmek için yönergeler sağlanmaktadır.|  
|[Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)|Gösterme, gizleme ve Şerit değiştirmek ve kullanıcıların özel görev bölmesi, Eylemler bölmesinde veya Outlook form bölgesi denetimlerinde kodu çalıştırmasına etkinleştirmek gösterilmiştir.|  
|[Nasıl yapılır: Şeritteki sekmenin konumunu değiştirme](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)|Şeritteki sekmelerin sırasını değiştirmek gösterilmiştir.|  
|[Nasıl yapılır: yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md)|Gruplar ve denetimler için yerleşik bir sekmeyi nasıl ekleneceğini gösterir.|  
|[Nasıl yapılır: Backstage görünümüne denetimler ekleme](../vsto/how-to-add-controls-to-the-backstage-view.md)|Denetimlerin tıkladığınızda açılır menüde nasıl ekleneceğini gösterir **dosya**.|  
|[Nasıl yapılır: Şerit grubuna iletişim kutusu başlatıcısı ekleme](../vsto/how-to-add-a-dialog-box-launcher-to-a-ribbon-group.md)|Herhangi bir Şerit grubuna iletişim kutusu başlatıcısı eklemek için gösterir.|  
|[Nasıl yapılır: Şerit Şerit Tasarımcısından Şerit XML'ine verebilir.](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)|Şerit Gelişmiş Şerit Tasarımcısından Şerit XML'ine vererek yollardan gösterilmektedir.|  
|[Şerit XML](../vsto/ribbon-xml.md)|Şerit XML kullanarak Şerit nasıl özelleştirebileceğiniz açıklanmaktadır.|  
|[İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)|Özel bir Şerit sekmesi kullanılarak oluşturulması gösterilmiştir **Şerit (XML)** öğesi.|  
  
  