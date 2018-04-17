---
title: 'İzlenecek yol: ampul önerileri görüntüleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 99e5566d-450e-4660-9bca-454e1c056a02
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 750e3b0915478b4249ce8db1ac294c1f2a3006f5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-displaying-light-bulb-suggestions"></a>İzlenecek yol: ampul önerileri görüntüleme
Ampuller eylemler kümesini görüntülemek için'nı genişletin, örneğin yerleşik kod çözümleyicilerini veya yeniden düzenleme kod tarafından tanımlanan sorunları giderir Visual Studio düzenleyicisinde kullanılan simgeler şunlardır.  
  
 Visual C# ve Visual Basic düzenleyicileri yazma ve kendi kod çözümleyicilerini ampuller otomatik olarak görüntüleme eylemleri olan paket için .NET derleyici Platformu ("Roslyn") kullanabilirsiniz. Daha fazla bilgi için bkz.:  
  
-   [Nasıl yapılır: C# tanılama ve düzeltme kod yazma](https://github.com/dotnet/roslyn/wiki/How-To-Write-a-C%23-Analyzer-and-Code-Fix)  
  
-   [Nasıl yapılır: Visual Basic tanılama ve düzeltme kod yazma](https://github.com/dotnet/roslyn/wiki/How-To-Write-a-Visual-Basic-Analyzer-and-Code-Fix)  
  
 C++ gibi diğer dilleri ampuller bu işlev bir saplama uygulaması oluşturmak için bir öneri gibi bazı hızlı eylemler için de sağlar.  
  
 İşte bir ampul gibi görünüyor. Geçersiz olduğunda bir Visual Basic veya Visual C# projesinde kırmızı dalgalı bir değişken adı altında görüntülenir. Geçersiz tanımlayıcı fare bir ampul imlecin yanında görüntülenir.  
  
 ![Ampul](../extensibility/media/lightbulb.png "ampul")  
  
 Ampul tarafından aşağı oku tıklatın, seçili eylem önizlemesini yanı sıra önerilen eylemler kümesi görüntülenir. Bu durumda, eylem yürütüyorsa kodunuzu yapılan değişiklikleri gösterir.  
  
 ![Ampul Önizleme](../extensibility/media/lightbulbpreview.png "LightBulbPreview")  
  
 Önerilen eylemleri sağlamak için ampuller kullanabilirsiniz. Örneğin, yeni bir satıra süslü ayraçlar açma taşıyabilir veya önceki satırın sonuna taşı eylemleri sağlayabilir. Aşağıdaki örneklerde geçerli sözcüğü görünür bir ampul oluşturulacağını gösterir ve iki önerilen eylemler vardır: **büyük harfe Dönüştür** ve **küçük harfe Dönüştür**.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Yönetilen Genişletilebilirlik Çerçevesi (MEF) proje oluşturma  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `LightBulbTest`.  
  
2.  Ekleme bir **Düzenleyicisi sınıflandırıcı** projeye öğe şablonu. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
4.  Aşağıdaki başvuru projeye ekleyin ve ayarlayın **kopya yerel** için `False`:  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
5.  Yeni bir sınıf dosyası ekleyin ve adını **LightBulbTest**.  
  
6.  Aşağıdaki using deyimlerini:  
  
    ```csharp  
    using System;  
    using System.Linq;  
    using System.Collections.Generic;  
    using System.Threading.Tasks;  
    using Microsoft.VisualStudio.Language.Intellisense;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Text.Operations;  
    using Microsoft.VisualStudio.Utilities;  
    using System.ComponentModel.Composition;  
    using System.Threading;  
  
    ```  
  
## <a name="implementing-the-light-bulb-source-provider"></a>Ampul kaynak sağlayıcıyı uygulama  
  
1.  LightBulbTest.cs sınıf dosyasında LightBulbTest sınıfı silin. Adlı bir sınıf ekleyin **TestSuggestedActionsSourceProvider** uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>. Bir adı ile dışarı **Test Önerilen Eylemler** ve <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "metin".  
  
    ```csharp  
    [Export(typeof(ISuggestedActionsSourceProvider))]  
    [Name("Test Suggested Actions")]  
    [ContentType("text")]  
    internal class TestSuggestedActionsSourceProvider : ISuggestedActionsSourceProvider  
    ```  
  
2.  Kaynak sağlayıcı sınıfı içinde alma <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> ve bir özellik olarak ekleyin.  
  
    ```csharp  
    [Import(typeof(ITextStructureNavigatorSelectorService))]  
    internal ITextStructureNavigatorSelectorService NavigatorService { get; set; }  
    ```  
  
3.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider.CreateSuggestedActionsSource%2A> döndürülecek yöntemi bir <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource> nesnesi. Kaynak sonraki bölümde aşağıdakiler ele alınacaktır.  
  
    ```csharp  
    public ISuggestedActionsSource CreateSuggestedActionsSource(ITextView textView, ITextBuffer textBuffer)  
    {  
        if (textBuffer == null && textView == null)  
        {  
            return null;  
        }  
        return new TestSuggestedActionsSource(this, textView, textBuffer);  
    }  
    ```  
  
## <a name="implementing-the-isuggestedactionsource"></a>ISuggestedActionSource uygulama  
 Önerilen eylemi kaynak sağ bağlamda ekleme ve önerilen eylemler kümesi toplama sorumludur. Bu durumda bağlamı geçerli sözcüğü ve önerilen eylemleri **UpperCaseSuggestedAction** ve **LowerCaseSuggestedAction**, hangi aşağıdaki bölümde aşağıdakiler ele alınacaktır.  
  
1.  Bir sınıf ekleyin **TestSuggestedActionsSource** uygulayan <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>.  
  
    ```csharp  
    internal class TestSuggestedActionsSource : ISuggestedActionsSource  
    ```  
  
2.  Önerilen eylemi kaynak sağlayıcısı, metin arabelleği ve metin görünümü için özel salt okunur alanları ekleyin.  
  
    ```csharp  
    private readonly TestSuggestedActionsSourceProvider m_factory;  
    private readonly ITextBuffer m_textBuffer;  
    private readonly ITextView m_textView;  
    ```  
  
3.  Özel alanları ayarlar bir oluşturucu ekleyin.  
  
    ```csharp  
    public TestSuggestedActionsSource(TestSuggestedActionsSourceProvider testSuggestedActionsSourceProvider, ITextView textView, ITextBuffer textBuffer)  
    {  
        m_factory = testSuggestedActionsSourceProvider;  
        m_textBuffer = textBuffer;  
        m_textView = textView;  
    }  
    ```  
  
4.  İmleç sözcüğünü döndürür özel bir yöntem ekleyin. Aşağıdaki yöntemi imleci geçerli konumda arar ve word uzantı için metin Yapı Gezgini sorar. İmleç bir sözcük üzerinde ise <xref:Microsoft.VisualStudio.Text.Operations.TextExtent> out parametresinde döndürülen; Aksi takdirde `out` parametresi `null` ve yöntemi `false`.  
  
    ```csharp  
    private bool TryGetWordUnderCaret(out TextExtent wordExtent)  
    {  
        ITextCaret caret = m_textView.Caret;  
        SnapshotPoint point;  
  
        if (caret.Position.BufferPosition > 0)  
        {  
            point = caret.Position.BufferPosition - 1;  
        }  
        else  
        {  
            wordExtent = default(TextExtent);  
            return false;  
        }  
  
        ITextStructureNavigator navigator = m_factory.NavigatorService.GetTextStructureNavigator(m_textBuffer);  
  
        wordExtent = navigator.GetExtentOfWord(point);  
        return true;  
    }  
    ```  
  
5.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource.HasSuggestedActionsAsync%2A> yöntemi. Düzenleyici ampul görüntülenip görüntülenmeyeceğini çıkışı bulmak için bu yöntemi çağırır. Bu çağrı, genellikle, imleci bir satırından getirdiğinde veya fare bir hata dalgalı geldiğinde örneğin yapılır. Bu yöntem çalışırken taşımak diğer UI işlemleri izin vermek üzere uyumsuzdur. Çoğu durumda, bazı ayrıştırma ve geçerli analiz gerçekleştirmek için bu yöntemin gerekir, böylece işlenmesi biraz zaman alabilir.  
  
     Bizim uygulamasında, zaman uyumsuz olarak alır <xref:Microsoft.VisualStudio.Text.Operations.TextExtent> ve bazı metin boşluk dışında olup ölçüde başka bir deyişle, önemli olup olmadığını belirler.  
  
    ```csharp  
    public Task<bool> HasSuggestedActionsAsync(ISuggestedActionCategorySet requestedActionCategories, SnapshotSpan range, CancellationToken cancellationToken)  
    {  
        return Task.Factory.StartNew(() =>  
        {  
            TextExtent extent;  
            if (TryGetWordUnderCaret(out extent))  
            {  
                // don't display the action if the extent has whitespace  
                return extent.IsSignificant;  
              }  
            return false;  
        });  
    }  
    ```  
  
6.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource.GetSuggestedActions%2A> bir dizi döndürür yöntemi <xref:Microsoft.VisualStudio.Language.Intellisense.SuggestedActionSet> farklı içeren nesneleri <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction> nesneleri. Ampul genişletildiğinde bu yöntem çağrılır.  
  
    > [!WARNING]
    >  Emin olmanız gerekir, uygulamalarını `HasSuggestedActionsAsync()` ve `GetSuggestedActions()` olan tutarlı; olan, `HasSuggestedActionsAsync()` döndürür `true`, sonra `GetSuggestedActions()` görüntülemek için bazı eylemler olması gerekir. Çoğu durumda `HasSuggestedActionsAsync()` hemen önce çağrılır `GetSuggestedActions()`, ancak bu her zaman geçerli değildir. Örneğin, kullanıcı tuşlarına basarak ampul Eylemler çağırırsa (CTRL +.) yalnızca `GetSuggestedActions()` olarak adlandırılır.  
  
    ```csharp  
    public IEnumerable<SuggestedActionSet> GetSuggestedActions(ISuggestedActionCategorySet requestedActionCategories, SnapshotSpan range, CancellationToken cancellationToken)  
    {  
        TextExtent extent;  
        if (TryGetWordUnderCaret(out extent) && extent.IsSignificant)  
        {  
            ITrackingSpan trackingSpan = range.Snapshot.CreateTrackingSpan(extent.Span, SpanTrackingMode.EdgeInclusive);  
            var upperAction = new UpperCaseSuggestedAction(trackingSpan);  
            var lowerAction = new LowerCaseSuggestedAction(trackingSpan);  
            return new SuggestedActionSet[] { new SuggestedActionSet(new ISuggestedAction[] { upperAction, lowerAction }) };  
        }  
        return Enumerable.Empty<SuggestedActionSet>();  
    }   
    ```  
  
7.  Tanımlayan bir `SuggestedActionsChanged` olay.  
  
    ```csharp  
    public event EventHandler<EventArgs> SuggestedActionsChanged;  
    ```  
  
8.  Uygulama tamamlamak için için uygulamaları ekleme `Dispose()` ve `TryGetTelemetryId()` yöntemleri. Telemetri yapmak için bu nedenle yalnızca false değerini döndürür ve GUID Empty olarak ayarlamak istemezsiniz.  
  
    ```csharp  
    public void Dispose()  
    {  
    }  
  
    public bool TryGetTelemetryId(out Guid telemetryId)  
    {  
        // This is a sample provider and doesn't participate in LightBulb telemetry  
        telemetryId = Guid.Empty;  
        return false;  
    }  
    ```  
  
## <a name="implementing-light-bulb-actions"></a>Ampul eylemleri uygulama  
  
1.  Projede Microsoft.VisualStudio.Imaging.Interop.14.0.DesignTime.dll ve kümesi için bir başvuru ekleyin **kopya yerel** için `False`.  
  
2.  İki sınıf oluşturmak ilk adlı `UpperCaseSuggestedAction` ve ikinci adlı `LowerCaseSuggestedAction`. Her iki sınıfları uygulamak <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction>.  
  
    ```csharp  
    internal class UpperCaseSuggestedAction : ISuggestedAction   
    internal class LowerCaseSuggestedAction : ISuggestedAction  
    ```  
  
     Bir çağırır dışında her iki sınıflar benzer <xref:System.String.ToUpper%2A> ve diğer çağrılar <xref:System.String.ToLower%2A>. Yalnızca büyük Eylem sınıfına aşağıdaki adımları kapsar, ancak her iki sınıfları uygulamalıdır. Büyük harf eylem küçük eylemi uygulamak için bir desen olarak uygulamak için adımları kullanın.  
  
3.  Aşağıdaki using deyimlerini bu sınıfları için:  
  
    ```csharp  
    using Microsoft.VisualStudio.Imaging.Interop;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Documents;  
    using System.Windows.Media;  
  
    ```  
  
4.  Özel alanları kümesini bildirin.  
  
    ```csharp  
    private ITrackingSpan m_span;  
    private string m_upper;  
    private string m_display;  
    private ITextSnapshot m_snapshot;  
    ```  
  
5.  Alanları ayarlar bir oluşturucu ekleyin.  
  
    ```csharp  
    public UpperCaseSuggestedAction(ITrackingSpan span)  
    {  
        m_span = span;  
        m_snapshot = span.TextBuffer.CurrentSnapshot;  
        m_upper = span.GetText(m_snapshot).ToUpper();  
        m_display = string.Format("Convert '{0}' to upper case", span.GetText(m_snapshot));  
    }  
    ```  
  
6.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.GetPreviewAsync%2A> böylece olan eylem Önizleme görüntüler yöntemi.  
  
    ```csharp  
    public Task<object> GetPreviewAsync(CancellationToken cancellationToken)  
    {  
        var textBlock = new TextBlock();  
        textBlock.Padding = new Thickness(5);  
        textBlock.Inlines.Add(new Run() { Text = m_upper });  
        return Task.FromResult<object>(textBlock);  
    }  
    ```  
  
7.  Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.GetActionSetsAsync%2A> boş bir şekilde döndürecek şekilde yöntemi <xref:Microsoft.VisualStudio.Language.Intellisense.SuggestedActionSet> numaralandırması.  
  
    ```csharp  
    public Task<IEnumerable<SuggestedActionSet>> GetActionSetsAsync(CancellationToken cancellationToken)  
    {  
        return Task.FromResult<IEnumerable<SuggestedActionSet>>(null);  
    }  
    ```  
  
8.  Özellikler aşağıdaki gibi uygulayın.  
  
    ```csharp  
    public bool HasActionSets  
    {  
        get { return false; }  
    }  
    public string DisplayText  
    {  
        get { return m_display; }  
    }  
    public ImageMoniker IconMoniker  
    {  
       get { return default(ImageMoniker); }  
    }  
    public string IconAutomationText  
    {  
        get  
        {  
            return null;  
        }  
    }  
    public string InputGestureText  
    {  
        get  
        {  
            return null;  
        }  
    }  
    public bool HasPreview  
    {  
        get { return true; }  
    }  
    ```  
  
9. Uygulama <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedAction.Invoke%2A> büyük eşdeğerleriyle aralık metinde değiştirerek yöntemi.  
  
    ```csharp  
    public void Invoke(CancellationToken cancellationToken)  
    {  
        m_span.TextBuffer.Replace(m_span.GetSpan(m_snapshot), m_upper);  
    }  
    ```  
  
    > [!WARNING]
    >  Ampul eylem **Invoke** yöntemi UI göstermek için beklenmiyor.  Eyleminizi yeni UI'yi (örneğin önizleme ya da seçimi iletişim) getirirseniz, doğrudan içinden kullanıcı Arabirimi gösterme **Invoke** yöntemi ancak bunun yerine, UI Döndürme sonra görüntülemek için zamanlama **Invoke**.  
  
10. Uygulama için eklemeniz `Dispose()` ve `TryGetTelemetryId()` yöntemleri.  
  
    ```csharp  
    public void Dispose()  
    {  
    }  
  
    public bool TryGetTelemetryId(out Guid telemetryId)  
    {  
        // This is a sample action and doesn't participate in LightBulb telemetry  
        telemetryId = Guid.Empty;  
        return false;  
    }  
    ```  
  
11. Aynı şey yapmak unutmayın `LowerCaseSuggestedAction` "Dönüştür '{0}' küçük harflere" ve çağrı için görüntülenecek metni değiştirme <xref:System.String.ToUpper%2A> için <xref:System.String.ToLower%2A>.  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
 Bu kodu test etmek için LightBulbTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
1.  Çözümü oluşturun.  
  
2.  Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
3.  Bir metin dosyası oluşturun ve bazı metin yazın. Ampul metni sola görmeniz gerekir.  
  
     ![Ampul test](../extensibility/media/testlightbulb.png "TestLIghtBulb")  
  
4.  Ampul gelin. Aşağı ok görmeniz gerekir.  
  
5.  Ampul tıkladığınızda, iki Önerilen Eylemler, seçilen eylem Önizleme birlikte görüntülenmesi gerekir.  
  
     ![Ampul, genişletilmiş test](../extensibility/media/testlightbulbexpanded.gif "TestLIghtBulbExpanded")  
  
6.  İlk eylem tıklarsanız, geçerli Word'de tüm metni büyük harflere dönüştürülmelidir. İkinci eylemi tıklarsanız, tüm metni küçük harflere dönüştürülmelidir.  
  