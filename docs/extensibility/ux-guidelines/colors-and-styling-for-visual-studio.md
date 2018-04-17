---
title: Renkleri ve Visual Studio için stil | Microsoft Docs
ms.custom: ''
ms.date: 07/31/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 0e384ea1-4d9e-4307-8884-6e183900732c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5cee3ec1308ee103d279a0d77ded4092e4ccf9b4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="colors-and-styling-for-visual-studio"></a>Renkleri ve Visual Studio için stil oluşturma
## <a name="using-color-in-visual-studio"></a>Visual Studio'da renk kullanma
Visual Studio'da renk öncelikle decoration gibi bir iletişim aracı olarak kullanılır. İstediğiniz durumlar için yedek ve renk en düşük düzeyde kullanın:

-   Anlamı veya katılımı (örneğin, platform veya Dil değiştiricileri) iletişim

-   Dikkatini (örneğin, bir durum değişikliği gösteren)

-   Okunabilirliğini artırmak ve kullanıcı arabirimini gezinmek için bilinen yerler sağlayın

-   Desirability artırın

Visual Studio kullanıcı Arabirimi öğeleri renkleri atamak için çeşitli seçenekler mevcuttur. Bazen bu şekle zor olabilir out hangi seçeneği kullanmak için beklenen olduğunuz veya doğru şekilde kullanma. Bu konuda size yardımcı olur:

1.  Visual Studio'da renkleri tanımlamak için kullanılan sistemler ve farklı Hizmetleri anlayın.

2.  Belirli bir öğenin doğru seçeneğini belirleyin.

3.  Doğru seçmiş olduğunuz seçeneğini kullanın.

> **Not:** hiçbir zaman stillerinizin onaltılık, RGB veya sistem renklerini, kullanıcı Arabirimi öğeleri için. Hizmetleri kullanarak ton ayarlama esneklik sağlar. Ayrıca, hizmeti olmadan, temasını değiştirdikten yeteneklerini yararlanmak mümkün olmaz [VSColor hizmet](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService).

### <a name="methods-for-assigning-color-to-visual-studio-interface-elements"></a>Visual Studio'ya renk atama yöntemlerini arabirim öğeleri
En iyi kullanıcı Arabirimi öğelerine uygun yöntemi seçin.

| UI | Yöntem | Bunlar nedir? |
| --- | --- | --- |
| Katıştırılmış veya tek başına iletişim kutuları. | **Sistem renkleri** | Renk ve kullanıcı Arabirimi öğeleri görünümünü tanımlamak işletim sisteminin izin sistem adları gibi ortak iletişim kutusu denetimleri gibi. |
| Genel VS ortamında ile tutarlı olmasını istediğiniz özel kullanıcı Arabirimi varsa ve kategori ve paylaşılan belirteçleri anlamsal anlamını eşleşen kullanıcı Arabirimi öğeleri. | **Ortak paylaşılan renkleri** | Belirli kullanıcı Arabirimi öğeleri için var olan önceden tanımlanmış renk belirteci adları |
| Bir ayrı özellik ya da Özellikler grubunu olduğunu ve benzer öğelerin paylaşılan hiçbir rengi. | **Özel renkler** | Bir alana özeldir ve diğer kullanıcı Arabirimi ile paylaşılacak düşünülmemiştir renk belirteci adları |
| Kullanıcı Arabirimi veya içeriği (örneğin, metin düzenleyiciler veya özelleştirilmiş Tasarımcı windows için) özelleştirmek son kullanıcı izin vermek istediğiniz. | **Son kullanıcı özelleştirme**<br /><br />**(Araçlar &gt; Seçenekleri iletişim kutusu)** | "Yazı tiplerini ve renkleri" sayfasında tanımlanan ayarlar **Araçları &gt; seçenekleri** iletişim kutusu veya bir kullanıcı Arabirimi özelliğinin belirli bir özel sayfa. |

### <a name="visual-studio-themes"></a>Visual Studio temaları
Visual Studio özellikleri üç farklı renk temaları: açık, koyu ve mavi. Ayrıca, erişilebilirlik için tasarlanmış bir sistem genelinde renk temasını olan yüksek karşıtlık modunda algılar.

Kullanıcılar kendi Visual Studio'nun ilk kullanım sırasında bir tema seçmek için istenir ve Temalar giderek daha sonra geçiş yapabilir **Araçları &gt; seçenekleri &gt; ortam &gt; genel** ve yeni bir temayı seçme "renk temasını" açılır menü.

Kullanıcılar ayrıca tüm sistemlerini birkaç yüksek karşıtlıklı tema birine geçiş yapmak için Denetim Masası'nı kullanabilirsiniz. Ardından bir kullanıcı bir yüksek karşıtlık teması seçerse, kullanıcıya yüksek karşıtlık modunda çıktığında Tema değişiklikleri için kaydedilir ancak Visual Studio renk tema Seçici Visual Studio'da renkleri artık etkiler. Yüksek karşıtlıklı modu hakkında daha fazla bilgi için bkz: [seçme yüksek karşıtlık renkleri](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ChoosingHighContrastColors).

### <a name="the-vscolor-service"></a>VSColor hizmeti
Visual Studio kullanıcı Arabirimi öğeleri renk değerlerini her Visual Studio temasını renk değerleri içeren adlandırılmış bir girişe bağlamak izin veren VSColor hizmet olarak bilinen bir ortam renk hizmetini sağlar. Bu, renkler geçerli kullanıcı tarafından seçilen tema veya sistem yüksek karşıtlıklı modu yansıtmak üzere otomatik olarak değişir sağlar. Tüm renk temasını ilgili değişiklikleri uyarlamasını tek bir yerde işlenir ve ortak paylaşılan renkleri hizmetinden kullanıyorsanız, UI otomatik olarak Visual Studio gelecekteki sürümlerinde yeni temalar yansıtır ve hizmetin kullanımını anlamına gelir.

### <a name="implementation"></a>Uygulama
Visual Studio kaynak kod listeleri belirteci adları ve her tema ilgili renk değerleri içeren birkaç paket tanımlama dosyaları içerir. Renk hizmeti bu paket tanımlama dosyaları tanımlanan VSColors okur. Bu renkleri XAML işaretleme veya kod başvurulan ve aracılığıyla yüklenen `IVsUIShell5.GetThemedColor` yöntemi veya DynamicResource eşlemesi.

### <a name="system-colors"></a>Sistem renkleri
Ortak Denetimler varsayılan olarak sistem renkleri başvuru. Oluştururken bir katıştırılmış veya tek başına iletişim kutusu gibi sistem renkleri kullanmak için kullanıcı Arabirimi istiyorsanız bir şey yapmanız gerekmez.

### <a name="common-shared-colors-in-the-vscolor-service"></a>VSColor hizmetinde ortak paylaşılan renkleri
Arabirim öğeleri genel Visual Studio ortamında yansıtmalıdır. Tasarladığınız UI bileşeni için uygun olan ortak paylaşılan renkleri yeniden kullanarak arabiriminiz diğer Visual Studio arabirimleri ile tutarlı olduğunu ve Temalar eklendiğinde veya güncelleştirilir renkleri otomatik olarak güncelleştirilecek emin olun.

Ortak paylaşılan renkleri kullanmadan önce bunların doğru şekilde nasıl kullanılacağını anladığınızdan emin olun. Ortak paylaşılan renkleri yanlış kullanımı, kullanıcılar için tutarsız, can sıkıcı veya karmaşık bir deneyim neden olabilir.

### <a name="user-customizable-colors"></a>Kullanıcı özelleştirilebilir renkleri
Bkz: [son kullanıcılar için renk gösterme](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ExposingColorsForEndUsers)

Bazı durumlarda, bir kod düzenleyicisinde veya tasarım yüzeyi oluştururken gibi kullanıcı arabirimini özelleştirmek son kullanıcı izin vermek istersiniz. İçinde bulunan özelleştirilebilir kullanıcı Arabirimi bileşenlerini **yazı tiplerini ve renkleri** bölümünü **Araçları &gt; seçenekleri** iletişim kutusunda, burada kullanıcılar seçebilirsiniz ön plan rengini, arka plan rengini veya her ikisi de değiştirmek için.

![Araçlar &gt; Seçenekleri iletişim kutusu](../../extensibility/ux-guidelines/media/0301-a_toolsoptionsdialog.png "0301 a_ToolsOptionsDialog")<br />Araçlar &gt; Seçenekleri iletişim kutusu

##  <a name="BKMK_TheVSColorService"></a> VSColor hizmeti
Visual Studio VSColor hizmeti veya kabuk renk hizmeti de adlı bir ortam renk hizmeti sağlar. Bu hizmet, bir ad-değer renk her tema renkleri içeren kümesini, kullanıcı Arabirimi öğeleri renk değerlerini bağlamak sağlar. Renkleri otomatik olarak geçerli kullanıcı tarafından seçilen tema yansıtacak şekilde değiştirebilir ve böylece UI ortamı renk hizmetine bağlı yeni temaları ile Visual Studio sürümleri gelecekte tümleştirecek VSColor hizmeti tüm kullanıcı Arabirimi öğeleri için kullanılması gerekir.

### <a name="how-the-service-works"></a>Hizmeti nasıl çalışır?
Ortam renk hizmeti VSColors .pkgdef UI bileşeni için tanımlanan okur. Bu VSColors XAML işaretleme veya kod ardından başvurulan ve aracılığıyla yüklenen `IVsUIShell5.GetThemedColor` veya `DynamicResource` eşleme.

![Ortam renk hizmet mimarisi](../../extensibility/ux-guidelines/media/0302-a_environmentcolorservicearchitecture.png "0302 a_EnvironmentColorServiceArchitecture")<br />Ortam renk hizmet mimarisi

### <a name="accessing-the-service"></a>Hizmete erişim
Ne tür bir renk belirteçler bağlı olarak VSColor hizmeti, kullandığınız erişmesini ve kod türüne sahip birçok farklı yolu vardır.

#### <a name="predefined-environment-colors"></a>Önceden tanımlanmış ortamı renkleri

##### <a name="from-native-code"></a>Yerel koddan
Kabuk erişim sağlayan bir hizmet sunar `COLORREF` renk. Hizmet/arabirimi şöyledir:

```
IVsUIShell2::GetVSSysColorEx(VSSYSCOLOR dwSysColIndex, DWORD *pdwRGBval)
```

VSShell80.idl, numaralandırma dosyasındaki `__VSSYSCOLOREX` Kabuk renk sabitleri vardır. Kullanmak için bir dizin değeri olarak değerlerinden birini geçirin `enum __VSSYSCOLOREX` içinde belgelenen MSDN veya API, Windows Sistem numarası normal bir dizin `GetSysColor`, kabul eder. Bunun yapılması, geri de ikinci parametre kullanılan rengi RGB değerini alır.

Kalem veya yeni bir renkli fırça depolamak istiyorsanız, gerekir `AdviseBroadcastMessages` (dışına Visual Studio Kabuğu) ve dinlemek `WM_SYSCOLORCHANGE` ve `WM_THEMECHANGED` iletileri.


Yerel kodda renk hizmetine erişmek için bu benzer bir arama yapacağız:

```
pUIShell2->GetVSSysColorEx(VSCOLOR_COLOR_NAME, &rgbLOCAL_COLOR);
```

> **Not:** `COLORREF` tarafından döndürülen değer `GetVSSysColorEx()` yalnızca R, G, içeren bir Tema rengi B bileşenleri. Bir tema girişi saydamlık kullanıyorsa, alfa kanal değeri döndürmeden önce göz ardı edilir. İlgi ortamı renk saydamlık kanal olduğu önemli bir yerde kullanılması gerekiyorsa, bu nedenle, kullanmalısınız `IVsUIShell5.GetThemedColor` yerine `IVsUIShell2::GetVSSysColorEx`, bu konunun ilerleyen bölümlerinde açıklandığı gibi.

##### <a name="from-managed-code"></a>Yönetilen koddan
Yerel kod üzerinden VSColor hizmete erişim oldukça basittir. Yönetilen kod ile çalışıyorsanız, ancak, hizmeti kullanmak nasıl yapılacağına ilişkin zor olabilir. Aklınızda bu işlemi gösteren bir C# kod parçacığı aşağıda verilmiştir:

```
private void VSColorPaint(object sender, System.Windows.Forms.PaintEventArgs e)
{
    //getIVSUIShell2
    IVsUIShell2 uiShell2 = Package.GetService(typeof(SVsUIShell)) as IVsUIShell2;
    Debug.Assert (uiShell2 != null, "failed to get IVsUIShell2");

    if (uiShell2 != null)
    {
        //get the COLORREF structure
        uint win32Color;
        uiShell.GetVSSysColorEx(VSSYSCOLOREX.VSCOLOR_SMARTTAG_HOVER_FILL, out win32Color);

        //translate it to a managed Color structure
        Color myColor = ColorTranslator.FromWin32((int)win32Color);
        //use it
        e.Graphics.FillRectangle(new SolidBrush(myColor), 0, 0, 100, 100);
    }
}
```

Visual Basic'te çalışıyorsanız, kullanın:

```
Dim myColor As Color = ColorTranslator.FromWin32((Integer)win32Color)
```

##### <a name="from-wpf-ui"></a>WPF kullanıcı Arabiriminden
Visual Studio renkleri uygulamanın dışarı değerleri ile bağlayabilirsiniz `ResourceDictionary`. Aşağıda, renk tablosu kaynaklardan kullanarak yanı XAML'de ortamı yazı tipi verilere bağlama örneğidir.

```
<Style TargetType="{x:Type Button}">
    <Setter Property="TextBlock.FontFamily"
            Value="{DynamicResource VsFont.EnvironmentFontFamily}" />
    <Setter Property="TextBlock.FontSize"
            Value="{DynamicResource VsFont.EnvironmentFontSize}" />
    <Setter Property="Background"
            Value="{DynamicResource VsBrush.EnvironmentBackgroundGradient}" />
</Style>
```

#### <a name="helper-classes-and-methods-for-managed-code"></a>Yardımcı sınıfları ve yönetilen kod için yöntemleri
Yönetilen kod, kabuğun paket çerçevesi ile yönetilen kitaplık için (`Microsoft.VisualStudio.Shell.12.0.dll`) birkaç tema renkleri kullanımını kolaylaştırmanın yardımcı sınıfları içerir.

Yardımcı yöntemler `Microsoft.VisualStudio.Shell.VsColors` MPF sınıfında dahil `GetThemedGDIColor()` ve `GetThemedWPFColor()`. Bu yardımcı yöntemler bir tema girişi olarak renk değerini döndürmek `System.Drawing.Color` veya `System.Windows.Media.Color`, WinForms veya WPF UI kullanılacak.

```
IVsUIShell5 shell5;
Button button = new Button();
button.BackColor = GetThemedGDIColor(shell5, SolutionExplorerColors.SelectedItemBrushKey);
button.ForeColor = GetThemedGDIColor(shell5, SolutionExplorerColors.SelectedItemTextBrushKey);

/// <summary>
/// Gets a System.Drawing.Color value from the current theme for the given color key.
/// </summary>
/// <param name="vsUIShell">The IVsUIShell5 service, used to get the color's value.</param>
/// <param name="themeResourceKey">The key to find the color for.</param>
/// <returns>The current theme's value of the named color.</returns>
public static System.Drawing.Color GetThemedGDIColor(this IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)
{
   Validate.IsNotNull(vsUIShell, "vsUIShell");
   Validate.IsNotNull(themeResourceKey, "themeResourceKey");

   byte[] colorComponents = GetThemedColorRgba(vsUIShell, themeResourceKey);

   // Note: The Win32 color we get back from IVsUIShell5.GetThemedColor is ABGR
   return System.Drawing.Color.FromArgb(colorComponents[3], colorComponents[0], colorComponents[1], colorComponents[2]);
}

private static byte[] GetThemedColorRgba(IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)
{
   Guid category = themeResourceKey.Category;
   __THEMEDCOLORTYPE colorType = __THEMEDCOLORTYPE.TCT_Foreground
   if (themeResourceKey.KeyType == ThemeResourceKeyType.BackgroundColor || themeResourceKey.KeyType == ThemeResourceKeyType.BackgroundBrush)
   {
      colorType = __THEMEDCOLORTYPE.TCT_Background;
   }

   // This call will throw an exception if the color is not found
   uint rgbaColor = vsUIShell.GetThemedColor(ref category, themeResourceKey.Name, (uint)colorType);
   return BitConverter.GetBytes(rgbaColor);
}
public static System.Windows.Media.Color GetThemedWPFColor(this IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)
{
   Validate.IsNotNull(vsUIShell, "vsUIShell");
   Validate.IsNotNull(themeResourceKey, "themeResourceKey");

   byte[] colorComponents = GetThemedColorComponents(vsUIShell, themeResourceKey);

    return System.Windows.Media.Color.FromArgb(colorComponents[3], colorComponents[0], colorComponents[1], colorComponents[2]);
}
```

Sınıfı için verilen bir WPF renk kaynak anahtarı, VSCOLOR tanımlayıcı elde etmek için de kullanılabilir (veya tersi).

```
public static string GetColorBaseKey(int vsSysColor);
public static bool TryGetColorIDFromBaseKey(string baseKey, out int vsSysColor);
```

Yöntemlerinin `VsColors` sınıfı sorgu bunlar çağrılır her zaman renk değeri döndürmek için VSColor hizmet. Bir renk değeri olarak elde etmek için `System.Drawing.Color`, daha iyi performans ile yöntemlerini kullanmayı alternatiftir `Microsoft.VisualStudio.PlatformUI.VSThemeColor` VSColor hizmetinden alınan renk değerleri önbelleğe sınıfı. Sınıf dahili Kabuk yayın iletilerini olayları kaydeder ve bir tema değiştirme olayı oluştuğunda önbelleğe alınan değeri atar. Ayrıca, bu sınıf sağladığı bir. Tema değişiklikleri abone olmak için NET kolay olay. Kullanmak `ThemeChanged` yeni bir işleyici ekleyin ve kullanmak için olay `GetThemedColor()` renk elde etmek için yöntemi değerleri `ThemeResourceKeys` ilgi. Örnek kod şu şekilde görünebilir:

```
public MyWindowPanel()
{
    InitializeComponent();

    // Subscribe to theme changes events so we can refresh the colors
    VSColorTheme.ThemeChanged += VSColorTheme_ThemeChanged;

    RefreshColors();
}

private void VSColorTheme_ThemeChanged(ThemeChangedEventArgs e)
{
    RefreshColors();

    // Also post a message to all the children so they can apply the current theme appropriately
    foreach (System.Windows.Forms.Control child in this.Controls)
    {
        NativeMethods.SendMessage(child.Handle, e.Message, IntPtr.Zero, IntPtr.Zero);
    }
}

private void RefreshColors()
{
    this.BackColor = VSColorTheme.GetThemedColor(EnvironmentColors.ToolWindowBackgroundColorKey);
    this.ForeColor = VSColorTheme.GetThemedColor(EnvironmentColors.ToolWindowTextColorKey);
}

protected override void Dispose(bool disposing)
{
    if (disposing)
    {
        VSColorTheme.ThemeChanged -= this.VSColorTheme_ThemeChanged;
        base.Dispose(disposing);}
}
```

##  <a name="BKMK_ChoosingHighContrastColors"></a> Yüksek Karşıtlık renklerini seçme

### <a name="overview"></a>Genel Bakış
Windows, öğeleri ekranda daha farklı görünür hale metin, arka planlar ve görüntüleri renk karşıtlığını artırmak birçok yüksek karşıtlıklı sistem düzeyindeki temayla kullanır. Erişilebilirlik nedeniyle, kullanıcı için yüksek karşıtlık teması değiştirdiğinizde Visual Studio arabirimi öğeleri doğru şekilde yanıt vermesini önemlidir.

Sistem renkleri sayıda yüksek karşıtlıklı tema için kullanılabilir. Sisteminizin renk adları seçerken, aşağıdaki ipuçları unutmayın:

1.  **Aynı anlam anlamları Sistem renklerini seçin** renklendirme öğe olarak. Örneği için bir pencere içindeki metni için bir yüksek karşıtlıklı renk seçme, WindowText ve değil ControlText kullanın.

2.  **Ön plan/arka plan çiftleri seçin** birlikte veya renk tercih ettiğiniz tüm yüksek karşıtlık Temalar çalışacağını emin olmaz.

3.  **UI hangi kısımlarının en önemli olduğunu belirlemek ve içerik alanları göze emin olun.** Farklı içerik alanlar için hiçbir renk çeşitleri olduğundan güçlü renkler kullanımını içerik alanları tanımlamak için ortak olacak şekilde, çok sayıda renk ton küçük farklılıklar normalde ayırt edebilir, ayrıntı kaybedersiniz.

### <a name="system-color-set"></a>Sistem renk kümesi
Tabloya [WPF ekibi blogu: SystemColors başvuru](http://blogs.msdn.com/b/wpf/archive/2010/11/30/systemcolors-reference.aspx) sistem renk adları ve her temada görüntülenen karşılık gelen tonlar tamamını gösterir.

Bu uygulama, kullanıcı Arabirimi için renk kümesi sınırlı olduğunda *"normal" Temalar da mevcut Zarif ayrıntıları kaybedersiniz beklenir*. Araç penceresi alanları ayırmak için kullanılan ince gri renklerle UI örneği aşağıda verilmiştir. Yüksek karşıtlık modunda görüntülenen aynı penceresi ile eşlenmiş, tüm arka planlar aynı ton olan ve bu alanlara Kenarlıklar kenarlık tek başına belirtilir görebilirsiniz:

![Nasıl Zarif ayrıntıları örneği, yüksek karşıtlıklı kayboluyor](../../extensibility/ux-guidelines/media/030303-a_propertieswindow.png "030303 a_PropertiesWindow")<br />Nasıl Zarif ayrıntıları örneği, yüksek karşıtlıklı kayboluyor

#### <a name="choosing-text-colors-in-an-editor"></a>Bir düzenleyicide metin renklerini seçme
Renklendirilen metin bir düzenleyicide veya tasarım yüzeyi kolay bir şekilde tanımlanması benzer öğeleri grupları için izin verme gibi anlamı belirtmek için kullanılır. Bir Yüksek Karşıtlık temasını ancak, siz arasında birden fazla üç metin renkleri ayırt etme olanağı yok. WindowText, GrayText ve HotTrackText WindowBackground yüzey üzerinde kullanılabilir tek renkleri vardır. Üçten fazla renk kullanılamaz olduğundan, yüksek karşıtlık modunda görüntülemek istediğiniz en önemli farklılıklar dikkatle seçin.

Tonlar her yüksek karşıtlık teması göründükleri gibi Düzenleyicisi yüzey üzerinde izin verilen belirteç adlarının her biri için:

![Yüksek Karşıtlık Düzenleyicisi karşılaştırma](../../extensibility/ux-guidelines/media/030303-b_hceditorcomparison.png "030303 b_HCEditorComparison")<br />Yüksek Karşıtlık Düzenleyicisi karşılaştırma

Mavi tema Düzenleyicisi yüzeyde örnekleri:

![Mavi tema düzenleyicisinde](../../extensibility/ux-guidelines/media/030303-c_editorblue.png "030303 c_EditorBlue")<br />Mavi tema Düzenleyicisi

![Yüksek Karşıtlık #1 tema düzenleyicisinde](../../extensibility/ux-guidelines/media/030303-d_editorhc1.png "030303 d_EditorHC1")<br />Yüksek Karşıtlık #1 tema Düzenleyicisi

### <a name="usage-patterns"></a>Kullanım desenleri
Birçok ortak kullanıcı Arabirimi öğeleri zaten tanımlı yüksek karşıtlık renkleri vardır. Kullanıcı Arabirimi öğeleri benzer bileşenleri ile tutarlı olmasını sağlamak, kendi sistem renk adları seçerken bu kullanım desenlerini başvurabilirsiniz.

| Sistem rengi | Kullanım |
| --- | --- |
| ActiveCaption | -Active IDE ve rafted penceresi düğmesi karakterlerde vurgulu ve tuşuna basın<br />-IDE ve rafted windows başlık çubuğu arka planı<br />-Varsayılan durum çubuğu arka plan |
| ActiveCaptionText | -Active IDE ve rafted windows başlık çubuğu ön plan (metin ve karakterlerin) için<br />-Arka plan ve kenarlık etkin pencereyi düğmelerini vurgulu ve tuşuna basın |
| Denetim | -Birleşik giriş kutusu ve aşağı açılan liste arama varsayılan denetlemek ve açılan düğmesine dahil olmak üzere arka plan, devre dışı<br />-Hedef düğmesi arka plan yerleştirme<br />-Komut çubuğu arka plan<br />-Aracı penceresi arka plan |
| ControlDark | -IDE arka plan<br />-Menü ve komut çubuğu ayırıcıları<br />-Komut çubuğu kenarlığı<br />-Menü shadows<br />-Penceresi sekmesi varsayılan ve vurgulu kenarlık ve ayırıcı aracı<br />-Belge iyi taşma düğmesi arka plan<br />-Dock hedef karakter kenarlığı |
| ControlDarkDark |-Odaksız, seçili belge sekmesi penceresi |
| ControlLight |-Sekme kenarlığı Otomatik-Gizle<br />-Birleşik giriş kutusu ve aşağı açılan liste kenarlığı<br />-Hedef arka plan ve kenarlık yerleştirme |
| ControlLightLight | -Seçili, odaklanmış geçici kenarlığı |
| ControlText | -Birleşik giriş kutusu ve aşağı açılan liste karakter<br />-Aracı penceresinde seçili sekme metni |
| GrayText |-Birleşik giriş kutusu ve aşağı açılan liste kenarlık, aşağı açılan karakter, metin ve menü öğesi metni devre dışı<br />-Devre dışı bırakılmış menü metni<br />-Arama denetim 'Arama Seçenekleri' üstbilgi metni<br />-Arama denetim bölüm ayırıcı |
| Vurgula | -Tüm vurgulu ve basılı arka planları ve birleşik giriş kutusu açılan düğmesine arka plan ve belge iyi taşma düğmesi kenarlığı dışında Kenarlıklar<br />-Seçili öğe arka planlar |
| HighlightText | -Tüm vurgulu ve basılı foregrounds (metin ve karakter)<br />-Odaklanmış aracı penceresi ve belge sekmesi penceresi denetim ön plan<br />-Odaklanmış aracı pencere başlık çubuğu kenarlığı<br />-Odaklanmış, seçili geçici sekmesini ön plan<br />-Belge iyi taşma düğmesi kenarlık vurgulu ve tuşuna basın<br />-Seçilen simge kenarlığı|
| HotTrack | -Kaydırma Flash arka plan ve kenarlık makinesinde çubuğu<br />-Ok karakter makinesinde çubuğu kaydırın |
| InactiveCaption | -Etkin olmayan IDE ve rafted penceresi vurgulu karakterlerde düğmesi<br />-IDE ve rafted windows başlık çubuğu arka planı<br />-Devre dışı arama denetim arka plan |
| InactiveCaptionText | -Etkin olmayan IDE ve rafted windows başlık çubuğu ön plan (metin ve karakter)<br />-Etkin olmayan pencere düğmelerinin arka plan ve vurgulu kenarlığı<br />-Odaksız araç penceresi düğmesi arka plan ve kenarlık<br />-Devre dışı arama denetim ön plan |
| Menü | -Aşağı açılan menü arka plan<br />-Checked ya da devre dışı bırakılmış onay işareti arka plan |
| MenuText | -Aşağı açılan menü kenarlık<br />-Onay işaretleri<br />-Menü Seçenekleri<br />-Aşağı açılan menü metni<br />-Seçilen simge kenarlığı |
| Kaydırma çubuğu | -Kaydırma çubuğu ve kaydırma ok arka plan, tüm durumları çubuğu |
| Pencere | -Otomatik olarak gizle sekmesi arka plan<br />-Menü çubuğu ve komut raf arka plan<br />-Odaksız veya seçili belge penceresinde sekme arka plan ve açık ve geçici sekmeler için belge kenarlığı<br />-Odaksız aracı penceresinin başlık çubuğu arka plan<br />-Aracı penceresi sekmesi arka plan, her ikisini de seçili ve seçili |
| WindowFrame | -IDE kenarlığı |
| WindowText | -Otomatik olarak gizle sekmesini ön plan<br />-Seçilen araç penceresi sekmesini ön plan<br />-Odaksız belge penceresi sekmesi ve Odaksız veya seçili geçici sekmesini ön plan<br />-Ağaç görünüm varsayılan ön plan ve vurgulu seçilmemiş karakter<br />-Aracı penceresinde seçili sekme kenarlığı<br />-Kaydırın parmak arka plan, kenarlık ve karakter |

##  <a name="BKMK_ExposingColorsForEndUsers"></a> Son kullanıcılar için renk gösterme

### <a name="overview"></a>Genel Bakış
Bazen bir kod düzenleyicisinde veya tasarım yüzeyi oluştururken gibi kullanıcı arabirimini özelleştirmek son kullanıcı izin vermek istersiniz. Bunu yapmanın en yaygın yolu kullanmaktır **Araçları &gt; seçenekleri** iletişim. Özel denetimler gerektirir UI yüksek oranda özelleştirilmiş sürece özelleştirme sunmak için en kolay yolu aracılığıyladır **yazı tiplerini ve renkleri** içinde sayfa **ortam** iletişim bölümü. Özelleştirme için kullanıma her öğe için ön plan rengini, arka plan rengini veya her ikisi de değiştirmek kullanıcı seçebilirsiniz.

### <a name="building-a-vspackage-for-your-customizable-colors"></a>VSPackage özelleştirilebilir renkler için oluşturma
Bir VSPackage yazı tiplerini ve renkleri özel kategoriler ile denetlemek ve yazı tipleri ve renkler özellik sayfasında öğeleri görüntüleyebilirsiniz. Bu mekanizma kullanırken, VSPackages uygulamalıdır [IVsFontAndColorDefaultsProvider](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaultsprovider.aspx) ve onun ilişkili arabirim.

Temelde, bu mekanizma tüm var olan öğeleri görüntüleme ve bunları içeren kategorilerini değiştirmek için kullanılabilir. Bununla birlikte, metin düzenleyici kategori veya kendi görüntü öğeleri değiştirmek için kullanılmamalıdır. Metin Düzenleyici kategori hakkında daha fazla bilgi için bkz: [yazı tipi ve renk genel bakış](../font-and-color-overview.md).

Özel kategoriler uygulamak veya öğeleri görüntülemek için bir VSPackage gerekir:

-   **Oluşturun veya kayıt defterinde kategorileri belirleyin.** IDE'nin uyarlamasını **yazı tiplerini ve renkleri** özellik sayfasında belirtilen kategori destekleyen hizmeti için doğru bir şekilde sorgulamak için bu bilgileri kullanır.

-   **Oluşturun veya grupları (isteğe bağlı) kayıt defterinde belirleyin.** İki veya daha fazla kategoriye birleşimi temsil eden bir grup tanımlamak yararlı olabilir. Bir grup tanımlanırsa, IDE otomatik olarak alt kategorileri birleştirir ve grup içindeki öğeleri görüntüleme dağıtır.

-   **IDE desteği uygulayın.**

-   **Yazı tipi ve renk değişiklikleri işleyin.**

#### <a name="to-create-or-identify-categories"></a>Oluşturma veya kategorileri tanımlamak için
Özel türde bir kategori kayıt defteri girişi altında oluşturmak `[HKLM\SOFTWARE\Microsoft \Visual Studio\\<Visual Studio version\>\FontAndColors\\<Category\>]` burada `<Category>` kategorisi yerelleştirilmemiş adıdır.

Kayıt defteri iki değerlerle doldurun:

| Ad | Tür | Veri | Açıklama |
| --- | --- | --- | --- |
| Kategori | REG_SZ | GUID | Kategori tanımlamak için oluşturulmuş bir GUID |
| Paket | REG_SZ | GUID | Kategori destekleyen VSPackage hizmet GUID'i |

 Kayıt defterinde belirtilen hizmet uygulaması sağlamalısınız [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) karşılık gelen bir kategorisi için.

#### <a name="to-create-or-identify-groups"></a>Gruplar oluşturma veya tanımlamak için
Özel türde bir kategori kayıt defteri girişi altında oluşturmak `[HKLM\SOFTWARE\Microsoft \Visual Studio\\<Visual Studio version\>\FontAndColors\\<group\>]` burada `<group>` yerelleştirilmemiş grubunun adıdır.

Kayıt defteri iki değerlerle doldurun:

| Ad | Tür | Veri | Açıklama |
|--- | --- | --- | --- |
| Kategori | REG_SZ | GUID | Kategori tanımlamak için oluşturulmuş bir GUID |
| Paket | REG_SZ | GUID | Kategori destekleyen VSPackage hizmet GUID'i |

Kayıt defterinde belirtilen hizmet uygulaması sağlamalısınız <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> ilgili grup.

![IVsFontAndColorGroup uyarlamasını](../../extensibility/ux-guidelines/media/0304-a_fontandcolorgroup.png "0304 a_FontAndColorGroup")<br />Uygulaması `IVsFontAndColorGroup`

### <a name="to-implement-ide-support"></a>IDE desteği uygulamak için
Uygulama [GetObject](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaultsprovider.getobject.aspx), ya da döndüren bir [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) arabirimi veya bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> arabirim için her kategori için IDE veya GUID sağlanmış grup.

Destekliyorsa her kategori için ayrı bir örneğini bir VSPackage uygulayan [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) arabirimi.

Yöntemleri aracılığıyla uygulanan [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) IDE ile sağlamanız gerekir:

-   Kategorideki öğeleri görüntüleme listesi

-   Görüntü öğeleri için yerelleştirilebilir adları

-   Her bir üyesi kategori bilgilerini görüntüleme

 > **Not:** her kategori en az bir görüntü öğesi içermelidir.

IDE kullanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> birkaç kategorisi birleşimini tanımlamak için arabirim.

Kendi uygulama ile bir IDE sağlar:

-   Belirli bir grubu oluşturan kategori listesi

-   Örneklerini erişimi [IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx) her kategori grubu içinde destekleme

-   Yerelleştirilebilir grup adları

#### <a name="updating-the-ide"></a>IDE güncelleştiriliyor
IDE yazı tipi ve renk ayarları hakkında bilgi önbelleğe alır. Bu nedenle, tüm IDE yazı tipi ve renk yapılandırmasını değiştirme sonrasında önbellek güncel olduğundan emin olmanın en iyi uygulamadır.

Önbelleği güncelleştiriliyor aracılığıyla yapılır [IvsFontAndColorCacheManager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorcachemanager.aspx) arabirim ve gerçekleştirilen genel olarak veya yalnızca üzerinde seçili öğeleri olabilir.

### <a name="handling-font-and-color-changes"></a>Yazı tipi ve renk değişiklikleri işleme
Düzgün bir VSPackage görüntülenen metin renklendirme desteklemek için VSPackage destekleyen renklendirme hizmeti yazı tiplerini ve renkleri özellikleri sayfasında yapılan kullanıcı tarafından başlatılan değişiklikleri yanıtlaması gerekir.

Bunu yapmak için bir VSPackage gerekir:

-   **IDE tarafından oluşturulan olayları ele** uygulayarak [IVsFontAndColorEvents](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorevents.aspx) arabirimi. IDE yazı tiplerini ve renkleri sayfasının kullanıcı değişiklikleri izleyen uygun yöntemini çağırır. Örneğin, çağıran [OnFontChanged](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorevents.onfontchanged.aspx) yeni bir yazı tipi seçtiyseniz yöntemi.

 **VEYA**

-   **IDE değişiklikleri için yoklama**. Bu sistem uygulanan yapılabilir [IVsFontAndColorStorage](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.aspx) arabirimi. Öncelikle desteği için Kalıcılık, ancak [GetItem](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.getitem.aspx) yöntemi görüntü öğeleri için yazı tipi ve renk bilgi elde edebilirsiniz. Yazı tipi ve renk ayarları hakkında daha fazla bilgi için MSDN makalesine bakın [erişme depolanan yazı tipi ve renk ayarlarını](../accessing-stored-font-and-color-settings.md).

> **Not:** yoklama sonuçları doğru olduğundan emin olmak için kullanmak [IVsFontAndColorCacheManager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorcachemanager.aspx) önbellek temizleme ve güncelleştirme alma yöntemlerini çağırmadan önce gerekli olup olmadığını belirlemek için arabirimi [ IVsFontAndColorStorage](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.aspx) arabirimi.

#### <a name="registering-custom-font-and-color-category-without-implementing-interfaces"></a>Arabirimler uygulama olmadan özel yazı tipi ve renk kategori kaydediliyor
Aşağıdaki kod örneğinde, özel yazı tipinin kaydı ve arabirimler uygulama olmadan kategori renk gösterilmiştir:

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\FontAndColors\CSharp Tool Window]
"Package"="{F5E7E71D-1401-11D1-883B-0000F87579D2}"
"Category"="{9FF46859-A47E-47bf-8AC5-EC3DBE69D1FE}"
"ToolWindowPackage"="{7259e420-6241-4e0d-b535-5b820671d183}"

    "NameID"=dword:00000064
```

Bu kod örneği için:
-   `"NameID"` yerelleştirilmiş kategori adı paketi kaynak kimliği =
-   `"ToolWindowPackage"` = Paketi GUID
-   `"Category"="{9FF46859-A47E-47bf-8AC5-EC3DBE69D1FE}"` yalnızca bir örnektir ve gerçek değer uygulayan tarafından sağlanan yeni bir GUID olabilir.

### <a name="set-the-font-and-color-property-category-guid"></a>Yazı tipi ve renk özelliği kategori GUID ayarlayın
Aşağıdaki kod örneği, kategori GUID'ler ayarını gösterir.

```
// m_pView is your IVsTextView
IVsTextEditorPropertyCategoryContainer spPropCatContainer =
(IVsTextEditorPropertyCategoryContainer)m_pView;
if (spPropCatContainer != null)
{
IVsTextEditorPropertyContainer spPropContainer;
Guid GUID_EditPropCategory_View_MasterSettings =
new Guid("{D1756E7C-B7FD-49a8-B48E-87B14A55655A}");
hr = spPropCatContainer.GetPropertyCategory(
ref GUID_EditPropCategory_View_MasterSettings,
out spPropContainer);
if(hr == 0)
{
hr =
spPropContainer.SetProperty(
VSEDITPROPID.VSEDITPROPID_ViewGeneral_FontCategory,
catGUID);
hr =
spPropContainer.SetProperty(
VSEDITPROPID.VSEDITPROPID_ViewGeneral_ColorCategory,
catGUID);
}
}
```
