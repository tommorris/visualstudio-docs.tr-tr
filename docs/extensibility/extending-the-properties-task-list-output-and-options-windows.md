---
title: "Özellikler, görev listesi, çıkış ve seçenekleri Windows genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties pane
- task list
- output window
- properties window
- tutorials
- tool windows
ms.assetid: 06990510-5424-44b8-9fd9-6481acec5c76
caps.latest.revision: "37"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 631c336d0350fdf8a43d747eb6bda7b01e9d1eba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-properties-task-list-output-and-options-windows"></a>Özellikler, görev listesi, çıkış ve seçenekleri Windows genişletme
Visual Studio'da herhangi bir araç penceresi erişebilir. Bu kılavuz, araç penceresi hakkında bilgi yeni bir tümleştirme gösterilmektedir **seçenekleri** sayfası ve yeni bir ayar **özellikleri** sayfası ve nasıl yazılacağını **görevlistesi** ve **çıkış** windows.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="create-an-extension-with-a-tool-window"></a>Bir uzantısı bir araç penceresi oluşturma  
  
1.  Adlı bir proje oluşturun **TodoList** VSIX şablonu kullanarak ve adlandırılmış bir özel araç pencere öğesi şablonu Ekle **TodoWindow**.  
  
    > [!NOTE]
    >  Bir araç penceresi uzantı oluşturma hakkında daha fazla bilgi için bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="set-up-the-tool-window"></a>Aracı penceresini ayarlama  
 Bir metin kutusunda, yeni bir Yapılacaklar öğesi, listeye yeni öğe eklemek için bir düğme ve listedeki öğeleri görüntülemek için bir liste türü ekleyin.  
  
1.  TodoWindow.xaml içinde UserControl düğmesi, metin kutusuna, StackPanel denetimleri silin.  
  
    > [!NOTE]
    >  Bu silmediği **button1_Click** bir sonraki adımda yeniden kullanılacak olay işleyicisi.  
  
2.  Gelen **tüm WPF denetimleri** bölümünü **araç**, sürükleyin bir **tuvale** denetimi kılavuza.  
  
3.  Sürükleme bir **TextBox**, **düğmesini**ve bir **ListBox** tuvale. Öğeleri metin kutusu ve düğmesi aynı düzeydeki ve bunları, aşağıda penceresinin resmi olduğu gibi rest ListBox doldurur şekilde düzenleyin.  
  
     ![Araç penceresi tamamlandı](../extensibility/media/t5-toolwindow.png "T5 araç penceresi")  
  
4.  XAML bölmesinde düğmeyi bulmak ve içerik özelliği ayarlamak **Ekle**. Düğme denetimi için düğmesi olay işleyicisi ekleyerek yeniden bir `Click="button1_Click"` özniteliği. Tuvale blok aşağıdaki gibi görünmelidir:  
  
    ```xml  
    <Canvas HorizontalAlignment="Left" Width="306">  
        <TextBox x:Name="textBox" HorizontalAlignment="Left" Height="23" Margin="10,10,0,0" TextWrapping="Wrap" Text="TextBox" VerticalAlignment="Top" Width="208"/>  
            <Button x:Name="button" Content="Add" HorizontalAlignment="Left" Margin="236,13,0,0" VerticalAlignment="Top" Width="48" Click="button1_Click"/>  
            <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="222" Margin="10,56,0,0" VerticalAlignment="Top" Width="274"/>  
    </Canvas>  
    ```  
  
#### <a name="customize-the-constructor"></a>Oluşturucusu özelleştirme  
  
1.  TodoWindowControl.xaml.cs dosyasında aşağıdaki ekleme deyimini kullanarak:  
  
    ```csharp  
    using System;  
    ```  
  
2.  TodoWindow ortak bir başvuru ekleyin ve TodoWindow bir parametre alan TodoWindowControl Oluşturucusu vardır. Kod gibi görünmelidir:  
  
    ```csharp  
    public TodoWindow parent;  
  
    public TodoWindowControl(TodoWindow window)  
    {  
        InitializeComponent();  
        parent = window;  
    }  
    ```  
  
3.  TodoWindow.cs içinde TodoWindowControl Oluşturucusu TodoWindow parametresi içerecek şekilde değiştirin. Kod gibi görünmelidir:  
  
    ```csharp  
    public TodoWindow() : base(null)  
    {  
        this.Caption = "TodoWindow";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
  
         this.Content = new TodoWindowControl(this);  
    }  
    ```  
  
## <a name="create-an-options-page"></a>Seçenekler sayfası oluşturma  
 Bir sayfa sağlayabilir **seçenekleri** iletişim kutusu kullanıcıların araç penceresi ayarlarını değiştirebilirsiniz. Seçenekler sayfası oluşturma seçeneklerini ve TodoListPackage.cs veya TodoListPackage.vb dosyasındaki bir giriş tanımlar hem bir sınıf gerektirir.  
  
1.  Adlı bir sınıf ekleyin `ToolsOptions.cs`. Devralınan ToolsOptions sınıfı olun <xref:Microsoft.VisualStudio.Shell.DialogPage>.  
  
    ```csharp  
    class ToolsOptions : DialogPage  
    {  
    }  
    ```  
  
2.  Aşağıdaki ekleme deyimini kullanarak:  
  
    ```csharp  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
3.  Bu kılavuzda seçenekleri sayfasında DaysAhead adında yalnızca bir seçenek sağlar. Adlı bir özel alan eklemek **daysAhead** ve adlı bir özellik **DaysAhead** ToolsOptions sınıfı için:  
  
    ```csharp  
    private double daysAhead;  
  
    public double DaysAhead  
    {  
        get { return daysAhead; }  
        set { daysAhead = value; }  
    }  
    ```  
  
 Şimdi, projenin Bu seçenekler sayfası farkında olmanız gerekir.  
  
#### <a name="make-the-options-page-available-to-users"></a>Seçenekler sayfası kullanıcılar tarafından kullanılabilmesini sağlamak  
  
1.  TodoWindowPackage.cs içinde eklemek bir <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> TodoWindowPackage sınıfı için:  
  
    ```csharp  
    [ProvideOptionPage(typeof(ToolsOptions), "ToDo", "General", 101, 106, true)]  
    ```  
  
2.  İlk parametre ProvideOptionPage oluşturucusu olarak daha önce oluşturduğunuz ToolsOptions sınıfının türüdür. İkinci parametresi, "ToDo" kategorisindeki adıdır **seçenekleri** iletişim kutusu. Üçüncü parametre "Genel" adıdır kategorisidir **seçenekleri** iletişim kutusu burada seçenekleri sayfasında kullanılabilir. Kaynak kimlikleri dizeleri için sonraki iki parametreleridir; İlk kategori adıdır ve ikinci kategori adıdır. Son parametre bu sayfayı Otomasyon kullanarak erişilebilir olup olmadığını belirler.  
  
     Seçenekler sayfası bir kullanıcı oturum açtığında, aşağıdaki resimde benzemelidir.  
  
     ![Seçenekler sayfası](../extensibility/media/t5optionspage.gif "T5OptionsPage")  
  
     Kategori fark **Yapılacaklar** ve kategori **genel**.  
  
## <a name="make-data-available-to-the-properties-window"></a>Verileri için Özellikler penceresini kullanılabilir yap  
 Bireysel öğeleri hakkında bilgi depolar Yapılacaklar listesinde Todoıtem adlı bir sınıf oluşturarak Yapılacaklar listesi bilgilerini kullanılabilir hale getirebilirsiniz.  
  
1.  Adlı bir sınıf ekleyin `TodoItem.cs`.  
  
     Araç penceresi kullanıcılar için kullanılabilir olduğunda, liste öğeleri Todoıtems temsil edilir. Kullanıcı bu öğelerden birini liste kutusunda seçtiğinde **özellikleri** pencere öğesiyle ilgili bilgileri görüntüler.  
  
     Verileri kullanılabilir yapmak için **özellikleri** penceresinde, açmanız verileri iki özel özniteliklere sahip genel özelliklerini `Description` ve `Category`. `Description`en altında görüntülenen metin **özellikleri** penceresi. `Category`özelliği zaman nerede görüneceğini belirler **özellikleri** penceresi görüntülenir **kategoriler** görünümü. Aşağıdaki resimde **özellikleri** penceredir içinde **kategoriler** görünümü **adı** özelliğinde **Yapılacaklar alanları** kategorisi Seçili ve açıklamasını **adı** özelliği, pencerenin alt kısmında görüntülenir.  
  
     ![Özellikler penceresi](../extensibility/media/t5properties.png "T5Properties")  
  
2.  Aşağıdaki using deyimlerini TodoItem.cs dosya.  
  
    ```csharp  
    using System.ComponentModel;  
    using System.Windows.Forms;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
3.  Ekleme `public` sınıfı bildirimine erişim değiştiricisi.  
  
    ```csharp  
    public class TodoItem  
    {  
    }  
    ```  
  
     İki özellik adı ve vade tarihi ekleyin. Biz UpdateList() ve CheckForErrors() daha sonra gerçekleştirirsiniz.  
  
    ```csharp  
    public class TodoItem  
    {  
        private TodoWindowControl parent;  
        private string name;  
        [Description("Name of the ToDo item")]  
        [Category("ToDo Fields")]  
        public string Name  
        {  
            get { return name; }  
            set  
            {  
                name = value;  
                parent.UpdateList(this);  
            }  
        }  
  
        private DateTime dueDate;  
        [Description("Due date of the ToDo item")]  
        [Category("ToDo Fields")]  
        public DateTime DueDate  
        {  
            get { return dueDate; }  
            set  
            {  
                dueDate = value;  
                parent.UpdateList(this);  
                parent.CheckForErrors();  
            }  
        }  
    }  
    ```  
  
4.  Kullanıcı denetimi için özel bir başvuru ekleyin. Kullanıcı denetimi ve bu Yapılacaklar öğesi için ad alan bir oluşturucu ekleyin. DaysAhead için değeri bulmak için seçenekler sayfası özelliği alır.  
  
    ```csharp  
    private TodoWindowControl parent;  
  
    public TodoItem(TodoWindowControl control, string itemName)  
    {  
        parent = control;  
        name = itemName;  
        dueDate = DateTime.Now;  
  
        double daysAhead = 0;  
        IVsPackage package = parent.parent.Package as IVsPackage;  
        if (package != null)  
        {  
            object obj;  
            package.GetAutomationObject("ToDo.General", out obj);  
  
            ToolsOptions options = obj as ToolsOptions;  
            if (options != null)  
            {  
                daysAhead = options.DaysAhead;  
            }  
        }  
  
        dueDate = dueDate.AddDays(daysAhead);  
    }  
    ```  
  
5.  Çünkü örneklerini `TodoItem` sınıfı liste kutusunda depolanır ve ListBox çağıracak `ToString` gerekir aşırı işlevi, `ToString` işlevi. Aşağıdaki kod TodoItem.cs için Oluşturucusu sonra ve önce sınıfı sonuna ekleyin.  
  
    ```csharp  
    public override string ToString()  
    {  
        return name + " Due: " + dueDate.ToShortDateString();  
    }  
    ```  
  
6.  TodoWindowControl.xaml.cs içinde TodoWindowControl sınıfı için saplama yöntemleri eklemek `CheckForError` ve `UpdateList` yöntemleri. Bunları ProcessDialogChar sonra ve önce dosyanın sonuna yerleştirin.  
  
    ```csharp  
    public void CheckForErrors()  
    {  
    }  
    public void UpdateList(TodoItem item)  
    {  
    }  
    ```  
  
     `CheckForError` Yöntemi, üst nesne ile aynı ada sahip bir yöntem çağıracaktır ve bu yöntem herhangi bir hata oluşmuş ve düzgün bir şekilde işler olup olmadığını kontrol eder. `UpdateList` Yöntemi üst denetiminde ListBox güncelleştirmek; yöntemi aldığında çağrılan `Name` ve `DueDate` Bu sınıf değişiklik özelliklerinde. Bunlar daha sonra uygulanacaktır.  
  
## <a name="integrate-into-the-properties-window"></a>Özellikler penceresine tümleştirme  
 Şimdi için bağlı ListBox yönetir kod yazmayı **özellikleri** penceresi.  
  
 Düğme değiştirmelisiniz metin okuma, bir Todoıtem oluşturmak için işleyicisi'ı tıklatın ve ListBox ekler.  
  
1.  Varolan `button1_Click` işlevi, yeni bir Todoıtem oluşturur ve ListBox ekler koda sahip. Daha sonra tanımlanacak TrackSelection() çağırır.  
  
    ```csharp  
    private void button1_Click(object sender, RoutedEventArgs e)  
    {  
        if (textBox.Text.Length > 0)  
        {  
            var item = new TodoItem(this, textBox.Text);  
            listBox.Items.Add(item);  
            TrackSelection();  
            CheckForErrors();  
        }  
    }  
    ```  
  
2.  ListBox denetimi Tasarım görünümünde seçin. İçinde **özellikleri** penceresinde **olay işleyicileri** düğmesine tıklayın ve SelectionChanged olayı bulun. Metin kutusuyla doldurun **listBox_SelectionChanged**. Bunun yapılması SelectionChanged işleyici için bir saplama ekler ve olayı atar.  
  
3.  TrackSelection() yöntemi uygulayabilirsiniz. Almanız gereken beri <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> Hizmetleri, olan yaptığınız <xref:Microsoft.VisualStudio.Shell.WindowPane.GetService%2A> TodoWindowControl tarafından erişilebilir. TodoWindow sınıfına aşağıdaki yöntemi ekleyin:  
  
    ```  
    internal object GetVsService(Type service)  
    {  
        return GetService(service);  
    }  
    ```  
  
4.  Aşağıdaki using deyimlerini TodoWindowControl.xaml.cs ekleyin:  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
5.  SelectionChanged işleyicisinde aşağıdaki gibi doldurun:  
  
    ```  
    private void listBox_SelectionChanged(object sender, SelectionChangedEventArgs e)  
    {  
        TrackSelection();  
    }  
    ```  
  
6.  Şimdi, ile tümleştirme sağlar TrackSelection işlevi doldurun **özellikleri** penceresi. Bu işlev, kullanıcı için ListBox bir öğe ekler veya ListBox bir öğeyi tıklattığında çağrılır. ListBox içeriğini bir SelectionContainer ekler ve SelectionContainer geçirir **özellikleri** pencerenin <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> olay işleyicisi. TrackSelection hizmeti kullanıcı arabirimi (UI) seçili nesneleri izler ve bunların özelliklerini görüntüler  
  
    ```csharp  
    private SelectionContainer mySelContainer;  
    private System.Collections.ArrayList mySelItems;  
    private IVsWindowFrame frame = null;  
  
    private void TrackSelection()  
    {  
        if (frame == null)  
        {  
            var shell = parent.GetVsService(typeof(SVsUIShell)) as IVsUIShell;  
            if (shell != null)  
            {  
                var guidPropertyBrowser = new  
                Guid(ToolWindowGuids.PropertyBrowser);  
                shell.FindToolWindow((uint)__VSFINDTOOLWIN.FTW_fForceCreate,  
                ref guidPropertyBrowser, out frame);  
            }  
        }  
        if (frame != null)  
            {  
                frame.Show();  
            }  
        if (mySelContainer == null)  
        {  
            mySelContainer = new SelectionContainer();  
        }  
  
        mySelItems = new System.Collections.ArrayList();  
  
        var selected = listBox.SelectedItem as TodoItem;  
        if (selected != null)  
        {  
            mySelItems.Add(selected);  
        }  
  
        mySelContainer.SelectedObjects = mySelItems;  
  
        ITrackSelection track = parent.GetVsService(typeof(STrackSelection))  
                                as ITrackSelection;  
        if (track != null)  
        {  
            track.OnSelectChange(mySelContainer);  
        }  
    }  
    ```  
  
     Bir sınıf sahip olduğunuza göre **özellikleri** penceresi kullanabilir, tümleştirebilirsiniz **özellikleri** araç penceresi penceresiyle. Kullanıcı aracı penceresinde ListBox bir öğeyi tıklattığında **özellikleri** penceresi uygun şekilde güncelleştirilmelidir. Benzer şekilde, kullanıcı değiştiğinde bir ToDo öğesinin **özellikleri** penceresinde ilişkilendirilen öğenin güncelleştirilmesi gerekir.  
  
7.  Şimdi, kodun kalan kısmı UpdateList işlevi içinde TodoWindowControl.xaml.cs ekleyin. Onu bırakın ve değiştirilmiş Todoıtem liste kutusundan yeniden eklemeniz gerekir.  
  
    ```csharp  
    public void UpdateList(TodoItem item)  
    {  
        var index = listBox.SelectedIndex;  
        listBox.Items.RemoveAt(index);  
        listBox.Items.Insert(index, item);  
        listBox.SelectedItem = index;  
    }  
    ```  
  
8.  Kodunuzu test etmek. Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenmesi gerekir.  
  
9. Açık **Araçlar / Seçenekler** sayfaları. Sol bölmede Yapılacaklar kategori görmeniz gerekir. Kategoriler alfabetik olarak listelenir, böylece altında Ts bakın.  
  
10. Yapılacaklar seçenekleri sayfasında ayarlanan DaysAhead özelliği görmelisiniz **0**. Şekilde değiştirin **2**.  
  
11. Görünüm / diğer Windows menüsü, açık **TodoWindow**. Tür **EndDate** tıklatın ve metin kutusu **Ekle**.  
  
12. Liste kutusunda tarihi bugünden sonraki iki gün görmeniz gerekir.  
  
## <a name="add-text-to-the-output-window-and-items-to-the-task-list"></a>Çıktı penceresi ve görev listesi öğelerine metin ekleme  
 İçin **görev listesi**, yeni bir nesne türü görev oluşturun ve bu görev nesnesi ekleme **görev listesi** Add yöntemini çağırarak. Yazılacak **çıkış** penceresinde bölmesi nesnesi elde etmek için kendi GetPane yöntemini çağırın ve ardından bölmesinde nesnesinin OutputString yöntemini çağırın.  
  
1.  TodoWindowControl.xaml.cs içinde içinde `button1_Click` yöntemi, almak için kodu ekleyin **genel** bölmesinde **çıkış** (varsayılan değer olan) penceresi ve yazma. Yöntemini aşağıdaki gibi görünmelidir:  
  
    ```csharp  
    private void button1_Click(object sender, EventArgs e)  
    {  
        if (textBox.Text.Length > 0)  
        {  
            var item = new TodoItem(this, textBox.Text);  
            listBox.Items.Add(item);  
  
            var outputWindow = parent.GetVsService(  
                typeof(SVsOutputWindow)) as IVsOutputWindow;  
            IVsOutputWindowPane pane;  
            Guid guidGeneralPane = VSConstants.GUID_OutWindowGeneralPane;  
            outputWindow.GetPane(ref guidGeneralPane, out pane);  
            if (pane != null)  
            {  
                 pane.OutputString(string.Format(  
                    "To Do item created: {0}\r\n",  
                 item.ToString()));  
        }  
            TrackSelection();  
            CheckForErrors();  
        }  
    }  
    ```  
  
2.  Görev listesine öğe eklemek için gereksinim duyduğunuz bir iç içe geçmiş sınıf TodoWindowControl sınıfa eklemek için. İç içe geçmiş sınıf türetin gerekiyor <xref:Microsoft.VisualStudio.Shell.TaskProvider>. TodoWindowControl sınıfı sonuna aşağıdaki kodu ekleyin.  
  
    ```csharp  
    [Guid("72de1eAD-a00c-4f57-bff7-57edb162d0be")]  
    public class TodoWindowTaskProvider : TaskProvider  
    {  
        public TodoWindowTaskProvider(IServiceProvider sp)  
            : base(sp)  
        {  
        }  
    }  
    ```  
  
3.  Sonraki TodoTaskProvider özel başvuru ve CreateProvider() yöntemi TodoWindowControl sınıfına ekleyin. Kod gibi görünmelidir:  
  
    ```csharp  
    private TodoWindowTaskProvider taskProvider;  
    private void CreateProvider()  
    {  
        if (taskProvider == null)  
        {  
            taskProvider = new TodoWindowTaskProvider(parent);  
            taskProvider.ProviderName = "To Do";  
        }  
    }  
    ```  
  
4.  Görev listesini temizler, ClearError() ve bir girdi görev listesine ekler, ReportError() TodoWindowControl sınıfına ekleyin.  
  
    ```csharp  
    private void ClearError()  
    {  
        CreateProvider();  
        taskProvider.Tasks.Clear();  
    }  
    private void ReportError(string p)  
    {  
        CreateProvider();  
        var errorTask = new Task();  
        errorTask.CanDelete = false;  
        errorTask.Category = TaskCategory.Comments;  
        errorTask.Text = p;  
  
        taskProvider.Tasks.Add(errorTask);  
  
        taskProvider.Show();  
  
        var taskList = parent.GetVsService(typeof(SVsTaskList))  
            as IVsTaskList2;  
        if (taskList == null)  
        {  
            return;  
        }  
  
        var guidProvider = typeof(TodoWindowTaskProvider).GUID;  
         taskList.SetActiveProvider(ref guidProvider);  
    }  
    ```  
  
5.  Şimdi CheckForErrors yöntemi aşağıdaki gibi uygulayın.  
  
    ```csharp  
    public void CheckForErrors()  
    {  
        foreach (TodoItem item in listBox.Items)  
        {  
            if (item.DueDate < DateTime.Now)  
            {  
                ReportError("To Do Item is out of date: "  
                    + item.ToString());  
            }  
        }  
    }  
    ```  
  
## <a name="trying-it-out"></a>Çalışırken  
  
1.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
2.  TodoWindow açın (**görünüm / diğer Windows / TodoWindow**).  
  
3.  Bir metin kutusuna yazın ve ardından **Ekle**.  
  
     Son tarihi bugün liste kutusu eklendikten sonra 2 gün. Herhangi bir hata oluşturulur ve **görev listesi** (**görüntülemek / görev listesi**) hiçbir girişlerine sahip olması.  
  
4.  Ayar şimdi değiştirmek **Araçlar / Seçenekler / ToDo** gelen sayfa **2** başa **0**.  
  
5.  İçinde başka bir şey yazın **TodoWindow** ve ardından **Ekle** yeniden. Bu bir hata ve ayrıca bir girişe tetikler **görev listesi**.  
  
     Öğeleri eklediğinizde, başlangıç tarihi şimdi artı 2 gün için ayarlanır.  
  
6.  Üzerinde **Görünüm** menüsünde tıklatın **çıkış** açmak için **çıkış** penceresi.  
  
     Her bir öğe ekleyin, bir ileti görüntülenir dikkat **görev listesi** bölmesi.  
  
7.  Liste kutusu öğelerden birini tıklatın.  
  
     **Özellikleri** pencere öğesi için iki özelliklerini görüntüler.  
  
8.  Özelliklerden birini değiştirin ve ardından ENTER tuşuna basın.  
  
     Öğe, liste kutusunda güncelleştirilir.