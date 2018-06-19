---
title: WPF araç kutusu denetimi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- toolbox control
- toolbox
- wpf
ms.assetid: 9cc34db9-b0d1-4951-a02f-7537fbbb51ad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0b8bfbde2459998f13b8b19b17cfecba172538aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107809"
---
# <a name="creating-a-wpf-toolbox-control"></a>WPF araç kutusu denetimi oluşturma
WPF (Windows Presentation Framework) araç kutusu denetim şablonu, otomatik olarak eklenir WPF denetimleri oluşturmanıza olanak tanır **araç** uzantısı yüklü olduğunda. Bu konuda şablonu oluşturmak için nasıl kullanılacağı gösterilmektedir bir **araç** denetim diğer kullanıcılara dağıtabilirsiniz.  
  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-wpf-toolbox-control"></a>WPF araç kutusu denetimi oluşturma  
  
#### <a name="create-an-extension-with-a-wpf-toolbox-control"></a>Uzantı ile WPF araç kutusu denetimi oluşturma  
  
1.  Adlı VSIX proje oluşturma `MyToolboxControl`. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Proje açıldığında eklemek bir **WPF araç kutusu denetimi** öğesi şablonuna `MyToolboxControl`. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **WPF araç kutusu denetimi**. İçinde **adı** alan penceresinin alt kısmında, komut dosyası adı Değiştir `MyToolboxControl.cs`.  
  
     Çözüm şimdi bir kullanıcı denetimini içeren bir `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> denetimine ekler **araç**ve bir **Microsoft.VisualStudio.ToolboxControl** için VSIX bildiriminde varlık girişi  dağıtımı.  
  
#### <a name="to-create-the-control-ui"></a>UI denetimi oluşturmak için  
  
1.  MyToolboxControl.xaml tasarımcısında açın.  
  
     Tasarımcı gösterir bir <xref:System.Windows.Controls.Grid> içeren denetimi bir <xref:System.Windows.Controls.Button> denetim.  
  
2.  Kılavuz düzeni düzenleyin. Seçtiğinizde, <xref:System.Windows.Controls.Grid> denetlemek, üst ve sol kenarlarının ızgaranın üzerinde mavi denetim çubukları görüntülenir. Çubukları tıklatarak kılavuza satırları ve sütunları ekleyebilirsiniz.  
  
3.  Alt denetimler kılavuzuna ekleyin. Buradan sürükleyerek bir alt denetim yerleştirebilirsiniz **araç** bir bölüme kılavuza veya ayarlayarak kendi `Grid.Row` ve `Grid.Column` XAML öznitelikleri. Aşağıdaki örnek, kılavuz ve ikinci satırında düğmesinde üst satırda iki etiketleri ekler.  
  
    ```xaml  
    <Grid>  
        <Label Grid.Row="0" Grid.Column="0" Name="label1" />  
        <Label Grid.Row="0" Grid.Column="1" Name="label2" />  
        <Button Name="button1" Click="button1_Click" Grid.Row="1" Grid.ColumnSpan="2" />  
    </Grid>  
    ```  
  
## <a name="renaming-the-control"></a>Denetimi yeniden adlandırma  
 Denetim görünür varsayılan olarak, **araç** olarak **MyToolboxControl** adlı bir grup içindeki **MyToolboxControl.MyToolboxControl**. Bu adları MyToolboxControl.xaml.cs dosyasında değiştirebilirsiniz.  
  
1.  MyToolboxControl.xaml.cs kod görünümünde açın.  
  
2.  MyToolboxControl sınıfı bulmak ve TestControl için yeniden adlandırın. (Bunu yapmak için en hızlı sınıfı yeniden adlandırmak için yoludur seçip **yeniden adlandırma** ve bağlam menüsünden ve adımları tamamlayın. (Hakkında daha fazla bilgi için **yeniden adlandırma** komutu, bkz: [yeniden adlandırma yeniden düzenlemesi (C#)](../ide/reference/rename.md).)
  
3.  Git `ProvideToolboxControl` özniteliği ve ilk parametresinin değerini değiştirin **Test**. Denetimde içerecek grubunun adıdır **araç**.  
  
     Sonuçta elde edilen kod gibi görünmelidir:  
  
    ```csharp  
    [ProvideToolboxControl("Test", true)]  
    public partial class TestControl : UserControl  
    {  
        public TestControl()  
        {  
            InitializeComponent();  
        }  
    }  
    ```  
  
## <a name="building-testing-and-deployment"></a>Derleme, test ve dağıtım  
 Projenin hata ayıklamasını yaparken, yüklü denetim bulmalısınız **araç** Visual Studio Deneysel örneğinin.  
  
#### <a name="to-build-and-test-the-control"></a>Derleme ve denetim sınamak için  
  
1.  Projeyi oluşturmak ve hata ayıklamayı Başlat.  
  
2.  Visual Studio yeni örneğini bir WPF uygulaması projesi oluşturun. XAML Tasarımcısı'nı açık olduğundan emin olun.  
  
3.  Denetiminde Bul **araç** ve tasarım yüzeyine sürükleyin.  
  
4.  WPF uygulaması hata ayıklamayı Başlat.  
  
5.  Denetim göründüğünden emin olun.  
  
#### <a name="to-deploy-the-control"></a>Denetim dağıtmak için  
  
1.  Sınanan Projeyi derledikten sonra .vsix dosyasını proje \bin\debug\ klasöründe bulabilirsiniz.  
  
2.  Yerel bir bilgisayarda .vsix dosyasını çift tıklayıp aşağıdaki yükleme yordamı yükleyebilirsiniz. Denetim kaldırmak için şu adrese gidin **Araçlar / Uzantılar ve güncelleştirmeler** ve denetim uzantısı arayın ve ardından **kaldırma**.  
  
3.  Bir ağ veya Web sitesine .vsix dosyasını karşıya yükleyin.  
  
     Dosyaya yüklerseniz [Visual Studio Galerisi](http://go.microsoft.com/fwlink/?LinkID=123847) Web sitesinin diğer kullanıcıların kullanabileceği **Araçlar / Uzantılar ve güncelleştirmeler** denetim çevrimiçi bulmak ve yüklemek için Visual Studio'da.