---
title: Web Performans Testi Sonuçları Görüntüleyicisi için Visual Studio eklentisi oluşturma
ms.date: 10/20/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, Visual Studio Add-in
- Visual Studio Add-in, Web performance tests
ms.assetid: 1118c604-4b1b-4b21-a04e-45995b676fa8
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 2d3f0ec5108d077346eb69f1fb1236a7ecee56d5
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751682"
---
# <a name="how-to-create-a-visual-studio-add-in-for-the-web-performance-test-results-viewer"></a>Nasıl yapılır: Web Başarım Testi Sonuçları Görüntüleyicisi için bir Visual Studio Eklentisi Oluşturma

Şu ad alanlarından kullanarak Web Performans Testi Sonuçları Görüntüleyicisi için UI genişletebilirsiniz:

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting>

-   <xref:Microsoft.VisualStudio.TestTools.WebTesting>

Ayrıca, bulunan LoadTestPackage DLL için bir başvuru eklemeniz gerekir *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies* klasör.

-   Web Performans Testi Sonuçları Görüntüleyicisi'nin UI genişletmek için Visual Studio eklentisi ve bir kullanıcı denetimi oluşturmanız gerekir. Aşağıdaki yordamlarda, eklentiyi oluşturma açıklanmaktadır kullanıcı denetimi ve Web Performans Testi Sonuçları Görüntüleyicisi'nin UI genişletmek gerekli sınıfların gerçekleştirme.

## <a name="create-or-open-a-solution-that-contains-an-aspnet-web-application-and-a-web-performance-and-load-test-project"></a>Oluşturun veya bir ASP.NET Web uygulaması ve Web performansı ve yük testi projesi içeren bir çözüm açın

### <a name="to-prepare-for-extending-the-web-performance-test-results-viewer"></a>Web Performans Testi Sonuçları Görüntüleyicisi genişletmek için hazırlamak için

Oluşturabilir veya, bir ASP.NET Web uygulaması içeren deneyimleyebilirsiniz ve Web performansı ve yük ile bir veya daha fazla Web performans testleri ASP.NET Web uygulaması için projeyi test üretim dışı çözümü açın.

> [!NOTE]
> Bir ASP.NET Web uygulaması oluşturabilir ve Web performansı ve yük test etme yordamları izleyerek Web performans testleri içeren projesi [nasıl yapılır: Web hizmet testi oluşturma](../test/how-to-create-a-web-service-test.md) ve [oluşturma ve çalıştırma kodlanmış web performans testi](../test/generate-and-run-a-coded-web-performance-test.md).

## <a name="create-a-visual-studio-add-in"></a>Visual Studio eklentisi oluşturma

Bir eklenti Visual Studio tümleşik geliştirme ortamı (IDE) çalıştıran bir derlenmiş DLL ' dir. Derleme, fikri mülkiyet korunmasına yardımcı olur ve performansı artırır. Eklentiler el ile oluşturabilirsiniz, ancak Eklenti Sihirbazı'nı kullanmayı daha kolay bulabilirsiniz. Bu sihirbaz, bir işlev ancak temel oluşturduktan sonra hemen çalıştırılabilen eklentisi oluşturur. Eklenti Sihirbazı temel programı oluşturduktan sonra kodu ekleyin ve özelleştirin.

 Eklenti Sihirbazı'nı bir görünen ad ve açıklama eklentiniz için sağlamanıza olanak tanır. Her ikisi de görünür **Eklenti Yöneticisi**. İsteğe bağlı olarak, ekleyen Sihirbazı kodu oluşturmasını sağlayabilirsiniz **Araçları** menü eklenti açmak için bir komutu. Ayrıca özel görüntülemeyi seçebilirsiniz **hakkında** eklentiniz için iletişim kutusu. Sihirbaz tamamlandığında, eklentiyi uygulayan yalnızca bir sınıfı olan yeni bir proje sahip. Bu sınıf, Bağlan olarak adlandırılır.

 Kullanacağınız **Eklenti Yöneticisi** bu konunun sonundaki.

### <a name="to-create-an-add-in-by-using-the-add-in-wizard"></a>Eklenti Sihirbazı'nı kullanarak bir eklenti oluşturmak için

1.  Çözüm Gezgini'nde çözüme sağ tıklayın, seçin **Ekle** ve ardından **yeni proje**.

     Yeni Proje iletişim kutusu görüntülenir.

2.  Altında **yüklü şablonlar**, genişletin **diğer proje türleri** seçip **genişletilebilirlik**.

3.  Şablonları listesinde seçin **Visual Studio eklentisi**.

4.  Adı altında eklenti için bir ad yazın. Örneğin, **WebPerfTestResultsViewerAddin**.

5.  Seçin **Tamam**.

     Visual Studio eklentisi Sorgu Sihirbazı'nı başlatır.

6.  Seçin **sonraki**.

7.  Üzerinde **bir programlama dili seç** sayfasında, eklenti yazmak için kullanmak istediğiniz programlama dilini seçin.

    > [!NOTE]
    > Bu konuda Visual C# örnek kodunu kullanır.

8.  Üzerinde **seçin uygulama ana bilgisayarı** sayfasında **Visual Studio** ve temizleyin **Visual Studio makroları**.

9. Seçin **sonraki**.

10. Bir ad ve açıklama eklentiniz için yazın **bir ad ve açıklama girin** sayfası.

     Eklenti oluşturulduktan sonra adını ve açıklamasını görüntülenen **kullanılabilir eklentiler** listesinde **Eklenti Yöneticisi**. Böylece kullanıcılar hangi eklentiniz öğrenebilirsiniz eklentiniz açıklamasına yeterli ayrıntı yok, nasıl çalışır ve benzeri ekleyin.

11. Seçin **sonraki**.

12. Üzerinde **eklenti seçeneklere** sayfasında, **my ana bilgisayar uygulaması başladığında yüklemek için eklenti ister misiniz**.

13. Kalan onay kutularını temizleyin.

14. Üzerinde **seçme 'Yardım konusu' bilgilerini** sayfasında, görüntülenecek eklentiniz hakkında bilgileri istediğinizi belirtebilirsiniz bir **hakkında** iletişim kutusu. Görüntülenecek bilgi istiyorsanız seçin **my 'İlgili' kutusu bilgileri sunmak için eklenti Evet, istiyorum** onay kutusu.

     Visual Studio eklenebilir bilgi **hakkında** sürüm numarası, destek ayrıntıları, lisans verilerini ve benzeri iletişim kutusu içerir.

15. Seçin **sonraki**.

16. Seçtiğiniz seçenekleri görüntülenmiyor **Özet** gözden geçirmeniz için sayfa. Memnun kaldığınızda **son** eklenti oluşturmak için. Bir şey değiştirmek istiyorsanız, tercih **geri** düğmesi.

     Yeni bir çözüm ve Proje oluşturulur ve yeni eklenti için Connect.cs dosyası Kod Düzenleyicisi'nde görüntülenir.

     Bir kullanıcı denetimi oluşturan aşağıdaki yordam bu WebPerfTestResultsViewerAddin projesi tarafından başvurulacak sonra Connect.cs dosyasına kod ekleyeceksiniz.

 Bir eklenti oluşturulduktan sonra etkinleştirilmeden önce onu Visual Studio ile kaydetmeniz gerekir **Eklenti Yöneticisi**. Bunun için bir .addin dosya adı uzantısına sahip bir XML dosyası kullanarak.

 .Addin dosyasının içinde görüntülemek için Visual Studio gerektirir bilgiler açıklanmaktadır **Eklenti Yöneticisi**. Visual Studio başladığında, tüm kullanılabilir .addin dosyaları için .addin dosya konumuna bakar. Herhangi bir bulursa, XML dosyasını okur ve verir **Eklenti Yöneticisi** eklenti tıklandığında başlatmak için gereken bilgileri.

 Bir eklenti Eklenti Sihirbazı'nı kullanarak oluşturduğunuz .addin dosyası otomatik olarak oluşturulur.

### <a name="add-in-file-locations"></a>Eklenti dosyası konumları

.Addin dosyasının iki kopyasını Eklenti Sihirbazı tarafından otomatik olarak şu şekilde oluşturulur:

|**. Eklentisi dosya konumu**|**Açıklama**|
|------------------------------|----------------------------|---------------------|
|Kök proje klasörü|Eklenti projesi dağıtımı için kullanılır. Proje düzenleme kolaylığı için dahil ve XCopy tarzı dağıtımının yerel yolu vardır.|
|Eklenti klasörü|Eklenti hata ayıklama ortamında çalıştırmak için kullanılır. Her zaman geçerli yapı yapılandırması çıkış yoluna işaret etmelidir.|

## <a name="create-a-windows-form-control-library-project"></a>Windows Form denetimi kitaplığı projesi oluşturma

Önceki yordamda oluşturduğunuz Visual Studio Eklentisi örneği oluşturmak için bir Windows Forms Denetim Kitaplığı projeye başvuruda bulunan bir <xref:System.Windows.Forms.UserControl> sınıfı.

### <a name="to-create-a-control-to-be-used-in-the-web-test-results-viewer"></a>Web Testi Sonuçları Görüntüleyicisi'nde kullanılacak bir denetim oluşturmak için

1.  Çözüm Gezgini'nde çözüme sağ tıklayın, seçin **Ekle** ve ardından **yeni proje**.

     **Yeni proje** iletişim kutusu görüntülenir.

2.  Altında **yüklü şablonlar**, genişletin **ya da Visual Basic** veya **Visual C#** seçip **Windows**.

    > [!NOTE]
    > Bu konuda Visual C# örnek kodunu kullanır.

3.  Şablonları listesinde seçin **Windows Forms Denetim Kitaplığı**.

4.  Altında **adı**, eklenti için bir ad yazın. Örneğin, **WebPerfTestResultsViewerControl**.

5.  Seçin **Tamam**.

     Çözüm Gezgini ve UserControl1.cs WebPerfTestResultsViewerControl eklenen Windows forms denetimi kitaplığı projesi Tasarım modunda görüntülenir.

6.  Araç Kutusu'ndan sürükleyin bir <xref:System.Windows.Forms.DataGridView> userControl1 yüzeyine.

7.  Eylem etiketi karakter tıklayın (![akıllı etiket karakteri](../test/media/vs_winformsmttagglyph.gif)) sağ üst köşesindeki <xref:System.Windows.Forms.DataGridView> ve aşağıdaki adımları izleyin:

    1.  Seçin **Ana kapsayıcıda yerleştir**.

    2.  Onay kutularını temizleyin **eklemeyi etkinleştir**, **düzenlemeyi etkinleştir**, **Enable Deleting** ve **sütun yeniden sıralamayı etkinleştir**.

    3.  Seçin **sütun eklemek**.

         **Sütun Ekle** iletişim kutusu görüntülenir.

    4.  İçinde **türü** aşağı açılan listesinden, **DataGridViewTextBoxColumn**.

    5.  "Column1" metin temizleyin **üstbilgi metni**.

    6.  Seçin **eklemek**.

    7.  Seçin **Kapat**.

8.  Özellikler penceresinde değiştirin **(ad)** özelliği <xref:System.Windows.Forms.DataGridView> için **resultControlDataGridView**.

9. Tasarım yüzeyi ve select sağ **görünümü kodu**.

     UserControl1.cs dosyası Kod Düzenleyicisi'nde görüntülenir.

10. Örneklenen adını değiştirmek <xref:System.Windows.Forms.UserControl> UserContro1 sınıfından resultControl için:

    ```csharp
    namespace WebPerfTestResultsViewerControl
    {
        public partial class resultControl : UserControl
        {
            public resultControl()
            {
                InitializeComponent();
            }
    ```

     Sonraki yordamda resultControl sınıfına başvuracak WebPerfTestResultsViewerAddin projesinin Connect.cs dosyasına kod ekleyeceksiniz.

     Bazı ek kod Connect.cs dosyasına daha sonra eklemek olacaktır.

## <a name="add-code-to-the-webperftestresultsvieweraddin"></a>WebPerfTestResultsViewerAddin için kod ekleme

### <a name="to-add-code-to-the-visual-studio-add-in-to-extend-the-web-test-results-viewer"></a>Visual Studio Web Testi Sonuçları Görüntüleyicisi genişletmek için eklenti için kod eklemek için

1.  Çözüm Gezgini'nde sağ **başvuruları** seçin ve WebPerfTestResultsViewerAddin proje düğümünde **Başvuru Ekle**.

2.  İçinde **Başvuru Ekle** iletişim kutusunda, seçin **.NET** sekmesi.

3.  Seçin ve aşağı kaydırma **Microsoft.VisualStudio.QualityTools.WebTestFramework** ve **System.Windows.Forms**.

4.  Seçin **Tamam**.

5.  Sağ **başvuruları** düğümü yeniden ve select **Başvuru Ekle**.

6.  İçinde **Başvuru Ekle** iletişim kutusunda, seçin **Gözat** sekmesi.

7.  İçin açılan seçin **konum** ve % ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies gidin ve Microsoft.VisualStudio.QualityTools.LoadTestPackage.dll seçin dosya.

8.  Seçin **Tamam**.

9. WebPerfTestResultsViewerAddin proje düğümüne sağ tıklayın ve seçin **Başvuru Ekle**.

10. İçinde **Başvuru Ekle** iletişim kutusunda, seçin **projeleri** sekmesi.

11. Altında **proje adı**seçin **WebPerfTestResultsViewerControl** proje ve seçin **Tamam**.

12. Connect.cs dosyası Solution Explorer'da hala açık değilse, sağ **Connect.cs** dosya WebPerfTestResultsViewerAddin projesinde ve seçin **görünümü kodu**.

13. Connect.cs dosyasında aşağıdaki kullanım deyimini ekleyin:

    ```csharp
    using System.IO;
    using System.Windows.Forms;
    using System.Collections.Generic;
    using Microsoft.VisualStudio.TestTools.LoadTesting;
    using Microsoft.VisualStudio.TestTools.WebTesting;
    using WebPerfTestResultsViewerControl;
    ```

14. Connect.cs dosyası en alta kadar kaydırın kaydırın. GUID'lerini listesini eklemeniz <xref:System.Windows.Forms.UserControl> Web Performans Testi Sonuçları Görüntüleyicisi birden fazla örneğini açık olması durumunda. Bu listeyi kullanan kodu ekleyeceksiniz.

     İkinci bir dize listesi, daha sonra kod OnDiscconection yönteminde kullanılır.

    ```csharp
    private DTE2 _applicationObject;
    private AddIn _addInInstance;

    private Dictionary<Guid, List<UserControl>> m_controls = new Dictionary<Guid, List<UserControl>>();        private List<string> temporaryFilePaths = new List<string>();
    ```

15. Connect.cs dosyası Bağlan adında bir sınıf oluşturur <xref:Extensibility.IDTExtensibility2> sınıfı ve Visual Studio eklentisi uygulanması için bazı yöntemler de içerir. Yöntemlerden birini eklenti yüklenmekte olduğuna dair bildirim alan OnConnection yöntemidir. OnConnection yönteminde Web Performans Testi Sonuçları Görüntüleyicisi için genişletilebilirlik paketinizi oluşturmak için LoadTestPackageExt sınıfını kullanır. OnConnection yöntemine aşağıdaki kodu ekleyin:

    ```csharp
    public void OnConnection(object application, ext_ConnectMode connectMode, object addInInst, ref Array custom)
                {
                _applicationObject = (DTE2)application;
                _addInInstance = (AddIn)addInInst;

                // Create a load test packge extensibility class.            LoadTestPackageExt loadTestPackageExt = _applicationObject.GetObject("Microsoft.VisualStudio.TestTools.LoadTesting.LoadTestPackageExt") as LoadTestPackageExt;            // Process open windows.            foreach (WebTestResultViewer webTestResultViewer in loadTestPackageExt.WebTestResultViewerExt.ResultWindows)            {                WindowCreated(webTestResultViewer);            }            // Create event handlers.            loadTestPackageExt.WebTestResultViewerExt.WindowCreated += new EventHandler<WebTestResultViewerExt.WindowCreatedEventArgs>(WebTestResultViewerExt_WindowCreated);            loadTestPackageExt.WebTestResultViewerExt.WindowClosed += new EventHandler<WebTestResultViewerExt.WindowClosedEventArgs>(WebTesResultViewer_WindowClosed);            loadTestPackageExt.WebTestResultViewerExt.SelectionChanged += new EventHandler<WebTestResultViewerExt.SelectionChangedEventArgs>(WebTestResultViewer_SelectedChanged);
            }
    ```

16. Yönteminin Webtestresultviewerext_windowcreated yöntemi ve OnConnection yöntemine eklediğiniz loadTestPackageExt.WebTestResultViewerExt.WindowCreated olay işleyicisi için oluşturmak için bağlan sınıfına aşağıdaki kodu ekleyin, WindowCreated yöntemi çağırır.

    ```csharp
            void WebTestResultViewerExt_WindowCreated(object sender, WebTestResultViewerExt.WindowCreatedEventArgs e)
            {
                // New control added to new result viewer window.
                WindowCreated(e.WebTestResultViewer);
            }

    private void WindowCreated(WebTestResultViewer viewer)        {            // Instantiate an instance of the resultControl referenced in the WebPerfTestResultsViewerControl project.
                resultControl resultControl = new resultControl();            // Add to the dictionary of open playback windows.            System.Diagnostics.Debug.Assert(!m_controls.ContainsKey(viewer.TestResultId));            List<UserControl> userControls = new List<UserControl>();            userControls.Add(resultControl);            // Add Guid to the m_control List to manage Result viewers and controls.            m_controls.Add(viewer.TestResultId, userControls);            // Add tabs to the playback control.            resultControl.Dock = DockStyle.Fill;            viewer.AddResultPage(new Guid(), "Sample", resultControl);        }
    ```

17. OnConnection yöntemine eklediğiniz loadTestPackageExt.WebTestResultViewerExt.SelectionChanged olay işleyicisine yönelik WebTestResultViewer_SelectedChanged yöntemi oluşturmak için bağlan sınıfına aşağıdaki kodu ekleyin:

    ```csharp
    void WebTestResultViewer_SelectedChanged(object sender, WebTestResultViewerExt.SelectionChangedEventArgs e)
    {
        foreach (UserControl userControl in m_controls[e.TestResultId])            {                // Update the userControl in each result viewer.                resultControl resultControl = userControl as resultControl;                if (resultControl != null)                    // Call the resultControl's Update method (This will be added in the next procedure).                    resultControl.Update(e.WebTestRequestResult);            }
    }
    ```

18. OnConnection yöntemine eklediğiniz loadTestPackageExt.WebTestResultViewerExt.WindowClosed için olay işleyicisini WebTesResultViewer_WindowClosed yöntemi oluşturmak için bağlan sınıfına aşağıdaki kodu ekleyin:

    ```csharp
    void WebTesResultViewer_WindowClosed(object sender, WebTestResultViewerExt.WindowClosedEventArgs e)
    {
        if (m_controls.ContainsKey(e.WebTestResultViewer.TestResultId))
        {
            m_controls.Remove(e.WebTestResultViewer.TestResultId);
        }
    }
    ```

     Kod için Visual Studio eklentisi tamamladığınıza göre resultControl güncelleştirme yöntemi eklemeniz gerekir WebPerfTestResultsViewerControl projesindeki.

## <a name="add-code-to-the-webperftestresultsviewercontrol"></a>Kodu WebPerfTestResultsViewerControl'a ekleyin

### <a name="to-add-code-to-the-user-control"></a>Kullanıcı denetimine kod eklemek için

1.  Çözüm Gezgini'nde WebPerfTestResultsViewerControl proje düğümüne sağ tıklayın ve seçin **özellikleri**.

2.  Seçin **uygulama** sekmesini ve ardından **hedef framework** aşağı açılan liste ve seçin **.NET Framework 4** ve özellikleri'ni kapatın.

     Web Performans Testi Sonuçları Görüntüleyicisi genişletmek için gereken DLL başvurularını desteklemek için bu gereklidir.

3.  Çözüm Gezgini'nde WebPerfTestResultsViewerControl projeye sağ **başvuruları** düğümü ve select **Başvuru Ekle**.

4.  İçinde **Başvuru Ekle** iletişim kutusu, tıklatın **.NET** sekmesi.

5.  Seçin ve aşağı kaydırma **Microsoft.VisualStudio.QualityTools.WebTestFramework**.

6.  Seçin **Tamam**.

7.  UserControl1.cs dosyasında aşağıdaki kullanım deyimini ekleyin:

    ```csharp
    using Microsoft.VisualStudio.TestTools.WebTesting;
    using Microsoft.VisualStudio.TestTools.WebTesting.Rules;
    ```

8.  Çağrılan ve WebTestRequestResult Connect.cs dosyasına WebPerfTestResultsViewerAddin WebTestResultViewer_SelectedChanged yönteminden geçirilen güncelleştirme yöntemi ekleyin. Update yöntemi DataGridView WebTestRequestResult geçirilen çeşitli özellikleri ile doldurur.

    ```csharp
    public void Update(WebTestRequestResult WebTestResults)
            {
                // Clear the DataGridView when a request is selected.
                resultControlDataGridView.Rows.Clear();
                // Populate the DataGridControl with properties from the WebTestResults.
                this.resultControlDataGridView.Rows.Add("Request: " + WebTestResults.Request.Url.ToString());
                this.resultControlDataGridView.Rows.Add("Response: " + WebTestResults.Response.ResponseUri.ToString());
                foreach (RuleResult ruleResult in WebTestResults.ExtractionRuleResults)
                {
                    this.resultControlDataGridView.Rows.Add("Extraction rule results: " + ruleResult.Message.ToString());
                }
                foreach (RuleResult ruleResult in WebTestResults.ValidationRuleResults)
                {
                    this.resultControlDataGridView.Rows.Add("Validation rule results: " + ruleResult.Message.ToString());
                }
                foreach (WebTestError webTestError in WebTestResults.Errors)
                {
                    this.resultControlDataGridView.Rows.Add("Error: " + webTestError.ErrorType.ToString() + " " + webTestError.ErrorSubtype.ToString() + " " + webTestError.ExceptionText.ToString());
                }
            }
    ```

## <a name="build-the-webperftestresultsvieweraddin-solution"></a>WebPerfTestResultsViewerAddin çözümü oluşturun

### <a name="to-build-the-solution"></a>Çözümü derlemek için

-   Üzerinde **yapı** menüsünde, select **yapı çözümü**.

## <a name="register-the-webperftestresultsvieweraddin-add-in"></a>WebPerfTestResultsViewerAddin Eklentisini Kaydet

### <a name="to-register-the-add-in-using-the-add-in-manager"></a>Eklenti Yöneticisi'ni kullanarak olarak kaydetmek için

1.  Üzerinde **Araçları** menüsünde, select **Eklenti Yöneticisi**.

2.  **Eklenti Yöneticisi** iletişim kutusu görüntülenir.

3.  WebPerfTestResultsViewerAddin eklentide onay kutusunu seçin **kullanılabilir eklentiler** sütun ve clear onay kutularını altında **başlangıç** ve **komut satırı**sütun.

4.  Seçin **Tamam**.

## <a name="run-the-web-performance-test-using-the-build-the-webperftestresultsvieweraddin-add-in"></a>Yapı WebPerfTestResultsViewerAddin eklentisi kullanarak Web performans testini çalıştırma

### <a name="to-run-the-new-vs-add-in-for-the-web-test-results-viewer"></a>Web Testi Sonuçları Görüntüleyicisi için yeni VS eklentisini çalıştırmak için

1.  Web performans testini çalıştırma ve Web Performans Testi Sonuçları Görüntüleyicisi'nde görüntülenen Örnek başlıklı WebPerfTestResultsViewerAddin eklentinin yeni sekmede görürsünüz.

2.  DataGridView üzerinde sunulan özelliklerini görmek için sekmesini seçin.

## <a name="net-framework-security"></a>.NET Framework Güvenliği

Otomatik olarak etkinleştirme amaçlı eklentiler engelleyerek güvenliğini artırmak için Visual Studio ayarlarında sağlar bir **Araçlar Seçenekler** adlı sayfası **/makroları güvenlik**.

Ayrıca, bu seçenekler sayfası, Visual Studio için arama klasörleri belirtmenize olanak sağlar. Eklentisi kayıt dosyaları. Bu konumları sınırlamanıza olanak tanıyarak güvenliği artırır burada. Eklentisi kayıt dosyaları okuyabilir. Bu, kötü amaçlı önlemeye yardımcı olur. Kasıtsız olarak kullanılan eklentisi dosyaları.

 **Eklenti güvenlik ayarları**

 İçin seçenekler sayfası ayarlarında güvenlik aşağıdaki gibidir Eklentisi:

-   **Yüklenecek eklenti bileşenlerine izin verin.** Varsayılan olarak seçilidir. Seçili olduğunda, eklentiler Visual Studio'da yüklemesine izin verilir. Seçili olmadığında, Visual Studio yüklenmesini eklentiler yasaktır.

-   **Bir URL'den yüklenecek eklenti bileşenlerine izin verin.** Varsayılan olarak seçili değildir. Seçili olduğunda, eklentiler dış Web sitelerinden yüklenmesine izin verilmez. Seçili olmadığında, uzak eklentiler Visual Studio'da yüklenmesini yasaktır. Ardından bir eklenti herhangi bir nedenden dolayı yüklenemiyorsa, Web'den yüklenemiyor. Bu ayar, yalnızca yükleme denetler eklentisi DLL. . Eklentisi kayıt dosyaları her zaman yerel sistemde bulunması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Windows.Forms.UserControl>
- <xref:Microsoft.VisualStudio.TestTools.LoadTesting>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules>
- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.DataGrid>
- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)