---
title: ".NET Framework 4 veya .NET Framework 4. 5'e geçiş Office projelerindeki Şerit Özelleştirmelerini Güncelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 4d3c2e834b3a618bf033ef7f37ca8bbac7d0efcf
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>.NET Framework 4 veya .NET Framework 4.5'e Geçirdiğiniz Office Projelerindeki Şerit Özelleştirmelerini Güncelleştirme
  Projenizi kullanılarak oluşturulmuş bir Şerit özelleştirme içeriyorsa **Şerit (Görsel Tasarımcı)** proje madde, hedef Framework'ü değiştirilirse proje kodunuza aşağıdaki değişiklikleri yapmalısınız [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya Daha sonra.  
  
-   Oluşturulmuş Şerit kodunu değiştirin.  
  
-   Şerit denetimlerini çalışma zamanında başlatır, Şerit olaylarını işleme veya program aracılığıyla bir Şerit bileşeninin konumunu ayarlar herhangi bir kodu değiştirin.  
  
## <a name="updating-the-generated-ribbon-code"></a>Oluşturulmuş Şerit kodunu güncelleme  
 Projenizin hedef çerçevesini değiştirilirse [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra aşağıdaki adımları gerçekleştirerek Şerit öğesi için oluşturulan kodu değiştirmeniz gerekir. Güncelleştirmek için gereken kod dosyaları programlama dili ve projeyi nasıl oluşturulacağını bağlıdır:  
  
-   Visual Basic projeleri veya ya da oluşturulan Visual C# projeleri [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] veya [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)] Şerit arka plan kodu dosyasındaki tüm adımları gerçekleştirin (*ŞeritÖğeniz*. Designer.cs veya *ŞeritÖğeniz*. Designer.vb olarak adlandırılır). Visual Basic projeleri arka plan kod dosyasına görmek için tıklatın **tüm dosyaları göster** düğmesini **Çözüm Gezgini**.  
  
-   Visual Studio 2008'de oluşturulan ve ardından yükseltildiğinde Visual C# projelerine [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], Şerit kod dosyasında ilk iki adımı gerçekleştirin (*ŞeritÖğeniz*.cs veya *ŞeritÖğeniz*.vb), ve Şerit arka plan kodu dosyasındaki kalan adımları gerçekleştirin.  
  
#### <a name="to-change-the-generated-ribbon-code"></a>Oluşturulmuş Şerit kodunu değiştirmek için  
  
1.  Şerit sınıfının bildirimini türetildiği şekilde değiştirmenize <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> Microsoft.Office.Tools.Ribbon.OfficeRibbon yerine.  
  
2.  Şerit sınıf aşağıda gösterildiği gibi değiştirin. Oluşturucuya kendi kodunuzu hiçbirini eklediyseniz, kodunuzu değiştirmeyin. Visual Basic projeleri içinde yalnızca parametresiz oluşturucuya değiştirin. Diğer oluşturucuyu yoksayın.  
  
     Aşağıdaki kod örneğinde .NET Framework 3.5 hedefleyen bir projedeki Şerit sınıfının varsayılan oluşturucusu gösterilmektedir.  
  
    ```vb  
    Public Sub New()  
        MyBase.New()  
        InitializeComponent()  
    End Sub  
    ```  
  
    ```csharp  
    public Ribbon1()  
    {  
        InitializeComponent();  
    }  
    ```  
  
     Aşağıdaki kod örneğinde bir Şerit sınıfının varsayılan oluşturucusu projede hedefleyen gösterilmektedir [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü.  
  
    ```vb  
    Public Sub New()  
        MyBase.New(Globals.Factory.GetRibbonFactory())  
        InitializeComponent()  
    End Sub  
    ```  
  
    ```csharp  
    public Ribbon1()  
        : base(Globals.Factory.GetRibbonFactory())  
    {  
        InitializeComponent();  
    }  
    ```  
  
3.  İçinde `InitializeComponent` yöntemi, bir Şerit denetimi oluşturur ve böylece kodu yerine yardımcı yöntemlerinden birini kullanan herhangi bir kod değiştirmek <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> nesnesi.  
  
    > [!NOTE]  
    >  Visual C# projelerinde adlı bölge genişletmeniz gerekir `Component Designer generated code` görmek için `InitializeComponent` yöntemi.  
  
     Örneğin, dosyanızı başlatır kod aşağıdaki satırı içerdiğini varsayar bir <xref:Microsoft.Office.Tools.Ribbon.RibbonButton> adlı `button1` .NET Framework 3.5 hedefleyen bir projede.  
  
    ```vb  
    Me.button1 = New Microsoft.Office.Tools.Ribbon.RibbonButton()  
    ```  
  
    ```csharp  
    this.button1 = new Microsoft.Office.Tools.Ribbon.RibbonButton();  
    ```  
  
     Hedefleyen bir projede [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra aşağıdaki kodu yerine kullanmanız gerekir.  
  
    ```vb  
    Me.button1 = Me.Factory.CreateRibbonButton()  
    ```  
  
    ```csharp  
    this.button1 = this.Factory.CreateRibbonButton();  
    ```  
  
     Şerit denetimleri için yardımcı yöntemler tam bir listesi için bkz: [başlatmasını Şerit denetimleri](#ribboncontrols).  
  
4.  Visual C# projelerinde, herhangi bir kod satırı değiştirme `InitializeComponent` kullanan yöntemi bir <xref:System.EventHandler%601> belirli bir Şerit temsilcisi kullanmanız için temsilci.  
  
     Örneğin, dosyanızı işleyen kodu aşağıdaki satırı içerdiğini varsayar <xref:Microsoft.Office.Tools.Ribbon.RibbonButton.Click> olay .NET Framework 3.5 hedefleyen bir projede.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
     Hedefleyen bir projede [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra aşağıdaki kodu yerine kullanmanız gerekir.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
     Şerit temsilcilerinin tam listesi için bkz: [Şerit olaylarını işleme](#ribbonevents).  
  
5.  Visual Basic projelerinde bulun `ThisRibbonCollection` dosyanın sonunda sınıfı. Bu sınıf bildirimi Microsoft.Office.Tools.Ribbon.RibbonReadOnlyCollection artık devralır şekilde değiştirin.  
  
##  <a name="ribboncontrols"></a>Şerit denetimlerini örnekleme  
 Dinamik olarak Şerit denetimleri başlatır herhangi bir kodu değiştirmeniz gerekir. Proje .NET Framework 3.5 hedefleyen Şerit denetimleri doğrudan belirli senaryolarda örneği sınıflardır. ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ya da daha sonra bu denetimlerin arabirimleri doğrudan örneği oluşturulamıyor. Tarafından sağlanan yöntemleri kullanarak denetimler oluşturmalısınız <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> nesnesi.  
  
 Erişim için iki yolla <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> nesnesi:  
  
-   Şerit sınıfı Fabrika özelliğini kullanarak. Şerit sınıfınızda kodda bu yaklaşımı kullanın.  
  
-   Globals.Factory.GetRibbonFactory yöntemini kullanarak. Şerit sınıfınızın dışındaki kodda bu yaklaşımı kullanın. Globals sınıfı hakkında daha fazla bilgi için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
 Aşağıdaki kod örneğinde nasıl oluşturulduğunu gösteren bir <xref:Microsoft.Office.Tools.Ribbon.RibbonButton> hedefleyen bir projede Şerit sınıfında [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü.  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>11</CodeContentPlaceHolder>  
 Aşağıdaki tabloda, programla oluşturabileceğiniz denetimler ve hedefleyen projelerde bu denetimleri oluşturmak için kullanılacak yöntemi listeler [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü.  
  
|Denetim|Kullanılacak RibbonFactory yöntemi [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ve sonraki projeleri|  
|-------------|---------------------------------------------------------------------------------------------------------------|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonButton%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonButtonGroup%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonCheckBox%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonComboBox%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonDialogLauncher%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>:|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonDropDown%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDownItem>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonDropDownItem%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonEditBox%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonGallery%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonGroup%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonLabel%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonManager>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonManager%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonMenu%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonSeparator%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonSplitButton%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonTab%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonToggleButton%2A>|  
  
##  <a name="ribbonevents"></a>Şerit olaylarını işleme  
 Şerit denetimlerini olaylarını işleme herhangi bir kodu değiştirmeniz gerekir. .NET Framework 3.5 hedefleyen projelerde, bu olaylar genel tarafından işlenen <xref:System.EventHandler%601> temsilci. ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bu olayları artık diğer temsilciler tarafından ele alınır.  
  
 Aşağıdaki tabloda Şerit olayları ve hedefleyen projelerde bunlarla ilişkili temsilciler listelenmektedir [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü.  
  
|Olay|Kullanılacak temsilci [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] ve sonraki projeleri|  
|-----------|---------------------------------------------------------------------------------------------------|  
|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>oluşturulan Şerit sınıfı olayı|<xref:Microsoft.Office.Tools.Ribbon.RibbonLoadImageEventHandler>|  
|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load>|<xref:Microsoft.Office.Tools.Ribbon.RibbonUIEventHandler>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton.Click><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.ItemsLoading><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.TextChanged><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.ButtonClick><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.ItemsLoading><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.SelectionChanged><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox.TextChanged><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ButtonClick><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.Click><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ItemsLoading><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup.DialogLauncherClick><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.ItemsLoading><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton.Click><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click>|<xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventHandler>|  
  
## <a name="setting-the-position-of-a-ribbon-component-programmatically"></a>Şerit bileşeninin konumunu programlı olarak ayarlama  
 Şerit grupları, sekmeleri veya denetimleri konumunu ayarlar herhangi bir kodu değiştirmeniz gerekir. Projelerinde .NET Framework 3.5 hedefleyen bir grup, sekme ya da Denetim Position özelliğini atamak için statik Microsoft.Office.Tools.Ribbon.RibbonPosition sınıfının AfterOfficeId ve BeforeOfficeId yöntemlerini kullanabilirsiniz. ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra bu yöntemleri kullanarak erişmeniz gerekir <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.RibbonPosition%2A> özelliği tarafından sağlanan <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> nesnesi.  
  
 Erişim için iki yolla <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> nesnesi:  
  
-   Şerit sınıfı Fabrika özelliğini kullanarak. Şerit sınıfınızda kodda bu yaklaşımı kullanın.  
  
-   Globals.Factory.GetRibbonFactory yöntemini kullanarak. Şerit sınıfınızın dışındaki kodda bu yaklaşımı kullanın. Globals sınıfı hakkında daha fazla bilgi için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
 Aşağıdaki kod örneği, .NET Framework 3.5 hedefleyen bir projede Şerit sınıfındaki sekmenin konumunu özelliğini ayarlamak gösterilmiştir.  
  
```vb  
Me.tab1.Position = RibbonPosition.AfterOfficeId("TabHome")  
```  
  
```csharp  
this.tab1.Position = RibbonPosition.AfterOfficeId("TabHome");  
```  
  
 Aşağıdaki kod örneğinde aynı görevin hedefleyen bir projede gösterilmektedir [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].  
  
```vb  
Me.tab1.Position = Me.Factory.RibbonPosition.AfterOfficeId("TabHome")  
```  
  
```csharp  
this.tab1.Position = this.Factory.RibbonPosition.AfterOfficeId("TabHome");  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerini geçirme .NET Framework 4 veya üstü](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)  
  
  