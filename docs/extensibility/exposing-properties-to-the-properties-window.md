---
title: "Özellikler penceresini özelliklerine gösterme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [Visual Studio SDK], exposing in Property Browser
- properties [Visual Studio SDK]
- Property Browser, exposing properties
ms.assetid: 47f295b5-1ca5-4e7b-bb52-7b926b136622
caps.latest.revision: "36"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7aed43ac4248c9bfd1e43d5e6c732a4fef3af529
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-properties-to-the-properties-window"></a>Özellikler penceresini özelliklerine gösterme
Bu kılavuz bir nesneye ortak özelliklerini gösterir **özellikleri** penceresi. Bu özellikler yaptığınız değişiklikler yansıtılır **özellikleri** penceresi.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="exposing-properties-to-the-properties-window"></a>Özellikler penceresini özelliklerine gösterme  
 Bu bölümde, bir özel araç penceresi oluşturun ve ilişkili pencere bölmesine nesnesinde ortak özelliklerini görüntüleyin **özellikleri** penceresi.  
  
#### <a name="to-expose-properties-to-the-properties-window"></a>Özellikler penceresini özelliklerini göstermek için  
  
1.  Visual Studio uzantılarının uzantısı varlıklar yer alacağı VSIX dağıtım projesi ile başlar. Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] adlı VSIX proje `MyObjectPropertiesExtension`. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Adlı bir özel araç penceresi öğesi şablonu ekleyerek bir araç penceresi `MyToolWindow`. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle iletişim**gidin **Visual C# öğeleri / genişletilebilirlik** seçip **özel araç penceresi**. İçinde **adı** alan iletişim kutusunun en altında dosya adını değiştirmek `MyToolWindow.cs`. Özel araç penceresi oluşturma hakkında daha fazla bilgi için bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
3.  MyToolWindow.cs açın ve aşağıdaki ekleme deyimini kullanarak:  
  
    ```  
    using System.Collections;  
    using System.ComponentModel;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
4.  Şimdi aşağıdaki alanları ekleyin `MyToolWindow` sınıfı.  
  
    ```csharp  
    private ITrackSelection trackSel;  
    private SelectionContainer selContainer;  
  
    ```  
  
5.  Aşağıdaki kod MyToolWindow sınıfına ekleyin.  
  
    ```csharp  
    private ITrackSelection TrackSelection  
    {  
        get  
        {  
            if (trackSel == null)  
                trackSel =  
                   GetService(typeof(STrackSelection)) as ITrackSelection;  
            return trackSel;  
        }  
    }  
  
    public void UpdateSelection()  
    {  
        ITrackSelection track = TrackSelection;  
        if (track != null)  
            track.OnSelectChange((ISelectionContainer)selContainer);  
    }  
  
    public void SelectList(ArrayList list)  
    {  
        selContainer = new SelectionContainer(true, false);  
        selContainer.SelectableObjects = list;  
        selContainer.SelectedObjects = list;  
        UpdateSelection();  
    }  
  
    public override void OnToolWindowCreated()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(this);  
        SelectList(listObjects);  
    }  
    ```  
  
     `TrackSelection` Özelliğini kullanan `GetService` elde etmek için bir `STrackSelection` sağlayan hizmetini bir <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> arabirimi. `OnToolWindowCreated` Olay işleyicisi ve `SelectList` yöntemi birlikte yalnızca araç penceresi bölmesinde nesnenin kendisini içeren seçili nesnelerin listesi oluşturun. `UpdateSelection` Yöntemi söyler **özellikleri** aracı pencere bölmesine genel özelliklerini görüntülemek için penceresi.  
  
6.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio'nun deneysel örneği görüntülenmesi gerekir.  
  
7.  Varsa **özellikleri** pencere görünür değil, F4 tuşuna basarak açın.  
  
8.  Açık **MyToolWindow** penceresi. İçinde bulabileceğiniz **görünüm / diğer pencereler**.  
  
     Penceresi açılır ve pencere bölmesine genel özelliklerini görüntülenmesini **özellikleri** penceresi.  
  
9. Değişiklik **resim yazısı** özelliğinde **özellikleri** penceresine **My nesne özellikleri**.  
  
     MyToolWindow pencere resim yazısı buna göre değişir.  
  
## <a name="exposing-tool-window-properties"></a>Araç penceresi özellikleri gösterme  
 Bu bölümde, bir araç penceresi ekleyin ve özelliklerini kullanıma sunar. Özelliklerine yaptığınız değişiklikler yansıtılır **özellikleri** penceresi.  
  
#### <a name="to-expose-tool-window-properties"></a>Araç penceresi özellikleri göstermek için  
  
1.  MyToolWindow.cs açın ve ortak boolean özelliği Taşmalar MyToolWindow sınıfına ekleyin.  
  
    ```csharp  
    [Category("My Properties")]  
    [Description("MyToolWindowControl properties")]  
    public bool IsChecked  
    {  
        get {  
            if (base.Content == null)  return false;  
            return (bool)(( MyToolWindowControl) base.Content).checkBox.IsChecked;   
        }  
        set {  
            ((MyToolWindowControl) base.Content).checkBox.IsChecked = value;  
        }  
    }  
    ```  
  
     Bu özellik, daha sonra oluşturacağınız WPF onay kutusunu durumunu alır.  
  
2.  MyToolWindowControl.xaml.cs açın ve MyToolWindowControl oluşturucusu aşağıdaki kodla değiştirin.  
  
    ```vb  
    private MyToolWindow pane;  
    public MyToolWindowControl(MyToolWindow pane)  
    {  
        InitializeComponent();  
        this.pane = pane;  
        checkBox.IsChecked = false;  
    }  
    ```  
  
     Bu verir `MyToolWindowControl` erişim `MyToolWindow` bölmesi.  
  
3.  MyToolWindow.cs içinde değiştirmek `MyToolWindow` şekilde Oluşturucusu:  
  
    ```csharp  
    base.Content = new MyToolWindowControl(this);  
    ```  
  
4.  MyToolWindowControl Tasarım görünümüne değiştirin.  
  
5.  Düğme silin ve onay kutusundan ekleyin **araç** sol üst köşedeki için.  
  
6.  Checked ve Unchecked olayları ekleyin. Tasarım görünümünde onay kutusunu seçin. İçinde **özellikleri** penceresinde, olay işleyicileri düğmesini (üst sağ **özellikleri** penceresi). Bul **işaretli** ve türü **checkbox_Checked** metin kutusuna, ardından bulmak **işaretlenmemiş** ve türü **checkbox_Unchecked** metin kutusuna.  
  
7.  Onay kutusu olay işleyicileri ekleyin:  
  
    ```csharp  
    private void checkbox_Checked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = true;  
        pane.UpdateSelection();  
    }  
    private void checkbox_Unchecked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = false;  
        pane.UpdateSelection();  
    }  
    ```  
  
8.  Projeyi derleyin ve hata ayıklamayı Başlat.  
  
9. Deneysel örneğinde açmak **MyToolWindow** penceresi.  
  
     Pencerenin özelliklerinde arayın **özellikleri** penceresi. **Taşmalar** özelliği penceresinin alt kısmında altında görünür **My özellikleri** kategorisi.  
  
10. Onay kutusunu işaretleyin **MyToolWindow** penceresi. **Taşmalar** içinde **özellikleri** penceresi değişiklikler **doğru**. Onay kutusundaki işareti kaldırın **MyToolWindow** penceresi. **Taşmalar** içinde **özellikleri** penceresi değişiklikler **False**. Değerini değiştirme **Taşmalar** içinde **özellikleri** penceresi. Onay kutusuna **MyToolWindow** yeni değerle eşleşecek şekilde penceresi değişiklikleri.  
  
    > [!NOTE]
    >  Görüntülenen bir nesne elden gerekir, **özellikleri** penceresinde, çağrı `OnSelectChange` ile bir `null` seçim kapsayıcısı ilk. Özellik veya nesne atma sonra güncelleştirilmiş bir seçim kapsayıcısı değiştirebilirsiniz <xref:Microsoft.VisualStudio.Shell.SelectionContainer.SelectableObjects%2A> ve <xref:Microsoft.VisualStudio.Shell.SelectionContainer.SelectedObjects%2A> listeler.  
  
## <a name="changing-selection-lists"></a>Seçim listeleri değiştirme  
 Bu bölümde temel özellik sınıfı için bir seçim listesi ekleme ve aracı pencere arabirimi görüntülemek için hangi seçim listesi seçmek için kullanın.  
  
#### <a name="to-change-selection-lists"></a>Seçim listeleri değiştirmek için  
  
1.  MyToolWindow.cs açın ve adlı ortak bir sınıf ekleyin `Simple`.  
  
    ```csharp  
    public class Simple  
    {  
        private string someText = "";  
  
        [Category("My Properties")]  
        [Description("Simple Properties")]  
        [DisplayName("My Text")]  
        public string SomeText  
        {  
            get { return someText; }  
            set { someText = value; }  
        }  
  
        [Category("My Properties")]  
        [Description("Read-only property")]  
        public bool ReadOnly  
        {  
            get { return false; }  
        }  
    }  
    ```  
  
2.  MyToolWindow sınıfı artı geçiş yapmak için iki yöntem SimpleObject özellik ekleme **özellikleri** pencere bölmesine arasında pencere seçimi ve `Simple` nesne.  
  
    ```csharp  
    private Simple simpleObject = null;  
    public Simple SimpleObject  
    {  
        get  
        {  
            if (simpleObject == null) simpleObject = new Simple();  
            return simpleObject;  
        }  
    }  
  
    public void SelectSimpleList()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(SimpleObject);  
        SelectList(listObjects);  
    }  
  
    public void SelectThisList()  
    {  
        ArrayList listObjects = new ArrayList();  
        listObjects.Add(this);  
        SelectList(listObjects);  
    }  
    ```  
  
3.  MyToolWindowControl.cs içinde bu kod satırıyla, onay kutusu işleyicileri değiştirin:  
  
    ```csharp  
    private void checkbox_Checked(object sender, RoutedEventArgs e)  
     {  
        pane.IsChecked = true;  
        pane.SelectSimpleList();  
        pane.UpdateSelection();  
    }  
    private void checkbox_Unchecked(object sender, RoutedEventArgs e)  
    {  
        pane.IsChecked = false;  
        pane.SelectThisList();  
        pane.UpdateSelection();  
    }  
    ```  
  
4.  Projeyi derleyin ve hata ayıklamayı Başlat.  
  
5.  Deneysel örneğinde açmak **MyToolWindow** penceresi.  
  
6.  Onay kutusunu işaretleyin **MyToolWindow** penceresi. **Özellikleri** penceresinde `Simple` nesne özelliklerini, **SomeText** ve **salt okunur**. Onay kutusunu temizleyin. Ortak Özellikler penceresi görünür **özellikleri** penceresi.  
  
    > [!NOTE]
    >  Görünen adı **SomeText** olan **My metin**.  
  
## <a name="best-practice"></a>En iyi uygulama  
 Bu kılavuzda <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> seçilebilir nesne koleksiyonu ve seçilen nesne koleksiyonu aynı koleksiyonda; böylece uygulanır. Yalnızca seçili nesnenin özellik tarayıcısı listesinde görüntülenir. Daha eksiksiz bir ISelectionContainer uygulaması için Reference.ToolWindow örnekleri bakın.  
  
 Visual Studio aracı windows Visual Studio oturumları arasında kalıcı olmasını sağlar. Araç penceresi durumu kalıcı yapma hakkında daha fazla bilgi için bkz: <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellikleri ve Özellik Penceresini Genişletme](../extensibility/extending-properties-and-the-property-window.md)