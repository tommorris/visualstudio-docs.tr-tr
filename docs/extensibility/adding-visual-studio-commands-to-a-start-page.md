---
title: "Visual Studio komut için başlangıç sayfası ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- start page commands
- vs:VSCommands
ms.assetid: a8e2765c-cfb5-47b5-a414-6e48b434e0c2
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: efb332de822bd86cc95c4786dbca3472fd0984cc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-visual-studio-commands-to-a-start-page"></a>Başlangıç sayfası için Visual Studio komut ekleme
Özel bir başlangıç sayfası oluşturduğunuzda, Visual Studio komutları ekleyebilirsiniz. Bu belge, başlangıç sayfasında XAML nesneleri Visual Studio komutları bağlamak için farklı yolları açıklanmaktadır.  
  
 XAML'de komutları hakkında daha fazla bilgi için bkz: [kumanda genel bakış](/dotnet/framework/wpf/advanced/commanding-overview)  
  
## <a name="adding-commands-from-the-command-well"></a>İyi komutundan komut ekleme  
 Başlangıç sayfası oluşturulan [bir özel başlangıç sayfası oluşturma](../extensibility/creating-a-custom-start-page.md) eklenen <xref:Microsoft.VisualStudio.PlatformUI?displayProperty=fullName> ve <xref:Microsoft.VisualStudio.Shell?displayProperty=fullName> şekilde ad alanları.  
  
```  
xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
```  
  
 Başka bir ad alanı için Microsoft.VisualStudio.Shell Microsoft.VisualStudio.Shell.Immutable.11.0.dll derlemesinden ekleyin. (Bu derlemesine başvuru projenize eklemeniz gerekebilir.)  
  
```xml  
xmlns:vscom="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.11.0"  
```  
  
 Kullanabileceğiniz `vscom:` XAML için Visual Studio komutları bağlamak için diğer ad ayarlayarak sayfadaki denetimleri <xref:System.Windows.Controls.Primitives.ButtonBase.Command%2A> denetiminin özelliği `vscom:VSCommands.ExecuteCommand`. Ardından ayarlayabilirsiniz <xref:System.Windows.Controls.Primitives.ButtonBase.CommandParameter%2A> özelliğine, aşağıdaki örnekte gösterildiği gibi yürütülecek komut adı.  
  
```xml  
<Button Name="btnNewProj" Content="New Project"   
    Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
    CommandParameter="File.NewProject" >  
</Button>  
```  
  
> [!NOTE]
>  `x:` XAML şema başvuruyor, diğer tüm komutlar, başında gereklidir.  
  
 Değerini ayarlayabilirsiniz `Command` erişilebilen herhangi bir komuttan özelliğine **komutu** penceresi. Kullanılabilir komutlar listesi için bkz: [Visual Studio komut diğer adları](../ide/reference/visual-studio-command-aliases.md).  
  
 Eklemek için komutu ek parametre gerektiriyorsa, değerine ekleyebilirsiniz `CommandParameter` özelliği. Aşağıdaki örnekte gösterildiği gibi alanları kullanarak komutları ayrı parametrelerinden.  
  
```xml  
<Button Content="Web Search"   
        Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
        CommandParameter="View.WebBrowser www.bing.com" />  
```  
  
### <a name="calling-extensions-from-the-command-well"></a>Uzantıları komuttan iyi çağırma  
 Diğer Visual Studio komutları çağırmak için kullanılan aynı sözdizimini kullanarak kayıtlı VSPackages komutları çağırabilir. Yüklü bir VSPackage eklerse, örneğin, bir **giriş sayfası** komutu **Görünüm** menüsünde ayarlayarak bu komutunu çağırabilir `CommandParameter` için `View.HomePage`.  
  
> [!NOTE]
>  Komutu çağrıldığında VSPackage ile ilişkili olan bir komutun çağırırsanız, paketin yüklenmesi gerekir.  
  
## <a name="adding-commands-from-assemblies"></a>Derlemelerden komut ekleme  
 Bir komut bir derlemeden veya menü komutu ile ilişkilendirilmemiş bir VSPackage erişim kodunda çağırmak için derleme için bir diğer ad oluşturmalı ve diğer çağırın.  
  
#### <a name="to-call-a-command-from-an-assembly"></a>Bir derlemeye ait bir komutu çağırmak için  
  
1.  Çözümünüze derlemesine başvuru ekleyin.  
  
2.  Aşağıdaki örnekte gösterildiği gibi StartPage.xaml dosyanın üst kısmında, derleme için bir ad alanı yönergesi ekleyin.  
  
    ```xml  
    xmlns:vsc="clr-namespace:WebUserControl;assembly=WebUserControl"  
    ```  
  
3.  Komut ayarlayarak çağırma `Command` aşağıdaki örnekte gösterildiği gibi XAML nesnesinin özelliği.  
  
     XAML  
  
    ```  
    <vs:Button Text="Hide me" Command="{x:Static vsc:HideControl}" .../>  
    ```  
  
> [!NOTE]
>  Derlemenizi kopyalayın ve ardından yapıştırın... \\ *Visual Studio yükleme klasörü*\Common7\IDE\PrivateAssemblies\ onu çağrılmadan önce yüklendiği emin olun.  
  
## <a name="adding-commands-with-the-dte-object"></a>DTE nesnesiyle komut ekleme  
 Bir başlangıç sayfası, biçimlendirme hem kod DTE nesnesine erişebilirsiniz.  
  
 Biçimlendirme içinde kullanarak erişebildiğinizi [biçimlendirme uzantısı bağlama](/dotnet/framework/wpf/advanced/binding-markup-extension) çağırmak için sözdizimi <xref:EnvDTE.DTE> nesnesi. Koleksiyonları döndüren olanlar gibi basit özellikler bağlamak için bu yaklaşım kullanabilirsiniz, ancak yöntemler veya hizmetlerine bağlanamaz. Aşağıdaki örnekte gösterildiği bir <xref:System.Windows.Controls.TextBlock> bağlar denetim <xref:EnvDTE._DTE.Name%2A> özelliği ve <xref:System.Windows.Controls.ListBox> numaralandırır denetim <xref:EnvDTE.Window.Caption%2A> tarafından döndürülen koleksiyon özelliklerini <xref:EnvDTE._DTE.Windows%2A> özelliği.  
  
```xml  
<TextBlock Text="{Binding Path=DTE.Name}" FontSize="12" HorizontalAlignment="Center"/>  
<ListBox ItemsSource="{Binding Path=DTE.Windows}">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <TextBlock Text="{Binding Path=Caption}"/>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
</ListBox  
```  
  
 Bir örnek için bkz: [izlenecek yol: bir başlangıç sayfası kullanıcı ayarları kaydetme](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlangıç Sayfasına Kullanıcı Denetimi Ekleme](../extensibility/adding-user-control-to-the-start-page.md)