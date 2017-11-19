---
title: "Yazı tipleri ve Visual Studio için biçimlendirme | Microsoft Docs"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3c3df69-83b4-4fd0-b5b1-e18c33f39376
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5a252e22cda234f6a45bee084522b2add2bafada
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="fonts-and-formatting-for-visual-studio"></a>Yazı tipleri ve Visual Studio için biçimlendirme
##  <a name="BKMK_TheEnvironmentFont"></a>Ortam yazı tipi  
 Visual Studio içinde tüm yazı tipleri için özelleştirme kullanıcıya sunulmalıdır. Bu öncelikle yoluyla yapılır **yazı tiplerini ve renkleri** sayfasındaki **Araçlar > Seçenekler** iletişim. Yazı tipi ayarlarını üç ana kategoride şunlardır:  
  
-   **Ortam yazı tipi** -iletişim kutuları, menüler, aracı windows ve belge pencereleri dahil olmak üzere tüm arabirim öğeleri için kullanılan birincil yazı tipi IDE (tümleşik geliştirme ortamı). Varsayılan olarak, geçerli Windows sürümlerinde 9 pt Segoe UI olarak görünür bir sistem yazı tipiyle ortamı yazı tipi bağlıdır. Bir yazı tipi için tüm arabirim öğeleri kullanılarak IDE genelinde tutarlı yazı tipi görünümünü sağlamaya yardımcı olur.  
  
-   **Metin düzenleyici** -kod ve diğer yüzey metin tabanlı düzenleyiciler Metin Düzenleyicisi'nde özelleştirilebilir, öğeleri sayfa **Araçlar > Seçenekler**.  
  
-   **Belirli koleksiyonlar** -kullanıcı arabirimi öğelerini özelleştirmesini tasarımlarını için özel yazı tipleri kullanıma sunma Tasarımcı windows yüzey kendi Ayarları sayfasında **Araçlar > Seçenekler**.  
  
### <a name="editor-font-customization-and-resizing"></a>Düzenleyici yazı tipi özelleştirme ve yeniden boyutlandırma  
 Kullanıcıların genellikle büyütün veya boyutu ve/veya bunların tercih genel kullanıcı arabiriminin bağımsız göre Düzenleyicisi içindeki metnin rengi Yakınlaştır. Ortam yazı tipi içinde veya bir düzenleyici/Tasarımcısı'nın bir parçası olarak görünebilir öğelerde kullanıldığından, bu yazı tipini sınıflandırmalarını biri değiştiğinde, beklenen bir davranış dikkate almak önemlidir.  
  
 Görüntülenen kullanıcı Arabirimi öğeleri parçası Düzenleyicisi ancak olan oluştururken *içerik*, böylece öngörülebilir bir yolla öğeleri yeniden boyutlandırın ortamı de değil metin yazı tipi kullanmak önemlidir.  
  
1.  Kod Metin Düzenleyicisi'nde kodu metin yazı tipi ayarı ile yeniden boyutlandırın ve düzenleyici metin yakınlaştırma düzeyini yanıt.  
  
2.  Arabirimin diğer tüm öğeleri ortamı yazı tipi ayarına bağlı ve genel değişiklikleri ortamında yanıt verir. Bu içerir (ancak bunlarla sınırlı değildir):  
  
    -   Bağlam menüleri metni  
  
    -   Bir düzenleyici adornment metinde ampul menü metni, Hızlı Bul Düzenleyicisi bölmesinde, ister ve bölmesine gidin  
  
    -   İletişim kutularındaki metinleri gibi etiket **dosyalarda Bul** veya **yeniden Düzenle**  
  
### <a name="accessing-the-environment-font"></a>Ortam yazı tipi erişme  
 Yöntemini çağırarak ortamı yazı tipi yerel ya da WinForms kodda erişilebilir `IUIHostLocale::GetDialogFont` arabirimden sorgulama sonra `SID_SUIHostLocale` hizmeti.  
  
 Windows Presentation Foundation (WPF) iletişim kutusu pencere sınıfı kabuğun türetilen `DialogWindow` sınıfını WPF'ın yerine `Window` sınıfı.  
  
 XAML'de code şöyle görünür:  
  
```  
<ui:DialogWindow  
    x:Class"MyNameSpace.MyWindow"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:s="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:ui="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.11.0"  
    ShowInTaskbar="False"  
    WindowStartupLocation="CenterOwner"  
    Title="My Dialog">  
</ui:DialogWindow>  
  
code behind:  
  
internal partial class WebConfigModificationWindow : DialogWindow  
{  
}  
```  
  
 (Değiştir `Microsoft.VisualStudio.Shell.11.0` MPF dll geçerli sürümünüzle.)  
  
 İletişim kutusunu görüntülemek için çağrı "`ShowModal()`" sınıfında `ShowDialog()`. `ShowModal()`Kabuğu'nda doğru kalıcı durumunu ayarlar, iletişim kutusunun üst pencere vb. ortalanır sağlar.  
  
 Kod aşağıdaki gibidir:  
  
```  
MyWindow window = new MyWindow();  
window.ShowModal()  
```  
  
 `ShowModal`bool verir? (boş değer atanabilir Boolean) ile `DialogResult`, kullanılabilecek gerekiyorsa. Dönüş değeri ile iletişim kapatılırsa true **Tamam**.  
  
 Bir iletişim kutusu değil ve barındırılan bazı WPF UI kendi görüntülemek gerekiyorsa `HwndSource`, bir açılır pencere veya bir Win32/WinForms üst penceresi penceresinin WPF alt pencere gibi ayarlamanız gerekir `FontFamily` ve `FontSize` WPF e kök öğesinin üzerinde öğesine. (Kabuk üzerinde ana penceresi özelliklerini ayarlar, ancak bunlar geçmiş devralınır olmayan bir `HWND`). Kabuk olduğu özellikleri, şu şekilde bağlanabilir kaynakları sağlar:  
  
```  
<Setter property="FontFamily" Value="{DynamicResource VsFont.EnvironmentFontFamily}" />  
<Setter property="FontSize" Value="{DynamicResource VsFont.EnvironmentFontSize}" />  
```  
  
###  <a name="BKMK_Formatting"></a>(Ölçeklendirme/kalın) başvuru biçimlendirme  
 Bazı iletişim kutuları kalın hale gelmesini belirli metin ya da ortam yazı tipi dışında bir boyut gerektirir. Daha önce ortam yazı tipi büyük yazı tipleri olarak kodlanmış "`environment font +2`" veya benzer. Sağlanan kod parçacıkları yüksek DPI izleyiciler destekler ve görüntüleme metni her zaman doğru boyut ve Ağırlık (açık veya Semilight gibi) göründüğünden emin olun.  
  
> **Not: biçimlendirme uygulamadan önce bulunan Kılavuzu izlediğinden emin olun [metin stili](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).**  
  
 Ortam yazı tipi ölçeklendirmek için TextBlock veya belirtildiği gibi etiket stili ayarlayın. Her düzgün bir şekilde kullanılan, bu kod parçacıkları uygun boyut ve Ağırlık Çeşitlemeler dahil olmak üzere doğru yazı tipi oluşturur.  
  
 Burada "`vsui`" ad alanı başvurusudur `Microsoft.VisualStudio.Shell`:  
  
```  
xmlns:vsui="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0" 
```  
  
#### <a name="375-environment-font--light"></a>%375 ortam yazı tipi + açık  
 **Gibi görünür:** 34 pt Segoe UI açık  
 **Kullanım için:** (nadir) benzersiz markalı UI, olduğu gibi başlangıç sayfası

 **Yordam kodu:** nerede `textBlock` önceden tanımlanmış TextBlock olduğu ve `label` önceden tanımlanmış bir etiket:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey);  
```  
  
 **XAML:** TextBlock veya etiket stili gösterilen şekilde ayarlayın.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment375PercentFontSizeStyleKey}}">TextBlock: 375 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment375PercentFontSizeStyleKey}}">Label: 375 Percent Scaling</Label>  
```  
  
#### <a name="310-environment-font--light"></a>%310 ortam yazı tipi + açık  
 **Gibi görünür:** 28 pt Segoe UI açık   
 **Kullanım için:** büyük imza iletişim başlıklar, raporlarda başlık ana  
  
 **Yordam kodu:** nerede `textBlock` önceden tanımlanmış TextBlock olduğu ve `label` önceden tanımlanmış bir etiket:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey);    
```  
  
 **XAML:** TextBlock veya etiket stili gösterilen şekilde ayarlayın.  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment310PercentFontSizeStyleKey}}">TextBlock: 310 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment310PercentFontSizeStyleKey}}">Label: 310 Percent Scaling</Label>     
```  
  
#### <a name="200-environment-font--semilight"></a>% 200 ortamı yazı tipi + Semilight  
 **Gibi görünür:** 18 pt Segoe UI Semilight    
 **Kullanım için:** başlıklar, küçük ve orta ölçekli iletişim kutuları başlıkları  
  
 **Yordam kodu:** nerede `textBlock` önceden tanımlanmış TextBlock olduğu ve `label` önceden tanımlanmış bir etiket: 
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey);    
```  
  
 **XAML:** TextBlock veya etiket stili gösterilen şekilde ayarlayın:  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment200PercentFontSizeStyleKey}}">TextBlock: 200 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment200PercentFontSizeStyleKey}}">Label: 200 Percent Scaling</Label>    
```  
  
#### <a name="155-environment-font"></a>%155 ortam yazı tipi  
 **Gibi görünür:** 14 pt Segoe UI    
 **Kullanım için:** belgede bölüm başlıkları yanı sıra kullanıcı Arabirimi veya raporları  
  
 **Yordam kodu:** nerede `textBlock` önceden tanımlanmış TextBlock olduğu ve `label` önceden tanımlanmış bir etiket:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey);    
```  
  
 **XAML:** TextBlock veya etiket stili gösterilen şekilde ayarlayın:  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment155PercentFontSizeStyleKey}}">TextBlock: 155 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment155PercentFontSizeStyleKey}}">Label: 155 Percent Scaling</Label>  
```  
  
#### <a name="133-environment-font"></a>% 133 ortamı yazı tipi  
 **Gibi görünür:** 12 pt Segoe UI    
 **Kullanım için:** imza iletişim kutuları ve belge küçük başlıkları yanı sıra kullanıcı Arabirimi  
  
 **Yordam kodu:** nerede `textBlock` önceden tanımlanmış TextBlock olduğu ve `label` önceden tanımlanmış bir etiket:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey);    
```  
  
 **XAML:** TextBlock veya etiket stili gösterilen şekilde ayarlayın:  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment133PercentFontSizeStyleKey}}">TextBlock: 133 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment133PercentFontSizeStyleKey}}">Label: 133 Percent Scaling</Label>    
```  
  
#### <a name="122-environment-font"></a>%122 ortam yazı tipi  
 **Gibi görünür:** 11 pt Segoe UI    
 **Kullanım için:** bölümünde imza iletişim kutuları başlıklar, üst ağaç görünümünde dikey sekme Gezinti düğümleri  
  
 **Yordam kodu:** nerede `textBlock` önceden tanımlanmış TextBlock olduğu ve `label` önceden tanımlanmış bir etiket:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey);    
```  
  
 **XAML:** TextBlock veya etiket stili gösterilen şekilde ayarlayın:  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironment122PercentFontSizeStyleKey}}">TextBlock: 122 Percent Scaling</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironment122PercentFontSizeStyleKey}}">Label: 122 Percent Scaling</Label>    
```  
  
#### <a name="environment-font--bold"></a>Ortam yazı tipi + kalın  
 **Gibi görünür:** kalın 9 pt Segoe UI    
 **Kullanım için:** etiketleri ve imza iletişim kutuları, raporlar ve belge alt başlıklar yanı sıra kullanıcı Arabirimi  
  
 **Yordam kodu:** nerede `textBlock` önceden tanımlanmış TextBlock olduğu ve `label` önceden tanımlanmış bir etiket:  
  
```  
textBlock.SetResourceReference(TextBlock.StyleProperty,    
        VsResourceKeys.TextBlockEnvironmentBoldStyleKey);   
label.SetResourceReference(Label.StyleProperty,    
        VsResourceKeys.LabelEnvironmentBoldStyleKey);    
```  
  
 **XAML:** TextBlock veya etiket stili gösterilen şekilde ayarlayın:  
  
```  
<TextBlock Style="{DynamicResource {x:Static vsui:VsResourceKeys.TextBlockEnvironmentBoldStyleKey}}"> Bold TextBlock</TextBlock>   
<Label Style="{DynamicResource {x:Static vsui:VsResourceKeys.LabelEnvironmentBoldStyleKey}}"> Bold Label</Label>    
```  
  
### <a name="localizable-styles"></a>Yerelleştirilebilir stilleri  
 Bazı durumlarda, çevirmenlerin yazı tipi stillerini kalın metin Doğu Asya dilleri için kaldırma gibi farklı yerel ayarlar için değiştirmeniz gerekecektir. Yazı tipi stillerini yerelleştirme mümkün kılmak için bu stiller .resx dosya içinde olmalıdır. Bunu gerçekleştirmek ve hala Visual Studio form tasarımcısında yazı tipi stilleri düzenlemek için en iyi yolu, tasarım zamanında yazı tipi stillerini açıkça ayarlamaktır. Bu bir tam yazı tipi nesnesi oluşturur ve üst yazı tipleri devralma bölüneceği görünebilir, ancak yalnızca FontStyle özelliği yazı tipini ayarlamak için kullanılır.  
  
 İletişim formun bağlanmanıza çözümdür `FontChanged` olay. İçinde `FontChanged` olay, tüm denetimler izlemek ve yazı tipleriyle ayarlanmış olup olmadığını denetleyin. Ayarlanırsa, formun yazı tipi ve denetimin önceki yazı tipi stilini temel alan yeni bir yazı tipi için değiştirin. Bu kod örneğidir:  
  
```  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
          SetFontStyles();  
}  
  
/// <summary>  
/// SetFontStyles - This function will iterate all controls on a page  
/// and recreate their font with the desired fontstyle.  
/// It should be called in the OnFontChanged handler (and also in the constructor  
/// in case the IUIService is not available so OnFontChange doesn't fire).  
/// This way, when the VS shell font is given to us the controls that have  
/// a different style for the font (bolded for example) will recreate their font  
/// and use the VS shell font but with a style variation (bolded ...).  
/// </summary>   
protected void SetFontStyles()  
{  
     SetFontStyles(this, this, this.Font);  
}  
  
protected static void SetFontStyles(Control topControl, Control parent, Font referenceFont)  
{  
     foreach(Control c in parent.Controls)  
     {  
          if (c.Controls != null && c.Controls.Count > 0) {  
               SetFontStyles(topControl, c, referenceFont);  
          }  
          if (c.Font != topControl.Font) {  
               c.Font = new Font(referenceFont, c.Font.Style);  
          }  
     }  
}  
```  
  
 Bu kodu kullanarak formun yazı tipi güncelleştirildiğinde denetimleri yazı tipleri de güncelleştirir güvence altına alır. İletişim kutusu örneği alma işlemi başarısız olduğundan bu yöntem de formun oluşturucudan çağrılmalıdır `IUIService` ve `FontChanged` olay hiçbir zaman yangın. Takma `FontChanged` yeni yazı tipi iletişim kutusu zaten açık olsa bile dinamik olarak almak iletişim kutularını izin verir.  
  
### <a name="testing-the-environment-font"></a>Sınama ortamı yazı tipi  
 UI ortamı yazı tipi kullanarak ve boyutu ayarları uyar emin olmak için açın **Araçlar > Seçenekler > ortamı > yazı tiplerini ve renkleri** ve altında "Ortam yazı tipini" seçin "ayarlarını göster:" açılır menü.  
  
 ![Yazı tipleri ve renkler ayarları Araçları &gt; Seçenekleri iletişim kutusu](../../extensibility/ux-guidelines/media/0201-a_optionsfonts.png "0201 a_OptionsFonts")<br />Yazı tipleri ve renkler ayarları Araçları &gt; Seçenekleri iletişim kutusu
  
 Yazı tipi çok varsayılandan farklı bir değere ayarlayın. Belirgin hangi UI güncelleştirilmediği yapmak için Serif (gibi "kez yeni Latin") ile bir yazı tipi seçin ve çok büyük bir boyuta ayarlayın. Ardından ortamı uyar emin olmak için UI testi. Lisans iletişim kutusunu kullanarak örnek aşağıda verilmiştir:  
  
 ![Ortam yazı tipi uymaz UI metin örneği](../../extensibility/ux-guidelines/media/0201-b_wrongfontdialog.png "0201 b_WrongFontDialog")<br />Ortam yazı tipi uymaz UI metin örneği
  
 Bu durumda, "Kullanıcı bilgileri" ve "Ürün bilgilerini" yazı tipi uyarak değil. Bazı durumlarda bu açık tasarım seçiminin olabilir, ancak açık yazı tipi redline belirtimlerini bir parçası olarak belirtilmezse, bir hata olabilir.  
  
 Yazı tipi sıfırlamak için "kullan" altında Varsayılanlar **Araçlar > Seçenekler > ortamı > yazı tiplerini ve renkleri**.  
  
##  <a name="BKMK_TextStyle"></a>Metin stili  
 Metin stili yazı tipi boyutu, ağırlık ve büyük/küçük harf başvuruyor. Uygulama yönergeleri için bkz [ortam yazı tipi](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).  
  
### <a name="text-casing"></a>Metin büyük/küçük harf  
  
#### <a name="all-caps"></a>Tümü büyük harf  
 Tümü büyük harf başlığı veya Visual Studio'da etiketleri için kullanmayın.  
  
#### <a name="all-lowercase"></a>Tüm küçük  
 Başlığı veya Visual Studio'da etiketleri için tamamen küçük harfli kullanmayın.  
  
#### <a name="sentence-and-title-case"></a>Tümce ve başlık durumu  
 Visual Studio'da metin ilk harfler büyük veya duruma bağlı olarak belirli bir cümle kullanmanız gerekir.  
  
|Başlık durumu için kullanın:|Cümle için kullanın:|  
|-------------------------|----------------------------|  
|İletişim başlıkları|Etiketler|  
|Grup kutuları|Onay kutuları|  
|Menü öğeleri|Radyo düğmeleri|  
|Bağlam menüsü öğeleri|Liste kutusu öğeleri|  
|Düğmeleri|Durum çubukları|  
|Tablo etiketleri||  
|Sütun üstbilgileri||  
|Araç ipuçları||  
  
##### <a name="title-case"></a>İlk harfler büyük  
 Başlık, çoğu veya hepsi bir deyimi içinde sözcükleri ilk harfler büyük harf bir stil durumdur. Visual Studio'da ilk harfler büyük dahil olmak üzere birçok öğeleri için kullanılır:  
  
-   **Araç ipuçları.** Örnek: "Seçili öğeleri Önizleme"  
  
-   **Sütun üstbilgileri.** Örnek: "sistem yanıt"  
  
-   **Menü öğeleri.** Örnek: "Tümünü Kaydet"  
  
 İlk harfler büyük kullanırken, bu sözcükleri sağladığınızdan ne zaman ve ne zaman küçük harfli bırakın yönergeler verilmiştir:  
  
|Büyük harfe|Yorumlar ve örnekler|  
|---------------|---------------------------|  
|Tüm adlar||  
|Tüm fiiller|"Olan" ve "olması için" diğer biçimleri gibi|  
|Tüm zarflar|"Den" ve "," dahil|  
|Tüm sıfatları|"Bu" ve "," dahil|  
|Tüm zamirler|İyelik eki dahil olmak üzere "," de "Olduğu gibi" daraltmaya gelebildiği, "," ve fiili "değil"|  
|Bölümleri konuşma bağımsız olarak ilk ve son sözcükler||  
|Bir fiil deyimi parçası olan edatlar|"Tüm Windows kapatma" veya "sisteminin kapatılmasını"|  
|Bir kısaltma tüm harfini|HTML, XML, URL, IDE, RGB|  
|İkinci bir isim veya uygun gelen ise ya da eşit ağırlık sözcükleri varsa, bileşik bir sözcük word|Çapraz, önceden Microsoft yazılım okuma/yazma erişimi, çalışma zamanı|  
  
|Küçük|Örnekler|  
|---------------|--------------|  
|Başka bir konuşma parçası veya ilk word değiştirme participle ise, bileşik bir word ikinci sözcüğü|Take dışı nasıl yapılır konuları|  
|Bir başlık ilk Word'de olmadığı sürece, makaleler|bir,|  
|Koordinat bağlaç|ve, ancak, ne de, veya|  
|Dört veya daha az harf bir fiil deyimi dışında sözcüklü edatlar|içinde üzerine olarak için üst kısmındaki çıkış,|  
|"İçin" bir çizilmesinin bir ifade kullanıldığında|"Sabit Disk biçimine"|  
  
##### <a name="sentence-case"></a>Cümle  
 Cümle, yazma, yalnızca ilk sözcüğün cümle büyük harfle, tüm uygun isimleri ve gelebildiği birlikte standart büyük/küçük harf yöntemidir "Ediyorum." Genel olarak, cümle okumak özellikle olduğunda içerik bir makine tarafından çevrilir dünya çapında bir izleyici için daha kolay olur. Cümle için kullanın:  
  
1.  **Durum çubuğu iletileri.** Bu kısa basit ve yalnızca durum bilgisi sağlayın. Örnek: "proje dosyası yükleniyor"  
  
2.  **Diğer tüm kullanıcı Arabirimi öğeleri**dahil etiketleri, onay kutularını, radyo düğmeleri ve kutusu öğeleri listesi. Örnek: "tüm öğeler Select listesinde"  
  
### <a name="text-formatting"></a>Metni Biçimlendirme  
 Visual Studio 2013'te biçimlendirme varsayılan metin tarafından denetlenir [ortam yazı tipi](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont). Bu hizmet (tümleşik geliştirme ortamı) IDE genelinde tutarlı yazı tipi görünümünü sağlamaya yardımcı olur ve kullanıcılarınız için tutarlı bir deneyim sağlamak için kullanmalısınız.  
  
 Visual Studio yazı tipi hizmeti tarafından kullanılan varsayılan boyutu Windows'dan gelir ve 9 pt görünür.  
  
 Ortam yazı tipi için biçimlendirme uygulayabilirsiniz. Bu konu, nasıl ve nerede kapsar stiller kullanmak için. Uygulama bilgisi için başvurmak [ortam yazı tipi](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont).  
  
#### <a name="bold-text"></a>Kalın metin  
 Kalın metin için ayrılmış olmalıdır ve Visual Studio'da tutumlu kullanılır:  
  
-   Sihirbazlar soru etiketler  
  
-   Çözüm Gezgini'nde etkin proje belirleme  
  
-   Geçersiz kılınan değerlerde özellikleri araç penceresi  
  
-   Visual Basic Düzenleyicisi açılır listelerinde belirli olaylar  
  
-   Belge Anahattı web sayfaları için sunucu tarafından üretilen içeriği  
  
-   bölüm üstbilgileri karmaşık iletişim veya Tasarımcısı kullanıcı Arabirimi  
  
#### <a name="italics"></a>İtalik  
 Visual Studio italik veya kalın, italik metin kullanmaz.  
  
#### <a name="color"></a>Renk  
  
-   Mavi (gezinti ve komut verme) köprüler için ayrılmıştır ve yönlendirme için hiçbir zaman kullanılmalıdır.  
  
-   Daha büyük başlıkları (ortamı yazı tipi %155 x veya daha büyük), bu amaçlar için renkli:  
  
    -   İmza Visual Studio kullanıcı Arabirimi kenar sağlamak için  
  
    -   Belirli bir alana dikkat çekmek için  
  
    -   Standart koyu gri/siyah ortamı metin renkten Tahliye sunmak için  
  
-   Başlıkları renkte mevcut Visual Studio marka renkler, öncelikle ana mor #FF68217A faydalanın.  
  
-   Renk başlıklarında kullanırken uymalısınız [renk yönergeleri Windows](https://msdn.microsoft.com/en-us/library/dn742482.aspx)Karşıtlık oranını ve diğer erişilebilirlik konuları dahil olmak üzere.  
  
### <a name="font-size"></a>Yazı tipi boyutu  
 Visual Studio kullanıcı Arabirimi tasarımı daha fazla boşluk içeren daha açık bir görünüm sunar. Mümkünse, chrome ve başlık çubukları azaltılmış veya kaldırılan. Visual Studio'da bir gereksinim bilgileri yoğunluğu olmakla birlikte, tipografi önemli bir Vurgu daha açık satır aralığı ve yazı tipi boyutlarını ve ağırlıklarını çeşitlemesi ile devam eder.  
  
 Aşağıdaki tablolarda, tasarım ayrıntıları ve Visual Studio'da kullanılan ekran yazı tipleri için görsel örnekler içerir. Boyut ve Ağırlık Semilight veya görünümlerini kodlanmış ışık gibi bazı görüntü yazı tipi farklılıklar vardır.  
  
 Tüm görüntü yazı tipleri için uygulama kod parçacıkları bulunabilir [(ölçeklendirme/kalın) başvuru biçimlendirme](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_Formatting).  
  
#### <a name="375-environment-font--light"></a>%375 ortam yazı tipi + açık  
  
|||  
|-|-|  
|**Kullanım:** nadir. Benzersiz kullanıcı Arabirimi yalnızca markalı.<br /><br /> **Yapın:**<br /><br /> -Cümle kullanın<br />-Her zaman hafif kullanın<br /><br /> **Yapma:**<br /><br /> -Kullanım için kullanıcı Arabirimi imza kullanıcı Arabirimi başlangıç sayfası gibi dışında<br />-Kalın, italik veya Kalın İtalik<br />-Kullanım için gövde metni<br />-Aracı windows kullanma|**Gibi görünür:** 34 pt Segoe UI açık<br /><br /> **Görsel örnek:**<br /><br /> *Şu anda kullanılmıyor. Başlangıç sayfası içinde kullanılabilir.*|  
  
#### <a name="310-environment-font--light"></a>%310 ortam yazı tipi + açık  
  
|||  
|-|-|  
|**Kullanım:**<br /><br /> -Büyük başlığına imza iletişim kutuları<br />-Ana rapor başlığı<br /><br /> **Yapın:**<br /><br /> -Cümle kullanın<br />-Her zaman hafif kullanın<br /><br /> **Yapma:**<br /><br /> -Kullanım için kullanıcı Arabirimi imza kullanıcı Arabirimi başlangıç sayfası gibi dışında<br />-Kalın, italik veya Kalın İtalik<br />-Kullanım için gövde metni<br />-Aracı windows kullanma|**Gibi görünür:** 28 pt Segoe UI açık<br /><br /> **Görsel örnek:**<br /><br /> ![%310 ortam yazı tipi &#43;örneği; Hafif başlık](../../extensibility/ux-guidelines/media/0202-a_ef310.png "0202 a_EF310")|  
  
#### <a name="200-environment-font--semilight"></a>% 200 ortamı yazı tipi + Semilight  
  
|||  
|-|-|  
|**Kullanım:**<br /><br /> -Başlıklar<br />-Başlıkları küçük ve orta ölçekli iletişim kutuları<br /><br /> **Yapın:**<br /><br /> -Cümle kullanın<br />-Her zaman Semilight ağırlık kullanın<br /><br /> **Yapma:**<br /><br /> -Kalın, italik veya Kalın İtalik<br />-Kullanım için gövde metni<br />-Aracı windows kullanma|**Gibi görünür:** 18 pt Segoe UI Semillight<br /><br /> **Görsel örnek:**<br /><br /> ![% 200 ortamı yazı tipi &#43;örneği; Semilight](../../extensibility/ux-guidelines/media/0202-b_ef200.png "0202 b_EF200")|  
  
#### <a name="155-environment-font"></a>%155 ortam yazı tipi  
  
|||  
|-|-|  
|**Kullanım:**<br /><br /> -Belgedeki bölüm başlıkları yanı sıra kullanıcı Arabirimi<br />-Raporları<br /><br /> **:** Cümle kullanın<br /><br /> **Yapma:**<br /><br /> -Kalın, italik veya Kalın İtalik<br />-Kullanım için gövde metni<br />-Standart Visual Studio denetimleri kullanın<br />-Aracı windows kullanma|**Gibi görünür:** 14 pt Segoe UI<br /><br /> **Görsel örnek:**<br /><br /> ![Örnek %155 ortam yazı tipi başlığının](../../extensibility/ux-guidelines/media/0202-c_ef155.png "0202 c_EF155")|  
  
#### <a name="133-environment-font"></a>% 133 ortamı yazı tipi  
  
|||  
|-|-|  
|**Kullanım:**<br /><br /> -Daha küçük alt başlıklar, imza iletişim kutuları<br />-Belgedeki küçük başlıkları yanı sıra kullanıcı Arabirimi<br /><br /> **:** Cümle kullanın<br /><br /> **Yapma:**<br /><br /> -Kalın, italik veya Kalın İtalik<br />-Kullanım için gövde metni<br />-Standart Visual Studio denetimleri kullanın<br />-Aracı windows kullanma|**Gibi görünür:** 12 pt Segoe UI<br /><br /> **Görsel örnek:**<br /><br /> ![% 133 ortamı yazı tipi başlık örneği](../../extensibility/ux-guidelines/media/0202-d_ef133.png "0202 d_EF133")|  
  
#### <a name="122-environment-font"></a>%122 ortam yazı tipi  
  
|||  
|-|-|  
|**Kullanım:**<br /><br /> -SECTION başlıklarında imza iletişim kutuları<br />-Ağaç görünümünde üst düğümleri<br />-Dikey sekme gezinme<br /><br /> **:** Cümle kullanın<br /><br /> **Yapma:**<br /><br /> -Kalın, italik veya Kalın İtalik<br />-Kullanım için gövde metni<br />-Standart Visual Studio denetimleri kullanın<br />-Aracı windows kullanma|**Gibi görünür:** 11 pt Segoe UI<br /><br /> **Görsel örnek:**<br /><br /> ![Örnek %122 ortam yazı tipi başlığının](../../extensibility/ux-guidelines/media/0202-e_ef122.png "0202 e_EF122")|  
  
#### <a name="environment-font--bold"></a>Ortam yazı tipi + kalın  
  
|||  
|-|-|  
|**Kullanım:**<br /><br /> -Etiketler ve imza iletişim kutuları, alt başlıklar<br />-Etiketler ve raporlarda alt başlıklar<br />-Etiketler ve alt başlıklar belgedeki yanı sıra kullanıcı Arabirimi<br /><br /> **Yapın:**<br /><br /> -Cümle kullanın<br />-Kalın ağırlık kullanın<br /><br /> **Yapma:**<br /><br /> -İtalik veya Kalın İtalik<br />-Kullanım için gövde metni<br />-Standart Visual Studio denetimleri kullanın<br />-Aracı windows kullanma|**Gibi görünür:** kalın 9 pt Segoe UI<br /><br /> **Görsel örnek:**<br /><br /> ![Ortam yazı tipi &#43;örneği; Kalın başlık](../../extensibility/ux-guidelines/media/0202-f_efb.png "0202 f_EFB")|  
  
#### <a name="environment-font"></a>Ortam yazı tipi  
  
|||  
|-|-|  
|**Kullanım:** diğer tüm metni<br /><br /> **:** Cümle kullanın<br /><br /> **Yok:** italik veya Kalın İtalik|**Gibi görünür:** 9 pt Segoe UI<br /><br /> **Görsel örnek:**<br /><br /> ![Ortam yazı tipi örneği](../../extensibility/ux-guidelines/media/0202-g_ef.png "0202 g_EF")|  
  
### <a name="padding-and-spacing"></a>Doldurma ve aralığı  
 Başlıkları bunları uygun Vurgu vermek için geçici alan gerektirir. Bu alanı punto boyutunu ve başka başlığı yatay bir kural veya ortam yazı tipi metin satırının gibi yakın nedir bağlı olarak değişir.  
  
-   Tek başına bir başlık için ideal doldurma büyük harf karakter yükseklik alanı % 90'ını olmalıdır. Örneğin, 26 pt cap yüksekliği 28 pt Segoe UI ışık başlığı var ve doldurma yaklaşık 23 pt ya da yaklaşık 31 piksel olması gerekir.  
  
-   Başlık geçici en düşük alan % 50'sini büyük harf karakter yüksekliğini olmalıdır. Daha az alan, bir başlığı bir kural veya diğer sıkı sığdırma öğesi tarafından eşlik olduğunda kullanılabilir.  
  
-   Kalın ortamı yazı tipi metin varsayılan satır yüksekliği boşlukları ve doldurma izlemelisiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSDN: Yazı tiplerini (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742483\(v=vs.85\).aspx)   
 [MSDN: Kullanıcı arabirimi metin (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx)