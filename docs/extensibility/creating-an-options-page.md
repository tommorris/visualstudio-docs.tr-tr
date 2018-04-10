---
title: Seçenekler sayfası oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], creating
ms.assetid: 9f4e210c-4b47-4daa-91fa-1c301c4587f9
caps.latest.revision: 62
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d0888a584e31c26c9f64cdcff70cc2f5dc8a1453
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="creating-an-options-page"></a>Seçenekler sayfası oluşturma
Bu kılavuzda inceleyebilir ve özelliklerini ayarlamak için özellik kılavuzunu kullanan basit bir Araçlar/Seçenekler sayfası oluşturur.  
  
 Bu özellikler kaydetmek ve ayarları dosyasından geri yüklemek için aşağıdaki adımları izleyin ve sonra bkz [ayarları kategorisi oluşturma](../extensibility/creating-a-settings-category.md).  
  
 Araçlar Seçenekler sayfalar oluşturmanıza yardımcı olmak üzere iki sınıf MPF sağlar <xref:Microsoft.VisualStudio.Shell.Package> sınıfı ve <xref:Microsoft.VisualStudio.Shell.DialogPage> sınıfı. Paket sınıfı sınıflara göre bu sayfaları için bir kapsayıcı sağlamak için bir VSPackage oluşturun. DialogPage sınıfından türetilen her Araçlar Seçenekler sayfası oluşturun.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-tools-options-grid-page"></a>Araçlar Seçenekler kılavuz sayfası oluşturma  
 Bu bölümde, bir basit Araçlar Seçenekler özellik Kılavuzu oluşturun. Görüntülemek ve bir özelliğin değerini değiştirmek için bu kılavuzu kullanın.  
  
#### <a name="to-create-the-vsix-project-and-add-a-vspackage"></a>VSIX proje oluşturmak ve bir VSPackage eklemek için  
  
1.  Visual Studio uzantılarının uzantısı varlıklar yer alacağı VSIX dağıtım projesi ile başlar. Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adlı VSIX proje `MyToolsOptionsExtension`. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Adlı bir Visual Studio Paketi öğesi şablonu ekleyerek bir VSPackage `MyToolsOptionsPackage`. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle iletişim**gidin **Visual C# öğeleri / genişletilebilirlik** seçip **Visual Studio Paketi**. İçinde **adı** alan iletişim kutusunun en altında dosya adını değiştirmek `MyToolsOptionsPackage.cs`. Bir VSPackage oluşturma hakkında daha fazla bilgi için bkz: [bir uzantısı ile VSPackage oluşturma](../extensibility/creating-an-extension-with-a-vspackage.md).  
  
#### <a name="to-create-the-tools-options-property-grid"></a>Araçlar Seçenekler özellik kılavuzu oluşturmak için  
  
1.  MyToolsOptionsPackage dosyasını Kod düzenleyicisinde açın.  
  
2.  Aşağıdaki ekleme deyimini kullanarak.  
  
    ```csharp  
    using System.ComponentModel;  
    ```  
  
3.  Bir OptionPageGrid sınıf bildirme ve buradan türetebilir <xref:Microsoft.VisualStudio.Shell.DialogPage>.  
  
    ```csharp  
    public class OptionPageGrid : DialogPage  
    {  }  
    ```  
  
4.  Geçerli bir <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> sınıfına bir seçenekleri kategorisi ve OptionPageGrid için seçenekler sayfası adı atamak için VSPackage sınıfı. Sonuç aşağıdaki gibi görünmelidir:  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [Guid(GuidList.guidMyToolsOptionsPkgString)]  
    [ProvideOptionPage(typeof(OptionPageGrid),  
        "My Category", "My Grid Page", 0, 0, true)]  
    public sealed class MyToolsOptionsPackage : Package  
    ```  
  
5.  Ekleme bir `OptionInteger` özelliğine `OptionPageGrid` sınıfı.  
  
    -   Geçerli bir <xref:System.ComponentModel.CategoryAttribute?displayProperty=fullName> özelliği kılavuz kategori özelliğine atama.  
  
    -   Geçerli bir <xref:System.ComponentModel.DisplayNameAttribute?displayProperty=fullName> özelliği için bir ad atamak için.  
  
    -   Geçerli bir <xref:System.ComponentModel.DescriptionAttribute?displayProperty=fullName> özelliği için bir açıklama atamaya.  
  
    ```csharp  
    public class OptionPageGrid : DialogPage  
    {  
        private int optionInt = 256;  
  
        [Category("My Category")]  
        [DisplayName("My Integer Option")]  
        [Description("My integer option")]  
        public int OptionInteger  
        {  
            get { return optionInt; }  
            set { optionInt = value; }  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  Varsayılan uygulaması <xref:Microsoft.VisualStudio.Shell.DialogPage> uygun dönüştürücüleri sahip olan veya yapıları veya uygun dönüştürücüleri sahip özelliklerini Genişletilebilir diziler özelliklerini destekler. Dönüştürücü bir listesi için bkz: <xref:System.ComponentModel> ad alanı.  
  
6.  Projeyi derleyin ve hata ayıklamayı Başlat.  
  
7.  Visual Studio deneysel örneğinde üzerinde **Araçları** menüsünü tıklatın **seçenekleri**.  
  
     Sol bölmede görmelisiniz **My kategori**. (Bunu hakkında yarı yarıya listede aşağı görünmesi gereken şekilde seçenekleri kategoriler alfabetik sırada listelenir.) Açık **My kategori** ve ardından **kılavuz sayfam**. Seçenekler kılavuz sağ bölmede görüntülenir. Özellik kategori **My seçenekleri**, özellik adı **My tamsayı seçeneği**. Özellik açıklaması **benim tamsayı seçeneğini**, bölmesinin en altında görüntülenir. Değer 256'ın başlangıç değerinden başka bir şey için değiştirin. Tıklatın **Tamam**ve ardından yeniden **kılavuz sayfam**. Yeni değer devam ettiğini görebilirsiniz.  
  
     Seçenekler sayfası, Visual Studio'nun hızlı başlatma kullanılabilir. IDE'nin sağ üst köşesindeki hızlı başlatma penceresinde yazın **My kategori** ve görürsünüz **My kategori kılavuz sayfam ->** açılır listede.  
  
## <a name="creating-a-tools-options-custom-page"></a>Araçlar Seçenekler özel oluşturma sayfası  
 Bu bölümde, özel bir kullanıcı Arabirimi ile bir Araçlar Seçenekler sayfası oluşturun. Görüntülemek ve bir özelliğin değerini değiştirmek için bu sayfayı kullanın.  
  
1.  MyToolsOptionsPackage dosyasını Kod düzenleyicisinde açın.  
  
2.  Aşağıdaki ekleme deyimini kullanarak.  
  
    ```vb  
    using System.Windows.Forms;  
    ```  
  
3.  Ekleme bir `OptionPageCustom` sınıfı, hemen önce `OptionPageGrid` sınıfı. Yeni sınıfından türetilen `DialogPage`.  
  
    ```csharp  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
    }  
    ```  
  
4.  GUID özniteliğini ekleyin. Bir OptionString özelliği ekleyin:  
  
    ```csharp  
    [Guid("00000000-0000-0000-0000-000000000000")]  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
    }  
    ```  
  
5.  İkinci bir uygulama <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> VSPackage sınıfı. Bu öznitelik sınıfı bir seçenekleri kategorisi ve seçenekleri sayfa adı atar.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [Guid(GuidList.guidMyToolsOptionsPkgString)]  
    [ProvideOptionPage(typeof(OptionPageGrid),  
        "My Category", "My Grid Page", 0, 0, true)]  
    [ProvideOptionPage(typeof(OptionPageCustom),  
        "My Category", "My Custom Page", 0, 0, true)]  
    public sealed class MyToolsOptionsPackage : Package  
    ```  
  
6.  Yeni bir ekleme **kullanıcı denetimi** projeye MyUserControl adlı.  
  
7.  Ekleme bir **TextBox** kullanıcı denetimi için denetim.  
  
     İçinde **özellikleri** araç penceresi tıklatın **olayları** düğmesine tıklayın ve ardından **bırakın** olay. Yeni olay işleyicisi MyUserControl.cs kodu görüntülenir.  
  
8.  Genel ekleme `OptionsPage` alan, bir `Initialize` control sınıfı ve güncelleştirme seçeneğini ayarlamak için olay işleyicisini değeri metin kutusunun içeriğini yöntemi:  
  
    ```csharp  
    public partial class MyUserControl : UserControl  
    {  
        public MyUserControl()  
        {  
            InitializeComponent();  
        }  
  
        internal OptionPageCustom optionsPage;  
  
        public void Initialize()  
        {  
            textBox1.Text = optionsPage.OptionString;  
        }  
  
        private void textBox1_Leave(object sender, EventArgs e)  
        {  
            optionsPage.OptionString = textBox1.Text;  
        }  
    }  
    ```  
  
     `optionsPage` Alan tutan bir üst başvuru `OptionPageCustom` örneği. `Initialize` Yöntemi görüntüler `OptionString` içinde **TextBox**. Olay işleyicisi geçerli değeri Yazar **TextBox** için `OptionString` bırakır'ne zaman odaklanmak **TextBox**.  
  
9. Paket kod dosyası için bir geçersiz kılma ekleyip `OptionPageCustom.Window` OptionPageCustom sınıfının bir örneğini döndürmek oluşturma ve başlatma özelliğine `MyUserControl`. Sınıf gibi görünmelidir:  
  
    ```csharp  
    [Guid("00000000-0000-0000-0000-000000000000")]  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
  
        protected override IWin32Window Window  
        {  
            get  
            {  
                MyUserControl page = new MyUserControl();  
                page.optionsPage = this;  
                page.Initialize();  
                return page;  
            }  
        }  
    }  
    ```  
  
10. Oluşturun ve projeyi çalıştırın.  
  
11. Deneysel örneğinde tıklatın **Araçlar / Seçenekler**.  
  
12. Bul **My kategori** ve ardından **özel sayfa**.  
  
13. Değerini değiştirme **OptionString**. Tıklatın **Tamam**ve ardından yeniden **özel sayfam**. Yeni değer kaydetti görebilirsiniz.  
  
## <a name="accessing-options"></a>Erişilebilirlik Seçenekleri  
 Bu bölümde, ilişkili Araçlar Seçenekler sayfası barındıran VSPackage bir seçenek değerini alın. Aynı tekniği herhangi bir ortak özellik değeri elde etmek için kullanılabilir.  
  
1.  Adlı bir ortak özellik paketi kod dosyasına ekleyin **OptionInteger** için **MyToolsOptionsPackage** sınıfı.  
  
    ```  
    public int OptionInteger  
    {  
        get  
        {  
            OptionPageGrid page = (OptionPageGrid)GetDialogPage(typeof(OptionPageGrid));  
            return page.OptionInteger;  
        }  
    }  
  
    ```  
  
     Bu kod çağırır <xref:Microsoft.VisualStudio.Shell.Package.GetDialogPage%2A> oluşturmak veya almak için bir `OptionPageGrid` örneği. `OptionPageGrid` çağrıları <xref:Microsoft.VisualStudio.Shell.DialogPage.LoadSettingsFromStorage%2A> ortak özellikleri onun seçeneklerini yüklenemiyor.  
  
2.  Şimdi adlı bir özel komut öğesi şablonu Ekle **MyToolsOptionsCommand** değerini görüntülemek için. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **özel komut**. İçinde **adı** alan penceresinin alt kısmında, komut dosyası adı Değiştir **MyToolsOptionsCommand.cs**.  
  
3.  MyToolsOptionsCommand dosyasında komutunun gövdesini değiştirin `ShowMessageBox` aşağıdaki yöntemiyle:  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        MyToolsOptionsPackage myToolsOptionsPackage = this.package as MyToolsOptionsPackage;  
        System.Windows.Forms.MessageBox.Show(string.Format(CultureInfo.CurrentCulture, "OptionInteger: {0}", myToolsOptionsPackage.OptionInteger));  
    }  
  
    ```  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat.  
  
5.  Deneysel örneğinde üzerinde **Araçları** menüsünde tıklatın **çağırma MyToolsOptionsCommand**.  
  
     Geçerli değeri bir ileti kutusu görüntüler `OptionInteger`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçenekler ve Seçenekler Sayfaları](../extensibility/internals/options-and-options-pages.md)