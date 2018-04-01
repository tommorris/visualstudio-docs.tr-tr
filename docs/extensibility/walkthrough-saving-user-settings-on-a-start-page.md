---
title: 'İzlenecek yol: Bir başlangıç sayfasında kullanıcı ayarları kaydetme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 754b9bf3-8681-4c77-b0a4-09146a4e1d2d
caps.latest.revision: 18
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 16de0e205d71e2a71b14f523dedbb45354157355
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-saving-user-settings-on-a-start-page"></a>İzlenecek yol: Bir başlangıç sayfasında kullanıcı ayarlarını kaydetme
Kullanıcı ayarları için başlangıç sayfanızı devam edebilir. Bu kılavuzu izleyerek, kullanıcı bir düğmesine tıkladığında ve başlangıç sayfası yükleyen her zaman bu ayarı alır, bir ayar kayıt defterine kaydettiği bir denetim oluşturabilirsiniz. Başlangıç sayfası proje şablonu özelleştirilebilir kullanıcı denetimini içerir ve varsayılan başlangıç sayfası XAML denetleyen çağırır çünkü başlangıç sayfası kendisini değiştirmek gerekmez.  
  
 Bu kılavuzda örneği ayarları deposu örneğidir <xref:Microsoft.VisualStudio.Shell.Interop.IVsWritableSettingsStore> okuyan ve bunu çağrıldığında, aşağıdaki kayıt defteri konumuna Yazar arabirimi: HKCU\Software\Microsoft\VisualStudio\14.0\\  *CollectionName*  
  
 Visual Studio deneysel örneğinde çalışırken, ayarları deposu okur ve HKCU\Software\Microsoft\VisualStudio\14.0Exp için Yazar\\*CollectionName.*  
  
 Ayarlarını sürdürmek nasıl hakkında daha fazla bilgi için bkz: [genişletme kullanıcı ayarları ve seçenekleri](../extensibility/extending-user-settings-and-options.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
  
> [!NOTE]
>  Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
>   
>  Başlangıç sayfası proje şablonunu kullanarak indirebilirsiniz **Uzantı Yöneticisi**.  
  
## <a name="setting-up-the-project"></a>Proje ayarlama  
  
#### <a name="to-configure-the-project-for-this-walkthrough"></a>Bu kılavuz projeyi yapılandırmak için  
  
1.  Bölümünde açıklandığı gibi bir başlangıç sayfası projesi oluşturma [bir özel başlangıç sayfası oluşturma](creating-a-custom-start-page.md). Proje adı **SaveMySettings**.  
  
2.  İçinde **Çözüm Gezgini**, aşağıdaki StartPageControl proje derleme başvuruları ekleyin:  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.OLE.Interop  
  
    -   Microsoft.VisualStudio.Shell.Interop.11.0  
  
3.  MyControl.xaml açın.  
  
4.  XAML bölmesinden, üst düzey <xref:System.Windows.Controls.UserControl> öğesi tanımı, aşağıdaki olay bildirimi ad alanı bildirimlerinden sonra ekleyin.  
  
    ```  
    Loaded="OnLoaded"  
    ```  
  
5.  Tasarım bölmesinde denetimi ana bölümünü tıklatın ve DELETE tuşlarına basın.  
  
     Bu kaldırır <xref:System.Windows.Controls.Border> öğesi ve her şeyi ve yalnızca en üst düzey bırakır <xref:System.Windows.Controls.Grid> öğesi.  
  
6.  Gelen **araç**, sürükleyin bir <xref:System.Windows.Controls.StackPanel> denetimi kılavuza.  
  
7.  Şimdi sürükleyin bir <xref:System.Windows.Controls.TextBlock>, <xref:System.Windows.Controls.TextBox>, bir düğmeyi ve <xref:System.Windows.Controls.StackPanel>.  
  
8.  Ekleme bir **x: Name** için öznitelik <xref:System.Windows.Controls.TextBox>ve bir `Click` olayı için <xref:System.Windows.Controls.Button>, aşağıdaki örnekte gösterildiği gibi.  
  
    ```xml  
    <StackPanel Width="300" HorizontalAlignment="Center" VerticalAlignment="Center">  
        <TextBlock Width="140" FontSize="14">Enter your setting</TextBlock>  
        <TextBox x:Name="txtblk" Margin="0, 5, 0, 10" Width="140" />  
        <Button Click="Button_Click" Width="100">Save My Setting</Button>  
    </StackPanel>  
    ```  
  
## <a name="implementing-the-user-control"></a>Kullanıcı denetimini uygulama  
  
#### <a name="to-implement-the-user-control"></a>Kullanıcı denetimi için  
  
1.  XAML bölmesinde, `Click` özniteliği <xref:System.Windows.Controls.Button> öğesi ve ardından **olay işleyicisi Git**.  
  
     Bu MyControl.xaml.cs açar ve bir saplama işleyicisi oluşturur `Button_Click` olay.  
  
2.  Aşağıdakileri ekleyin `using` deyimlerini dosyanın en üstüne ekleyin.  
  
     [!code-csharp[StartPageDTE#11](../extensibility/codesnippet/CSharp/walkthrough-saving-user-settings-on-a-start-page_1.cs)]  
  
3.  Özel eklemek `SettingsStore` aşağıdaki örnekte gösterildiği gibi özelliği.  
  
    ```csharp  
    private IVsWritableSettingsStore _settingsStore = null;  
    private IVsWritableSettingsStore SettingsStore  
    {  
        get  
        {  
            if (_settingsStore == null)  
            {  
                // Get a reference to the DTE from the DataContext.   
                var typeDescriptor = DataContext as ICustomTypeDescriptor;  
                var propertyCollection = typeDescriptor.GetProperties();  
                var dte = propertyCollection.Find("DTE", false).GetValue(  
                    DataContext) as DTE2;  
  
                // Get the settings manager from the DTE.   
                var serviceProvider = new ServiceProvider(  
                    (Microsoft.VisualStudio.OLE.Interop.IServiceProvider)dte);  
                var settingsManager = serviceProvider.GetService(  
                    typeof(SVsSettingsManager)) as IVsSettingsManager;  
  
                // Write the user settings to _settingsStore.  
                settingsManager.GetWritableSettingsStore(  
                    (uint)__VsSettingsScope.SettingsScope_UserSettings,  
                    out _settingsStore);  
            }  
            return _settingsStore;  
        }  
    }  
    ```  
  
     Bu özellik ilk önce bir başvuru edinir <xref:EnvDTE80.DTE2> Otomasyon nesne modeli içerir arabirimi <xref:System.Windows.FrameworkElement.DataContext%2A> kullanıcı denetimi ve ardından kullanır örneği alınacağı DTE <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsManager> arabirimi. Daha sonra geçerli kullanıcı ayarları döndürmek için bu örneğini kullanır.  
  
4.  Doldurmak `Button_Click` şekilde olay.  
  
    ```csharp  
    private void Button_Click(object sender, RoutedEventArgs e)  
    {  
        int exists = 0;  
        SettingsStore.CollectionExists("MySettings", out exists);  
        if (exists != 1)  
        {  
            SettingsStore.CreateCollection("MySettings");  
        }  
        SettingsStore.SetString("MySettings", "MySetting", txtblk.Text);  
    }  
    ```  
  
     Bu kayıt defteri "MySettings" koleksiyonunda "MySetting" alanına metin kutusunun içeriğini yazar. Koleksiyon yoksa, oluşturulur.  
  
5.  Aşağıdaki işleyicisi ekleme `OnLoaded` kullanıcı denetiminin olay.  
  
    ```csharp  
    private void OnLoaded(Object sender, RoutedEventArgs e)  
    {  
        string value;  
        SettingsStore.GetStringOrDefault(  
            "MySettings", "MySetting", "", out value);  
        txtblk.Text = value;  
    }  
    ```  
  
     Bu metni metin kutusunun geçerli "MySetting" değerine ayarlar.  
  
6.  Kullanıcı denetimi oluşturmak.  
  
7.  İçinde **Çözüm Gezgini**, source.extension.vsixmanifest açın.  
  
8.  Bildirim düzenleyicisinde ayarlama **ürün adı** için **My ayarları başlangıç sayfası kaydetmek**.  
  
     Görünmesi olduğu gibi bu başlangıç sayfası adını ayarlar **başlangıç sayfasını özelleştirme** listesinde **seçenekleri** iletişim kutusu.  
  
9. StartPage.xaml oluşturun.  
  
## <a name="testing-the-control"></a>Denetim test etme  
  
#### <a name="to-test-the-user-control"></a>Kullanıcı denetimi sınamak için  
  
1.  F5 tuşuna basın.  
  
     Visual Studio Deneysel örneğini açar.  
  
2.  Deneysel örneğinde üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.  
  
3.  İçinde **ortam** düğümü tıklatın **başlangıç**ve ardından **başlangıç sayfasını özelleştirme** listesinden, **[uzantısı yüklü] Kaydet My ayarları başlangıç sayfası** .  
  
     **Tamam**'ı tıklatın.  
  
4.  Başlangıç sayfası açıksa ve ardından kapatmak **Görünüm** menüsünde tıklatın **başlangıç sayfası**.  
  
5.  Başlangıç sayfasında, tıklatın **Denetimim** sekmesi.  
  
6.  Metin kutusuna **kat**ve ardından **Kaydet My ayarı**.  
  
7.  Başlangıç sayfasını kapatın ve yeniden açın.  
  
     Word "Kat" metin kutusunda görüntülenmesi gerekir.  
  
8.  "Kat" word "Köpek" word ile değiştirin. Düğmesini değil.  
  
9. Başlangıç sayfasını kapatın ve yeniden açın.  
  
     Ayarı olmayan kaydedilmiş olsa da metin kutusuna "Köpek" word görüntülenmesi gerekir. Visual Studio aracı windows bellekte tuttuğu için Visual Studio kendisini kapatılana kadar bunlar kapalı olduğundan olsa bile bu gerçekleşir.  
  
10. Visual Studio Deneysel örneklerini kapatın.  
  
11. Deneysel örneğini yeniden açmak için F5 tuşuna basın.  
  
12. Word "Kat" metin kutusunda görüntülenmesi gerekir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Kaydetmek ve herhangi bir sayıda özel ayarları almak ve ayarlamak için farklı olay işleyicileri farklı değerleri kullanarak almak için bu kullanıcı denetimi değiştirebileceğiniz `SettingsStore` özelliği. Farklı bir kullandığınız sürece `propertyName` her çağrı için parametre <xref:Microsoft.VisualStudio.Shell.Interop.IVsWritableSettingsStore.SetString%2A>, değerleri birbirine kayıt defterinde üzerine yazmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:EnvDTE80.DTE2?displayProperty=fullName>     
 [Başlangıç Sayfasına Visual Studio Komutları Ekleme](../extensibility/adding-visual-studio-commands-to-a-start-page.md)