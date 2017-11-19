---
title: "Office kullanıcı arabirimini özelleştirme | Microsoft Docs"
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
- menus [Office development in Visual Studio], customizing
- actions panes [Office development in Visual Studio], creating
- WPF [Office development in Visual Studio]
- toolbars [Office development in Visual Studio], customizing
- Office applications [Office development in Visual Studio], UI customization
ms.assetid: 3d7c7b88-2053-4ada-bfe7-e7bb202c430b
caps.latest.revision: "74"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7af3c33ed45a5e0b9678a41900280b1e665766ed
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="office-ui-customization"></a>Office Kullanıcı Arabirimini Özelleştirme
  Visual Studio'da Office geliştirici araçları kullanarak, kullanıcı arabirimi (UI) Microsoft Office uygulamalarının özelleştirebilirsiniz. Bu konu aşağıdaki bölümlerde özelleştirebileceğiniz UI özellikleri açıklanmaktadır:  
  
-   [UI özellikleri karşılaştırması](#Comparison)  
  
-   [Eylemler bölmeleri ve özel görev bölmeleri](#Actions)  
  
-   [Özel Şerit UI'si](#Ribbon)  
  
-   [Backstage görünümü](#Backstage)  
  
-   [Outlook Form bölgeleri](#FormRegion)  
  
-   [Belgelerindeki denetimler](#Controls)  
  
-   [Kısayol menüleri](#Shortcut)  
  
##  <a name="Comparison"></a>UI özellikleri karşılaştırması  
 Aşağıdaki tabloda, Microsoft Office projelerinde özelleştirebileceğiniz ana UI özellikleri karşılaştırılmıştır.  
  
|Özellik|Desteklenen proje türleri|Desteklenen Microsoft Office uygulamaları|  
|-------------|-----------------------------|---------------------------------------------|  
|Eylemler bölmesi|Belge düzeyinde özelleştirmeler|Excel<br /><br /> Word|  
|Özel görev bölmeleri|VSTO eklentileri|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)]<br /><br /> [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Word<br /><br /> Excel|  
|Özel Şerit UI'si|Belge düzeyinde özelleştirmeler<br /><br /> VSTO eklentileri|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)]<br /><br /> [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Project<br /><br /> Word<br /><br /> Visio|  
|Backstage görünümü|Belge düzeyinde özelleştirmeler<br /><br /> VSTO eklentileri|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)].<br /><br /> [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Project<br /><br /> Word<br /><br /> Visio|  
|Outlook form bölgeleri|VSTO eklentileri|Outlook|  
|Belgelerindeki denetimler|Belge düzeyinde özelleştirmeler<br /><br /> VSTO eklentileri|Excel<br /><br /> Word|  
|Kısayol menüleri|Belge düzeyinde özelleştirmeler<br /><br /> VSTO eklentileri|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)]<br /><br /> [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Project<br /><br /> Word<br /><br /> Visio<br /><br /> Excel|  
  
##  <a name="Actions"></a>Eylemler bölmeleri ve özel görev bölmeleri  
 Görev bölmeleri genellikle bir tarafa bir Microsoft Office uygulamasında penceresinin yerleştirilmiş kullanıcı arabirimi bölmeleri sunulmuştur. Neredeyse tüm Microsoft Office uygulamaları yerleşik görev bölmeleri içerir. Word Yardım görev bölmesinde bir görev bölmesi örnektir.  
  
 Visual Studio'da Office geliştirme araçları görev bölmelerini özelleştirmek için iki farklı yollar sağlar:  
  
-   Belge düzeyi özelleştirme Eylemler bölmesi ekleyebilirsiniz. Varsayılan olarak, belge sağındaki uygulama sağ tarafındaki Eylemler bölmesinde görüntülenir. Ancak, Eylemler bölmesinde sola, üst veya alt belgenin görüntülenebilir.  
  
-   VSTO eklenti için bir özel görev bölmesi ekleyebilirsiniz. Kullanıcıların uygulama penceresinin farklı kenarlara özel görev bölmeleri sabitleyebilirsiniz veya penceresinde herhangi bir konuma özel görev bölmeleri sürükleyebilirsiniz.  
  
 Eylemler bölmeleri ve özel görev bölmeleri denetimleri kullanıcıların veri girişi gibi görevleri yardımcı olmak için çeşitli barındırarak işlevsellik sağlar. Şerit grubuna ile karşılaştırıldığında, Eylemler bölmeleri ve özel görev bölmeleri metin ve denetimleri dahil olmak üzere daha geniş bir alan sağlar.  
  
 Eylemler bölmeleri hakkında daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md). Özel görev bölmeleri hakkında daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md).  
  
##  <a name="Ribbon"></a>Özel Şerit UI'si  
 Office uygulamalarında eklemek işlevselliği kullanıma sunmak için Şerit UI'ını özelleştirebilirsiniz. Şerit, böylece daha kolay bulmak için (denetimleri biçiminde) ilgili komutları düzenlemek için bir yoldur. Kendi Şerit sekmeler ve çözümünüzde sağladığınız işlevine kullanıcılara erişim vermek için gruplar oluşturabilirsiniz. Microsoft Office sistemi önceki sürümlerinde menüleri ve araç çubukları aracılığıyla erişim özelliklerin çoğunu artık Şerit kullanarak erişilebilir.  
  
 Daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
##  <a name="Backstage"></a>Backstage görünümü  
 Tıklayarak Office uygulamalarında **dosya** sekmesi Backstage görünümü açılır. Backstage görünümü dosya düzeyinde görevleri ve eylemleri birleştirir ve benzer işlevselliği Microsoft Office düğmesinden erişilen 2007 Microsoft Office sistemi değiştiren bir kullanıcı Arabirimi sağlar. Backstage görünümü XML tamamen Genişletilebilir kullanmaktır.  
  
 Visual Studio Tasarımcısı veya API'leri Backstage görünümünü özelleştirmek için sağlamaz. Ancak, eklerseniz bir **Şerit (XML)** öğesi Office projenize XML Backstage görünümünü özelleştirmek için Şerit XML dosyasına ekleyebilirsiniz. Hakkında daha fazla bilgi için **Şerit (XML)** öğeler, bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
 Backstage görünümünü özelleştirme hakkında daha fazla bilgi için bkz: [giriş geliştiricilerin Office 2010 Backstage görünümüne](http://go.microsoft.com/fwlink/?LinkId=182189) ve [geliştiricilerin Office 2010 Backstage görünümünü özelleştirme](http://go.microsoft.com/fwlink/?LinkId=182188).  
  
##  <a name="FormRegion"></a>Outlook Form bölgeleri  
 Form bölgeleri için standart Microsoft Office Outlook form özel işlevsellik eklemek için kullanın. Varolan bir formu ek alanlar veya denetimleri ile genişletmek form bölgeleri oluşturabilirsiniz. Visual Studio'da Office geliştirme araçlarını kullanarak yeni bir form bölgesi oluşturursanız, yalnızca Windows Forms denetimleri form bölgesi üzerindeki kullanabilirsiniz. Outlook'ta tasarlanan form bölgesini içe aktarırsanız, sadece yerel Outlook denetimleri kullanabilirsiniz.  
  
 Outlook UI işleminin farklı alanları kaplar form bölgeleri oluşturabilirsiniz. Örneğin, bitişik form bölgeleri formun ilk sayfasının en altında görüntülenir ve her bitişik form bölgesi daraltılabilir. Bir tam ek form sayfası olarak görüntülenir ve görünen, ayrı form bölgesini de, herhangi bir varolan standart form veya özel form da ekleyebilirsiniz.  
  
 Daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
##  <a name="Controls"></a>Belgelerindeki denetimler  
 Word belgelerini ve Excel çalışma sayfaları için denetimleri çeşitli ekleyebilirsiniz. Örneğin, böylece kullanıcı standart bir biçimde tarihleri girin veya bir veritabanına veri göndermek için bir çalışma sayfası üzerinde bir düğme put tarih seçici denetimi belge eklemek isteyebilirsiniz.  
  
 Excel veya Word için belge düzeyi projelerine geliştirirken denetimleri projenizdeki belge veya çalışma kitabına tasarım zamanında eklemek için Visual Studio tasarımcısını kullanabilirsiniz veya çalışma zamanında denetimlerini programlı olarak ekleyebilirsiniz. Excel veya Word için VSTO eklentisi projelerine geliştirdiğinizde, programlı olarak denetimleri herhangi bir açık belge veya çalışma zamanında ekleyebilirsiniz.  
  
 Daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md) ve [Office belgeleri genel bakış Windows Forms denetimleri](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
##  <a name="Shortcut"></a>Kısayol menüleri  
 Bir belge veya bir uygulama penceresinin sağ tıklattığınızda bir kısayol menüsü görüntülenir. Bir olay bir kullanıcı bir belge, çalışma kitabı veya konak denetimi tıklattığında gibi gerçekleştikten sonra görünmesi bir kısayol menüsü ayarlayabilirsiniz. Birkaç farklı menü komutları veya denetimlerin bir kısayol menüsüne ekleyebilirsiniz. Kısayol menüleri XML kullanarak oluşturun. Eklerseniz bir **Şerit (XML)** öğesi Office projenize kısayol menüleri oluşturmak için Şerit XML dosyasını XML ekleyebilirsiniz. Kısayol menüleri oluşturmak için XML kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: kısayol menüleri ekleme komutları](../vsto/how-to-add-commands-to-shortcut-menus.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Windows Forms denetimleri Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Özel görev bölmeleri](../vsto/custom-task-panes.md)   
 [Office çözümlerinde WPF denetimlerini kullanma](../vsto/using-wpf-controls-in-office-solutions.md)   
 [Nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)   
 [Nasıl yapılır: eklenti kullanıcı arayüzü hatalarını gösterme](../vsto/how-to-show-add-in-user-interface-errors.md)   
 [İzlenecek yol: bir Windows formu kullanarak veri toplama](../vsto/walkthrough-collecting-data-using-a-windows-form.md)  
  
  