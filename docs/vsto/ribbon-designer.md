---
title: "Şerit Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Designer_Microsoft.VisualStudio.Tools.Office.Ribbon.Design.RibbonDesigner
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, about Ribbon Designer
- controls [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], controls
- customizing the Ribbon, about Ribbon Designer
- Ribbon [Office development in Visual Studio], visual designer
- customizing the Ribbon
- custom Ribbon
- designers [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], customizing
- Ribbon [Office development in Visual Studio], common tasks
- Ribbon Designer [Office development in Visual Studio]
- read-only properties
- Ribbon [Office development in Visual Studio], shortcut keys
ms.assetid: 26617206-f4da-416f-a18a-d817b2d4872d
caps.latest.revision: "79"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 941ca002d2f840805253624e7e0004fb560c4167
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ribbon-designer"></a>Şerit Tasarımcısı
  Şerit Tasarımcısı bir görsel tasarım tuvali olur. Şerit Tasarımcısı özel sekmeler, gruplar ve denetimler Microsoft Office uygulama Şerite eklemek için kullanın.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 Şerit Tasarımcısı'nı açın, eklemek bir **Şerit (Görsel Tasarımcı)** projenize öğesi. Ardından aşağıdaki görevler için tasarım araçlarını kullanabilirsiniz:  
  
-   [Şerit düzeni tasarlama](#DesigningRibbonLayout)  
  
-   [Olayları işlemek ve denetim özelliklerini ayarlama](#HandleEventsSetProperties)  
  
-   [Backstage görünümüne denetimler ekleme](#CustomizingMicrosoftOfficeButton)  
  
> [!NOTE]  
>  Şerit Tasarımcısı kullanarak yapamayacağınız bazı görevler vardır. Bu görevler ve bunları nasıl gerçekleştirebileceğiniz hakkında daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [I: kullanma Şerit Tasarımcısı Outlook Şeritte özelleştirmek için?](http://go.microsoft.com/fwlink/?LinkID=130312).  
  
## <a name="adding-a-ribbon-visual-designer-item-to-a-project"></a>Projeye Şerit (Görsel Tasarımcı) öğesi ekleme  
 Şerit Tasarımcısını kullanmak için yeni bir ekleme **Şerit (Görsel Tasarımcı)** projenize öğesi. Daha fazla bilgi için bkz: [nasıl yapılır: Get Şerit özelleştirme başlatılan](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
 Yeni bir eklediğinizde **Şerit (Görsel Tasarımcı)** öğesi, Visual Studio otomatik olarak aşağıdaki dosyaları projenize ekler:  
  
-   Şerit kod dosyası. Bu dosya için belirttiğiniz ada sahip **Şerit (Görsel Tasarımcı)** öğesi **Yeni Öğe Ekle** iletişim kutusu. Bu dosya için Şerit olayları işlemek için kodu ekleyin.  
  
-   Şerit Tasarımcısı kod dosyası. Bu dosya Şerit Tasarımcısı tarafından oluşturulan kodu içerir ve doğrudan düzenlenmemelidir.  
  
-   Bir kaynak dosyası. Bu dosya, Şerit üzerindeki her denetim özellik değerlerini içerir.  
  
 Zaten varsa bir **Şerit (Görsel Tasarımcı)** öğesi başka bir projeden onu anki projenizde kullanarak tekrar kullanabilirsiniz **varolan öğeyi Ekle** iletişim kutusu.  
  
##  <a name="DesigningRibbonLayout"></a>Şeriti Tasarlama  
 Şerit Tasarımcısı açmak için üç yolu vardır:  
  
-   İçinde **Çözüm Gezgini**, Şerit kod dosyasına çift tıklayın.  
  
-   İçinde **Çözüm Gezgini**Şerit kod dosyasını sağ tıklatın ve ardından **Görünüm Tasarımcısı**.  
  
-   İçinde **Çözüm Gezgini**Şerit kod dosyasını seçin ve ardından **Tasarımcısı** üzerinde **Görünüm** menüsü.  
  
 Şerit Tasarımcısı varsayılan bir sekme ve grup içerir. Şerit Tasarımcısı'ndan varsayılan sekme ve grup kaldırabilirsiniz. Varsayılan grubu kaldırmak için sağ **Group1**ve ardından **silmek**. Varsayılan sekmeyi kaldırmak için tasarım yüzeyi boş bir alana sağ tıklayın ve ardından **Şerit Sekmesi Kaldır**.  
  
 Şerit Tasarımcısı özel sekmeler, gruplar ve denetimler de ekleyebilirsiniz. Bu denetimlerin bulabilirsiniz **araç**, **Office Şerit denetimleri** grubu. Denetimlerden eklemenin üç yolu vardır **Office Şerit denetimleri** Şerit Tasarımcısı Grup:  
  
-   Bir denetimi Şerit Tasarımcısı üzerinde uygun bir alana sürükleyin.  
  
-   Bir denetim ve Şerit Tasarımcısı uygun bir alana tıklayın.  
  
-   Tasarımcıda uygun bir alan seçin, bir denetiminde çift tıklayın ve ardından **araç**.  
  
### <a name="ribbon-design-workflow"></a>Şerit tasarımı iş akışı  
 Şerit düzeni tasarlamak için temel adımları izleyin:  
  
1.  [Şerite özel sekme ekleme](#AddTabToRibbon).  
  
2.  [Grupları sekmesine eklemek için](#AddGroupsToTab).  
  
3.  [Denetimleri gruplara eklemek](#AddControlsToGroups).  
  
 Denetimleri yalnızca gruplarında bırakılabilir; bir denetimi doğrudan bir sekmesinde veya Şeridin sürükleyin olamaz. Gruplar yalnızca sekmelerinde bırakılabilir; bir grubu doğrudan Şerite sürükleyin olamaz.  
  
 Denetimleri doğru konumlara sürükleyerek düzenleyin. Bir denetimin özelliklerini kullanarak ayarlayabilirsiniz **özellikleri** penceresi.  
  
 Denetimleri bir sekmeye diğerine Şerit'te sürüklediğiniz olamaz. Başka bir sekmeye bir denetimi taşımak istiyorsanız, kullanmalısınız **kesme** bir sekmeye bir denetimi kaldırıp denetimi başka bir sekmeye yapıştırın komutu. Denetim kesin ve yapıştırın, olay işleyicisi çalışmayı durdurur. Olay işleyicisini yeniden **özellikleri** penceresi. Daha fazla bilgi için bkz: [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
###  <a name="AddTabToRibbon"></a>Şerite özel sekmeler ekleme  
 Şerite özel sekme eklemenin üç yolu vardır:  
  
-   Bir sekmesinden ekleyin **araç**.  
  
-   Şerit Tasarımcısı sağ tıklayın ve ardından **Şerit sekmesi Ekle**.  
  
-   Açık **Sekme Koleksiyonu Düzenleyicisi**ve ardından **Ekle**.  
  
     Açmak için **Sekme Koleksiyonu Düzenleyicisi**, **özellikleri** penceresinde, seçin **sekmeleri** özelliği ve üç nokta düğmesini tıklatıp ![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips").  
  
 Sekme ekledikten sonra denetimleri içermesi için gruplar ekleyebilirsiniz.  
  
#### <a name="removing-custom-tabs-from-the-ribbon"></a>Şeritten özel sekmeleri kaldırma  
 Özel sekme Şeritten kaldırmak için üç yolu vardır:  
  
-   Tasarımcısı'nı sağ tıklatın ve ardından **Şerit Sekmesi Kaldır**.  
  
-   İçinde **komutları** bölmesinde **özellikleri** penceresinde tıklatın **Şerit Sekmesi Kaldır**.  
  
-   Açık **Sekme Koleksiyonu Düzenleyicisi**sekmesini seçin ve ardından **kaldırmak**.  
  
#### <a name="changing-the-position-of-a-tab-on-the-ribbon"></a>Şeritteki sekmenin konumunu değiştirme  
 Şerit özel sekme sırasını değiştirebilirsiniz. Ayrıca, önce veya sonra Şerit üzerindeki yerleşik bir sekmeyi özel sekmeler konum. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritteki sekmenin konumunu değiştirme](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md).  
  
#### <a name="customizing-built-in-tabs-on-the-ribbon"></a>Şerit'te yerleşik sekmeleri özelleştirme  
 Yerleşik bir sekmeyi zaten bir Microsoft Office uygulamasından Şerit'te olan sekme olarak kullanılır. Örneğin, **veri** sekme, yerleşik bir sekmeyi Excel'de kullanılabilir.  
  
 Gruplar ve denetimler için yerleşik bir sekmeyi ekleyebilirsiniz. Bunu önce veya sonra herhangi bir yerleşik grubu sekmesinde taşıyabilir ancak varsayılan olarak, özel bir grup yerleşik bir sekmede son grup olarak görünür.  
  
 Yerleşik grupları kaldırılamıyor.  
  
 Yerleşik bir sekmeyi özelleştirme hakkında daha fazla bilgi için bkz [nasıl yapılır: yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md).  
  
###  <a name="AddGroupsToTab"></a>Bir sekmeye grupları ekleme  
 Grupları, Şerit üzerindeki denetimleri mantıksal olarak düzenlemenize. Sekmelere gruplar ekleyin. Diğer tüm denetimler grubuna ekleyin.  
  
###  <a name="AddControlsToGroups"></a>Gruplara denetim ekleme  
 Bir veya daha fazla denetim bir gruba ekleyin. Aşağıdaki tabloda her denetim açıklanmaktadır.  
  
|Denetim|Açıklama|  
|-------------|-----------------|  
|**Kutusu**|Bir grup denetimlerini düzenler kapsayıcı. Bir kutu ayırıcı, bir grup veya bir sekme dışındaki herhangi bir denetimi ekleyebilirsiniz. Yatay veya dikey bir kutu olabilir.|  
|**Düğmesi**|Eylem başlatan bir düğme. Bir grup, düğme grubuna, aşağı açılan listesinde, bir galeri, menü veya Bölünmüş düğme bir düğme ekleyebilirsiniz.|  
|**ButtonGroup**|Bir veya daha fazla düğme, iki durumlu düğmeler, menüler, Bölünmüş düğme ve galerileri içeren grup. Bir grup veya menü düğmesi grubu ekleyebilirsiniz.|  
|**Onay kutusu**|Seçilen veya bir seçenek açıp temizlenmiş bir kutu.|  
|**ComboBox**|Liste kutusu ekli bir düzenleme kutusu. Kullanıcıların yazın veya kendi seçtikleri seçebilirsiniz. Geçerli seçim kutusunu görüntüler. Kullanım <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Items%2A> adresindeki öğeleri eklemek ve kaldırmak için özellik çalışma zamanında önce veya Şerit Office uygulamasına yüklendikten sonra.|  
|**Açılır**|Kullanıcının seçebileceği öğelerin bir listesi. Kullanıcı yeni bir öğe aşağı açılan listesinde yazamazsınız.<br /><br /> Kullanım <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Items%2A> listesine öğe eklemek için özellik. Öğeleri çalışma zamanında ekleyip çıkarabilirsiniz.<br /><br /> Kullanım <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.Buttons%2A> düğmeleri listesine eklemek için özellik. Ancak, Ekle ve Şerit Office uygulamasına yüklendikten sonra çalışma zamanında düğmeleri kaldırın.|  
|**EditBox**|Kullanıcı metin yazabileceğiniz bir kutu.|  
|**Galerisi**|Menü, bir dizi veya kullanıcıların seçebileceği görsel seçimler kılavuzunun gösterir. Menüdeki seçimlerin düzenini denetleyebilirsiniz. Kullanım <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> ve <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> satır ve sütun sayısı, öğelerin gösterecek ve düğmeleri Galerisi belirtmek için özellikleri.|  
|**Etiket**|Şerit üzerindeki denetimleri tanımlamak için kullanabileceğiniz metin.|  
|**Menü**|Aşağıdaki denetimleri içerebilir aşağı açılan listesi:<br /><br /> -Düğmesi<br />-Onay kutusu<br />-Galerisi<br />-Menüsü<br />-Bölünmüş düğme<br />-İki durumlu düğme<br />-Ayırıcı<br /><br /> Şerit Tasarımcısı menüde bir denetim eklemek için menü tasarım yüzeyini kullanıma sunmak için menüsünde aşağı oka tıklayın. Şerit denetimlerini sonra sürükleyebilirsiniz **araç** menüye. Denetimleri düzenlemek için istediğiniz yere sürükleyin.<br /><br /> Denetimler eklemek için <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> Şerit Office uygulamasına yüklendikten sonra ayarlamalısınız <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> özelliğine **true** Şerit yüklenmeden önce. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [Şerit nesne modeline genel bakış](../vsto/ribbon-object-model-overview.md).|  
|**Ayırıcı**|Bir listedeki öğeleri ayırmak için kullanılan ince bir çubuk. Bir gruba eklendiğinde çubuk dikey olur. Bir menüye eklendiğinde çubuk yatay olur.|  
|**Bölünmüş düğme**|Menü iliştirilmiş bir düğme. Bölünmüş düğme aşağıdaki denetimleri içerebilir:<br /><br /> -Düğmesi<br />-Onay kutusu<br />-Galerisi<br />-Menüsü<br />-Bölünmüş düğme<br />-İki durumlu düğme<br />-Ayırıcı<br /><br /> Menü gibi kendi tasarım yüzeyi Bölünmüş düğme vardır. Şerit Office uygulamasına yüklenmeden önce ancak, bir menü farklı olarak, yalnızca bir Bölünmüş düğme öğelerde güncelleştirebilirsiniz. Bölünmüş düğme öğelerde güncelleştirme hakkında daha fazla bilgi için bkz: [Şerit nesne modeline genel bakış](../vsto/ribbon-object-model-overview.md).|  
|**ToggleButton**|Görünen bir düğmesine basıldığında veya basılı olmadığından.|  
  
##  <a name="HandleEventsSetProperties"></a>Olayları işleme ve özelliklerini ayarlama  
 Şerit Tasarımcısı kullanarak tasarım zamanında denetim özelliklerini ayarlamanıza olanak tanır **özellikleri** penceresi. Ayrıca, Şerit almak ve Şerit denetimlerini çalışma zamanında ayarlamak için kullanabileceğiniz bir kesin türü belirtilmiş nesne modeli sunar.  
  
 Herhangi bir denetimin varsayılan olayı için bir olay işleyicisi açmak için tasarımcı denetiminde çift tıklayabilirsiniz. Diğer tüm denetim olayları için olay işleyicilerini kullanarak oluşturabileceğiniz **özellikleri** penceresi.  
  
 Şerit olayları ve özellikleri içinde bulunur <xref:Microsoft.Office.Tools.Ribbon> ad alanı. **Şerit (Görsel Tasarımcı)** öğesine otomatik olarak projede bu derleme için bir başvuru ekler ve uygun ekler **kullanarak** veya **içeri aktarmalar** üst deyimi Şerit kod dosyası.  
  
 Şerit olaylarını işleme ve Şerit denetimlerini çalışma zamanında ayarlama hakkında daha fazla bilgi için bkz: [Şerit nesne modeline genel bakış](../vsto/ribbon-object-model-overview.md).  
  
##  <a name="CustomizingMicrosoftOfficeButton"></a>Backstage görünümüne özelleştirme  
 ' I tıklattığınızda, açılan menüye denetim eklemek için Şerit Tasarımcısını kullanabilirsiniz **dosya** sekmesi. Bu menü Backstage görünümü adı verilir.  
  
 Denetimleri önce veya sonra yerleşik denetimleri Şerit Tasarımcısını kullanarak konumlandırmak olamaz. Yerleşik denetim Backstage görünümünde görüntülenen bir denetimdir. Önce veya sonra yerleşik denetimleri denetimleri konumlandırmak istiyorsanız, Şerit XML kullanmanız gerekir. Hakkında daha fazla bilgi için **Şerit (XML)**, bkz: [Şerit XML](../vsto/ribbon-xml.md). Backstage görünümünü özelleştirme hakkında daha fazla bilgi için bkz: [giriş geliştiricilerin Office 2010 Backstage görünümüne](http://go.microsoft.com/fwlink/?LinkId=182189) ve [geliştiricilerin Office 2010 Backstage görünümünü özelleştirme](http://go.microsoft.com/fwlink/?LinkId=182188).  
  
 [!INCLUDE[appliesto_ribbon_2010](../vsto/includes/appliesto-ribbon-2010-md.md)]  
  
 Backstage görünümüne denetimler ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: Backstage görünümüne Denetimler Ekle](../vsto/how-to-add-controls-to-the-backstage-view.md).  
  
##  <a name="Accessibility"></a>Şerit Tasarımcısı'nda erişilebilirlik  
 Şerit Tasarımcısı'nda denetimleri taşımak için klavye kısayollarını kullanabilirsiniz. Tüm denetimler için bazı klavye kısayolları ve bazı menüleri sahip denetimleri uygulayın.  
  
 Tüm denetimler için uygulama klavye kısayolları aşağıdaki tabloda gösterilmiştir.  
  
|Eylem|Klavye kısayolu|  
|------------|-----------------------|  
|Önceki denetim önce bir denetim listesinde taşıyın.|CTRL + YUKARI OK<br /><br /> CTRL + SOL|  
|Listeden bir sonraki denetime sonra bir denetim taşıyın.|CTRL + AŞAĞI OK<br /><br /> CTRL + SAĞ OK|  
|Seçimi bir denetimden aynı gruptaki diğerine taşır. Aşağı açılan paneli için üst ve açılan panelinde denetimi arasında geçiş yapar.|AYARLAMA<br /><br /> AŞAĞI|  
|Tüm denetimler arasında ileriye doğru yineleme.|TAB|  
|Tüm denetimler aracılığıyla geriye doğru yineleme.|SHIFT+TAB|  
|Seçili denetimi veya denetimleri kümesini silin.|DELETE|  
|Seçili denetimleri kopyalayın.|CTRL+C|  
|Seçili denetimleri keser.|CTRL+X|  
|Panodaki denetimleri yapıştırın.|CTRL+V|  
|Seçin **araç**.|CTRL + ALT + X|  
|Üst bileşeni seçin.|ESC|  
  
 Yalnızca Microsoft Office menüsüne, uygulanan klavye kısayolları <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>, ve <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton> aşağıdaki tabloda gösterilmiştir.  
  
|Eylem|Klavye kısayolu|  
|------------|-----------------------|  
|Üst denetim açılır panel açıksa ve açılan panelde seçili bir denetim seçin.|SOL|  
|Aşağı açılan paneli açılır panel açıksa ve üst denetimin seçili kapatın.|SOL|  
|Aşağı açılan Masası'nı açın.|SAĞ|  
|Aşağı açılan Masası açık değilse, aşağı açılan panelindeki ilk denetimi seçin.|SAĞ|  
|Aşağı açılan Masası'nı kapatın.|ESC|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit XML](../vsto/ribbon-xml.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Nasıl yapılır: Şerit Şerit Tasarımcısından Şerit XML dışarı aktarma](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  