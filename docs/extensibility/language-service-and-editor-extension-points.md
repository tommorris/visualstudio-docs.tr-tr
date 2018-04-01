---
title: Dil hizmeti ve düzenleyici uzantı noktaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - extension points
ms.assetid: 91a6417e-a6fe-4bc2-9d9f-5173c634a99b
caps.latest.revision: 33
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7e62f1f3cac8f279dedbc79f283b908119d66ff2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="language-service-and-editor-extension-points"></a>Dil hizmeti ve düzenleyici uzantı noktaları
Düzenleyici çoğu dil hizmet özellikleri dahil olmak üzere Yönetilen Genişletilebilirlik Çerçevesi (MEF) bileşeni parçaları olarak genişletebilirsiniz uzantı noktaları sağlar. Bu ana uzantısı noktası kategorileri şunlardır:  
  
-   İçerik türleri  
  
-   Sınıflandırma türleri ve sınıflandırma biçimleri  
  
-   Kenar boşlukları ve kaydırma çubukları  
  
-   Etiketler  
  
-   Adornments  
  
-   Fare işlemcileri  
  
-   Açılan işleyicileri  
  
-   Seçenekler  
  
-   IntelliSense  
  
## <a name="extending-content-types"></a>İçerik türlerini genişletme  
 Metin Düzenleyicisi tarafından örneğin ele, "metin", "code" veya "CSharp" tür tanımlarını içerik türleridir. Türünde bir değişken bildirerek yeni bir içerik türü tanımladığınız <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> ve yeni içerik türü benzersiz bir ad verip. İçerik türü Düzenleyicisi ile kaydetmek için aşağıdaki öznitelikler birlikte dışarı aktarın:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>içerik türü adıdır.  
  
-   <xref:Microsoft.VisualStudio.Utilities.BaseDefinitionAttribute>Bu içerik türü türetildiği içerik türü adıdır. Bir içerik türü diğer birden çok içerik türlerinden devralır.  
  
 Çünkü <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> sınıfın korumalı, hiçbir tür parametresi ile dışarı aktarabilirsiniz.  
  
 Aşağıdaki örnek, bir içerik türü tanımı verme öznitelikleri gösterir.  
  
```  
[Export]  
[Name("test")]  
[BaseDefinition("code")]  
[BaseDefinition("projection")]  
internal static ContentTypeDefinition TestContentTypeDefinition;  
```  
  
 İçerik türleri sıfır veya daha fazla önceden var olan içerik türlerine bağlı olabilir. Yerleşik türleri şunlardır:  
  
-   Herhangi bir: temel içerik türü. Tüm diğer içerik türleri üst.  
  
-   Metin: projeksiyon olmayan içerik için temel türü. "Herhangi" devralır.  
  
-   Düz metin: kod olmayan metin. "Metin" devralır.  
  
-   Kod: kod her tür için. "Metin" devralır.  
  
-   Simge: metin işleme her türlü dışlar. Bu içerik türü metnin hiçbir zaman uygulanan tüm uzantısına sahip olacaktır.  
  
-   Projeksiyon: içeriğini projeksiyon arabellekleri için. "Herhangi" devralır.  
  
-   IntelliSense: içeriğini IntelliSense için. "Metin" devralır.  
  
-   Sighelp: İmza yardımcı olur. "IntelliSense" devralır.  
  
-   Sighelp-doc: İmza Yardım belgelerine. "IntelliSense" devralır.  
  
 Bu, bazı Visual Studio tarafından tanımlanan içerik türleri ve Visual Studio'da barındırılan dilleri bazıları şunlardır:  
  
-   Temel  
  
-   C/C++  
  
-   ConsoleOutput  
  
-   CSharp  
  
-   CSS  
  
-   ÇÖZÜCÜ  
  
-   FindResults  
  
-   F#  
  
-   HTML  
  
-   JScript  
  
-   XAML  
  
-   XML  
  
 Kullanılabilir içerik türlerinin listesini bulmak için alma <xref:Microsoft.VisualStudio.Utilities.IContentTypeRegistryService>, içerik türleri Koleksiyonu Düzenleyicisi korur. Aşağıdaki kod bu hizmet bir özellik olarak alır.  
  
```  
[Import]  
internal IContentTypeRegistryService ContentTypeRegistryService { get; set; }  
```  
  
 Bir içerik türü bir dosya adı uzantısı ile ilişkilendirmek üzere kullanabileceği <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition>.  
  
> [!NOTE]
>  Visual Studio'da, dosya adı uzantılarını kullanarak kayıtlı <xref:Microsoft.VisualStudio.Shell.ProvideLanguageExtensionAttribute> dil hizmet paketi üzerinde. <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> Bir MEF içerik türü bu şekilde kayıtlı bir dosya adı uzantısı ile ilişkilendirir.  
  
 Dosya adı uzantısı için içerik türü tanımı dışarı aktarmak için aşağıdaki öznitelikler şunları içermelidir:  
  
-   <xref:Microsoft.VisualStudio.Utilities.FileExtensionAttribute>: dosya adı uzantısını belirtir.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: içerik türünü belirtir.  
  
 Çünkü <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> sınıfın korumalı, hiçbir tür parametresi ile dışarı aktarabilirsiniz.  
  
 Aşağıdaki örnek, bir dosya adı uzantısı için bir içerik türü tanımı üzerinde dışarı aktarma öznitelikleri gösterir.  
  
```  
[Export]  
[FileExtension(".test")]  
[ContentType("test")]  
internal static FileExtensionToContentTypeDefinition TestFileExtensionDefinition;  
```  
  
 <xref:Microsoft.VisualStudio.Utilities.IFileExtensionRegistryService> Dosya adı uzantılarını ve içerik türleri arasındaki ilişkilendirmeleri yönetir.  
  
## <a name="extending-classification-types-and-classification-formats"></a>Sınıflandırma türleri ve sınıflandırma genişletme biçimleri  
 Sınıflandırma türleri (örneğin, "anahtar" metin mavi ve "Açıklama" metnini yeşil renklendirme) farklı işleme sağlamak istediğiniz metni türlerini tanımlamak için kullanabilirsiniz. Yeni sınıflandırma tür türünde bir değişken bildirerek tanımlama <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeDefinition> ve benzersiz bir ad verip.  
  
 Sınıflandırma türü Düzenleyicisi ile kaydetmek için aşağıdaki öznitelikler birlikte dışarı aktarın:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: sınıflandırma türünün adı.  
  
-   <xref:Microsoft.VisualStudio.Utilities.BaseDefinitionAttribute>: Bu sınıflandırma türü devraldığı sınıflandırma türünün adı. Tüm sınıflandırma türleri "metin" devralır ve sınıflandırma türü birden çok diğer sınıflandırma türlerinden devral.  
  
 Çünkü <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeDefinition> sınıfın korumalı, hiçbir tür parametresi ile dışarı aktarabilirsiniz.  
  
 Aşağıdaki örnek, bir sınıflandırma tür tanımında verme öznitelikleri gösterir.  
  
```  
[Export]  
[Name("csharp.test")]  
[BaseDefinition("test")]  
internal static ClassificationTypeDefinition CSharpTestDefinition;  
```  
  
 <xref:Microsoft.VisualStudio.Language.StandardClassification.IStandardClassificationService> Standart sınıflandırmaları erişim sağlar. Yerleşik sınıflandırma türleri bu görevler şunlardır:  
  
-   "metin"  
  
-   "doğal dil" ("metin" türetilen)  
  
-   "resmi language (türetilen"metin")"  
  
-   "dize ("literal"türetilen)"  
  
-   "karakter ("literal"türetilen)"  
  
-   "sayısal" ("literal" türetilen)  
  
 Farklı hata türleri kümesi devral <xref:Microsoft.VisualStudio.Text.Adornments.ErrorTypeDefinition>. Bunlar, aşağıdaki hata türleri şunlardır:  
  
-   "sözdizimi hatası"  
  
-   "derleyici hatası"  
  
-   "başka bir hata"  
  
-   "uyarı"  
  
 Kullanılabilir sınıflandırma türlerinin bir listesini bulmak için alma <xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService>, sınıflandırma türleri Koleksiyonu Düzenleyicisi korur. Aşağıdaki kod bu hizmet bir özellik olarak alır.  
  
```  
[Import]  
internal IClassificationTypeRegistryService ClassificationTypeRegistryService { get; set; }  
```  
  
 Yeni sınıflandırma türünüz için bir sınıflandırma biçim tanımını tanımlayabilirsiniz. Öğesinden bir sınıf türetin <xref:Microsoft.VisualStudio.Text.Classification.ClassificationFormatDefinition> ve tür ile dışarı aktarma <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition>, aşağıdaki özniteliklerle birlikte:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: biçim adı.  
  
-   <xref:Microsoft.VisualStudio.Utilities.DisplayNameAttribute>: biçimi görünen adı.  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.UserVisibleAttribute>: biçimi üzerinde görünüp görünmeyeceğini belirtir **yazı tiplerini ve renkleri** sayfasında **seçenekleri** iletişim kutusu.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: öncelik biçimi. Geçerli değerler: <xref:Microsoft.VisualStudio.Text.Classification.Priority>.  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.ClassificationTypeAttribute>: sınıflandırmasının adını yazın bu biçim eşlenmiş için.  
  
 Aşağıdaki örnek, bir sınıflandırma biçimi tanımına verme öznitelikleri gösterir.  
  
```  
[Export(typeof(EditorFormatDefinition))]  
[ClassificationType(ClassificationTypeNames = "test")]  
[Name("test")]  
[DisplayName("Test")]  
[UserVisible(true)]  
[Order(After = Priority.Default, Before = Priority.High)]  
internal sealed class TestFormat : ClassificationFormatDefinition  
```  
  
 Kullanılabilir biçimleri listesini bulmak için alma <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>, biçimleri Koleksiyonu Düzenleyicisi korur. Aşağıdaki kod bu hizmet bir özellik olarak alır.  
  
```  
[Import]  
internal IEditorFormatMapService FormatMapService { get; set; }  
```  
  
## <a name="extending-margins-and-scrollbars"></a>Genişletme kenar boşlukları ve kaydırma çubukları  
 Kenar boşlukları ve scrollbars ana görünüm metin görünümü yanı sıra Düzenleyicisi öğeleridir. Kenar boşlukları metin görünümünde görünür standart kenar boşluklarını yanı sıra herhangi bir sayıda sağlayabilir.  
  
 Uygulama bir <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMargin> kenar boşluğu tanımlamak için arabirim. Ayrıca uygulamalıdır <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewMarginProvider> kenar oluşturmak için arabirimi.  
  
 Düzenleyiciyle kenar boşluğu sağlayıcısını kaydetmek için aşağıdaki öznitelikler birlikte sağlayıcısı dışarı aktarmanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: kenar adı.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: kenar göründüğü, diğer kenar boşluklarını göre sırası.  
  
     Yerleşik kenar şunlardır:  
  
    -   "Wpf yatay kaydırma çubuğu"  
  
    -   "Wpf dikey Scrollbar"  
  
    -   "Wpf satır numarası kenar boşluğu"  
  
     Bir sipariş özniteliği yatay kenar boşlukları `After="Wpf Horizontal Scrollbar"` yerleşik kenar boşluğu ve bir sipariş özniteliği yatay kenar boşlukları görüntülenen `Before ="Wpf Horizontal Scrollbar"` üstündeki yerleşik kenar boşluğu görüntülenir. Bir sipariş özniteliği Dikey Kenar boşluklarını sağ `After="Wpf Vertical Scrollbar"` scrollbar sağında görüntülenir. Bir sipariş özniteliği Dikey Kenar boşluklarını sol `After="Wpf Line Number Margin"` (görünür durumdaysa), satır numarası kenar boşluğu solunda görüntülenir.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.MarginContainerAttribute>: kenar boşluğu (sol, sağ, üst veya alt) türü.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: içerik (örneğin, "metin" veya "code"), kenar boşluğu olduğu geçerli türü.  
  
 Aşağıdaki örnek, satır numarası kenar boşluğu sağında görünür bir kenar için kenar boşluğu sağlayıcıdaki verme öznitelikleri gösterir.  
  
```  
[Export(typeof(IWpfTextViewMarginProvider))]  
[Name("TestMargin")]  
[Order(Before = "Wpf Line Number Margin")]  
[MarginContainer(PredefinedMarginNames.Left)]  
[ContentType("text")]   
```  
  
## <a name="extending-tags"></a>Etiketler genişletme  
 Etiket metni farklı türde verileri ilişkilendirme bir yoludur. Çoğu durumda, ilişkili veriler görsel bir efekt görüntülenir, ancak bir görsel sunumu tüm etiketlere sahip. Etiket kendi tür uygulayarak tanımlayabilirsiniz <xref:Microsoft.VisualStudio.Text.Tagging.ITag>. Ayrıca uygulamalıdır <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> belirli bir metin yayılma kümesi için etiketler sağlamak için ve bir <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider> etiketleme sağlamak için. Aşağıdaki öznitelikler birlikte etiketleme sağlayıcısı dışarı aktarmanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: içerik (örneğin, "metin" veya "code"), etiket olduğu geçerli türü.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute>: Etiket türü.  
  
 Aşağıdaki örnek, bir etiketleme sağlayıcısında verme öznitelikleri gösterir.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
 Etiket şu tür yerleşik şunlardır:  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.ClassificationTag>: ile ilişkili bir <xref:Microsoft.VisualStudio.Text.Classification.IClassificationType>.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.ErrorTag>: hata türleri ile ilişkili.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>: bir adornment ile ilişkilendirilmiş.  
  
    > [!NOTE]
    >  Bir örnek için bir <xref:Microsoft.VisualStudio.Text.Tagging.TextMarkerTag>, HighlightWordTag tanımı'nda bkz [izlenecek yol: Metin vurgulama](../extensibility/walkthrough-highlighting-text.md).  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag>: genişletilmiş veya anahat oluşturma de daraltılmış bölgeleri ile ilişkilendirilmiş.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>: bir metin görünümünde bir adornment kapladığı alanı tanımlar. Alanı anlaşması adornments hakkında daha fazla bilgi için aşağıdaki bölümüne bakın.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.IntraTextAdornmentTag>: Otomatik aralık ve adornment boyutlandırma sağlar.  
  
 Bul ve arabellek ve görünümler için etiketleri kullanmak için alma <xref:Microsoft.VisualStudio.Text.Tagging.IViewTagAggregatorFactoryService> veya <xref:Microsoft.VisualStudio.Text.Tagging.IBufferTagAggregatorFactoryService>, hangi size bir <xref:Microsoft.VisualStudio.Text.Tagging.ITagAggregator%601> istenen türde. Aşağıdaki kod bu hizmet bir özellik olarak alır.  
  
```  
[Import]  
internal IViewTagAggregatorFactoryService ViewTagAggregatorFactoryService { get; set; }  
```  
  
#### <a name="tags-and-markerformatdefinitions"></a>Etiketleri ve MarkerFormatDefinitions  
 Genişletebilirsiniz <xref:Microsoft.VisualStudio.Text.Classification.MarkerFormatDefinition> bir etiket görünümünü tanımlamak için sınıf. Sınıfınızda dışarı aktarmanız gerekir (olarak bir <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition>) aşağıdaki özelliklere sahip:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: Bu biçim başvurmak için kullanılan ad  
  
-   <xref:Microsoft.VisualStudio.Text.Classification.UserVisibleAttribute>: Bu kullanıcı Arabiriminde görünen biçimde neden olur  
  
 Oluşturucuda etiketi görünümünü ve görünen ad tanımlayın. <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.BackgroundColor%2A>Dolgu rengi tanımlar ve <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.ForegroundColor%2A> kenarlık rengini tanımlar. <xref:Microsoft.VisualStudio.Text.Classification.EditorFormatDefinition.DisplayName%2A> Biçim tanımını yerelleştirilebilir adıdır.  
  
 Bir biçim tanımını örneği verilmiştir:  
  
```  
[Export(typeof(EditorFormatDefinition))]  
[Name("MarkerFormatDefinition/HighlightWordFormatDefinition")]  
[UserVisible(true)]  
internal class HighlightWordFormatDefinition : MarkerFormatDefinition  
{  
    public HighlightWordFormatDefinition()  
    {  
        this.BackgroundColor = Colors.LightBlue;  
        this.ForegroundColor = Colors.DarkBlue;  
        this.DisplayName = "Highlight Word";   
        this.ZOrder = 5;  
    }  
}  
  
```  
  
 Bu biçim tanımı için bir etiket uygulamak için (görünen adı değil) Sınıf adı özniteliğinde ayarlanan adına başvuru.  
  
> [!NOTE]
>  Bir örnek için bir <xref:Microsoft.VisualStudio.Text.Classification.MarkerFormatDefinition>, HighlightWordFormatDefinition sınıfında bkz [izlenecek yol: Metin vurgulama](../extensibility/walkthrough-highlighting-text.md).  
  
## <a name="extending-adornments"></a>Adornments genişletme  
 Adornments ya da bir metin görünümünde görüntülenen metin eklenebilir veya metnin kendisi görüntülemek görsel efektler tanımlayın. Herhangi bir türde kendi adornment tanımlayabilirsiniz <xref:System.Windows.UIElement>.  
  
 Adornment sınıfınızda bildirmelisiniz bir <xref:Microsoft.VisualStudio.Text.Editor.AdornmentLayerDefinition>. Adornment katmanınız kaydetmek için aşağıdaki öznitelikler birlikte dışarı aktarın:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: adornment adı.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: adornment diğer adornment katmanları göre sıralama. Sınıf <xref:Microsoft.VisualStudio.Text.Editor.PredefinedAdornmentLayers> dört varsayılan katmanı tanımlar: seçimi, Anahat, düzeltme işareti ve metin.  
  
 Aşağıdaki örnek, bir adornment katman tanımında verme öznitelikleri gösterir.  
  
```  
[Export]  
[Name("TestEmbeddedAdornment")]  
[Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
internal AdornmentLayerDefinition testLayerDefinition;  
```  
  
 Uygulayan bir ikinci sınıf oluşturmalısınız <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener> ve işler, <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> adornment örneği tarafından olay. Bu sınıf aşağıdaki öznitelikler birlikte dışarı aktarmanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: adornment olduğu geçerli içerik (örneğin, "metin" veya "code") türü.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>: Bu adornment olduğu geçerli metin görünüm türü. Sınıf <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles> tanımlanmış metin görünümü rolleri kümesi vardır. Örneğin, <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document> dosyaları metin görünümler için temel olarak kullanılır. <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive>Kullanıcı düzenleme veya fare ve klavye kullanarak gezinme metin görünümler için kullanılır. Örnekleri <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive> görünümlerdir düzenleyici metin görünümü ve **çıkış** penceresi.  
  
 Aşağıdaki örnek adornment sağlayıcısı verme öznitelikleri gösterir.  
  
```  
[Export(typeof(IWpfTextViewCreationListener))]  
[ContentType("csharp")]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
internal sealed class TestAdornmentProvider : IWpfTextViewCreationListener  
```  
  
 Bir alanı anlaşması adornment metin olarak aynı düzeyde yer kaplar biridir. Bu tür bir adornment oluşturmak için öğesinden devralınan bir etiket sınıf tanımlama <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>, adornment kapladığı alanı tanımlar.  
  
 Tüm adornments gibi ile adornment katman tanımı dışarı aktarmanız gerekir.  
  
```  
[Export]  
[Name("TestAdornment")]  
[Order(After = DefaultAdornmentLayers.Text)]  
internal AdornmentLayerDefinition testAdornmentLayer;  
```  
  
 Alanı anlaşması adornment örneği oluşturmak için uygulayan bir sınıf oluşturma <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider>, uygulayan sınıfa yanı sıra <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener> (adornments diğer tür olduğu gibi).  
  
 Etiketleme sağlayıcısını kaydetmek için aşağıdaki öznitelikler birlikte dışarı aktarmanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: içerik (örneğin, "metin" veya "code"), adornment olduğu geçerli türü.  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>: metin görünümü bu tür etiketi veya adornment geçerlidir. Sınıf <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles> tanımlanmış metin görünümü rolleri kümesi vardır. Örneğin, <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document> dosyaları metin görünümler için temel olarak kullanılır. <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive>Kullanıcı düzenleme veya fare ve klavye kullanarak gezinme metin görünümler için kullanılır. Örnekleri <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Interactive> görünümlerdir düzenleyici metin görünümü ve **çıkış** penceresi.  
  
-   <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute>: etiketi veya tanımlamış olduğunuz adornment türü. İkinci bir eklemelisiniz <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> için <xref:Microsoft.VisualStudio.Text.Tagging.SpaceNegotiatingAdornmentTag>.  
  
 Aşağıdaki örnek, alan anlaşması adornment etiket etiketleme sağlayıcıdaki verme öznitelikleri gösterir.  
  
```  
[Export(typeof(ITaggerProvider))]  
[ContentType("text")]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
[TagType(typeof(SpaceNegotiatingAdornmentTag))]  
[TagType(typeof(TestSpaceNegotiatingTag))]  
internal sealed class TestTaggerProvider : ITaggerProvider  
```  
  
## <a name="extending-mouse-processors"></a>Fare işlemciler genişletme  
 Fare girişi için özel işleme ekleyebilirsiniz. Öğesinden devralınan bir sınıf oluşturun <xref:Microsoft.VisualStudio.Text.Editor.MouseProcessorBase> ve fare olayları işlemek istediğiniz girişi için geçersiz kılın. Ayrıca uygulamalıdır <xref:Microsoft.VisualStudio.Text.Editor.IMouseProcessorProvider> ikinci sınıfında ve ile birlikte dışarı aktarma <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> fare işleyicinizi olduğu geçerli içerik (örneğin, "metin" veya "code") türü belirtir.  
  
 Aşağıdaki örnek, bir fare işlemci sağlayıcısında verme öznitelikleri gösterir.  
  
```  
[Export(typeof(IMouseProcessorProvider))]  
[Name("test mouse processor")]  
[ContentType("text")]  
[TextViewRole(PredefinedTextViewRoles.Interactive)]   
internal sealed class TestMouseProcessorProvider : IMouseProcessorProvider  
```  
  
## <a name="extending-drop-handlers"></a>Açılan işleyicileri genişletme  
 Uygulayan bir sınıf oluşturarak metin belirli tür için açılan işleyiciler davranışını özelleştirebilirsiniz <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.IDropHandler> ve ikinci uygulayan bir sınıf <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.IDropHandlerProvider> açılan işleyici oluşturulamadı. Aşağıdaki öznitelikler birlikte açılan işleyici dışarı aktarmanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.DragDrop.DropFormatAttribute>: Bu açılan işleyici olduğu geçerli metin biçimi. Aşağıdaki biçimlerden öncelik sırasına yüksekten en düşüğe ele alınmıştır:  
  
    1.  Özel bir biçim  
  
    2.  FileDrop  
  
    3.  EnhancedMetafile  
  
    4.  WaveAudio  
  
    5.  RIFF  
  
    6.  DIF  
  
    7.  Yerel Ayar  
  
    8.  Palet  
  
    9. PenData  
  
    10. Seri hale getirilebilir  
  
    11. SymbolicLink  
  
    12. XAML  
  
    13. XamlPackage  
  
    14. TIFF  
  
    15. Bit eşlem  
  
    16. DIB  
  
    17. MetafilePicture  
  
    18. CSV  
  
    19. System.String  
  
    20. HTML biçiminde  
  
    21. UnicodeText  
  
    22. OEMText  
  
    23. Metin  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: açılan işleyicisi adı.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: açılan işleyicisini önce veya sonra varsayılan açılan işleyici sıralama. Visual Studio için varsayılan açılan işleyicisi "DefaultFileDropHandler" olarak adlandırılır.  
  
 Aşağıdaki örnekte bir açılan işleyici sağlayıcısında verme öznitelikleri gösterir.  
  
```  
[Export(typeof(IDropHandlerProvider))]  
[DropFormat("Text")]   
[Name("TestDropHandler")]  
[Order(Before="DefaultFileDropHandler")]   
internal class TestDropHandlerProvider : IDropHandlerProvider  
```  
  
## <a name="extending-editor-options"></a>Düzenleyici Seçenekleri genişletme  
 Bir metin görünümünde yalnızca bir belirli kapsamda, örneğin, geçerli olması için seçenekleri tanımlayabilirsiniz. Bu önceden tanımlanmış seçenekleri kümesi Düzenleyici sağlar: Düzenleyici seçenekleri, görünüm seçenekleri ve Windows Presentation Foundation (WPF) görüntüleme seçenekleri. Bu seçenekler bulunabilir <xref:Microsoft.VisualStudio.Text.Editor.DefaultOptions>, <xref:Microsoft.VisualStudio.Text.Editor.DefaultTextViewOptions>, ve <xref:Microsoft.VisualStudio.Text.Editor.DefaultWpfViewOptions>.  
  
 Yeni bir seçenek eklemek için bu seçeneği tanımı sınıfları birinden bir sınıf türetin:  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.EditorOptionDefinition%601>  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.ViewOptionDefinition%601>  
  
-   <xref:Microsoft.VisualStudio.Text.Editor.WpfViewOptionDefinition%601>  
  
 Aşağıdaki örnek, bir Boolean değerine sahip bir seçenek tanımı dışarı aktarma gösterir.  
  
```  
[Export(typeof(EditorOptionDefinition))]  
internal sealed class TestOption : EditorOptionDefinition<bool>  
```  
  
## <a name="extending-intellisense"></a>IntelliSense genişletme  
 IntelliSense yapılandırılmış metin hakkında bilgi sağlayan özellikleri grubu için genel bir terim ve deyimi tamamlanmasını ' dir. Deyim tamamlama, imza Yardım, hızlı bilgi ve ampuller bu özellikler içerir. Deyim tamamlama, kullanıcıların bir dil anahtar sözcüğü veya üye adı doğru şekilde yazın yardımcı olur. İmza veya imza yalnızca kullanıcının girdiği yöntemi için imza Yardımı görüntüler. Fare üzerine getirildiğinde bir tür veya üye adı için tam bir imza hızlı bilgi görüntüler. Ampul bazı bağlamlarda, örneğin, belirli tanımlayıcıları için ek eylemler bir oluşumu adlandırıldı sonra bir değişken tüm oluşumlarını yeniden adlandırma sağlar.  
  
 IntelliSense özelliği tasarımını çok tüm durumlarda aynıdır:  
  
-   Bir IntelliSense *Aracısı* için genel işlem sorumludur.  
  
-   Bir IntelliSense *oturum* sunan ve committal veya seçimi iptaline tetikleme arasında olaylar dizisini temsil eder. Oturum genellikle bazı kullanıcı hareketi tarafından tetiklenir.  
  
-   Bir IntelliSense *denetleyicisi* ne zaman oturum başlayıp biteceğini karar sorumludur. Ayrıca zaman bilgileri kaydedilmiş olmalıdır ve oturum zaman iptal karar verir.  
  
-   Bir IntelliSense *kaynak* içerik sağlar ve en iyi eşleşmeyi karar verir.  
  
-   Bir IntelliSense *sunum* içeriği görüntülemek için sorumludur.  
  
 Çoğu durumda, en az bir kaynak ve denetleyicisi sağlamanızı öneririz. Görüntü özelleştirmek istiyorsanız bir sunum de sağlayabilirsiniz.  
  
### <a name="implementing-an-intellisense-source"></a>IntelliSense kaynağı uygulama  
 Bir kaynak özelleştirmek için aşağıdaki kaynak arabirimleri bir (veya daha fazla) uygulamanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSource>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>  
  
> [!IMPORTANT]
>  <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagSource>Şunun için kullanım <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSource>.  
  
 Ayrıca, aynı türde bir sağlayıcı uygulamanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ICompletionSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.IQuickInfoSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISignatureHelpSourceProvider>  
  
-   <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>  
  
> [!IMPORTANT]
>  <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagSourceProvider>Şunun için kullanım <xref:Microsoft.VisualStudio.Language.Intellisense.ISuggestedActionsSourceProvider>.  
  
 Aşağıdaki öznitelikler birlikte sağlayıcısı dışarı aktarmanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: kaynağının adı.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: kaynak geçerli olduğu (örneğin, "metin" veya "code") içerik türü.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: kaynak (göre diğer kaynakları) görünmelidir sırası.  
  
-   Aşağıdaki örnekte bir tamamlanma kaynak sağlayıcı verme öznitelikleri gösterir.  
  
```  
Export(typeof(ICompletionSourceProvider))]  
[Name(" Test Statement Completion Provider")]  
[Order(Before = "default")]  
[ContentType("text")]  
internal class TestCompletionSourceProvider : ICompletionSourceProvider  
```  
  
 IntelliSense kaynakları uygulama hakkında daha fazla bilgi için aşağıdaki izlenecek bakın:  
  
 [İzlenecek Yol: HızlıBilgi Araç İpuçlarını Görüntüleme](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)  
  
 [İzlenecek Yol: İmza Yardımını Görüntüleme](../extensibility/walkthrough-displaying-signature-help.md)  
  
 [İzlenecek Yol: Deyim Tamamlamayı Görüntüleme](../extensibility/walkthrough-displaying-statement-completion.md)  
  
### <a name="implementing-an-intellisense-controller"></a>IntelliSense denetleyicisi uygulama  
 Bir denetleyici özelleştirmek için uygulamanız gereken <xref:Microsoft.VisualStudio.Language.Intellisense.IIntellisenseController> arabirimi. Ayrıca, aşağıdaki öznitelikler birlikte controller sağlayıcısı uygulamanız gerekir:  
  
-   <xref:Microsoft.VisualStudio.Utilities.NameAttribute>: denetleyicinin adı.  
  
-   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>: denetleyicisi geçerli olduğu (örneğin, "metin" veya "code") içerik türü.  
  
-   <xref:Microsoft.VisualStudio.Utilities.OrderAttribute>: siparişin denetleyici (göre diğer denetleyicileri) görünmelidir.  
  
 Aşağıdaki örnek, bir tamamlama denetleyicisi sağlayıcısında dışarı aktarma öznitelikleri gösterir.  
  
```  
Export(typeof(IIntellisenseControllerProvider))]  
[Name(" Test Controller Provider")]  
[Order(Before = "default")]  
[ContentType("text")]  
internal class TestIntellisenseControllerProvider : IIntellisenseControllerProvider  
```  
  
 IntelliSense denetleyicileri kullanma hakkında daha fazla bilgi için aşağıdaki izlenecek bakın:  
  
 [İzlenecek Yol: HızlıBilgi Araç İpuçlarını Görüntüleme](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)