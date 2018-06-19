---
title: 'İzlenecek yol: Metni vurgulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - highlight text
ms.assetid: 64b772ad-4392-42e9-a237-5137f0384bf0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 90bf22bfe65b1120f5cc149d95eea25357b8ffa4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31147225"
---
# <a name="walkthrough-highlighting-text"></a>İzlenecek yol: Metni vurgulama
Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşeni bölümleri oluşturarak düzenleyiciye farklı görsel efektler ekleyebilirsiniz. Bu kılavuz, bir metin dosyasındaki geçerli sözcüğü her geçtiği vurgulamak gösterilmiştir. Bir sözcük, bir metin dosyasına birden fazla kez oluşur ve bir yineleme şapka getirin, her oluşumu vurgulanır.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Bir MEF projesi oluşturma  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `HighlightWordTest`.  
  
2.  Bir düzenleyici sınıflandırıcı öğe şablonu projeye ekleyin. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Varolan sınıf dosyaları silin.  
  
## <a name="defining-a-textmarkertag"></a>Bir TextMarkerTag tanımlama  
 Metni vurgulama ilk adımı için sınıfıdır <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> ve görünümünü tanımlayın.  
  
#### <a name="to-define-a-textmarkertag-and-a-markerformatdefinition"></a>Bir TextMarkerTag ve bir MarkerFormatDefinition tanımlamak için  
  
1.  Bir sınıf dosyası ekleyin ve adını **HighlightWordTag**.  
  
2.  Aşağıdaki başvurular ekleyin:  
  
    1.  Microsoft.VisualStudio.CoreUtility  
  
    2.  Microsoft.VisualStudio.Text.Data  
  
    3.  Microsoft.VisualStudio.Text.Logic  
  
    4.  Microsoft.VisualStudio.Text.UI  
  
    5.  Microsoft.VisualStudio.Text.UI.Wpf  
  
    6.  System.ComponentModel.Composition  
  
    7.  Presentation.Core  
  
    8.  Presentation.Framework  
  
3.  Şu ad alanlarından içe aktarın.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using System.Linq;  
    using System.Threading;  
    using Microsoft.VisualStudio.Text;  
    using Microsoft.VisualStudio.Text.Classification;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.Text.Operations;  
    using Microsoft.VisualStudio.Text.Tagging;  
    using Microsoft.VisualStudio.Utilities;  
    using System.Windows.Media;  
    ```  
  
4.  Öğesinden devralınan bir sınıf oluşturun <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag> ve adlandırın `HighlightWordTag`.  
  
    ```csharp  
    internal class HighlightWordTag : TextMarkerTag  
    {  
  
    }  
    ```  
  
5.  Öğesinden devralınan ikinci sınıf oluşturma <xref:Microsoft.VisualStudio.Text.Classification.MarkerFormatDefinition>ve HighlightWordFormatDefinition olarak adlandırın. Bu biçim tanımını etiket için kullanmak için aşağıdaki özniteliklerle dışarı aktarmanız gerekir:  
  
    -   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: etiketler bu biçim başvurmak için bunu kullanın  
  
    -   <xref:Microsoft.VisualStudio.Text.Classification.UserVisibleAttribute>: Bu kullanıcı Arabiriminde görünen biçimde neden olur  
  
    ```csharp  
  
    [Export(typeof(EditorFormatDefinition))]  
    [Name("MarkerFormatDefinition/HighlightWordFormatDefinition")]  
    [UserVisible(true)]  
    internal class HighlightWordFormatDefinition : MarkerFormatDefinition  
    {  
  
    }  
    ```  
  
6.  HighlightWordFormatDefinition oluşturucusu, görüntü adına ve görünümüne tanımlayın. Ön plan özelliği kenarlık rengi açıklarken arka plan özelliği dolgu rengini tanımlar.  
  
    ```csharp  
    public HighlightWordFormatDefinition()  
    {  
                this.BackgroundColor = Colors.LightBlue;  
        this.ForegroundColor = Colors.DarkBlue;  
        this.DisplayName = "Highlight Word";  
        this.ZOrder = 5;  
    }  
    ```  
  
7.  HighlightWordTag Oluşturucusu oluşturduğunuz biçim tanımını adına geçirin.  
  
    ```  
    public HighlightWordTag() : base("MarkerFormatDefinition/HighlightWordFormatDefinition") { }  
    ```  
  
## <a name="implementing-an-itagger"></a>Bir ITagger uygulama  
 Sonraki adım uygulamaktır <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> arabirimi. Bu arabirim, verilen metin arabelleği, metni vurgulama sağlamak etiketleri ve diğer görsel efektler atar.  
  
#### <a name="to-implement-a-tagger"></a>Bir etiketleme uygulamak için  
  
1.  Arabirimini uygulayan bir sınıf oluşturun <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> türü `HighlightWordTag`ve adlandırın `HighlightWordTagger`.  
  
    ```csharp  
    internal class HighlightWordTagger : ITagger<HighlightWordTag>  
    {  
  
    }  
    ```  
  
2.  Aşağıdaki özel alanlar ve Özellikler sınıfına ekleyin:  
  
    -   Bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>, geçerli metni görünümüne karşılık gelir.  
  
    -   Bir <xref:Microsoft.VisualStudio.Text.ITextBuffer>, metin görünümü altını çizen metin arabelleğini karşılık gelir.  
  
    -   Bir <xref:Microsoft.VisualStudio.Text.Operations.ITextSearchService>, metin bulmak için kullanılır.  
  
    -   Bir <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator>, metin yayılma içinde gezinmek için yöntemleri vardır.  
  
    -   A <xref:Microsoft.VisualStudio.Text.NormalizedSnapshotSpanCollection>, sözcükleri vurgulamak için kümesi içerir.  
  
    -   A <xref:Microsoft.VisualStudio.Text.SnapshotSpan>, geçerli Word'e karşılık gelir.  
  
    -   A <xref:Microsoft.VisualStudio.Text.SnapshotPoint>, düzeltme işareti geçerli konumuna karşılık gelir.  
  
    -   Kilit nesnesi.  
  
    ```csharp  
    ITextView View { get; set; }  
    ITextBuffer SourceBuffer { get; set; }  
    ITextSearchService TextSearchService { get; set; }  
    ITextStructureNavigator TextStructureNavigator { get; set; }  
    NormalizedSnapshotSpanCollection WordSpans { get; set; }  
    SnapshotSpan? CurrentWord { get; set; }  
    SnapshotPoint RequestedPoint { get; set; }  
    object updateLock = new object();  
  
    ```  
  
3.  Daha önce listelenen özellikleri başlatır ve ekleyen bir oluşturucu ekleyin <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> ve <xref:Microsoft.VisualStudio.Text.Editor.ITextCaret.PositionChanged> olay işleyicileri.  
  
    ```csharp  
    public HighlightWordTagger(ITextView view, ITextBuffer sourceBuffer, ITextSearchService textSearchService,  
    ITextStructureNavigator textStructureNavigator)  
    {  
        this.View = view;  
        this.SourceBuffer = sourceBuffer;  
        this.TextSearchService = textSearchService;  
        this.TextStructureNavigator = textStructureNavigator;  
        this.WordSpans = new NormalizedSnapshotSpanCollection();  
        this.CurrentWord = null;  
        this.View.Caret.PositionChanged += CaretPositionChanged;  
        this.View.LayoutChanged += ViewLayoutChanged;  
    }  
  
    ```  
  
4.  Her ikisi de çağrı olay işleyicileri `UpdateAtCaretPosition` yöntemi.  
  
    ```csharp  
    void ViewLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)  
    {  
        // If a new snapshot wasn't generated, then skip this layout   
        if (e.NewSnapshot != e.OldSnapshot)  
        {  
            UpdateAtCaretPosition(View.Caret.Position);  
        }  
    }  
  
    void CaretPositionChanged(object sender, CaretPositionChangedEventArgs e)  
    {  
        UpdateAtCaretPosition(e.NewPosition);  
    }  
    ```  
  
5.  Ayrıca eklemelisiniz bir `TagsChanged` güncelleştirme yöntemi tarafından çağrılacak olay.  
  
     [!code-csharp[VSSDKHighlightWordTest#10](../extensibility/codesnippet/CSharp/walkthrough-highlighting-text_1.cs)]
     [!code-vb[VSSDKHighlightWordTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-highlighting-text_1.vb)]  
  
6.  `UpdateAtCaretPosition()` Yöntemi imleci nereye yerleştirilir ve bir listesini oluşturur Word'e aynıdır metin arabelleği her word bulur <xref:Microsoft.VisualStudio.Text.SnapshotSpan> word oluşumları karşılık nesneleri. Daha sonra çağırır `SynchronousUpdate`, hangi başlatır `TagsChanged` olay.  
  
    ```csharp  
    void UpdateAtCaretPosition(CaretPosition caretPosition)  
    {  
        SnapshotPoint? point = caretPosition.Point.GetPoint(SourceBuffer, caretPosition.Affinity);  
  
        if (!point.HasValue)  
            return;  
  
        // If the new caret position is still within the current word (and on the same snapshot), we don't need to check it   
        if (CurrentWord.HasValue  
            && CurrentWord.Value.Snapshot == View.TextSnapshot  
            && point.Value >= CurrentWord.Value.Start  
            && point.Value <= CurrentWord.Value.End)  
        {  
            return;  
        }  
  
        RequestedPoint = point.Value;  
        UpdateWordAdornments();  
    }  
  
    void UpdateWordAdornments()  
    {  
        SnapshotPoint currentRequest = RequestedPoint;  
        List<SnapshotSpan> wordSpans = new List<SnapshotSpan>();  
        //Find all words in the buffer like the one the caret is on  
        TextExtent word = TextStructureNavigator.GetExtentOfWord(currentRequest);  
        bool foundWord = true;  
        //If we've selected something not worth highlighting, we might have missed a "word" by a little bit  
        if (!WordExtentIsValid(currentRequest, word))  
        {  
            //Before we retry, make sure it is worthwhile   
            if (word.Span.Start != currentRequest  
                 || currentRequest == currentRequest.GetContainingLine().Start  
                 || char.IsWhiteSpace((currentRequest - 1).GetChar()))  
            {  
                foundWord = false;  
            }  
            else  
            {  
                // Try again, one character previous.    
                //If the caret is at the end of a word, pick up the word.  
                word = TextStructureNavigator.GetExtentOfWord(currentRequest - 1);  
  
                //If the word still isn't valid, we're done   
                if (!WordExtentIsValid(currentRequest, word))  
                    foundWord = false;  
            }  
        }  
  
        if (!foundWord)  
        {  
            //If we couldn't find a word, clear out the existing markers  
            SynchronousUpdate(currentRequest, new NormalizedSnapshotSpanCollection(), null);  
            return;  
        }  
  
        SnapshotSpan currentWord = word.Span;  
        //If this is the current word, and the caret moved within a word, we're done.   
        if (CurrentWord.HasValue && currentWord == CurrentWord)  
            return;  
  
        //Find the new spans  
        FindData findData = new FindData(currentWord.GetText(), currentWord.Snapshot);  
        findData.FindOptions = FindOptions.WholeWord | FindOptions.MatchCase;  
  
        wordSpans.AddRange(TextSearchService.FindAll(findData));  
  
        //If another change hasn't happened, do a real update   
        if (currentRequest == RequestedPoint)  
            SynchronousUpdate(currentRequest, new NormalizedSnapshotSpanCollection(wordSpans), currentWord);  
    }  
    static bool WordExtentIsValid(SnapshotPoint currentRequest, TextExtent word)  
    {  
        return word.IsSignificant  
            && currentRequest.Snapshot.GetText(word.Span).Any(c => char.IsLetter(c));  
    }  
  
    ```  
  
7.  `SynchronousUpdate` Zaman uyumlu bir güncelleştirme gerçekleştirir `WordSpans` ve `CurrentWord` özellikleri ve başlatır `TagsChanged` olay.  
  
    ```vb  
    void SynchronousUpdate(SnapshotPoint currentRequest, NormalizedSnapshotSpanCollection newSpans, SnapshotSpan? newCurrentWord)  
    {  
        lock (updateLock)  
        {  
            if (currentRequest != RequestedPoint)  
                return;  
  
            WordSpans = newSpans;  
            CurrentWord = newCurrentWord;  
  
            var tempEvent = TagsChanged;  
            if (tempEvent != null)  
                tempEvent(this, new SnapshotSpanEventArgs(new SnapshotSpan(SourceBuffer.CurrentSnapshot, 0, SourceBuffer.CurrentSnapshot.Length)));  
        }  
    }  
    ```  
  
8.  Uygulamanız gereken <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> yöntemi. Bu yöntem bir koleksiyonunu alır <xref:Microsoft.VisualStudio.Text.SnapshotSpan> nesneleri ve etiket yayılma numaralandırması döndürür.  
  
     C# ' ta etiketleri, geç değerlendirme (diğer bir deyişle, değerlendirme yalnızca tek öğelerin erişildiğinde kümesi) sağlar ve verim yineleyici bu yöntemi uygulaması. Visual Basic'te etiketler bir listeye ekleyin ve listesini döndürür.  
  
     Burada bu yöntem döndürür bir <xref:Microsoft.VisualStudio.Text.Tagging.TagSpan%601> , "mavi" sahip bir nesne <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>, mavi bir arka plan sağlar.  
  
    ```csharp  
    public IEnumerable<ITagSpan<HighlightWordTag>> GetTags(NormalizedSnapshotSpanCollection spans)  
    {  
        if (CurrentWord == null)  
            yield break;  
  
        // Hold on to a "snapshot" of the word spans and current word, so that we maintain the same  
        // collection throughout  
        SnapshotSpan currentWord = CurrentWord.Value;  
        NormalizedSnapshotSpanCollection wordSpans = WordSpans;  
  
        if (spans.Count == 0 || wordSpans.Count == 0)  
            yield break;  
  
        // If the requested snapshot isn't the same as the one our words are on, translate our spans to the expected snapshot   
        if (spans[0].Snapshot != wordSpans[0].Snapshot)  
        {  
            wordSpans = new NormalizedSnapshotSpanCollection(  
                wordSpans.Select(span => span.TranslateTo(spans[0].Snapshot, SpanTrackingMode.EdgeExclusive)));  
  
            currentWord = currentWord.TranslateTo(spans[0].Snapshot, SpanTrackingMode.EdgeExclusive);  
        }  
  
        // First, yield back the word the cursor is under (if it overlaps)   
        // Note that we'll yield back the same word again in the wordspans collection;   
        // the duplication here is expected.   
        if (spans.OverlapsWith(new NormalizedSnapshotSpanCollection(currentWord)))  
            yield return new TagSpan<HighlightWordTag>(currentWord, new HighlightWordTag());  
  
        // Second, yield all the other words in the file   
        foreach (SnapshotSpan span in NormalizedSnapshotSpanCollection.Overlap(spans, wordSpans))  
        {  
            yield return new TagSpan<HighlightWordTag>(span, new HighlightWordTag());  
        }  
    }  
    ```  
  
## <a name="creating-a-tagger-provider"></a>Etiketleme sağlayıcı oluşturma  
 Etiketleme oluşturmak için uygulamanız gereken bir <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider>. Bu sınıf bir MEF Bileşeni bölümü kitabıdır böylece bu uzantı tanınan doğru öznitelikleri ayarlamanız gerekir.  
  
> [!NOTE]
>  MEF hakkında daha fazla bilgi için bkz: [Yönetilen Genişletilebilirlik Çerçevesi (MEF)](/dotnet/framework/mef/index).  
  
#### <a name="to-create-a-tagger-provider"></a>Etiketleme sağlayıcısı oluşturmak için  
  
1.  Adlı bir sınıf oluşturun `HighlightWordTaggerProvider` uygulayan <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider>ve onunla verme bir <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "metin" ve <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> , <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>.  
  
    ```csharp  
    [Export(typeof(IViewTaggerProvider))]  
    [ContentType("text")]  
    [TagType(typeof(TextMarkerTag))]  
    internal class HighlightWordTaggerProvider : IViewTaggerProvider  
    { }  
    ```  
  
2.  İki Düzenleyicisi Hizmetleri aktarmalısınız <xref:Microsoft.VisualStudio.Text.Operations.ITextSearchService> ve <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>, etiketleme örneği oluşturmak için.  
  
    ```csharp  
    [Import]  
    internal ITextSearchService TextSearchService { get; set; }  
  
    [Import]  
    internal ITextStructureNavigatorSelectorService TextStructureNavigatorSelector { get; set; }  
  
    ```  
  
3.  Uygulama <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider.CreateTagger%2A> örneği döndürülecek yöntemi `HighlightWordTagger`.  
  
    ```csharp  
    public ITagger<T> CreateTagger<T>(ITextView textView, ITextBuffer buffer) where T : ITag  
    {  
        //provide highlighting only on the top buffer   
        if (textView.TextBuffer != buffer)  
            return null;  
  
        ITextStructureNavigator textStructureNavigator =  
            TextStructureNavigatorSelector.GetTextStructureNavigator(buffer);  
  
        return new HighlightWordTagger(textView, buffer, TextSearchService, textStructureNavigator) as ITagger<T>;  
    }  
    ```  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
 Bu kodu test etmek için HighlightWordTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
#### <a name="to-build-and-test-the-highlightwordtest-solution"></a>Derleme ve HighlightWordTest çözüm sınamak için  
  
1.  Çözümü oluşturun.  
  
2.  Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
3.  Bir metin dosyası oluşturun ve içinde sözcükleri yinelenir, bazı Örneğin, "Merhaba hello hello" metni yazın.  
  
4.  İmleç "hello" oluşumları getirin. Her oluşumu mavi renkte vurgulanmış olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yol: Bir İçerik Türünü Dosya Adı Uzantısına Bağlama](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)