---
title: "Şerit nesne modeline genel bakış | Microsoft Docs"
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
helpviewer_keywords: Ribbon [Office development in Visual Studio], object model
ms.assetid: cae24f66-e980-41ee-a915-d4c8e03efbc1
caps.latest.revision: "75"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 655a1b6f3d57ac15fc7a50a603b2a12791251c9d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ribbon-object-model-overview"></a>Şerit Nesne Modeline Genel Bakış
  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Almak ve Şerit denetimlerini çalışma zamanında ayarlamak için kullanabileceğiniz bir kesin türü belirtilmiş nesne modeli sunar. Örneğin, dinamik olarak menü denetimleri doldurmak veya gösterebilir ve denetimleri bağlam gizle. Şerit, ancak yalnızca Şerit Office uygulaması tarafından yüklenmeden sekmeler, gruplar ve denetimler de ekleyebilirsiniz. Bilgi için bkz: [ayarı özellikleri, hale salt okunur](#SettingReadOnlyProperties).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
 Şerit nesne modeli çoğunlukla oluşan [Şerit sınıfı](#RibbonClass), [Şerit olayları](#RibbonEvents), ve [Şerit denetim sınıfları](#RibbonControlClasses).  
  
##  <a name="RibbonClass"></a>Şerit sınıfı  
 Yeni bir eklediğinizde **Şerit (Görsel Tasarımcı)** öğesi bir proje için Visual Studio ekler bir **Şerit** projenize sınıfı. **Şerit** sınıfının devraldığı <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> sınıfı.  
  
 Bu sınıf, Şerit kod dosyası ve Şerit Tasarımcısı kod dosyası arasında bölünmüş bir parçalı sınıf olarak görünür.  
  
##  <a name="RibbonEvents"></a>Şerit olayları  
 **Şerit** sınıfı, aşağıdaki üç olayı içerir:  
  
|Olay|Açıklama|  
|-----------|-----------------|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Load>|Office uygulaması Şerit Özelleştirmelerini yüklediğinde oluşur. <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load> Olay işleyicisi Şerit kod dosyasına otomatik olarak eklenir. Bu olay işleyicisi Şerit yüklediğinde özel kodu çalıştırmak için kullanın.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.LoadImage>|Şerit yüklediğinde Şerit özelleştirme önbellek görüntülere sağlar. Bu olay işleyicisi Şerit görüntülerinde önbelleğe almak için kod yazma küçük bir performans kazancı elde edebilirsiniz. Daha fazla bilgi için bkz. <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>.|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Close>|Şerit örneği kapandığında ortaya çıkar.|  
  
##  <a name="RibbonControlClasses"></a>Şerit denetimleri  
 <xref:Microsoft.Office.Tools.Ribbon> Ad alanında gördüğünüz her denetim için bir tür **Office Şerit denetimleri** grubunu **araç**.  
  
 Aşağıdaki tabloda türü her biri için gösterilir `Ribbon` denetim. Her denetim açıklaması için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
|Denetim adı|Sınıf adı|  
|------------------|----------------|  
|**Kutusu**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|  
|**Düğmesi**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|  
|**ButtonGroup**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|  
|**Onay kutusu**|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|  
|**ComboBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|  
|**Açılır**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>|  
|**EditBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**Galerisi**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**Grup**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|  
|**Etiket**|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|  
|**Menü**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|  
|**Ayırıcı**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|  
|**Bölünmüş düğme**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**Sekmesi**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**ToggleButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
  
 <xref:Microsoft.Office.Tools.Ribbon> Ad alanı, Denetim sınıfları adlarını içeren bir ad çakışması önlemek için bu tür "Şerit" önekini kullanır <xref:System.Windows.Forms> ad alanı.  
  
 Şerit Tasarımcısı sınıfı bu denetim için bir denetim için Şerit Tasarımcısı eklediğinizde, Şerit Tasarımcısı kod dosyasında bir alan olarak bildirir.  
  
### <a name="common-tasks-using-the-properties-of-ribbon-controls"></a>Şerit denetimlerini kullanarak ortak görevleri  
 Her `Ribbon` denetimi bir denetim için etiket atama veya gizleme ve denetimleri görüntüleme gibi çeşitli görevleri gerçekleştirmek için kullanabileceğiniz özellikler içerir.  
  
 Bazı durumlarda, Özellikler Şerit yüklemeden sonra veya bir denetim dinamik menüye eklendikten sonra salt okunur hale gelir. Daha fazla bilgi için bkz: [ayarı özellikleri salt okunur bu Become](#SettingReadOnlyProperties).  
  
 Aşağıdaki tabloda kullanarak gerçekleştirebileceğiniz görevlerden bazıları açıklanmaktadır `Ribbon` denetleyen özellikler.  
  
|Bu görev için:|Bunu yapın:|  
|--------------------|--------------|  
|Bir denetim göstermek veya gizlemek.|Vısıble özelliği kullanın.|  
|Etkinleştirmek veya devre dışı bir denetim.|Etkin özelliğini kullanın.|  
|Bir denetimin boyutunu ayarlayın.|ControlSize özelliğini kullanın.|  
|Bir denetimde görüntülenen resmi alın.|Görüntü özelliğini kullanın.|  
|Bir denetimin etiket değiştirin.|Etiket özelliğini kullanın.|  
|Kullanıcı tanımlı veri için bir denetim ekleyin.|Tag özelliği kullanın.|  
|Öğeleri alma bir <xref:Microsoft.Office.Tools.Ribbon.RibbonBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>, veya<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>Denetim.|Öğeleri özelliğini kullanın.|  
|Öğeleri Ekle bir <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, veya <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> denetim.|Öğeleri özelliğini kullanın.|  
|Denetimler ekleme bir <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>.|Öğeleri özelliğini kullanın.<br /><br /> Denetimler eklemek için <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> Şerit Office uygulamasına yüklendikten sonra ayarlamalısınız <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> özelliğine **true** Şerit Office uygulamasına yüklenmeden önce. Bilgi için bkz: [ayarı özellikleri, hale salt okunur](#SettingReadOnlyProperties).|  
|Seçilen öğe, almak bir <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>,<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, veya <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>.|SelectedItem özelliğini kullanın. İçin bir <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>, kullanın <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Text%2A> özelliği.|  
|Grupları alma bir <xref:Microsoft.Office.Tools.Ribbon.RibbonTab>.|Kullanım <xref:Microsoft.Office.Tools.Ribbon.RibbonTab.Groups%2A> özelliği.|  
|Satır ve sütun sayısı, görünen belirtin bir <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>.|Kullanım <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> ve <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> özellikleri.|  
  
##  <a name="SettingReadOnlyProperties"></a>Salt okunur ayarı özellikleri  
 Şerit yüklemeden önce bazı özellikleri yalnızca ayarlayabilirsiniz. Bu özellikleri ayarlamak için üç yerde vardır:  
  
-   Visual Studio'da **özellikleri** penceresi.  
  
-   Oluşturucusunun içinde **Şerit** sınıfı.  
  
-   Yöntemini içinde `ThisAddin`, `ThisWorkbook`, veya `ThisDocument` projenizin sınıfı.  
  
 Dinamik menüler bazı özel durumlar sağlar. Yeni denetimler oluşturma, bunların özelliklerini ayarlamak ve sonra bile menüyü içeren Şerit yüklendikten sonra çalışma zamanında dinamik menüye ekleyin.  
  
 Dinamik menüye eklediğiniz denetimlerin özelliklerini herhangi bir zamanda ayarlanabilir.  
  
 Daha fazla bilgi için bkz: [özellikleri salt okunur bu Become](#ReadOnlyProperties).  
  
### <a name="setting-properties-in-the-constructor-of-the-ribbon"></a>Şerit oluşturucuda özelliklerini ayarlama  
 Özellikleri ayarlayabilirsiniz bir `Ribbon` oluşturucusunun denetiminde **Şerit** sınıfı. Çağrısından sonra bu kodu görünmelidir `InitializeComponent` yöntemi. Geçerli saat 17:00 ise aşağıdaki örnek yeni bir düğme bir gruba ekler. Pasifik Saati (UTC-8) veya sonraki bir sürümü.  
  
 Aşağıdaki kodu ekleyin.  
  
 [!code-csharp[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/CSharp/trin_ribbon_objectmodel_dotnet4/Ribbon1.Designer.cs#1)]
 [!code-vb[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/VisualBasic/trin_ribbon_objectmodel_dotnet4/Ribbon1.Designer.vb#1)]  
  
 Visual Studio 2008'den yükseltilen Visual C# projelerinde, yapıcı Şerit kod dosyasında görünür.  
  
 Visual Basic projeleri ya da, oluşturduğunuz Visual C# projeleri [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], yapıcı Şerit Tasarımcısı kod dosyasında görünür. Bu dosya adlı *ŞeritÖğeniz*. Designer.cs veya *ŞeritÖğeniz*. Designer.vb olarak adlandırılır. Visual Basic projelerinde bu dosyayı görmek için önce tıklatmalısınız **tüm dosyaları göster** Çözüm Gezgini'nde düğmesi.  
  
### <a name="setting-properties-in-the-createribbonextensibilityobject-method"></a>Yöntemini özelliklerini ayarlama  
 Özellikleri ayarlayabilirsiniz bir `Ribbon` yöntemini de kıldığınızda kontrol `ThisAddin`, `ThisWorkbook`, veya `ThisDocument` projenizin sınıfı. Yöntemini hakkında daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
 Aşağıdaki örnek, yöntemindeki içinde Şerit özelliklerini ayarlar `ThisWorkbook` Excel çalışma kitabı sınıfı.  
  
 Aşağıdaki kodu ekleyin.  
  
 [!code-vb[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/VisualBasic/trin_ribbon_objectmodel_dotnet4/ThisWorkbook.vb#2)]
 [!code-csharp[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/CSharp/trin_ribbon_objectmodel_dotnet4/ThisWorkbook.cs#2)]  
  
###  <a name="ReadOnlyProperties"></a>Salt okunur özellikler  
 Aşağıdaki tabloda Şerit yüklemeden önce yalnızca ayarlanabilir özellikleri gösterir.  
  
> [!NOTE]  
>  Herhangi bir zamanda dinamik menüler denetimlerin özelliklerini ayarlayabilirsiniz. Bu tablo bu durumda geçerli değildir.  
  
|Özellik|Şerit denetim sınıfı|  
|--------------|--------------------------|  
|**BoxStyle**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|  
|**ButtonType**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**ColumnCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ControlId**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**DialogLauncher**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|  
|**Dinamik**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|  
|**Genel**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**Grupları**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|  
|**Görüntü adı**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
|**ItemSize**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|  
|**MaxLength**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**Ad**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComponent>|  
|**Konumu**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonTab><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|  
|**RibbonType**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**Satır sayısı**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemImage**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemLabel**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**ShowItemSelection**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|  
|**SizeString**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|  
|**StartFromScratch**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**Sekmeleri**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|  
|**Başlık**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|  
  
### <a name="setting-properties-for-ribbons-that-appear-in-outlook-inspectors"></a>Outlook Inspector görünen Şerit özelliklerini ayarlama  
 Şerit yeni bir örneğini bir kullanıcı Inspector Şerit göründüğü her açtığında oluşturulur. Ancak, yalnızca Şerit ilk örneği oluşturulmadan önce yukarıdaki tabloda listelenen özellikleri ayarlayabilirsiniz. Sonra ilk örneği oluşturulduğunda, bu özellikleri ilk örnek Outlook'un Şerit'i yüklemek için kullandığı XML dosyası tanımladığından salt okunur hale gelir.  
  
 Şerit'ın diğer örneklerini oluşturduğunuzda, bu özelliklerden herhangi biri için farklı bir değer ayarlar koşullu mantık varsa, bu kod hiçbir etkisi olmayacaktır.  
  
> [!NOTE]  
>  Emin **adı** özelliği Outlook Şeridine eklediğiniz her denetim için ayarlanır. Çalışma zamanında Outlook Şeridine denetim eklerseniz, bu özellik, kodunuzda ayarlamanız gerekir. Tasarım zamanında Outlook Şeridine denetim eklerseniz, Name özelliği otomatik olarak ayarlanır.  
  
## <a name="ribbon-control-events"></a>Şerit denetim olayları  
 Her denetim sınıfı bir veya daha fazla olayları içerir. Aşağıdaki tabloda bu olaylar açıklanmaktadır.  
  
|Olay|Açıklama|  
|-----------|-----------------|  
|Şuna tıklayın|Bir denetim tıklatıldığında gerçekleşir.|  
|TextChanged|Metin düzenleme kutusu veya açılan kutunun değiştiğinde gerçekleşir.|  
|ItemsLoading|Denetim öğeleri koleksiyonu Office tarafından istendiğinde oluşur. Kodunuzu denetim özelliklerini değiştirir veya çağırmanız kadar ofisi önbellekleri öğeler koleksiyonunu <xref:Microsoft.Office.Core.IRibbonUI.InvalidateControl%2A> yöntemi.|  
|ButtonClick|Bir düğme oluşur bir <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> veya <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> tıklandığında.|  
|SelectionChanged|Oluşur, seçim bir <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> veya <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> değişiklikler.|  
|DialogLauncherClick|Bir grup sağ alt köşesindeki iletişim Başlatıcısı simgesi tıklatıldığında gerçekleşir.|  
  
 Bu olaylar için olay işleyicileri aşağıdaki iki parametreye sahiptir.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*gönderen*|Bir <xref:System.Object> olayı denetimi temsil eder.|  
|*e*|A <xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventArgs> içeren bir <xref:Microsoft.Office.Core.IRibbonControl>. Tarafından sağlanan Şerit nesne modeli kullanılamıyor herhangi bir özelliğe erişmek için bu denetimi kullanın [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [İzlenecek yol: Şerit denetimlerini çalışma zamanında güncelleme](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Nasıl yapılır: yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md)   
 [Nasıl yapılır: Backstage görünümüne denetimler ekleme](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Nasıl yapılır: Şerit Şerit Tasarımcısından Şerit XML dışarı aktarma](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Nasıl yapılır: eklenti kullanıcı arayüzü hatalarını gösterme](../vsto/how-to-show-add-in-user-interface-errors.md)  
  
  