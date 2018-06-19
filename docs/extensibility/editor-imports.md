---
title: Düzenleyici içeri aktarmalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - services
ms.assetid: 8d096de3-33b4-427a-a122-4aeff8a72da0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f01567efa411187bede4f6daf15012da81c2331f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132740"
---
# <a name="editor-imports"></a>Düzenleyici içeri aktarmalar
Düzenleyici Hizmetleri, oluşturucuları ve farklı türde erişim çekirdek düzenleyiciye uzantınızı sağlayan aracıların sayısı içeri aktarabilirsiniz. Örneğin, alabileceğiniz <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> sizinle sağlamak için bir <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator> verilen bir içerik türü için. (Bu Gezgin aramaları farklı türde bir metin arabelleği gerçekleştirmek izin verir.)  
  
 Bir düzenleyici alma kullanmak için alan veya bir Genişletilebilirlik Çerçevesi ile yönetilen bileşen bölümü aktaran bir sınıfın özelliği aktarmadan.  
  
> [!NOTE]
>  Yönetilen Genişletilebilirlik Çerçevesi hakkında daha fazla bilgi için bkz: [Yönetilen Genişletilebilirlik Çerçevesi (MEF)](/dotnet/framework/mef/index).  
  
## <a name="import-syntax"></a>İçeri aktarma sözdizimi  
 Aşağıdaki örnek Düzenleyicisi içeri aktarma seçenekleri factory hizmetinin gösterir.  
  
```  
[Import]  
internal IEditorOptionsFactoryService EditorOptions { get; set; }  
```  
  
 Hizmet bir alan ve bir özellik almak istiyorsanız, bunu ayarlamanız gerekir `null` bildiriminde bir değişkene atama değil hakkında derleyici uyarıları önlemek için:  
  
```  
[Import]  
internal IEditorOptionsFactoryService m_editorOptions = null;  
```  
  
 İçeri aktarmalar kullanarak daha fazla örnekler için aşağıdaki izlenecek bakın:  
  
 [İzlenecek Yol: Dış Boşluk Karakteri Oluşturma](../extensibility/walkthrough-creating-a-margin-glyph.md)  
  
 [İzlenecek Yol: Metin Görünümünü Özelleştirme](../extensibility/walkthrough-customizing-the-text-view.md)  
  
 [İzlenecek Yol: Metni Vurgulama](../extensibility/walkthrough-highlighting-text.md)  
  
 [İzlenecek Yol: HızlıBilgi Araç İpuçlarını Görüntüleme](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)  
  
 [İzlenecek Yol: İmza Yardımını Görüntüleme](../extensibility/walkthrough-displaying-signature-help.md)  
  
 [İzlenecek Yol: Deyim Tamamlamayı Görüntüleme](../extensibility/walkthrough-displaying-statement-completion.md)  
  
 [İzlenecek Yol: Ampul Önerilerini Görüntüleme](../extensibility/walkthrough-displaying-light-bulb-suggestions.md)  
  
## <a name="importing-the-service-provider"></a>Hizmet sağlayıcısı alınıyor  
 Ayrıca içeri aktarabilirsiniz bir <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> (Microsoft.VisualStudio.Shell.Immutable.10.0 derlemesinde) Visual Studio hizmetlerine erişmek için aynı şekilde:  
  
```  
[Import]  
internal SVsServiceProvider ServiceProvider = null;   
```  
  
 Bkz: [izlenecek yol: bir düzenleyici uzantı DTE nesnesine erişim](../extensibility/walkthrough-accessing-the-dte-object-from-an-editor-extension.md) daha fazla bilgi için.  
  
## <a name="services"></a>Hizmetler  
 Düzenleyici, bir hizmet sağlamak ve birden çok bileşenler genelinde paylaşılan genellikle tek varlıkları hizmetleridir.  
  
|{1&gt;İçeri Aktar&lt;1}|Sağlar|  
|------------|--------------|  
|<xref:Microsoft.VisualStudio.Utilities.IFileExtensionRegistryService>|Dosya uzantıları arasındaki ilişkiyi ve <xref:Microsoft.VisualStudio.Utilities.IContentType> nesneleri.|  
|<xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>|Koleksiyonu <xref:Microsoft.VisualStudio.Utilities.IContentType> nesneleri.|  
|<xref:Microsoft.VisualStudio.Editor.IVsFontsAndColorsInformationService>|<xref:Microsoft.VisualStudio.Editor.IVsFontsAndColorsInformation> Nesneleri|  
|<xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>|Birçok Düzenleyicisi bağdaştırıcısı nesneler:<br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|  
|<xref:Microsoft.VisualStudio.Text.IncrementalSearch.IIncrementalSearchFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.IncrementalSearch.IIncrementalSearch> verilen metin görünümü için nesne.|  
|<xref:Microsoft.VisualStudio.Text.ITextBufferFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.ITextBuffer>.|  
|<xref:Microsoft.VisualStudio.Text.ITextDocumentFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.ITextDocument>.|  
|<xref:Microsoft.VisualStudio.Text.Differencing.IDifferenceService>|Bir <xref:Microsoft.VisualStudio.Text.Differencing.IDifferenceCollection%601> farklılıkların.|  
|<xref:Microsoft.VisualStudio.Text.Differencing.IHierarchicalStringDifferenceService>|Bir <xref:Microsoft.VisualStudio.Text.Differencing.IHierarchicalDifferenceCollection> farklılıkların.|  
|<xref:Microsoft.VisualStudio.Text.Projection.IProjectionBufferFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.Projection.IProjectionBuffer> veya bir <xref:Microsoft.VisualStudio.Text.Projection.IElisionBuffer>.|  
|<xref:Microsoft.VisualStudio.Text.Projection.IBufferGraphFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.Projection.IBufferGraph> kümesi için <xref:Microsoft.VisualStudio.Text.ITextBuffer> nesneleri.|  
|<xref:Microsoft.VisualStudio.Text.Classification.IClassifierAggregatorService>|Bir <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> için bir <xref:Microsoft.VisualStudio.Text.ITextBuffer>.|  
|<xref:Microsoft.VisualStudio.Text.Classification.IViewClassifierAggregatorService>|Bir <xref:Microsoft.VisualStudio.Text.Classification.IClassifier> için bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.|  
|<xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMapService>|Bir <xref:Microsoft.VisualStudio.Text.Classification.IClassificationFormatMap> için bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.|  
|<xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>|Bir <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap> için bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.|  
|<xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService>|Koleksiyonunu tutan <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType> nesneleri.|  
|<xref:Microsoft.VisualStudio.Text.Tagging.IBufferTagAggregatorFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601> için bir metin arabelleği.|  
|<xref:Microsoft.VisualStudio.Text.Tagging.IViewTagAggregatorFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601> metin görünümü.|  
|<xref:Microsoft.VisualStudio.Text.Editor.IEditorOptionsFactoryService>|<xref:Microsoft.VisualStudio.Text.Editor.IEditorOptions> Belirtilen kapsam için.|  
|<xref:Microsoft.VisualStudio.Text.Editor.IScrollMapFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.Editor.IScrollMap> metin görünümü.|  
|<xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentationService>|Bir <xref:Microsoft.VisualStudio.Text.Editor.ISmartIndent> için bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.|  
|<xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentationService>|Otomatik Girinti alır <xref:Microsoft.VisualStudio.Text.Editor.ISmartIndentProvider> nesneleri.|  
|<xref:Microsoft.VisualStudio.Text.Editor.ITextEditorFactoryService>|Yöneten <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> için bir <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView>.|  
|<xref:Microsoft.VisualStudio.Text.Formatting.IFormattedTextSourceFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.Formatting.IFormattedLineSource>.|  
|<xref:Microsoft.VisualStudio.Text.Formatting.IRtfBuilderService>|RTF biçimli metin anlık görüntü yayılma kümesinden oluşturur.|  
|<xref:Microsoft.VisualStudio.Text.Formatting.ITextAndAdornmentSequencerFactoryService>|Bir <xref:Microsoft.VisualStudio.Text.Formatting.ITextAndAdornmentSequencer> için bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.|  
|<xref:Microsoft.VisualStudio.Text.Formatting.ITextParagraphPropertiesFactoryService>|A <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> görünümünde metin satırlarını biçimlendirme.|  
|<xref:Microsoft.VisualStudio.Text.Operations.IEditorOperationsFactoryService>|A <xref:Microsoft.VisualStudio.Text.Operations.IEditorOperations> için nesne bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.|  
|<xref:Microsoft.VisualStudio.Text.Operations.ITextSearchService>|Bir metin anlık görüntü arar.|  
|<xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>|Bir <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigator> için bir <xref:Microsoft.VisualStudio.Text.ITextBuffer> tarafından <xref:Microsoft.VisualStudio.Utilities.IContentType>.|  
|<xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManagerService>|Bir <xref:Microsoft.VisualStudio.Text.Outlining.IOutliningManager> metin görünümü.|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.IGlyphService>|Bir standart karakterleri ayarlayın.|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSessionStackMapService>|Bir <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseSessionStack> için bir <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.IWpfKeyboardTrackingService>|Parçaları işleme klavye.|  
|<xref:Microsoft.VisualStudio.Language.StandardClassification.IStandardClassificationService>|Standart <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType> nesneleri.|  
|<xref:Microsoft.VisualStudio.Text.Operations.ITextUndoHistoryRegistry>|Metin arabelleği arasındaki ilişkiyi korur ve <xref:Microsoft.VisualStudio.Text.Operations.ITextUndoHistory> nesneleri.|  
  
## <a name="other-imports"></a>Diğer içeri aktarmalar  
 Sağlayıcı üreteçlerinin ve aracıların genellikle birden çok bileşeni birden çok örneği olan varlıklardır.  
  
|{1&gt;İçeri Aktar&lt;1}|Sağlar|  
|------------|--------------|  
|<xref:Microsoft.VisualStudio.Text.Adornments.IErrorProviderFactory>|Bir <xref:Microsoft.VisualStudio.Text.Tagging.SimpleTagger%601> türü <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>) için verilen arabellek.|  
|<xref:Microsoft.VisualStudio.Text.Adornments.ITextMarkerProviderFactory>|Bir metin işaretçisi etiketleme (bir <xref:Microsoft.VisualStudio.Text.Tagging.SimpleTagger%601> türü <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>).|  
|<xref:Microsoft.VisualStudio.Text.Adornments.IToolTipProviderFactory>|Bir <xref:Microsoft.VisualStudio.Text.Adornments.IToolTipProvider> için bir verilen <xref:Microsoft.VisualStudio.Text.Editor.ITextView>.|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionBroker>|Bir <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSession>.|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoBroker>|Bir <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSession>.|  
|<xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpBroker>|Bir <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSession>.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil Hizmeti ve Düzenleyici Uzantı Noktaları](../extensibility/language-service-and-editor-extension-points.md)