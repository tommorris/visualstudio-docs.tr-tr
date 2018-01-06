---
title: "Bir araç penceresi arama ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tool windows, adding search
ms.assetid: f78c4892-8060-49c4-8ecd-4360f1b4d133
caps.latest.revision: "38"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d37956c01cbbebbe29d7506cf5eacd9456b3bbc1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-search-to-a-tool-window"></a>Bir araç penceresi arama ekleme
Oluşturduğunuzda ya da bir araç penceresi uzantı güncelleştirme başka bir yerde görünür aynı arama işlevini Visual Studio'da ekleyebilirsiniz. Bu işlevsellik, aşağıdaki özellikleri içerir:  
  
-   Her zaman özel araç alanında bulunan bir arama kutusu.  
  
-   Arama kutusuna kendisini yayılan bir İlerleme göstergesi.  
  
-   Her karakteri (hızlı arama) girin hemen veya yalnızca Enter tuşuna (isteğe bağlı arama) seçtikten sonra sonuçları göstermek için yeteneği.  
  
-   Kendisi için en son aradıktan koşulları gösteren bir liste.  
  
-   Belirli alanları veya arama hedeflerini yönlerini aramaları filtreleme yeteneği.  
  
 Bu kılavuzu izleyerek, aşağıdaki görevleri gerçekleştirmek nasıl öğreneceksiniz:  
  
1.  VSPackage projesi oluşturun.  
  
2.  Salt okunur metin kutusu ile bir UserControl içeren bir araç penceresi oluşturun.  
  
3.  Bir arama kutusu araç penceresi ekleyin.  
  
4.  Arama uygulama ekleyin.  
  
5.  Hızlı arama ve bir ilerleme çubuğu görüntülemeyi etkinleştirir.  
  
6.  Ekleme bir **eşleşen durumda** seçeneği.  
  
7.  Ekleme bir **arama yalnızca bile satırları** Filtresi.  
  
## <a name="to-create-a-vsix-project"></a>VSIX proje oluşturmak için  
  
1.  Adlı VSIX proje oluşturma `TestToolWindowSearch` adlı bir araç penceresi ile **TestSearch**. Bunun yapılması yardıma gereksinim duyarsanız, bkz: [bir uzantısı bir araç penceresi oluşturma](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="to-create-a-tool-window"></a>Araç penceresi oluşturmak için  
  
1.  İçinde `TestToolWindowSearch` projesi, TestSearchControl.xaml dosyasını açın.  
  
2.  Varolan `<StackPanel>` salt okunur ekler aşağıdaki blok blok <xref:System.Windows.Controls.TextBox> için <xref:System.Windows.Controls.UserControl> aracı penceresinde.  
  
    ```xaml  
    <StackPanel Orientation="Vertical">  
        <TextBox Name="resultsTextBox" Height="800.0"  
            Width="800.0"  
            IsReadOnly="True">  
        </TextBox>  
    </StackPanel>  
    ```  
  
3.  TestSearchControl.xaml.cs dosyasında aşağıdaki ekleme deyimini kullanarak:  
  
    ```csharp  
    using System.Text;  
    ```  
  
4.  Kaldırma `button1_Click()` yöntemi.  
  
     İçinde **TestSearchControl** sınıfında, aşağıdaki kodu ekleyin.  
  
     Bu kod bir ortak ekler <xref:System.Windows.Controls.TextBox> adlı özellik **SearchResultsTextBox** ve adlı bir ortak dize özelliği **SearchContent**. Oluşturucu, metin kutusuna SearchResultsTextBox ayarlanır ve SearchContent dizeler yeni satır ile ayrılmış kümesi için başlatılır. Metin kutusunun içeriğini dizeler kümesi de başlatılır.  
  
    ```csharp  
    public partial class TestSearchControl : UserControl  
    {  
        public TextBox SearchResultsTextBox { get; set; }  
        public string SearchContent { get; set; }  
  
        public TestSearchControl()  
        {  
            InitializeComponent();  
  
            this.SearchResultsTextBox = resultsTextBox;  
            this.SearchContent = BuildContent();  
  
            this.SearchResultsTextBox.Text = this.SearchContent;  
        }  
  
        private string BuildContent()  
        {  
            StringBuilder sb = new StringBuilder();  
            sb.AppendLine("1 go");  
            sb.AppendLine("2 good");  
            sb.AppendLine("3 Go");  
            sb.AppendLine("4 Good");  
            sb.AppendLine("5 goodbye");  
            sb.AppendLine("6 Goodbye");  
  
            return sb.ToString();  
        }  
    }  
    ```  
  
     [!code-csharp[ToolWindowSearch#1](../extensibility/codesnippet/CSharp/adding-search-to-a-tool-window_1.cs)]
     [!code-vb[ToolWindowSearch#1](../extensibility/codesnippet/VisualBasic/adding-search-to-a-tool-window_1.vb)]  
  
5.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio'nun deneysel örneği görüntülenir.  
  
6.  Menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **TestSearch**.  
  
     Araç penceresi görünür, ancak arama denetimini henüz görünmüyor.  
  
## <a name="to-add-a-search-box-to-the-tool-window"></a>Araç penceresi için bir arama kutusu eklemek için  
  
1.  TestSearch.cs dosyasına aşağıdaki kodu ekleyin `TestSearch` sınıfı. Kodu geçersiz kılmaları <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> özellik get erişimcisine döndürür böylece `true`.  
  
     Aramayı etkinleştirmek için geçersiz kılmanız gerekir <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> özelliği. <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> Uygulayan sınıf <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch> ve arama sağlamaz varsayılan uygulamasını sağlar.  
  
    ```csharp  
    public override bool SearchEnabled  
    {  
        get { return true; }  
    }  
    ```  
  
2.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
3.  Visual Studio deneysel örneği açın **TestSearch**.  
  
     Bir arama denetimini aracı penceresinin en üstünde görünür bir **arama** Filigran ve büyütme cam simgesi. Ancak, arama işlemi uygulanmadı çünkü arama henüz işe yaramaz.  
  
## <a name="to-add-the-search-implementation"></a>Arama uygulaması eklemek için  
 Üzerinde arama etkinleştirdiğinizde bir <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>gibi önceki yordamda araç penceresi arama ana bilgisayar oluşturur. Bu konak kurar ve her zaman bir arka plan iş parçacığı üzerinde gerçekleşen arama işlemlerini yönetir. Çünkü <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> sınıfı oluşturulmasını arama ana ve ayarı arama yukarı yönetir, yalnızca bir arama görev oluşturmanız ve arama yöntemi sağlar. Arka plan iş parçacığında arama işlemi gerçekleşir ve kullanıcı Arabirimi iş parçacığı üzerinde araç penceresi denetim çağrıları gerçekleşir. Bu nedenle, kullanmalısınız <xref:Microsoft.VisualStudio.Shell.ThreadHelper.Invoke%2A> denetimi ile ilgili yaptığınız tüm çağrıları yönetmek için yöntem.  
  
1.  Aşağıdaki TestSearch.cs dosyasına ekleyin `using` deyimleri:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Runtime.InteropServices;  
    using System.Text;  
    using System.Windows.Controls;  
    using Microsoft.Internal.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.PlatformUI;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
2.  İçinde `TestSearch` sınıfında, aşağıdaki eylemleri gerçekleştirir aşağıdaki kodu ekleyin:  
  
    -   Geçersiz kılmaları <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> arama görev oluşturmak için yöntem.  
  
    -   Geçersiz kılmaları <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> metin kutusunun durumunu geri yüklemek için yöntem. Bir kullanıcı bir arama görevi ve ne zaman bir kullanıcı ayarlar veya seçenekleri veya filtreleri dağıtır iptal ettiğinde bu yöntem çağrılır. Her ikisi de <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> UI iş parçacığında denir. Bu nedenle, metin kutusuna yoluyla erişmek gerekmeyen <xref:Microsoft.VisualStudio.Shell.ThreadHelper.Invoke%2A> yöntemi.  
  
    -   Adlı bir sınıf oluşturur `TestSearchTask` devraldığı <xref:Microsoft.VisualStudio.Shell.VsSearchTask>, bir varsayılan uygulaması sağlayan <xref:Microsoft.VisualStudio.Shell.Interop.IVsSearchTask>.  
  
         İçinde `TestSearchTask`, araç penceresi başvuruda bulunan özel bir alan oluşturucu ayarlar. Search yöntemini sağlamak için geçersiz kılma <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> ve <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStopSearch%2A> yöntemleri. <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> Yöntemdir burada arama işlemi uygulayın. Bu işlem aramadan, metin kutusuna arama sonuçları görüntüleme ve arama tamamlandığını bildirmek için bu yöntemi temel sınıf uygulamasını çağırma içerir.  
  
    ```csharp  
    public override IVsSearchTask CreateSearch(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback)  
    {  
        if (pSearchQuery == null || pSearchCallback == null)  
            return null;  
         return new TestSearchTask(dwCookie, pSearchQuery, pSearchCallback, this);  
    }  
  
    public override void ClearSearch()  
    {  
        TestSearchControl control = (TestSearchControl)this.Content;  
        control.SearchResultsTextBox.Text = control.SearchContent;  
    }  
  
    internal class TestSearchTask : VsSearchTask  
    {  
        private TestSearch m_toolWindow;  
  
        public TestSearchTask(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback, TestSearch toolwindow)  
            : base(dwCookie, pSearchQuery, pSearchCallback)  
        {  
            m_toolWindow = toolwindow;  
        }  
  
        protected override void OnStartSearch()  
        {  
            // Use the original content of the text box as the target of the search.   
            var separator = new string[] { Environment.NewLine };  
            TestSearchControl control = (TestSearchControl)m_toolWindow.Content;  
            string[] contentArr = control.SearchContent.Split(separator, StringSplitOptions.None);  
  
            // Get the search option.   
            bool matchCase = false;  
            // matchCase = m_toolWindow.MatchCaseOption.Value;   
  
                // Set variables that are used in the finally block.  
                StringBuilder sb = new StringBuilder("");  
                uint resultCount = 0;  
                this.ErrorCode = VSConstants.S_OK;  
  
                try  
                {  
                    string searchString = this.SearchQuery.SearchString;  
  
                    // Determine the results.   
                    uint progress = 0;  
                    foreach (string line in contentArr)  
                    {  
                        if (matchCase == true)  
                        {  
                            if (line.Contains(searchString))  
                            {  
                                sb.AppendLine(line);  
                                resultCount++;  
                            }  
                        }  
                        else  
                            {  
                                if (line.ToLower().Contains(searchString.ToLower()))  
                                {  
                                    sb.AppendLine(line);  
                                    resultCount++;  
                                }  
                            }  
  
                            // SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));   
  
                            // Uncomment the following line to demonstrate the progress bar.   
                            // System.Threading.Thread.Sleep(100);  
                        }  
                    }  
                    catch (Exception e)  
                    {  
                        this.ErrorCode = VSConstants.E_FAIL;  
                    }  
                    finally  
                    {  
                        ThreadHelper.Generic.Invoke(() =>  
                        { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });  
  
                        this.SearchResults = resultCount;  
                    }  
  
            // Call the implementation of this method in the base class.   
            // This sets the task status to complete and reports task completion.   
            base.OnStartSearch();  
        }  
  
        protected override void OnStopSearch()  
        {  
            this.SearchResults = 0;  
        }  
    }  
    ```  
  
3.  Aşağıdaki adımları gerçekleştirerek arama uygulamanızı test edin:  
  
    1.  Projeyi oluşturmak ve hata ayıklamayı Başlat.  
  
    2.  Visual Studio'nun deneysel örneği, aracı penceresini yeniden açın, arama penceresinde bazı arama metni girin ve ENTER tuşuna basın.  
  
         Doğru sonuçlar görüntülenmesi gerekir.  
  
## <a name="to-customize-the-search-behavior"></a>Arama davranışını özelleştirmek için  
 Arama ayarları değiştirerek arama denetimini nasıl göründüğünü ve arama nasıl gerçekleştirildiği değişiklikleri çeşitli yapabilirsiniz. Örneğin, filigran (arama kutusunda görüntülenen varsayılan metin), en düşük ve en büyük genişliği arama denetiminin ve bir ilerleme çubuğu gösterilip gösterilmeyeceğini değiştirebilirsiniz. (İsteğe bağlı veya hızlı arama) görünmesini hangi arama sonuçları başlatın ve bir listesi için son arama terimleri gösterilip gösterilmeyeceğini noktada de değiştirebilirsiniz. Ayarların tam listesi bulabilirsiniz <xref:Microsoft.VisualStudio.PlatformUI.SearchSettingsDataSource> sınıfı.  
  
1.  TestSearch.cs dosyasına aşağıdaki kodu ekleyin `TestSearch` sınıfı. Bu kod, isteğe bağlı arama (kullanıcının ENTER tıklattığınızdan yoksa anlamına gelir) yerine hızlı arama sağlar. Kodu geçersiz kılmaları `ProvideSearchSettings` yönteminde `TestSearch` varsayılan ayarlarını değiştirmek gerekli olan sınıf.  
  
    ```csharp  
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)  
    {  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchStartTypeProperty.Name,   
            (uint)VSSEARCHSTARTTYPE.SST_INSTANT);}  
    ```  
  
2.  Yeni test çözümü yeniden oluşturma ve hata ayıklayıcısı yeniden ayarlama.  
  
     Arama sonuçları, arama kutusuna bir karakter girin, her zaman görüntülenir.  
  
3.  İçinde `ProvideSearchSettings` yöntemi, bir ilerleme çubuğu görüntülenmesini sağlar aşağıdaki satırı ekleyin.  
  
    ```csharp  
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)  
    {  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchStartTypeProperty.Name,   
             (uint)VSSEARCHSTARTTYPE.SST_INSTANT);  
        Utilities.SetValue(pSearchSettings,   
            SearchSettingsDataSource.SearchProgressTypeProperty.Name,   
             (uint)VSSEARCHPROGRESSTYPE.SPT_DETERMINATE);  
    }  
    ```  
  
     İlerleme çubuğu görünmesi ilerleme bildirilmelidir. İlerleme raporu için aşağıdaki kodda açıklamadan çıkarın `OnStartSearch` yöntemi `TestSearchTask` sınıfı:  
  
    ```csharp  
    SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));  
    ```  
  
4.  Yeterli ilerleme işleme yavaş çubuğu görünür, aşağıdaki satırı açıklamadan kaldırmasına `OnStartSearch` yöntemi `TestSearchTask` sınıfı:  
  
    ```csharp  
    System.Threading.Thread.Sleep(100);  
    ```  
  
5.  Yeni ayarları debugb için başlangıç ve çözümü yeniden sınayın.  
  
     İlerleme çubuğu arama penceresinde (olarak, arama metin kutusuna aşağıda mavi bir çizgi) her zaman bir arama yapmak görüntülenir.  
  
## <a name="to-enable-users-to-refine-their-searches"></a>Kullanıcıların kendi aramaları iyileştirmek için  
 Kullanıcıların kendi arama seçenekleri gibi İyileştir izin ver **eşleşen durumda** veya **eşleşen tam sözcükleri**. Onay kutularını veya düğmeleri olarak komutları olarak göründüğü seçenekleri boolean, olabilir. Bu kılavuz için bir Boole seçeneği oluşturacaksınız.  
  
1.  TestSearch.cs dosyasına aşağıdaki kodu ekleyin `TestSearch` sınıfı. Kodu geçersiz kılmaları `SearchOptionsEnum` belirli bir seçenek açmak veya kapatmak olup olmadığını algılamak arama uygulaması sağlayan yöntemi. Kodda `SearchOptionsEnum` talebine eşleştirmek için bir seçenek ekler bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumWindowSearchOptions> Numaralandırıcı. Büyük küçük harf duyarlı seçeneği de olarak kullanılabilir hale getirileceğini `MatchCaseOption` özelliği.  
  
    ```csharp  
    private IVsEnumWindowSearchOptions m_optionsEnum;  
    public override IVsEnumWindowSearchOptions SearchOptionsEnum  
    {  
        get  
        {  
            if (m_optionsEnum == null)  
            {  
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();  
  
                list.Add(this.MatchCaseOption);  
  
                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;  
            }  
            return m_optionsEnum;  
        }  
    }  
  
    private WindowSearchBooleanOption m_matchCaseOption;  
    public WindowSearchBooleanOption MatchCaseOption  
    {  
        get  
        {  
            if (m_matchCaseOption == null)  
            {  
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);  
            }  
            return m_matchCaseOption;  
        }  
    }  
    ```  
  
2.  İçinde `TestSearchTask` sınıfı, matchCase satırı açıklamadan kaldırmasına `OnStartSearch` yöntemi:  
  
    ```csharp  
    private IVsEnumWindowSearchOptions m_optionsEnum;  
    public override IVsEnumWindowSearchOptions SearchOptionsEnum  
    {  
        get  
        {  
            if (m_optionsEnum == null)  
            {  
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();  
  
                list.Add(this.MatchCaseOption);  
  
                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;  
            }  
            return m_optionsEnum;  
        }  
    }  
  
    private WindowSearchBooleanOption m_matchCaseOption;  
    public WindowSearchBooleanOption MatchCaseOption  
    {  
        get  
         {  
            if (m_matchCaseOption == null)  
            {  
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);  
            }  
            return m_matchCaseOption;  
        }  
    }  
    ```  
  
3.  Seçenek test edin:  
  
    1.  Projeyi derleyin ve hata ayıklamayı Başlat. Deneysel örneği görüntülenir.  
  
    2.  Araç penceresi metin kutusunun sağ tarafındaki aşağı ok seçin.  
  
         **Eşleşen durumda** onay kutusu görüntülenir.  
  
    3.  Seçin **eşleşen durumda** onay kutusunu işaretleyin ve sonra bazı aramaları gerçekleştirin.  
  
## <a name="to-add-a-search-filter"></a>Bir arama filtresi eklemek için  
 Arama hedeflerini kümesini iyileştirmek kullanıcıların arama filtreleri ekleyebilirsiniz. Örneğin, dosya Gezgini'ndeki dosyaları üzerinde bunların en son değiştirildiği tarih ve kendi dosya adı uzantıları tarafından filtre uygulayabilirsiniz. Bu kılavuzda, yalnızca bile satırlar için bir filtre ekleyeceksiniz. Kullanıcı Bu filtre seçtiğinde, arama ana belirttiğiniz dizeleri arama sorgusu ekler. Bu dizeler, arama yönteminin içinde tanımlamak ve arama hedeflerini buna göre filtreleyin.  
  
1.  TestSearch.cs dosyasına aşağıdaki kodu ekleyin `TestSearch` sınıfı. Kod uygulayan `SearchFiltersEnum` ekleyerek bir <xref:Microsoft.VisualStudio.PlatformUI.WindowSearchSimpleFilter> yalnızca bile satırları görünmesini sağlayacak şekilde arama sonuçlarını filtrelemek için belirtir.  
  
    ```csharp  
    public override IVsEnumWindowSearchFilters SearchFiltersEnum  
    {  
        get  
        {  
            List<IVsWindowSearchFilter> list = new List<IVsWindowSearchFilter>();  
            list.Add(new WindowSearchSimpleFilter("Search even lines only", "Search even lines only", "lines", "even"));  
            return new WindowSearchFilterEnumerator(list) as IVsEnumWindowSearchFilters;  
        }  
    }  
  
    ```  
  
     Arama filtresi arama denetimini görüntüler artık `Search even lines only`. Ne zaman kullanıcının seçtiği filtre dizesi `lines:"even"` arama kutusunda görüntülenir. Diğer arama ölçütlerini aynı anda filtre olarak yer alabilir. Arama dizelerini önce filtreyi, filtre veya her ikisi de sonra görünebilir.  
  
2.  TestSearch.cs dosyasında aşağıdaki yöntemi ekleyin `TestSearchTask` bulunduğu sınıfı `TestSearch` sınıfı. Bu yöntemler Destek `OnStartSearch` sonraki adımda değiştireceksiniz yöntemi.  
  
    ```csharp  
    private string RemoveFromString(string origString, string stringToRemove)  
    {  
        int index = origString.IndexOf(stringToRemove);  
        if (index == -1)  
            return origString;  
        else   
             return (origString.Substring(0, index) + origString.Substring(index + stringToRemove.Length)).Trim();  
    }  
  
    private string[] GetEvenItems(string[] contentArr)  
    {  
        int length = contentArr.Length / 2;  
        string[] evenContentArr = new string[length];  
  
        int indexB = 0;  
        for (int index = 1; index < contentArr.Length; index += 2)  
        {  
            evenContentArr[indexB] = contentArr[index];  
            indexB++;  
        }  
  
        return evenContentArr;  
    }  
    ```  
  
3.  İçinde `TestSearchTask` sınıfı, güncelleştirme `OnStartSearch` aşağıdaki kod ile yöntemi. Bu değişiklik filtre desteklemek için kodu güncelleştirir.  
  
    ```csharp  
    protected override void OnStartSearch()  
    {  
        // Use the original content of the text box as the target of the search.   
        var separator = new string[] { Environment.NewLine };  
        string[] contentArr = ((TestSearchControl)m_toolWindow.Content).SearchContent.Split(separator, StringSplitOptions.None);  
  
        // Get the search option.   
        bool matchCase = false;  
        matchCase = m_toolWindow.MatchCaseOption.Value;  
  
        // Set variables that are used in the finally block.  
        StringBuilder sb = new StringBuilder("");  
        uint resultCount = 0;  
        this.ErrorCode = VSConstants.S_OK;  
  
        try  
        {  
            string searchString = this.SearchQuery.SearchString;  
  
            // If the search string contains the filter string, filter the content array.   
            string filterString = "lines:\"even\"";  
  
            if (this.SearchQuery.SearchString.Contains(filterString))  
            {  
                // Retain only the even items in the array.  
                contentArr = GetEvenItems(contentArr);  
  
                // Remove 'lines:"even"' from the search string.  
                searchString = RemoveFromString(searchString, filterString);  
            }  
  
            // Determine the results.   
            uint progress = 0;  
            foreach (string line in contentArr)  
            {  
                if (matchCase == true)  
                {  
                    if (line.Contains(searchString))  
                    {  
                        sb.AppendLine(line);  
                        resultCount++;  
                    }  
                }  
                else  
                {  
                    if (line.ToLower().Contains(searchString.ToLower()))  
                    {  
                        sb.AppendLine(line);  
                        resultCount++;  
                    }  
                }  
  
                SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));  
  
                // Uncomment the following line to demonstrate the progress bar.   
                // System.Threading.Thread.Sleep(100);  
            }  
        }  
        catch (Exception e)  
        {  
            this.ErrorCode = VSConstants.E_FAIL;  
        }  
        finally  
        {  
            ThreadHelper.Generic.Invoke(() =>  
            { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });  
  
            this.SearchResults = resultCount;  
        }  
  
        // Call the implementation of this method in the base class.   
        // This sets the task status to complete and reports task completion.   
        base.OnStartSearch();  
    }  
    ```  
  
4.  Kodunuzu test etmek.  
  
5.  Projeyi derleyin ve hata ayıklamayı Başlat. Visual Studio deneysel örneğinde, araç penceresi açın ve ardından arama denetimini aşağı oka seçin.  
  
     **Eşleşen durumda** onay kutusunu ve **arama yalnızca bile satırları** filtre görünür.  
  
6.  Filtre seçin.  
  
     Arama kutusuna içeren **satırları: "bile"**, ve aşağıdaki sonuçlar görüntülenir:  
  
     iyi 2  
  
     4 iyi  
  
     6 güle güle  
  
7.  Silme `lines:"even"` arama kutusundan **eşleşen durumda** onay kutusunu işaretleyin ve ardından girin `g` arama kutusuna.  
  
     Aşağıdaki sonuçları görüntülenir:  
  
     1 Git  
  
     iyi 2  
  
     5 güle güle  
  
8.  Arama kutusunun sağ tarafındaki X'i seçin.  
  
     Arama kaldırılır ve özgün içeriği görüntülenir. Ancak, **eşleşen durumda** onay kutusunun seçili hala.