---
title: VSIX renk Düzenleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 70879c5d-e0f0-4845-993c-2f4229869706
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3404505da4b006327aebb5b8cd7b69fc69e218d0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vsix-color-editor"></a>VSIX renk Düzenleyicisi
Visual Studio uzantısı renk Düzenleyicisi araç oluşturun ve Visual Studio için özel renkler düzenleyin. Böylece renkleri kodda kullanılabilir aracı tema kaynak anahtarları de oluşturabilirsiniz. Bu araç, renkler tema destekleyen Visual Studio uzantısı yapmak için kullanışlıdır. Bu araç .pkgdef ve .xml dosyaları açabilirsiniz. Visual Studio Temalar (.vstheme dosyaları) için .xml dosya uzantısı değiştirerek Visual Studio uzantısı renk Düzenleyicisi ile kullanılabilir. Ayrıca, .vstheme dosya geçerli bir .xml dosyasına aktarılabilir.  
  
 ![VSIX renk Düzenleyicisi kahramanı](../../extensibility/internals/media/vsix-color-editor-hero.png "VSIX renk Düzenleyicisi kahramanı")  
  
 **Paket tanımlama dosyaları**  
  
 Paket tanımlama (.pkgdef) dosyaları Temalar tanımlayan dosyalarıdır. Renkleri kendilerini .pkgdef dosyasına derlenmiş Tema rengi .xml dosyaları depolanır. .Pkgdef dosyaları çalışma zamanında işlenen, Visual Studio aranabilir konumlara dağıtılan ve Temalar tanımlamak için birlikte birleştirilir.  
  
 **Renk belirteçleri**  
  
 Bir renk belirteci dört öğelerden oluşur:  
  
-   **Kategori adı:** renkleri kümesi için mantıksal bir gruplandırma. İstenen kullanıcı Arabirimi öğesi ya da kullanıcı Arabirimi öğeleri grubu için belirli renkleri zaten varsa var olan bir kategori adı kullanın.  
  
-   **Belirteç adını:** renk belirtecini ve simge kümeler için açıklayıcı bir ad. Böylece çiftleri ve geçerli durumlarını tanımlamak kolay bu adlı olmalıdır ve tüm durumlarını yanı sıra arka plan ve ön plan (metin) belirteci adları ayarlar içerir.  
  
-   **Renk değerleri (veya tonlar):** her renkli tema için gerekli. Her zaman arka plan ve metin rengi değerleri çiftler halinde oluşturun. Metin (ön) rengi her zaman çizilmiş arka plan rengi karşı okunabilir olmasını sağlamak için arka plan/ön plan renkleri eşleştirilmelidir. Bu renkleri bağlı olan ve kullanıcı Arabiriminde birlikte kullanılır. Arka plan metin ile kullanılmak üzere tasarlanmamıştır, ön plan rengini tanımlamayın.  
  
-   **Sistem renk adı:** kullanılmak üzere yüksek karşıtlıklı görüntüler.  
  
## <a name="how-to-use-the-tool"></a>Aracı nasıl kullanılır  
 Mümkün olduğunca ve uygun olan yerlerde, mevcut Visual Studio renkleri yenilerini yapılmak yerine yeniden. Ancak, hiçbir uygun renkleri tanımlandığı durumlarda, özel renkler, bir uzantı tema uyumlu tutmak için oluşturulmalıdır.  
  
 **Yeni renk belirteç oluşturma**  
  
 Visual Studio uzantısı renk Düzenleyicisi'ni kullanarak özel renkler oluşturmak için aşağıdaki adımları izleyin:  
  
1.  Yeni renk belirteçleri için kategori ve belirteç adları belirleyin.  
  
2.  Kullanıcı Arabirimi öğesi için yüksek karşıtlık her teması ve sistem rengi için kullanacağı tonları seçin.  
  
3.  Yeni renk belirteçleri oluşturmak için renk Düzenleyicisi'ni kullanın.  
  
4.  Visual Studio Uzantısı'nda renkleri kullanın.  
  
5.  Değişiklikleri Visual Studio'da test edin.  
  
 **1. adım: yeni renk belirteçleri için belirteç adları ve kategori belirler.**  
  
 Tercih edilen adlandırma düzen bir VSColor için **[Kategori] [UI türü] [State]**. Yedek olduğu gibi "renk" word VSColor adlarında kullanmayın.  
  
 Kategori adları mantıksal gruplandırmaları sağlayın ve mümkün olduğunca dar olarak tanımlanması gerekir. Örneğin, bir tek araç penceresi adı bir kategori adı olabilir, ancak tüm iş birimi veya projeyi takım adı değil. Girişleri kategoriler halinde gruplandırma, Karışıklığı önlemek için aynı ada sahip renkler arasındaki önlemeye yardımcı olur.  
  
 Belirteç adını, öğe türü ve durumlar veya "durumu rengi uygulanır," açıkça belirtmeniz gerekir. Örneğin, bir etkin veri ipucunun **[UI türü]** adlandırılabilir "**DataTip**" ve **[State]** adlandırılabilir "**etkin**," olarak ortaya çıkan bir renk adını "**DataTipActive**." Veri ipuçları metin sahip olduğundan, bir ön plan ve arka plan rengi tanımlanması gerekir. Arka plan/ön plan eşleştirme kullanarak, renk Düzenleyicisi'ni otomatik olarak renkleri oluşturacaksınız "**DataTipActive**" arka planı için ve "**DataTipActiveText**" ön için.  
  
 UI parçası yalnızca bir durum varsa **[State]** adının bir parçası etmeyebilirsiniz. Örneğin, bir arama kutusu kenarlığı varsa ve kenarlık 's rengi etkileyecek durumu değişiklik yoktur, ardından kenarlık 's renk belirteç adını yalnızca çağrılabilir "**SearchBoxBorder**."  
  
 Bazı ortak durumu adları şunlardır:  
  
-   Etkin  
  
-   Etkin olmayan  
  
-   Fare üzerinde  
  
-   MouseDown  
  
-   Seçili  
  
-   Odaklanmış  
  
 Bir liste öğesi denetimini bölümleri için birkaç belirteci adları örnekleri:  
  
-   ListItem  
  
-   ListItemBorder  
  
-   ListItemMouseOver  
  
-   ListItemMouseOverBorder  
  
-   ListItemSelected  
  
-   ListItemSelectedBorder  
  
-   ListItemDisabled  
  
-   ListItemDisabledBorder  
  
 **2. adım: kullanıcı Arabirimi öğesi için yüksek karşıtlık her teması ve sistem rengi için kullanacağı tonları seçin.**  
  
 Özel renkler için kullanıcı Arabirimi seçerken, benzer bir var olan kullanıcı Arabirimi öğesi seçin ve temel olarak kendi renkleri kullanın. Böylece uygun ara ve tüm temalar düzgün çalışmasını içindeki kutu kullanıcı Arabirimi öğeleri renklerini incelemesi ve testi, yapılması.  
  
 **3. adım: yeni renk belirteçleri oluşturmak için renk Düzenleyicisi'ni kullanın.**  
  
 Renk Düzenleyicisi'ni başlatın ve yeni bir özel tema renkleri .xml dosyası oluşturun veya açın. Seçin **Düzenle > Yeni bir renk** menüsünde. Bu kategori belirtmek için bir iletişim kutusu ve bu kategorideki renk girişi için bir veya daha fazla adları açar:  
  
 ![VSIX renk Düzenleyicisi yeni renk](../../extensibility/internals/media/vsix-color-editor-new-color.png "VSIX renk Düzenleyicisi yeni rengi")  
  
 Var olan bir kategori seçin ya da seçin **yeni kategori** yeni bir kategori oluşturmak için. Yeni bir kategori adı oluşturma başka bir iletişim kutusunu açar:  
  
 ![VSIX renk Düzenleyicisi yeni kategori](../../extensibility/internals/media/vsix-color-editor-new-category.png "VSIX renk Düzenleyicisi yeni kategori")  
  
 Yeni kategori sonra kullanılabilir olacak **yeni renk** kategorisi açılır menüsünden. Bir kategori seçme sonra her yeni renk belirteci için satır başına bir ad girin ve "bittiğinde oluştur" seçeneğini belirleyin:  
  
 ![VSIX renk Düzenleyicisi yeni renk doldurulmuş](../../extensibility/internals/media/vsix-color-editor-new-color-filled.png "VSIX renk Düzenleyicisi yeni renk dolu")  
  
 Renk değerleri "Hiçbiri ile" rengi tanımlanmamış belirten arka plan/ön plan çiftler halinde gösterilir. Not: bir renk metin rengi/arka plan rengi çifti yoksa sonra yalnızca arka plan tanımlanması gerekiyor.  
  
 ![VSIX renk Düzenleyicisi renk değerleri](../../extensibility/internals/media/vsix-color-editor-color-values.png "VSIX renk Düzenleyicisi renk değerleri")  
  
 Bir renk belirteci düzenlemek için bu belirteci temasını (sütun) için bir renk girişi seçin. Renk değeri bir onaltılık renk değeri 8 basamaklı ARGB biçiminde yazarak, hücreye sistem renk adı girerek, veya istenen rengi renk kaydırıcılar kümesi ya da sistem renk listesi aracılığıyla seçmek için aşağı açılan menüsünü kullanarak ekleyin.  
  
 ![VSIX renk Düzenleyicisi'ni Düzenle renk](../../extensibility/internals/media/vsix-color-editor-edit-color.png "VSIX renk Düzenleyicisi'ni Düzenle rengi")  
  
 ![VSIX renk Düzenleyicisi arka plan](../../extensibility/internals/media/vsix-color-editor-background.png "VSIX renk Düzenleyicisi arka plan")  
  
 Metin görüntüleme gerekmez bileşenleri için yalnızca bir renk değeri girin: arka plan rengi. Aksi takdirde, eğik tarafından ayrılmış, arka plan ve metin rengi için değerler girin.  
  
 Değerleri için yüksek karşıtlık girerken, geçerli Windows sistem renk adlarını girin. Sabit kodlanmış ARGB değerlerini girmeyin. "Arka plan: Sistem" veya "Ön plan: Sistem" renk değeri açılan menülerden seçerek, geçerli sistem renk adlarının bir listesini görüntüleyebilirsiniz. Metin bileşenleriniz öğeleri oluştururken, doğru arka plan/metin sistem renk çifti kullanın veya metin okunamaz olabilir.  
  
 Renk belirteçlerini düzenleme oluşturma ve ayarlama bitirdikten sonra bunları istenen .xml ya da .pkgdef biçiminde kaydedin. Hiçbiri bir arka plan rengi belirteçler veya bir ön plan kümesi .xml biçiminde boş renkler olarak kaydedilir, ancak .pkgdef biçiminde atılır. Boş renkleri .pkgdef dosyaya kaydetmeyi denediğinizde bir iletişim kutusu, renk kaybı sizi uyarır.  
  
 **4. adım: Visual Studio Uzantısı'nda renkleri kullanın.**  
  
 Yeni bir renk tanımlama sonra belirteçleri, "" İçerik"ayarlanmış eylem derleme" ile proje dosyasında .pkgdef içerir ve "içinde VSIX dahil" "True" olarak ayarlayın  
  
 ![VSIX renk Düzenleyicisi pkgdef](../../extensibility/internals/media/vsix-color-editor-pkgdef.png "VSIX renk Düzenleyicisi pkgdef")  
  
 Visual Studio uzantısı renk Düzenleyicisi'nde bir dosya seçin > özel erişmek için kullanılan kod görüntülemek için kaynak kodu göster renkleri WPF tabanlı kullanıcı Arabirimi.  
  
 ![VSIX renk Düzenleyicisi kaynak kodu Görüntüleyicisi](../../extensibility/internals/media/vsix-color-editor-resource-code-viewer.png "VSIX renk Düzenleyicisi kaynak kodu Görüntüleyicisi")  
  
 Bu kod projesinde statik bir sınıf ekleyin. Bir başvuru **Microsoft.VisualStudio.Shell.\< VSVersion >.0.dll** kullanmak için proje eklenmesi gerekir **ThemeResourceKey** türü.  
  
```csharp  
namespace MyCustomColors  
{  
    public static class MyCategory  
    {  
        #region Autogenerated resource keys  
        // These resource keys are generated by Visual Studio Extension Color Editor, and should be replaced when new colors are added to this category.  
        public static readonly Guid Category = new Guid("faf7f3f9-9fe5-4dd3-9350-59679617dfbe");  
  
        private static ThemeResourceKey _MyColor1ColorKey;  
        private static ThemeResourceKey _MyColor1BrushKey;  
        private static ThemeResourceKey _MyColor1TextColorKey;  
        private static ThemeResourceKey _MyColor1TextBrushKey;  
        public static ThemeResourceKey MyColor1ColorKey { get { return _MyColor1ColorKey ?? (_MyColor1ColorKey = new ThemeResourceKey(Category, "MyColor1", ThemeResourceKeyType.BackgroundColor)); } }  
        public static ThemeResourceKey MyColor1BrushKey { get { return _MyColor1BrushKey ?? (_MyColor1BrushKey = new ThemeResourceKey(Category, "MyColor1", ThemeResourceKeyType.BackgroundBrush)); } }  
        public static ThemeResourceKey MyColor1TextColorKey { get { return _MyColor1TextColorKey ?? (_MyColor1TextColorKey = new ThemeResourceKey(Category, "MyColor1", ThemeResourceKeyType.ForegroundColor)); } }  
        public static ThemeResourceKey MyColor1TextBrushKey { get { return _MyColor1TextBrushKey ?? (_MyColor1TextBrushKey = new ThemeResourceKey(Category, "MyColor1", ThemeResourceKeyType.ForegroundBrush)); } }  
        #endregion  
    }  
}  
```  
  
 Bu, XAML kodu renkleri erişmesini sağlar ve tema değişikliklere için kullanıcı Arabirimi sağlar.  
  
```xaml  
<UserControl x:Class="NewTestProject.TestPackageControl" Name="MyToolWindow"  
             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
             xmlns:ns="clr-namespace:MyCustomColors">  
  <Grid>  
    <TextBlock Background="{DynamicResource {x:Static ns:MyCategory.MyColor1BrushKey}}"  
               Foreground="{DynamicResource {x:Static ns:MyCategory.MyColor1TextBrushKey}}"  
      >Sample Text</TextBlock>  
  
  </Grid>  
</UserControl>  
```  
  
 **5. adım: Visual Studio'da değişiklikleri sınayın.**  
  
 Renk Düzenleyicisi'ni geçici olarak renk belirteçleri uzantısı paketi derlenmeden renkleri için dinamik değişiklikleri görmek için Visual Studio çalışan örneklerini uygulayabilirsiniz. Bunu yapmak için her bir tema sütun üst bilgisinde bulunan "Visual Studio windows çalıştıran için bu temayı uygulamak" düğmesini tıklatın. VSIX renk Düzenleyicisi'ni kapatıldığında bu geçici tema kaybolur.  
  
 ![VSIX renk Düzenleyicisi'ni uygulamak](../../extensibility/internals/media/vsix-color-editor-apply.png "VSIX renk Düzenleyicisi Uygula")  
  
 Değişiklikleri kalıcı hale getirmek için yeniden oluşturun ve yeni renkler .pkgdef dosyasına ekleyip bu renkleri kullanacağı kod yazma sonra Visual Studio uzantısı yeniden dağıtın. Visual Studio uzantısı yeniden yeni renkler için kayıt defteri değerlerini temaları rest birleştirin. Visual Studio'yu yeniden başlatın, kullanıcı arabirimini görüntülemek ve yeni renkler beklendiği gibi göründüğünü doğrulayın.  
  
## <a name="notes"></a>Notlar  
 Bu aracı önceden var olan Visual Studio Temalar ya da özel bir Visual Studio Tema renkleri düzenleme için özel renkler oluşturmak için kullanılmak üzere tasarlanmıştır. Eksiksiz özel Visual Studio tema oluşturmak için Yükle [Visual Studio renkli tema Düzenleyicisi uzantısı](http://visualstudiogallery.msdn.microsoft.com/6f4b51b6-5c6b-4a81-9cb5-f2daa560430b) Visual Studio uzantıları galerisinden.  
  
## <a name="sample-output"></a>Örnek Çıktı  
 **XML renk çıktısı**  
  
 Aracı tarafından oluşturulan .xml dosyası aşağıdakine benzer olacaktır:  
  
```xml  
<Themes>  
  <Theme Name="Light" GUID="{de3dbbcd-f642-433c-8353-8f1df4370aba}">  
    <Category Name="CategoryName" GUID="{eee9d521-dac2-48d9-9a5e-5c625ba2040c}">  
      <Color Name="ColorName1">  
        <Background Type="CT_RAW" Source="FFFFFFFF" />  
      </Color>  
      <Color Name="ColorName2">  
        <Background Type="CT_RAW" Source="FFFFFFFF" />  
        <Foreground Type="CT_RAW" Source="FF000000" />  
      </Color>  
      <Color Name="ColorName3">  
        <Background Type="CT_RAW" Source="FFFF0000" />  
      </Color>  
      <Color Name="ColorName4">  
        <Background Type="CT_RAW" Source="FF000088" />  
        <Foreground Type="CT_RAW" Source="FFFFFFFF" />  
      </Color>  
    </Category>  
  </Theme>  
  <Theme Name="Dark" GUID="{1ded0138-47ce-435e-84ef-9ec1f439b749}">...</Theme>  
  <Theme Name="Blue" GUID="{a4d6a176-b948-4b29-8c66-53c97a1ed7d0}">...</Theme>  
  <Theme Name="HighContrast" GUID="{a5c004b4-2d4b-494e-bf01-45fc492522c7}">...</Theme>  
</Themes>  
  
```  
  
 **PKGDEF renk çıktısı**  
  
 Aracı tarafından oluşturulan .pkgdef dosyası aşağıdakine benzer olacaktır:  
  
```  
[$RootKey$\Themes\{de3dbbcd-f642-433c-8353-8f1df4370aba}\CategoryName]  
"Data"=hex:78,00,00,00,0b,00,00,00,01,00,00,00,21,d5,e9,ee,c2,da,d9,48,9a,5e,5c,62,5b,a2,04,0c,04,00,00,00,0a,00,00,00,43,6f,6c,6f,72,4e,61,6d,65,31,01,ff,ff,ff,ff,00,0a,00,00,00,43,6f,6c,6f,72,4e,61,6d,65,32,01,ff,ff,ff,ff,01,00,00,00,ff,0a,00,00,00,43,6f,6c,6f,72,4e,61,6d,65,33,01,ff,00,00,ff,00,0a,00,00,00,43,6f,6c,6f,72,4e,61,6d,65,34,01,00,00,88,ff,01,ff,ff,ff,ff  
[$RootKey$\Themes\{1ded0138-47ce-435e-84ef-9ec1f439b749}\CategoryName]  
"Data"=hex:...  
[$RootKey$\Themes\{a4d6a176-b948-4b29-8c66-53c97a1ed7d0}\CategoryName]  
"Data"=hex:...  
[$RootKey$\Themes\{a5c004b4-2d4b-494e-bf01-45fc492522c7}\CategoryName]  
"Data"=hex:...  
  
```  
  
 **C# kaynak anahtarları sarmalayıcı**  
  
 Aracı tarafından oluşturulan renk kaynak anahtarları, aşağıdakine benzer olacaktır:  
  
```csharp  
namespace MyNamespace  
{  
    public static class MyColors  
    {  
        #region Autogenerated resource keys  
        // These resource keys are generated by Visual Studio Extension Color Editor, and should be replaced when new colors are added to this category.  
  
        public static string ColorName1ColorKey { get { return "ColorName1ColorKey"; } }  
        public static string ColorName1BrushKey { get { return "ColorName1BrushKey"; } }  
  
        public static string ColorName2ColorKey { get { return "ColorName2ColorKey"; } }  
        public static string ColorName2BrushKey { get { return "ColorName2BrushKey"; } }  
        public static string ColorName2TextColorKey { get { return "ColorName2TextColorKey"; } }  
        public static string ColorName2TextBrushKey { get { return "ColorName2TextBrushKey"; } }  
  
        public static string ColorName3ColorKey { get { return "ColorName4ColorKey"; } }  
        public static string ColorName3BrushKey { get { return "ColorName4BrushKey"; } }  
        public static string ColorName3TextColorKey { get { return "ColorName4TextColorKey"; } }  
        public static string ColorName3TextBrushKey { get { return "ColorName4TextBrushKey"; } }  
        #endregion  
    }  
}  
```  
  
 **WPF kaynak sözlük sarmalayıcı**  
  
 Renk **ResourceDictionary** aracı tarafından üretilen anahtarlar aşağıdakine benzer olacaktır:  
  
```xaml  
<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:colors="clr-namespace:MyNamespace">  
  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName1BrushKey}" Color="#FFFFFFFF" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName1ColorKey}" A="255" R="255" G="255" B="255" />  
  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName2BrushKey}" Color="#FFFFFFFF" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName2ColorKey}" A="255" R="255" G="255" B="255" />  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName2TextBrushKey}" Color="#FF000000" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName2TextColorKey}" A="255" R="0" G="0" B="0" />  
  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName3BrushKey}" Color="#FFFF0000" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName3ColorKey}" A="255" R="255" G="0" B="0" />  
  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName4BrushKey}" Color="#FF000088" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName4ColorKey}" A="255" R="0" G="0" B="136" />  
  <SolidColorBrush x:Key="{x:Static colors:MyColors.ColorName4TextBrushKey}" Color="#FFFFFFFF" />  
  <Color x:Key="{x:Static colors:MyColors.ColorName4TextColorKey}" A="255" R="255" G="255" B="255" />  
</ResourceDictionary>  
```