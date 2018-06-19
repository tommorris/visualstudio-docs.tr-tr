---
title: Görüntü hizmet ve Katalog | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 34990c37-ae98-4140-9b1e-a91c192220d9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d9b393d9dcf732d9042338dc0786d824351deca3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134682"
---
# <a name="image-service-and-catalog"></a>Yansıma hizmeti ve Katalog
Bu kılavuzu yönerge ve Visual Studio Görüntü hizmeti ve görüntü Visual Studio 2015'te tanıtılan Kataloğu'nu benimseme için en iyi yöntemler içerir.  
  
 Visual Studio 2015'te tanıtılan Görüntü hizmeti, geliştiricilerin cihaz ve bunlar görüntülenir bağlamı için doğru Tema oluşturma dahil olmak üzere bu görüntüyü görüntülemek için seçilen tema kullanıcı için en iyi görüntüleri alma olanak sağlar. Görüntü hizmeti benimsenmesi varlık bakım, HDPI ölçekleme ve Tema oluşturma ile ilgili önemli sorun teşkil edecek noktalar ortadan kaldırmanıza yardımcı olur.  
  
|||  
|-|-|  
|**Bugün sorunları**|**Çözümler**|  
|Arka plan rengi karıştırma|Yerleşik alfa karıştırma|  
|Tema (bazı) görüntüleri|Tema meta verileri|  
|Yüksek karşıtlıklı modu|Diğer yüksek karşıtlık kaynakları|  
|Farklı DPI modu birden fazla kaynak gerekiyor|Vektör tabanlı geri dönüş seçilebilir kaynaklarla|  
|Yinelenen görüntüleri|Görüntü kavram başına bir tanımlayıcı|  
  
 Görüntü hizmeti neden benimsemeyi?  
  
-   Her zaman en son "mükemmel piksel" görüntüsünü Visual Studio'dan Al  
  
-   Gönderme ve kendi görüntünüzü kullanma  
  
-   Windows yeni DPI ölçeklendirme eklediğinde çıkışı görüntülerinizi test gerek yoktur  
  
-   Eski mimari zorluklardan, uygulamalarında adres  
  
 Visual Studio Kabuğu araç önce ve sonra görüntüyü hizmetini kullanarak:  
  
 ![Görüntü önce ve sonra hizmeti](../extensibility/media/image-service-before-and-after.png "önce ve sonra görüntü hizmeti")  
  
## <a name="how-it-works"></a>Nasıl çalışır?  
 Yansıma hizmeti için desteklenen tüm UI çerçevesi uygun bir eşlemli görüntü sağlayabilir:  
  
-   WPF: BitmapSource  
  
-   WinForms: System.Drawing.Bitmap  
  
-   Win32: HBITMAP  
  
 Yansıma hizmeti Akış Diyagramı  
  
 ![Görüntü hizmet Akış Diyagramı](../extensibility/media/image-service-flow-diagram.png "görüntü hizmet Akış Diyagramı")  
  
 **Görüntü adlar**  
  
 Bir görüntü bilinen ad (veya kısaca takma ad) bir görüntü varlığı veya görüntü listesi varlık Resim Kitaplığı'ndaki benzersiz olarak tanımlayan bir GUID/kimliği çiftidir.  
  
 **Bilinen adlar**  
  
 Visual Studio Görüntü Kataloğu ve tüketilebilir genel olarak herhangi bir Visual Studio bileşeni veya uzantısı tarafından bulunan görüntü adlar kümesi.  
  
 **Görüntü bildirim dosyaları**  
  
 Görüntü bildirimi (.imagemanifest) dosyaları görüntü varlıklar, bu varlıkları ve gerçek görüntü ya da her varlık temsil görüntüleri temsil adlar kümesini tanımlayan XML dosyalarıdır. Eski kullanıcı Arabirimi desteği görüntü listeleri veya görüntü bildirimleri tek başına görüntüleri tanımlayabilirsiniz. Ayrıca, varlık veya ayrı ayrı görüntülere her varlık arkasında olduğunda ve bu varlıkları nasıl görüntülendiğini değiştirmek için ayarlanabilen özniteliği vardır.  
  
 **Görüntü bildirim şeması**  
  
 Bir tam görüntü bildirimi şöyle görünür:  
  
```xml  
<ImageManifest>  
      <!-- zero or one Symbols elements -->  
      <Symbols>  
        <!-- zero or more Import, Guid, ID, or String elements -->  
      </Symbols>  
      <!-- zero or one Images elements -->  
      <Images>  
        <!-- zero or more Image elements -->  
      </Images>  
      <!-- zero or one ImageLists elements -->  
      <ImageLists>  
        <!-- zero or more ImageList elements -->  
      </ImageLists>  
</ImageManifest>  
```  
  
 **Semboller**  
  
 Okunabilirlik ve bakıma yardımcı olmak gibi görüntü bildirimi sembolleri öznitelik değerleri kullanabilirsiniz. Simgeler şu şekilde tanımlanır:  
  
```xml  
<Symbols>  
      <Import Manifest="manifest" />  
      <Guid Name="ShellCommandGuid" Value="8ee4f65d-bab4-4cde-b8e7-ac412abbda8a" />  
      <ID Name="cmdidSaveAll" Value="1000" />  
      <String Name="AssemblyName" Value="Microsoft.VisualStudio.Shell.UI.Internal" />  
</Symbols>  
```  
  
|||  
|-|-|  
|**Alt öğe**|**Tanım**|  
|{1&gt;İçeri Aktar&lt;1}|Geçerli bildirimi kullanmak için belirtilen bildirim dosyası simgelerini alır|  
|Guid|Simgenin bir GUID temsil eder ve GUID biçimlendirme eşleşmelidir|  
|Kimlik|Simgenin bir Kimliğini temsil eder ve negatif olmayan bir tamsayı olmalıdır|  
|Dize|Simgenin bir isteğe bağlı bir dize değeri temsil eder|  
  
 Büyük küçük harfe duyarlı ve başvurulan $(symbol-name) sözdizimini kullanarak simgeler şunlardır:  
  
```xml  
<Image Guid="$(ShellCommandGuid)" ID="$(cmdidSaveAll)" >  
      <Source Uri="/$(AssemblyName);Component/Resources/image.xaml" />  
</Image>  
```  
  
 Bazı simgeleri tüm bildirimler için önceden tanımlanmıştır. Bu URI özniteliğinde kullanılabilir \<kaynak > veya \<alma > öğesi başvurusu yollara yerel makine üzerinde.  
  
|||  
|-|-|  
|**Simgesi**|**Açıklama**|  
|CommonProgramFiles|% CommonProgramFiles % ortam değişkeninin değeri|  
|LocalAppData|% LocalAppData % ortam değişkeninin değeri|  
|ManifestFolder|Bildirim dosyasını içeren klasör|  
|MyDocuments|Geçerli kullanıcının Belgelerim klasörün tam yolunu|  
|ProgramFiles|% ProgramFiles % ortam değişkeni değeri|  
|Sistem|Windows\System32 klasöründe|  
|WinDir|% WinDir % ortam değişkeni değeri|  
  
 **Görüntü**  
  
 \<Görüntü > öğesi bir bilinen ad tarafından başvurulan bir görüntü tanımlar. Birlikte ele alındığında kimliği ve GUID görüntü ad oluşturur. Görüntü için ad tüm görüntü kitaplığı arasında benzersiz olması gerekir. Bir verilen ad birden çok görüntü varsa, kitaplık derlenirken hatalarla karşılaşıldı birinci tutulur adrestir.  
  
 En az bir kaynak içermelidir. Boyutu Tarafsız kaynakları çok çeşitli boyutlarda arasında en iyi sonuçlar verir, ancak bunlar gerekli değildir. Hizmet tanımlı olmayan bir boyutu görüntüsü için sorulan varsa \<Görüntü > öğesi ve boyutu Tarafsız kaynağı yok, hizmet en iyi boyutu özgü kaynağını seçin ve istenen boyuta ölçeklendirin.  
  
```xml  
<Image Guid="guid" ID="int" AllowColorInversion="true/false">  
      <Source ... />  
      <!-- optional additional Source elements -->  
</Image>  
```  
  
|||  
|-|-|  
|**Özniteliği**|**Tanım**|  
|Guid|[Gerekli] Görüntü ad GUID bölümünü|  
|Kimlik|[Gerekli] Görüntü ad kimliği bölümünü|  
|AllowColorInversion|[İsteğe bağlı, varsayılan true] Görüntünün koyu bir arka plan üzerinde kullanıldığında program aracılığıyla ters renklerini sahip olup olamayacağını gösterir.|  
  
 **Kaynak**  
  
 \<Kaynak > öğesi (XAML ve PNG) tek bir görüntü kaynağı varlık tanımlar.  
  
```xml  
<Source Uri="uri" Background="background">  
      <!-- optional NativeResource element -->  
 </Source>  
```  
  
|||  
|-|-|  
|**Özniteliği**|**Tanım**|  
|URI|[Gerekli] Gelen görüntünün nerede yüklenebilir tanımlayan bir URI. Aşağıdakilerden biri olabilir:<br /><br /> -A [Pack URI](http://msdn.microsoft.com/en-US/library/aa970069\(v=vs.100\).aspx) uygulamasını kullanarak: / / / yetkilisi<br />-Bir mutlak bileşen kaynak başvurusu<br />-Yerel kaynak içeren bir dosya yolu|  
|Arka Plan|[İsteğe bağlı] Ne tür bir arka plan kaynak kullanılması amaçlanmıştır gösterir.<br /><br /> Aşağıdakilerden biri olabilir:<br /><br /> *Açık:* kaynağı açık bir arka plan üzerinde kullanılabilir.<br /><br /> *Koyu:* kaynağı koyu bir arka plan üzerinde kullanılabilir.<br /><br /> *Yüksek Karşıtlık:* kaynağı yüksek karşıtlık modunda herhangi bir arka plan üzerinde kullanılabilir.<br /><br /> *HighContrastLight:* kaynak açık bir arka plan yüksek karşıtlık modunda kullanılabilir.<br /><br /> *HighContrastDark:* kaynağı yüksek karşıtlık modunda koyu arka plan üzerinde kullanılabilir.<br /><br /> Arka plan özniteliği belirtilmezse, kaynağı herhangi bir arka plan üzerine kullanılabilir.<br /><br /> Arka plan ise *açık*, *koyu*, *HighContrastLight*, veya *HighContrastDark*, hiçbir zaman kaynağının renkleri ters. Arka plan atlanmış veya kümesine *Yüksek Karşıtlık*, kaynağın renkleri ters çevirmeyi görüntünün tarafından denetlenen **AllowColorInversion** özniteliği.|  
|||  
  
 A \<kaynak > öğesi aşağıdaki isteğe bağlı alt öğeleri tam olarak birine sahip olabilir:  
  
||||  
|-|-|-|  
|**Öğesi**|**Öznitelikler (tüm gerekli)**|**Tanım**|  
|\<Boyutu >|Değer|Kaynak görüntüleri verilen boyutta (aygıt birimleri) için kullanılır. Görüntü kare olur.|  
|\<SizeRange >|MinSize, MaxSize|Kaynak görüntülerden MinSize MaxSize (birimlerindeki aygıt) için ikisi de dahil olmak kullanılır. Görüntü kare olur.|  
|\<Boyutlar >|Genişlik, yükseklik|Kaynak belirtilen genişlik ve yükseklik (aygıt birimleri), görüntüleri için kullanılır.|  
|\<DimensionRange >|Değeri, MinHeight MinWidth,<br /><br /> MaxWidth, MaxHeight|Kaynak için en küçük genişliği/yüksekliğinin görüntülere (aygıt birimlerindeki) en büyük genişliği/yüksekliğinin ikisi de dahil olmak kullanılır.|  
  
 A \<kaynak > öğesi de isteğe bağlı bir olabilir \<NativeResource > tanımlar alt öğe bir \<kaynak > yönetilen bir derleme yerine yerel bir derleme yüklenir.  
  
```xml  
<NativeResource Type="type" ID="int" />  
```  
  
|||  
|-|-|  
|**Özniteliği**|**Tanım**|  
|Tür|[Gerekli] XAML veya PNG yerel kaynak türü|  
|Kimlik|[Gerekli] Yerel kaynak tamsayı kimliği bölümünü|  
  
 **ImageList**  
  
 \<ImageList > öğesi içinde tek bir Şerit döndürülebilecek görüntüleri koleksiyonunu tanımlar. Şerit isteğe bağlı olarak, gerektiği gibi yerleşik olarak bulunur.  
  
```xml  
<ImageList>  
      <ContainedImage Guid="guid" ID="int" External="true/false" />  
      <!-- optional additional ContainedImage elements -->  
 </ImageList>  
```  
  
|||  
|-|-|  
|**Özniteliği**|**Tanım**|  
|Guid|[Gerekli] Görüntü ad GUID bölümünü|  
|Kimlik|[Gerekli] Görüntü ad kimliği bölümünü|  
|Harici|[İsteğe bağlı, varsayılan false] Görüntü ad görüntüyü geçerli bildiriminde başvuruda bulunup bulunmadığını gösterir.|  
  
 Kapsanan görüntüsü için ad, geçerli bildiriminde tanımlanan bir görüntü başvurmak yok. Kapsanan görüntünün görüntü kitaplığı'nda bulunamazsa boş yer tutucu görüntüsü onun yerine kullanılır.  
  
## <a name="using-the-image-service"></a>Görüntü hizmeti kullanma  
  
### <a name="first-steps-managed"></a>İlk adımlar (yönetilen)  
 Görüntü hizmetini kullanmak için bazıları veya tümü aşağıdaki derlemeler başvuruları projenize eklemeniz gerekir:  
  
-   **Microsoft.VisualStudio.ImageCatalog.dll**  
  
    -   Yerleşik Görüntü Kataloğu KnownMonikers kullanıyorsanız gereklidir  
  
-   **Microsoft.VisualStudio.Imaging.dll**  
  
    -   Kullanırsanız, gerekli **CrispImage** ve **ImageThemingUtilities** WPF kullanıcı arabiriminde  
  
-   **Microsoft.VisualStudio.Imaging.Interop.14.0.DesignTime.dll**  
  
    -   Kullanırsanız, gerekli **ImageMoniker** ve **ImageAttributes** türleri  
  
    -   **EmbedInteropTypes** ayarlanmalıdır true  
  
-   **Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime**  
  
    -   Kullanırsanız, gerekli **IVsImageService2** türü  
  
    -   **EmbedInteropTypes** ayarlanmalıdır true  
  
-   **Microsoft.VisualStudio.Utilities.dll**  
  
    -   Kullanırsanız, gerekli **BrushToColorConverter** ImageThemingUtilities için. **ImageBackgroundColor** WPF kullanıcı arabiriminde  
  
-   **Microsoft.VisualStudio.Shell. \<VSVersion >.0**  
  
    -   Kullanırsanız, gerekli **IVsUIObject** türü  
  
-   **Microsoft.VisualStudio.Shell.Interop.10.0.dll**  
  
    -   WinForms ilgili UI Yardımcıları kullanıyorsanız gereklidir  
  
    -   **EmbedInteropTypes** ayarlanmalıdır true  
  
### <a name="first-steps-native"></a>İlk adımlar (yerel)  
 Görüntü hizmetini kullanmak için bazılarını veya tümünü aşağıdaki üst bilgiler projenize eklemeniz gerekir:  
  
-   **KnownImageIds.h**  
  
    -   Yerleşik Görüntü Kataloğu kullanıyorsanız gereklidir **KnownMonikers**, ancak kullanamazsınız **ImageMoniker** zaman gelen döndürme değerleri gibi türü **IVsHierarchy GetGuidProperty**veya **GetProperty** çağrıları.  
  
-   **KnownMonikers.h**  
  
    -   Yerleşik Görüntü Kataloğu kullanıyorsanız gereklidir **KnownMonikers**.  
  
-   **ImageParameters140.h**  
  
    -   Kullanırsanız, gerekli **ImageMoniker** ve **ImageAttributes** türleri.  
  
-   **VSShell140.h**  
  
    -   Kullanırsanız, gerekli **IVsImageService2** türü.  
  
-   **ImageThemingUtilities.h**  
  
    -   Tema oluşturma sizin için yapar Görüntü hizmeti izin sorunu yaşıyor gereklidir.  
  
    -   Bu üst Görüntü hizmeti görüntü Tema oluşturma işleyebiliyorsa kullanmayın.  
  
-   **VSUIDPIHelper.h**  
  
    -   Geçerli DPI almak için DPI Yardımcıları kullanıyorsanız gereklidir.  
  
## <a name="how-do-i-write-new-wpf-ui"></a>Yeni WPF UI nasıl yazma?  
  
1.  Yukarıdaki gerekli derleme başvurularını ekleyerek başlangıç ilk adımlar bölümüne projenize. Bunların tümünün eklemek, bu nedenle yalnızca gereksinim duyduğunuz başvurular eklemek gerekmez. (Not: kullanıyorsanız veya erişimi **renkleri** yerine **Fırçalar**, başvuru atlayabilirsiniz sonra **yardımcı programları**, bu yana dönüştürücü gerekmez.)  
  
2.  İstediğiniz görüntüyü seçin ve takma adı alın. Kullanan bir **KnownMoniker**, veya kendi özel görüntülerinizi ve adları varsa, kendi kullanın.  
  
3.  Ekleme **CrispImages** XAML için. (Örneğe bakın.)  
  
4.  Ayarlama **ImageThemingUtilities.ImageBackgroundColor** UI hiyerarşinizdeki özelliği. (Bu burada arka plan rengini bilinir, açık olmayan mutlaka konumda ayarlanmalıdır **CrispImage**.) (Örneğe bakın.)  
  
```xaml  
<Window  
  x:Class="WpfApplication.MainWindow"  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:imaging="clr-namespace:Microsoft.VisualStudio.Imaging;assembly=Microsoft.VisualStudio.Imaging"  
  xmlns:theming="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Imaging"  
  xmlns:utilities="clr-namespace:Microsoft.Internal.VisualStudio.Imaging;assembly=Microsoft.VisualStudio.Imaging"  
  xmlns:catalog="clr-namespace:Microsoft.VisualStudio.Imaging;assembly=Microsoft.VisualStudio.ImageCatalog"  
  Title="MainWindow" Height="350" Width="525" UseLayoutRounding="True">  
  <Window.Resources>  
    <utilities:BrushToColorConverter x:Key="BrushToColorConverter"/>  
  </Window.Resources>  
  <StackPanel Background="White" VerticalAlignment="Center"   
    theming:ImageThemingUtilities.ImageBackgroundColor="{Binding Background, RelativeSource={RelativeSource Self}, Converter={StaticResource BrushToColorConverter}}">  
    <imaging:CrispImage Width="16" Height="16" Moniker="{x:Static catalog:KnownMonikers.MoveUp}" />  
  </StackPanel>  
</Window>  
```  
  
 **Varolan WPF UI nasıl güncelleştiririm?**  
  
 Varolan WPF UI güncelleştirme üç temel adımdan oluşan oldukça basit bir işlemdir:  
  
1.  Tüm değiştirmek \<Görüntü > ile UI öğelerini \<CrispImage > öğeleri  
  
2.  Tüm kaynak özniteliklerini AD özniteliklerini değiştirme  
  
    -   Görüntü hiçbir zaman değiştirse ve kullanmakta olduğunuz **KnownMonikers**, bu özelliği statik olarak Bağla **KnownMoniker**. (Yukarıdaki örnekte bkz.)  
  
    -   Görüntü hiçbir zaman değişir ve kendi özel görüntünüzü kullanıyorsanız, statik olarak kendi ad bağlayın.  
  
    -   Resmi değiştirebilirsiniz, ad özniteliği özelliği değişiklikleri bildiren bir kod özelliği bağlar.  
  
3.  UI hiyerarşideki herhangi bir yerde ayarlamak **ImageThemingUtilities.ImageBackgroundColor** emin renkleri ters çevirmeyi yapmak için düzgün şekilde çalışır.  
  
    -   Bu kullanımını gerektirebilir **BrushToColorConverter** sınıfı. (Yukarıdaki örnekte bkz.)  
  
## <a name="how-do-i-update-win32-ui"></a>Win32 UI nasıl güncelleştiririm?  
 Aşağıdaki uygun yerlerde ham yükleme görüntülerinin değiştirmek kodunuzu ekleyin. Gerektiğinde HBITMAPs HICONs HIMAGELIST karşı karşı döndürmek için değerleri geçin.  
  
 **Yansıma hizmeti Al**  
  
```cpp  
CComPtr<IVsImageService2> spImgSvc;  
CGlobalServiceProvider::HrQueryService(SID_SVsImageService, &spImgSvc);  
```  
  
 **Görüntü isteme**  
  
```cpp  
ImageAttributes attr = { 0 };  
attr.StructSize      = sizeof(attributes);  
attr.Format          = DF_Win32;  
// IT_Bitmap for HBITMAP, IT_Icon for HICON, IT_ImageList for HIMAGELIST  
attr.ImageType       = IT_Bitmap;  
attr.LogicalWidth    = 16;  
attr.LogicalHeight   = 16;  
attr.Dpi             = VsUI::DpiHelper::GetDeviceDpiX();  
attr.Background      = 0xFFFFFFFF;  
// Desired RGBA color, if you don't use this, don't set IAF_Background below  
attr.Flags           = IAF_RequiredFlags | IAF_Background;  
  
CComPtr<IVsUIObject> spImg;  
// Replace this KnownMoniker with your desired ImageMoniker  
spImgSvc->GetImage(KnownMonikers::Blank, attributes, &spImg);  
  
```  
  
## <a name="how-do-i-update-winforms-ui"></a>WinForms UI nasıl güncelleştiririm?  
 Aşağıdaki uygun yerlerde ham yükleme görüntülerinin değiştirmek kodunuzu ekleyin. Bit eşlemler simgeler karşı gerektiğinde döndürmek için değerleri geçin.  
  
 **Using deyimi yararlı**  
  
```csharp  
using GelUtilities = Microsoft.Internal.VisualStudio.PlatformUI.Utilities;  
```  
  
 **Yansıma hizmeti Al**  
  
```csharp  
// This or your preferred way of querying for Visual Studio services  
IVsImageService2 imageService = (IVsImageService2)Package.GetGlobalService(typeof(SVsImageService));  
  
```  
  
 **İstek resmi**  
  
```csharp  
ImageAttributes attributes = new ImageAttributes  
{  
    StructSize    = Marshal.SizeOf(typeof(ImageAttributes)),  
    // IT_Bitmap for Bitmap, IT_Icon for Icon  
    ImageType     = (uint)_UIImageType.IT_Bitmap,  
    Format        = (uint)_UIDataFormat.DF_WinForms,  
    LogicalWidth  = 16,  
    LogicalHeight = 16,  
    // Desired RGBA color, if you don't use this, don't set IAF_Background below  
    Background    = 0xFFFFFFFF,  
    Flags = (uint)_ImageAttributesFlags.IAF_RequiredFlags | _ImageAttributesFlags.IAF_Background,  
};  
  
// Replace this KnownMoniker with your desired ImageMoniker  
IVsUIObject uIObj = imageService.GetImage(KnownMonikers.Blank, attributes);  
  
Bitmap bitmap = (Bitmap)GelUtilities.GetObjectData(uiObj); // Use this if you need a bitmap  
// Icon icon = (Icon)GelUtilities.GetObjectData(uiObj); // Use this if you need an icon  
  
```  
  
## <a name="how-do-i-use-image-monikers-in-a-new-tool-window"></a>Yeni bir aracı penceresi nasıl görüntü adlar kullanıyor?  
 VSIX paketi proje şablonu, Visual Studio 2015 için güncelleştirilmiştir. Yeni bir araç penceresi oluşturmak için VSIX projeye sağ tıklayın ve "Yeni öğe... Ekle" seçin (Ctrl + Shift + A). Proje dili için genişletilebilirlik düğümü altında "Özel araç penceresi," seçmek araç penceresi bir ad verin ve "Ekle" düğmesine basın.  
  
 Bu araç penceresinde adlar kullanmak için anahtar yerlerdir. Her biri için yönergeleri izleyin:  
  
1.  Sekmeleri küçük aldığınızda araç penceresi sekmesine yeterli (Ctrl + sekme pencere değiştirici da kullanılır).  
  
     Öğesinden türetilen sınıf oluşturucusu bu satırı ekleyin **ToolWindowPane** türü:  
  
    ```csharp  
    // Replace this KnownMoniker with your desired ImageMoniker  
    this.BitmapImageMoniker = KnownMonikers.Blank;  
    ```  
  
2.  Araç penceresi açmak için komutu.  
  
     Paket .vsct dosyasında aracı pencerenin komut düğmesi düzenleyin:  
  
    ```xml  
    <Button guid="guidPackageCmdSet" id="CommandId" priority="0x0100" type="Button">  
      <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
      <!-- Replace this KnownMoniker with your desired ImageMoniker -->  
      <Icon guid="ImageCatalogGuid" id="Blank" />  
      <!-- Add this -->  
      <CommandFlag>IconIsMoniker</CommandFlag>  
      <Strings>  
        <ButtonText>MyToolWindow</ButtonText>  
      </Strings>  
    </Button>  
    ```  
  
 **Var olan bir araç penceresinde nasıl görüntü adlar kullanıyor?**  
  
 Görüntü adlar kullanmak için var olan bir araç penceresi güncelleştirme yeni bir araç penceresi oluşturma adımları benzerdir.  
  
 Bu araç penceresinde adlar kullanmak için anahtar yerlerdir. Her biri için yönergeleri izleyin:  
  
1.  Sekmeleri küçük aldığınızda araç penceresi sekmesine yeterli (Ctrl + sekme pencere değiştirici da kullanılır).  
  
    1.  (Varsa) bu satırları türeyen sınıf oluşturucusu kaldırmak **ToolWindowPane** türü:  
  
        ```csharp  
        this.BitmapResourceID = <Value>;  
        this.BitmapIndex = <Value>;  
        ```  
  
    2.  #1. adımını bkz "Nasıl yedeklerim kullanım görüntü adlar yeni bir aracı pencerede?" Yukarıdaki bölümde.  
  
2.  Araç penceresi açmak için komutu.  
  
    -   #2. adımını bkz "Nasıl yedeklerim kullanım görüntü adlar yeni bir aracı pencerede?" Yukarıdaki bölümde.  
  
## <a name="how-do-i-use-image-monikers-in-a-vsct-file"></a>.Vsct dosyasında nasıl görüntü adlar kullanıyor?  
 .Vsct dosyanızı aşağıdaki açıklamalı satırları tarafından belirtildiği şekilde güncelleştirin:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <!--  Include the definitions for images included in the VS image catalog -->  
  <Include href="KnownImageIds.vsct"/>  
  <Commands package="guidMyPackage">  
    <Buttons>  
      <Button guid="guidMyCommandSet" id="cmdidMyCommand" priority="0x0000" type="Button">  
        <!-- Add an Icon element, changing the attributes to match the image moniker you want to use.  
             In this case, we're using the Guid for the VS image catalog.  
             Change the id attribute to be the ID of the desired image moniker. -->  
        <Icon guid="ImageCatalogGuid" id="OpenFolder" />  
        <CommandFlag>DynamicVisibility</CommandFlag>  
        <CommandFlag>DefaultInvisible</CommandFlag>  
        <CommandFlag>DefaultDisabled</CommandFlag>  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>IconAndText</CommandFlag>  
        <!-- Add the IconIsMoniker CommandFlag -->  
        <CommandFlag>IconIsMoniker</CommandFlag>  
        <Strings>  
          <ButtonText>Quick Fixes...</ButtonText>  
          <CommandName>Show Quick Fixes</CommandName>  
          <CanonicalName>ShowQuickFixes</CanonicalName>  
          <LocCanonicalName>ShowQuickFixes</LocCanonicalName>  
        </Strings>  
      </Button>  
    </Buttons>  
  </Commands>  
  <!-- It is recommended that you remove <Bitmap> elements that are no longer used in the vsct file -->  
  <Symbols>  
    <GuidSymbol name="guidMyPackage"    value="{1491e936-6ffe-474e-8371-30e5920d8fdd}" />  
    <GuidSymbol name="guidMyCommandSet" value="{10347de4-69a9-47f4-a950-d3301f6d2bc7}">  
      <IDSymbol name="cmdidMyCommand" value="0x9437" />  
    </GuidSymbol>  
  </Symbols>  
</CommandTable>  
```  
  
 **Ne my .vsct dosya Ayrıca, Visual Studio'nun daha eski sürümleri tarafından okunması gerekir?**  
  
 Visual Studio'nun daha eski sürümleri tarafından tanınmayan **IconIsMoniker** bayrağı komutu. Görüntü hizmeti görüntülerden destekliyorsa, ancak Visual Studio'nun daha eski sürümleri eski Tarz görüntüleri kullanmaya devam Visual Studio sürümlerinde kullanabilirsiniz. Bunu yapmak için .vsct dosya değişmeden (ve bu nedenle, Visual Studio'nun daha eski sürümleri ile uyumlu) bırakın ve bir .vsct dosyasının tanımlanan GUID/kimliği çiftleri eşleyen CSV (virgülle ayrılmış değerler) dosyası oluşturun \<bit eşlemler > görüntüsüne öğesi ad GUID/kimliği çiftleri.  
  
 Eşleme CSV dosya biçimi şöyledir:  
  
```  
Icon guid, Icon id, Moniker guid, Moniker id  
b714fcf7-855e-4e4c-802a-1fd87144ccad,1,fda30684-682d-421c-8be4-650a2967058e,100  
b714fcf7-855e-4e4c-802a-1fd87144ccad,2,fda30684-682d-421c-8be4-650a2967058e,200  
```  
  
 CSV dosyasını paket ile dağıtılır ve konumuna tarafından belirtilen **IconMappingFilename** özelliği **ProvideMenuResource** paket özniteliği:  
  
```csharp  
[ProvideMenuResource("MyPackage.ctmenu", 1, IconMappingFilename="IconMappings.csv")]  
```  
  
 **IconMappingFilename** göreli bir yol örtük olarak kökü $PackageFolder $ (örneğin, yukarıdaki örnek) veya mutlak bir yol açıkça kökü @"%UserProfile%\ gibi bir ortam değişkeni tarafından tanımlanan bir dizin dir1\dir2\MyMappingFile.csv".  
  
## <a name="how-do-i-port-a-project-system"></a>Proje sistemi nasıl bağlantı noktası?  
 **Proje için ImageMonikers sağlamak nasıl**  
  
1.  Uygulama **VSHPROPID_SupportsIconMonikers** projenin üzerinde **IVsHierarchy**ve true döndürür.  
  
2.  Ya da uygulama **VSHPROPID_IconMonikerImageList** (özgün proje kullandıysanız **VSHPROPID_IconImgList**) veya **VSHPROPID_IconMonikerGuid**,  **VSHPROPID_IconMonikerId**, **VSHPROPID_OpenFolderIconMonikerGuid**, **VSHPROPID_OpenFolderIconMonikerId** (özgün proje kullandıysanız  **VSHPROPID_IconHandle** ve **VSHPROPID_OpenFolderIconHandle**).  
  
3.  Uzantı noktaları bunları isterse simgeleri "eski" sürümlerini oluşturmak için simgeler için özgün VSHPROPIDs uygulamasını değiştirin. **IVsImageService2** bu simgeleri almak gerekli işlevselliği sağlar  
  
 **VB için ek gereksinimler / C# proje özellikleri**  
  
 Yalnızca uygulama **VSHPROPID_SupportsIconMonikers** projenizi olduğunu tespit ederse **en dıştaki özellik**. Aksi takdirde, gerçek dıştaki özellik görüntü adlar gerçekte desteklemiyor olabilir ve temel özellik etkili bir şekilde "özelleştirilmiş görüntüleri gizlemek".  
  
 **CPS nasıl görüntü adlar kullanıyor?**  
  
 CPS (ortak proje sistem) özel görüntüleri ayarlama el ile veya proje sistem genişletilebilirliği SDK ile birlikte gelen bir öğe şablonu aracılığıyla yapılabilir.  
  
 **Proje sistem genişletilebilirliği SDK'sını kullanma**  
  
 Bölümündeki yönergeleri izleyin [proje türü/öğe türü için özel simgeleri sağlayın](https://github.com/Microsoft/VSProjectSystem/blob/master/doc/scenario/provide_custom_icons_for_the_project_or_item_type.md) CPS görüntülerinizi özelleştirmek için. CPS hakkında daha fazla bilgi bulunabilir [Visual Studio Proje sistem genişletilebilirlik belgeleri](https://github.com/Microsoft/VSProjectSystem)  
  
 **El ile ImageMonikers kullanın**  
  
1.  Uygulama ve dışarı aktarma **IProjectTreeModifier** proje sisteminizdeki arabirimi.  
  
2.  Hangi belirleme **KnownMoniker** veya kullanmak istediğiniz özel görüntü ad.  
  
3.  İçinde **ApplyModifications** yöntemi, aşağıdakileri yönteminde benzer yeni ağacı dönmeden önce herhangi bir yerde örnek aşağıda:  
  
    ```csharp  
    // Replace this KnownMoniker with your desired ImageMoniker  
    tree = tree.SetIcon(KnownMonikers.Blank.ToProjectSystemType());  
    ```  
  
4.  Yeni bir ağaç oluşturuyorsanız, benzer NewTree yöntemiyle istenen adları geçirerek özel resimler ayarlayabilirsiniz örnek aşağıda:  
  
    ```csharp  
    // Replace this KnownMoniker with your desired ImageMoniker  
    ProjectImageMoniker icon         = KnownMonikers.FolderClosed.ToProjectSystemType();  
    ProjectImageMoniker expandedIcon = KnownMonikers.FolderOpened.ToProjectSystemType();  
  
    return this.ProjectTreeFactory.Value.NewTree(/*caption*/<value>,  
                                                 /*filePath*/<value>,  
                                                 /*browseObjectProperties*/<value>,  
                                                 icon,  
                                                 expandedIcon);  
    ```  
  
## <a name="how-do-i-convert-from-a-real-image-strip-to-a-moniker-based-image-strip"></a>Bir bilinen ad tabanlı görüntü Şerit nasıl gerçek görüntü Şerit dönüştürülsün mü?  
 **HIMAGELISTs destek gerekir**  
  
 Görüntü hizmetini kullanmak için güncelleştirmek istediğiniz, ancak görüntü listeleri geçici geçirme gerektiren API tarafından kısıtlanmıştır kodunuz için zaten varolan bir görüntü Şerit ise, yansıma hizmeti yararları hala alabilirsiniz. Ad tabanlı görüntü Şerit oluşturmak için bildirim var olan adlar oluşturmak için aşağıdaki adımları izleyin.  
  
1.  Çalıştırma **ManifestFromResources** aracı, görüntü Şerit geçirme. Bu Şerit yönelik bir bildirim oluşturur.  
  
    -   Önerilen: kullanım uyacak şekilde bildirimi için varsayılan olmayan ad sağlayın.  
  
2.  Yalnızca kullanıyorsanız **KnownMonikers**, aşağıdakileri yapın:  
  
    -   Değiştir \<görüntüleri > bildirimine bölümünü \<görüntüleri / >.  
  
    -   Tüm subimage kimlikleri kaldırın (hepsi birlikte \<imagestrip adı > _ ##).  
  
    -   Önerilen: AssetsGuid simge ve görüntü Şerit simgesi kullanım uyacak şekilde yeniden adlandırın.  
  
    -   Her Değiştir **ContainedImage**ait GUID $(ImageCatalogGuid) ile değiştirin her **ContainedImage**'s $ Kimliğiyle (\<ad >) ve her dış="true"özniteliğiniekleyin**ContainedImage**  
  
        -   \<Ad > ile değiştirilmelidir **KnownMoniker** resmin eşleştirir ancak "KnownMonikers." adından kaldırıldı.  
  
    -   Ekle < alma Manifest="$(ManifestFolder)\\< göreli yükleme dizini yolu\>\Microsoft.VisualStudio.ImageCatalog.imagemanifest" /\> üstüne \<simgeleri > bölümü.  
  
        -   Göreli yolu için bildirim yazma Kurulum tanımlanan dağıtım konumu tarafından belirlenir.  
  
3.  Çalıştırma **ManifestToCode** görüntü Şerit Görüntü hizmeti sorgulamak için kullanabileceğiniz bir bilinen ad var olan kodu sahip olması sarmalayıcılar aracı.  
  
    -   Önerilen: sarmalayıcıları ve bunların kullanım uyacak şekilde ad alanları için varsayılan olmayan adlar sağlar.  
  
4.  Tümünü ekler, yazma Kurulum/dağıtım ve yansıma hizmeti ve yeni dosyalar ile çalışmak için diğer kod değişiklikleri.  
  
 Örnek bildirimi ne gibi görünmelidir görmek için hem iç hem de dış görüntüleri dahil olmak üzere:  
  
```xml  
<?xml version="1.0"?>  
<ImageManifest  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
  xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014">  
  
  <Symbols>  
    <!-- This needs to be the relative path from your manifest to the ImageCatalog's manifest  
         where $(ManifestFolder) is the deployed location of this manifest. -->  
    <Import Manifest="$(ManifestFolder)\<RelPath>\Microsoft.VisualStudio.ImageCatalog.imagemanifest" />  
  
    <String Name="Resources" Value="/My.Assembly.Name;Component/Resources/ImageStrip" />  
    <Guid Name="ImageGuid" Value="{fb41b7ef-6587-480c-aa27-5b559d42cfc9}" />  
    <Guid Name="ImageStripGuid" Value="{9c84a570-d9a7-4052-a340-188fb276f973}" />  
    <ID Name="MyImage_0" Value="100" />  
    <ID Name="MyImage_1" Value="101" />  
    <ID Name="InternalList" Value="1001" />  
    <ID Name="ExternalList" Value="1002" />  
  </Symbols>  
  
  <Images>  
    <Image Guid="$(ImageGuid)" ID="$(MyImage_0)">  
      <Source Uri="$(Resources)/MyImage_0.png">  
        <Size Value="16" />  
      </Source>  
    </Image>  
    <Image Guid="$(ImageGuid)" ID="$(MyImage_1)">  
      <Source Uri="$(Resources)/MyImage_1.png">  
        <Size Value="16" />  
      </Source>  
    </Image>  
  </Images>  
  
  <ImageLists>  
    <ImageList Guid="$(ImageStripGuid)" ID="$(InternalList)">  
      <ContainedImage Guid="$(ImageGuid)" ID="$(MyImage_0)" />  
      <ContainedImage Guid="$(ImageGuid)" ID="$(MyImage_1)" />  
    </ImageList>  
    <ImageList Guid="$(ImageStripGuid)" ID="$(ExternalList)">  
      <ContainedImage Guid="$(ImageCatalogGuid)" ID="$(StatusError)" External="true" />  
      <ContainedImage Guid="$(ImageCatalogGuid)" ID="$(StatusWarning)" External="true" />  
      <ContainedImage Guid="$(ImageCatalogGuid)" ID="$(StatusInformation)" External="true" />  
    </ImageList>  
  </ImageLists>  
  
</ImageManifest>  
```  
  
 **HIMAGELISTs destek gerek yoktur**  
  
1.  Belirlemek **KnownMonikers** , görüntü Şerit görüntülerinde eşleşmiyor veya kendi adlar görüntüleri için görüntü Şerit oluşturun.  
  
2.  Görüntü Şerit adlar yerine kullanmak için gerekli dizindeki görüntü almak için kullanılan ne olursa olsun eşleme güncelleştirin.  
  
3.  Güncelleştirilmiş eşleme aracılığıyla adlar istemek için Görüntü hizmeti kullanmak için kodunuzu güncelleştirin. (Bu güncelleştirme anlamına gelebilir **CrispImages** yönetilen kodu veya HBITMAPs veya HICONs görüntü Hizmeti'nden istiyor ve bunları çözmek için yerel koda geçirme.)  
  
## <a name="testing-your-images"></a>Görüntülerinizi test etme  
 Görüntü bildirimlerinizi her şeyin doğru yazılmasını emin olmak için test etmek için resim kitaplığı Görüntüleyici aracını kullanabilirsiniz. Aracı bulabilirsiniz [Visual Studio 2015 SDK](http://msdn.microsoft.com/library/bb166441.aspx). Bu araç ve diğerleri için belgeler bulunabilir [burada](http://aka.ms/VSImageThemeTools).  
  
## <a name="additional-resources"></a>Ek kaynaklar  
  
### <a name="samples"></a>Örnekler  
 Visual Studio Örnekleri github'da çeşitli görüntü Hizmeti'nin çeşitli Visual Studio genişletilebilirlik noktaları bir parçası olarak nasıl kullanılacağını göstermek için güncelleştirilmiştir.  
  
 Denetleme [ http://github.com/Microsoft/VSSDK-Extensibility-Samples ](http://github.com/Microsoft/VSSDK-Extensibility-Samples) son örnekleri için.  
  
### <a name="tooling"></a>Araçları  
 Yansıma hizmeti için destek araçları kümesi oluşturma/resim hizmeti ile çalışan kullanıcı arabirimini güncelleştirme yardımcı olmak için oluşturuldu. Her aracı hakkında daha fazla bilgi için araçları ile birlikte gelen belgelere bakın. Araçlar parçası olarak dahil [Visual Studio 2015 SDK.](http://msdn.microsoft.com/library/bb166441.aspx)  
  
 **ManifestFromResources**  
  
 Bildirim kaynakları aracından görüntü kaynakları (PNG ya da XAML) listesini alır ve görüntü hizmetiyle bu görüntüleri kullanmak için bir resim bildirim dosyası oluşturur.  
  
 **ManifestToCode**  
  
 Kod aracı bildirime bir görüntü bildirim dosyası alır ve bildirim değerlerin kod (C++, C# ve VB) veya .vsct dosyalarında başvuran bir sarmalayıcı dosyası oluşturur.  
  
 **ImageLibraryViewer**  
  
 Görüntü kitaplığı Viewer Tool görüntü bildirimleri yükleyebilir ve Visual Studio bildirim doğru yazılmasını sağlayın ister aynı şekilde yönetmenize olanak verir. Kullanıcı, arka plan, boyutları, DPI ayarı, yüksek karşıtlık ve diğer ayarları değiştirebilir. Ayrıca, bildirimleri hatalarını bulmak için yükleme bilgilerini görüntüler ve bildiriminde her görüntü kaynağı bilgilerini görüntüler.  
  
## <a name="faq"></a>SSS  
  
-   Yüklenirken içermesi gereken bağımlılıkları vardır \<başvuru Include="Microsoft.VisualStudio.*. Interop.14.0.DesignTime"/ >?  
  
    -   Ayarlama EmbedInteropTypes = "Tüm birlikte çalışma DLL'lere true".  
  
-   My uzantısı ile nasıl bir görüntü bildirimi dağıtabilir?  
  
    -   .İmagemanifest dosyayı projenize ekleyin.  
  
    -   "İçinde VSIX içine dahil" True olarak ayarlayın.  
  
-   CPS proje sistemimin güncelleştiriliyor. Ne oldu **görüntü adı** ve **StockIconService**?  
  
    -   o adlar kullanmak için CPS güncelleştirildiğinde bu kaldırıldı. Çağrı gerek **StockIconService**, istenen geçirmeniz yeterlidir **KnownMoniker** yöntemi veya özelliği kullanılarak **ToProjectSystemType()** genişletme yöntemi CPS yardımcı programları. Eşlemeyi bulabilirsiniz **görüntü adı** için **KnownMonikers** altında:  
  
        |||  
        |-|-|  
        |**Görüntü adı**|**KnownMoniker**|  
        |ImageName.OfflineWebApp|KnownImageIds.Web|  
        |ImageName.WebReferencesFolder|KnownImageIds.Web|  
        |ImageName.OpenReferenceFolder|KnownImageIds.FolderOpened|  
        |ImageName.ReferenceFolder|KnownImageIds.Reference|  
        |ImageName.Reference|KnownImageIds.Reference|  
        |ImageName.SdlWebReference|KnownImageIds.WebReferenceFolder|  
        |ImageName.DiscoWebReference|KnownImageIds.DynamicDiscoveryDocument|  
        |ImageName.Folder|KnownImageIds.FolderClosed|  
        |ImageName.OpenFolder|KnownImageIds.FolderOpened|  
        |ImageName.ExcludedFolder|KnownImageIds.HiddenFolderClosed|  
        |ImageName.OpenExcludedFolder|KnownImageIds.HiddenFolderOpened|  
        |ImageName.ExcludedFile|KnownImageIds.HiddenFile|  
        |ImageName.DependentFile|KnownImageIds.GenerateFile|  
        |ImageName.MissingFile|KnownImageIds.DocumentWarning|  
        |ImageName.WindowsForm|KnownImageIds.WindowsForm|  
        |ImageName.WindowsUserControl|KnownImageIds.UserControl|  
        |ImageName.WindowsComponent|KnownImageIds.ComponentFile|  
        |ImageName.XmlSchema|KnownImageIds.XMLSchema|  
        |ImageName.XmlFile|KnownImageIds.XMLFile|  
        |ImageName.WebForm|KnownImageIds.Web|  
        |ImageName.WebService|KnownImageIds.WebService|  
        |ImageName.WebUserControl|KnownImageIds.WebUserControl|  
        |ImageName.WebCustomUserControl|KnownImageIds.WebCustomControl|  
        |ImageName.AspPage|KnownImageIds.ASPFile|  
        |ImageName.GlobalApplicationClass|KnownImageIds.SettingsFile|  
        |ImageName.WebConfig|KnownImageIds.ConfigurationFile|  
        |ImageName.HtmlPage|KnownImageIds.HTMLFile|  
        |ImageName.StyleSheet|KnownImageIds.StyleSheet|  
        |ImageName.ScriptFile|KnownImageIds.JSScript|  
        |ImageName.TextFile|KnownImageIds.Document|  
        |ImageName.SettingsFile|KnownImageIds.Settings|  
        |ImageName.Resources|KnownImageIds.DocumentGroup|  
        |ImageName.Bitmap|KnownImageIds.Image|  
        |ImageName.Icon|KnownImageIds.IconFile|  
        |ImageName.Image|KnownImageIds.Image|  
        |ImageName.ImageMap|KnownImageIds.ImageMapFile|  
        |ImageName.XWorld|KnownImageIds.XWorldFile|  
        |ImageName.Audio|KnownImageIds.Sound|  
        |ImageName.Video|KnownImageIds.Media|  
        |ImageName.Cab|KnownImageIds.CABProject|  
        |ImageName.Jar|KnownImageIds.JARFile|  
        |ImageName.DataEnvironment|KnownImageIds.DataTable|  
        |ImageName.PreviewFile|KnownImageIds.Report|  
        |ImageName.DanglingReference|KnownImageIds.ReferenceWarning|  
        |ImageName.XsltFile|KnownImageIds.XSLTransform|  
        |ImageName.Cursor|KnownImageIds.CursorFile|  
        |ImageName.AppDesignerFolder|KnownImageIds.Property|  
        |ImageName.Data|KnownImageIds.Database|  
        |ImageName.Application|KnownImageIds.Application|  
        |ImageName.DataSet|KnownImageIds.DatabaseGroup|  
        |ImageName.Pfx|KnownImageIds.Certificate|  
        |ImageName.Snk|KnownImageIds.Rule|  
        |ImageName.VisualBasicProject|KnownImageIds.VBProjectNode|  
        |ImageName.CSharpProject|KnownImageIds.CSProjectNode|  
        |ImageName.Empty|KnownImageIds.Blank|  
        |ImageName.MissingFolder|KnownImageIds.FolderOffline|  
        |ImageName.SharedImportReference|KnownImageIds.SharedProject|  
        |ImageName.SharedProjectCs|KnownImageIds.CSSharedProject|  
        |ImageName.SharedProjectVc|KnownImageIds.CPPSharedProject|  
        |ImageName.SharedProjectJs|KnownImageIds.JSSharedProject|  
        |ImageName.CSharpCodeFile|KnownImageIds.CSFileNode|  
        |ImageName.VisualBasicCodeFile|KnownImageIds.VBFileNode|  
  
    -   Tamamlanma listesi sağlayıcım güncelleştiriliyor. Ne **KnownMonikers** eski eşleşen **StandardGlyphGroup** ve **StandardGlyph** değerleri?  
  
        ||||  
        |-|-|-|  
        |GlyphGroupClass|GlyphItemPublic|ClassPublic|  
        |GlyphGroupClass|GlyphItemInternal|ClassInternal|  
        |GlyphGroupClass|GlyphItemFriend|ClassInternal|  
        |GlyphGroupClass|GlyphItemProtected|ClassProtected|  
        |GlyphGroupClass|GlyphItemPrivate|ClassPrivate|  
        |GlyphGroupClass|GlyphItemShortcut|ClassShortcut|  
        |GlyphGroupConstant|GlyphItemPublic|ClassPublic|  
        |GlyphGroupConstant|GlyphItemInternal|ClassInternal|  
        |GlyphGroupConstant|GlyphItemFriend|ClassInternal|  
        |GlyphGroupConstant|GlyphItemProtected|ClassProtected|  
        |GlyphGroupConstant|GlyphItemPrivate|ClassPrivate|  
        |GlyphGroupConstant|GlyphItemShortcut|ClassShortcut|  
        |GlyphGroupDelegate|GlyphItemPublic|DelegatePublic|  
        |GlyphGroupDelegate|GlyphItemInternal|DelegateInternal|  
        |GlyphGroupDelegate|GlyphItemFriend|DelegateInternal|  
        |GlyphGroupDelegate|GlyphItemProtected|DelegateProtected|  
        |GlyphGroupDelegate|GlyphItemPrivate|DelegatePrivate|  
        |GlyphGroupDelegate|GlyphItemShortcut|DelegateShortcut|  
        |GlyphGroupEnum|GlyphItemPublic|EnumerationPublic|  
        |GlyphGroupEnum|GlyphItemInternal|EnumerationInternal|  
        |GlyphGroupEnum|GlyphItemFriend|EnumerationInternal|  
        |GlyphGroupEnum|GlyphItemProtected|EnumerationProtected|  
        |GlyphGroupEnum|GlyphItemPrivate|EnumerationPrivate|  
        |GlyphGroupEnum|GlyphItemShortcut|EnumerationShortcut|  
        |GlyphGroupEnumMember|GlyphItemPublic|EnumerationMemberPublic|  
        |GlyphGroupEnumMember|GlyphItemInternal|EnumerationMemberInternal|  
        |GlyphGroupEnumMember|GlyphItemFriend|EnumerationMemberInternal|  
        |GlyphGroupEnumMember|GlyphItemProtected|EnumerationMemberProtected|  
        |GlyphGroupEnumMember|GlyphItemPrivate|EnumerationMemberPrivate|  
        |GlyphGroupEnumMember|GlyphItemShortcut|EnumerationMemberShortcut|  
        |GlyphGroupEvent|GlyphItemPublic|EventPublic|  
        |GlyphGroupEvent|GlyphItemInternal|EventInternal|  
        |GlyphGroupEvent|GlyphItemFriend|EventInternal|  
        |GlyphGroupEvent|GlyphItemProtected|EventProtected|  
        |GlyphGroupEvent|GlyphItemPrivate|EventPrivate|  
        |GlyphGroupEvent|GlyphItemShortcut|EventShortcut|  
        |GlyphGroupException|GlyphItemPublic|ExceptionPublic|  
        |GlyphGroupException|GlyphItemInternal|ExceptionInternal|  
        |GlyphGroupException|GlyphItemFriend|ExceptionInternal|  
        |GlyphGroupException|GlyphItemProtected|ExceptionProtected|  
        |GlyphGroupException|GlyphItemPrivate|ExceptionPrivate|  
        |GlyphGroupException|GlyphItemShortcut|ExceptionShortcut|  
        |GlyphGroupField|GlyphItemPublic|FieldPublic|  
        |GlyphGroupField|GlyphItemInternal|FieldInternal|  
        |GlyphGroupField|GlyphItemFriend|FieldInternal|  
        |GlyphGroupField|GlyphItemProtected|FieldProtected|  
        |GlyphGroupField|GlyphItemPrivate|FieldPrivate|  
        |GlyphGroupField|GlyphItemShortcut|FieldShortcut|  
        |GlyphGroupInterface|GlyphItemPublic|InterfacePublic|  
        |GlyphGroupInterface|GlyphItemInternal|InterfaceInternal|  
        |GlyphGroupInterface|GlyphItemFriend|InterfaceInternal|  
        |GlyphGroupInterface|GlyphItemProtected|InterfaceProtected|  
        |GlyphGroupInterface|GlyphItemPrivate|InterfacePrivate|  
        |GlyphGroupInterface|GlyphItemShortcut|InterfaceShortcut|  
        |GlyphGroupMacro|GlyphItemPublic|MacroPublic|  
        |GlyphGroupMacro|GlyphItemInternal|MacroInternal|  
        |GlyphGroupMacro|GlyphItemFriend|MacroInternal|  
        |GlyphGroupMacro|GlyphItemProtected|MacroProtected|  
        |GlyphGroupMacro|GlyphItemPrivate|MacroPrivate|  
        |GlyphGroupMacro|GlyphItemShortcut|MacroShortcut|  
        |GlyphGroupMap|GlyphItemPublic|MapPublic|  
        |GlyphGroupMap|GlyphItemInternal|MapInternal|  
        |GlyphGroupMap|GlyphItemFriend|MapInternal|  
        |GlyphGroupMap|GlyphItemProtected|MapProtected|  
        |GlyphGroupMap|GlyphItemPrivate|MapPrivate|  
        |GlyphGroupMap|GlyphItemShortcut|MapShortcut|  
        |GlyphGroupMapItem|GlyphItemPublic|MapItemPublic|  
        |GlyphGroupMapItem|GlyphItemInternal|MapItemInternal|  
        |GlyphGroupMapItem|GlyphItemFriend|MapItemInternal|  
        |GlyphGroupMapItem|GlyphItemProtected|MapItemProtected|  
        |GlyphGroupMapItem|GlyphItemPrivate|MapItemPrivate|  
        |GlyphGroupMapItem|GlyphItemShortcut|MapItemShortcut|  
        |GlyphGroupMethod|GlyphItemPublic|MethodPublic|  
        |GlyphGroupMethod|GlyphItemInternal|MethodInternal|  
        |GlyphGroupMethod|GlyphItemFriend|MethodInternal|  
        |GlyphGroupMethod|GlyphItemProtected|MethodProtected|  
        |GlyphGroupMethod|GlyphItemPrivate|MethodPrivate|  
        |GlyphGroupMethod|GlyphItemShortcut|MethodShortcut|  
        |GlyphGroupOverload|GlyphItemPublic|MethodPublic|  
        |GlyphGroupOverload|GlyphItemInternal|MethodInternal|  
        |GlyphGroupOverload|GlyphItemFriend|MethodInternal|  
        |GlyphGroupOverload|GlyphItemProtected|MethodProtected|  
        |GlyphGroupOverload|GlyphItemPrivate|MethodPrivate|  
        |GlyphGroupOverload|GlyphItemShortcut|MethodShortcut|  
        |GlyphGroupModule|GlyphItemPublic|ModulePublic|  
        |GlyphGroupModule|GlyphItemInternal|ModuleInternal|  
        |GlyphGroupModule|GlyphItemFriend|ModuleInternal|  
        |GlyphGroupModule|GlyphItemProtected|ModuleProtected|  
        |GlyphGroupModule|GlyphItemPrivate|ModulePrivate|  
        |GlyphGroupModule|GlyphItemShortcut|ModuleShortcut|  
        |GlyphGroupNamespace|GlyphItemPublic|NamespacePublic|  
        |GlyphGroupNamespace|GlyphItemInternal|NamespaceInternal|  
        |GlyphGroupNamespace|GlyphItemFriend|NamespaceInternal|  
        |GlyphGroupNamespace|GlyphItemProtected|NamespaceProtected|  
        |GlyphGroupNamespace|GlyphItemPrivate|NamespacePrivate|  
        |GlyphGroupNamespace|GlyphItemShortcut|NamespaceShortcut|  
        |GlyphGroupOperator|GlyphItemPublic|OperatorPublic|  
        |GlyphGroupOperator|GlyphItemInternal|OperatorInternal|  
        |GlyphGroupOperator|GlyphItemFriend|OperatorInternal|  
        |GlyphGroupOperator|GlyphItemProtected|OperatorProtected|  
        |GlyphGroupOperator|GlyphItemPrivate|OperatorPrivate|  
        |GlyphGroupOperator|GlyphItemShortcut|OperatorShortcut|  
        |GlyphGroupProperty|GlyphItemPublic|PropertyPublic|  
        |GlyphGroupProperty|GlyphItemInternal|PropertyInternal|  
        |GlyphGroupProperty|GlyphItemFriend|PropertyInternal|  
        |GlyphGroupProperty|GlyphItemProtected|PropertyProtected|  
        |GlyphGroupProperty|GlyphItemPrivate|PropertyPrivate|  
        |GlyphGroupProperty|GlyphItemShortcut|PropertyShortcut|  
        |GlyphGroupStruct|GlyphItemPublic|StructurePublic|  
        |GlyphGroupStruct|GlyphItemInternal|StructureInternal|  
        |GlyphGroupStruct|GlyphItemFriend|StructureInternal|  
        |GlyphGroupStruct|GlyphItemProtected|StructureProtected|  
        |GlyphGroupStruct|GlyphItemPrivate|StructurePrivate|  
        |GlyphGroupStruct|GlyphItemShortcut|StructureShortcut|  
        |GlyphGroupTemplate|GlyphItemPublic|TemplatePublic|  
        |GlyphGroupTemplate|GlyphItemInternal|TemplateInternal|  
        |GlyphGroupTemplate|GlyphItemFriend|TemplateInternal|  
        |GlyphGroupTemplate|GlyphItemProtected|TemplateProtected|  
        |GlyphGroupTemplate|GlyphItemPrivate|TemplatePrivate|  
        |GlyphGroupTemplate|GlyphItemShortcut|TemplateShortcut|  
        |GlyphGroupTypedef|GlyphItemPublic|TypeDefinitionPublic|  
        |GlyphGroupTypedef|GlyphItemInternal|TypeDefinitionInternal|  
        |GlyphGroupTypedef|GlyphItemFriend|TypeDefinitionInternal|  
        |GlyphGroupTypedef|GlyphItemProtected|TypeDefinitionProtected|  
        |GlyphGroupTypedef|GlyphItemPrivate|TypeDefinitionPrivate|  
        |GlyphGroupTypedef|GlyphItemShortcut|TypeDefinitionShortcut|  
        |GlyphGroupType|GlyphItemPublic|TypePublic|  
        |GlyphGroupType|GlyphItemInternal|TypeInternal|  
        |GlyphGroupType|GlyphItemFriend|TypeInternal|  
        |GlyphGroupType|GlyphItemProtected|TypeProtected|  
        |GlyphGroupType|GlyphItemPrivate|TypePrivate|  
        |GlyphGroupType|GlyphItemShortcut|TypeShortcut|  
        |GlyphGroupUnion|GlyphItemPublic|UnionPublic|  
        |GlyphGroupUnion|GlyphItemInternal|UnionInternal|  
        |GlyphGroupUnion|GlyphItemFriend|UnionInternal|  
        |GlyphGroupUnion|GlyphItemProtected|UnionProtected|  
        |GlyphGroupUnion|GlyphItemPrivate|UnionPrivate|  
        |GlyphGroupUnion|GlyphItemShortcut|UnionShortcut|  
        |GlyphGroupVariable|GlyphItemPublic|FieldPublic|  
        |GlyphGroupVariable|GlyphItemInternal|FieldInternal|  
        |GlyphGroupVariable|GlyphItemFriend|FieldInternal|  
        |GlyphGroupVariable|GlyphItemProtected|FieldProtected|  
        |GlyphGroupVariable|GlyphItemPrivate|FieldPrivate|  
        |GlyphGroupVariable|GlyphItemShortcut|FieldShortcut|  
        |GlyphGroupValueType|GlyphItemPublic|ValueTypePublic|  
        |GlyphGroupValueType|GlyphItemInternal|ValueTypeInternal|  
        |GlyphGroupValueType|GlyphItemFriend|ValueTypeInternal|  
        |GlyphGroupValueType|GlyphItemProtected|ValueTypeProtected|  
        |GlyphGroupValueType|GlyphItemPrivate|ValueTypePrivate|  
        |GlyphGroupValueType|GlyphItemShortcut|ValueTypeShortcut|  
        |GlyphGroupIntrinsic|GlyphItemPublic|ObjectPublic|  
        |GlyphGroupIntrinsic|GlyphItemInternal|ObjectInternal|  
        |GlyphGroupIntrinsic|GlyphItemFriend|ObjectInternal|  
        |GlyphGroupIntrinsic|GlyphItemProtected|ObjectProtected|  
        |GlyphGroupIntrinsic|GlyphItemPrivate|ObjectPrivate|  
        |GlyphGroupIntrinsic|GlyphItemShortcut|ObjectShortcut|  
        |GlyphGroupJSharpMethod|GlyphItemPublic|MethodPublic|  
        |GlyphGroupJSharpMethod|GlyphItemInternal|MethodInternal|  
        |GlyphGroupJSharpMethod|GlyphItemFriend|MethodInternal|  
        |GlyphGroupJSharpMethod|GlyphItemProtected|MethodProtected|  
        |GlyphGroupJSharpMethod|GlyphItemPrivate|MethodPrivate|  
        |GlyphGroupJSharpMethod|GlyphItemShortcut|MethodShortcut|  
        |GlyphGroupJSharpField|GlyphItemPublic|FieldPublic|  
        |GlyphGroupJSharpField|GlyphItemInternal|FieldInternal|  
        |GlyphGroupJSharpField|GlyphItemFriend|FieldInternal|  
        |GlyphGroupJSharpField|GlyphItemProtected|FieldProtected|  
        |GlyphGroupJSharpField|GlyphItemPrivate|FieldPrivate|  
        |GlyphGroupJSharpField|GlyphItemShortcut|FieldShortcut|  
        |GlyphGroupJSharpClass|GlyphItemPublic|ClassPublic|  
        |GlyphGroupJSharpClass|GlyphItemInternal|ClassInternal|  
        |GlyphGroupJSharpClass|GlyphItemFriend|ClassInternal|  
        |GlyphGroupJSharpClass|GlyphItemProtected|ClassProtected|  
        |GlyphGroupJSharpClass|GlyphItemPrivate|ClassPrivate|  
        |GlyphGroupJSharpClass|GlyphItemShortcut|ClassShortcut|  
        |GlyphGroupJSharpNamespace|GlyphItemPublic|NamespacePublic|  
        |GlyphGroupJSharpNamespace|GlyphItemInternal|NamespaceInternal|  
        |GlyphGroupJSharpNamespace|GlyphItemFriend|NamespaceInternal|  
        |GlyphGroupJSharpNamespace|GlyphItemProtected|NamespaceProtected|  
        |GlyphGroupJSharpNamespace|GlyphItemPrivate|NamespacePrivate|  
        |GlyphGroupJSharpNamespace|GlyphItemShortcut|NamespaceShortcut|  
        |GlyphGroupJSharpInterface|GlyphItemPublic|InterfacePublic|  
        |GlyphGroupJSharpInterface|GlyphItemInternal|InterfaceInternal|  
        |GlyphGroupJSharpInterface|GlyphItemFriend|InterfaceInternal|  
        |GlyphGroupJSharpInterface|GlyphItemProtected|InterfaceProtected|  
        |GlyphGroupJSharpInterface|GlyphItemPrivate|InterfacePrivate|  
        |GlyphGroupJSharpInterface|GlyphItemShortcut|InterfaceShortcut|  
        |GlyphGroupError||StatusError|  
        |GlyphBscFile||ClassFile|  
        |GlyphAssembly||Başvuru|  
        |GlyphLibrary||Kitaplığı|  
        |GlyphVBProject||VBProjectNode|  
        |GlyphCoolProject||CSProjectNode|  
        |GlyphCppProject||CPPProjectNode|  
        |GlyphDialogId||İletişim kutusu|  
        |GlyphOpenFolder||FolderOpened|  
        |GlyphClosedFolder||FolderClosed|  
        |GlyphArrow||Sonrakine Git|  
        |GlyphCSharpFile||CSFileNode|  
        |GlyphCSharpExpansion||kod parçacığında|  
        |GlyphKeyword||IntellisenseKeyword|  
        |GlyphInformation||StatusInformation|  
        |GlyphReference||ClassMethodReference|  
        |GlyphRecursion||Yinelenme|  
        |GlyphXmlItem||Etiket|  
        |GlyphJSharpProject||DocumentCollection|  
        |GlyphJSharpDocument||Belge|  
        |GlyphForwardType||Sonrakine Git|  
        |GlyphCallersGraph||CallTo|  
        |GlyphCallGraph||CallFrom|  
        |GlyphWarning||StatusWarning|  
        |GlyphMaybeReference||QuestionMark|  
        |GlyphMaybeCaller||CallTo|  
        |GlyphMaybeCall||CallFrom|  
        |GlyphExtensionMethod||ExtensionMethod|  
        |GlyphExtensionMethodInternal||ExtensionMethod|  
        |GlyphExtensionMethodFriend||ExtensionMethod|  
        |GlyphExtensionMethodProtected||ExtensionMethod|  
        |GlyphExtensionMethodPrivate||ExtensionMethod|  
        |GlyphExtensionMethodShortcut||ExtensionMethod|  
        |GlyphXmlAttribute||XmlAttribute|  
        |GlyphXmlChild||XmlElement|  
        |GlyphXmlDescendant||XmlDescendant|  
        |GlyphXmlNamespace||XmlNamespace|  
        |GlyphXmlAttributeQuestion||XmlAttributeLowConfidence|  
        |GlyphXmlAttributeCheck||XmlAttributeHighConfidence|  
        |GlyphXmlChildQuestion||XmlElementLowConfidence|  
        |GlyphXmlChildCheck||XmlElementHighConfidence|  
        |GlyphXmlDescendantQuestion||XmlDescendantLowConfidence|  
        |GlyphXmlDescendantCheck||XmlDescendantHighConfidence|  
        |GlyphCompletionWarning||IntellisenseWarning|