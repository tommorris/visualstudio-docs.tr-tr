---
title: Kod parçacıkları eski dil hizmetindeki desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- snippets, supporting in language services
- code snippets, supporting in language services [managed package framework]
- language services [managed package framework], supporting code snippets
ms.assetid: 7490325b-acee-4c2d-ac56-1cd5db1a1083
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: eb62481b9ba2c42ed067275480ba137b151a483b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="support-for-code-snippets-in-a-legacy-language-service"></a>Kod parçacıkları eski dil hizmetindeki desteği
Kod parçacığı, kaynak dosyasına eklenen kod parçasıdır. Parçacığı alanları kümesini XML tabanlı bir şablonla ' dir. Kod parçacığını eklenir ve kod parçacığında eklenen içerik bağlı olarak farklı değerlere sahip olabilir sonra bu alanlar vurgulanır. Kod parçacığını hemen eklendikten sonra dil hizmeti kod parçacığını biçimlendirebilirsiniz.  
  
 Kod parçacığını bir özel düzenleme modunda SEKME tuşunu kullanarak gittiğinizde parçacığı alanlarının verir eklenir. Alanları IntelliSense stili aşağı açılır menüler destekleyebilir. Kullanıcı kod parçacığını girin veya ESC tuşuna yazarak kaynak dosyaya kaydeder. Kod parçacıkları hakkında daha fazla bilgi için lütfen bkz [kod parçacıkları](../../ide/code-snippets.md).  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Daha fazla bilgi bulmak için bkz: [izlenecek yol: uygulama kod parçacıkları](../../extensibility/walkthrough-implementing-code-snippets.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
## <a name="managed-package-framework-support-for-code-snippets"></a>Yönetilen kod parçacıkları için paket Framework desteği  
 Yönetilen paket framework (MPF) kod parçacığını ekleme şablonu okuma gelen çoğu parçacığı işlevselliği destekler ve özel etkinleştirme düzenleme modunda. Destek üzerinden yönetilir <xref:Microsoft.VisualStudio.Package.ExpansionProvider> sınıfı.  
  
 Zaman <xref:Microsoft.VisualStudio.Package.Source> sınıf örneği, <xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionProvider%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı almak için çağrılır bir <xref:Microsoft.VisualStudio.Package.ExpansionProvider> nesne (unutmayın temel <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı her zaman döndürür yeni bir <xref:Microsoft.VisualStudio.Package.ExpansionProvider> her nesne <xref:Microsoft.VisualStudio.Package.Source> Nesne).  
  
 MPF genişletme işlevleri desteklemiyor. Bir genişletme işlevi parçacığı şablonda katıştırılır ve bir alana yerleştirilecek bir veya daha fazla değer döndüren bir adlandırılmış bir işlevdir. Dil tarafından döndürülen değerlerin kendisi aracılığıyla hizmet bir <xref:Microsoft.VisualStudio.Package.ExpansionFunction> nesnesi. <xref:Microsoft.VisualStudio.Package.ExpansionFunction> Genişletme işlevlerini desteklemek için dil hizmeti tarafından nesne uygulanmadı.  
  
## <a name="providing-support-for-code-snippets"></a>Kod parçacıkları için desteği sağlama  
 Kod parçacıkları desteğini etkinleştirmek için sağlayın veya parçacıkları yükleyin ve bu parçacıkları eklemeye kullanıcı araçlarını sağlamanız gerekir. Kod parçacıkları desteğini etkinleştirmek için üç adım vardır:  
  
1.  Parçacık dosyaları yükleme.  
  
2.  Kod parçacıkları dil hizmetiniz için etkinleştiriliyor.  
  
3.  Çağırma <xref:Microsoft.VisualStudio.Package.ExpansionProvider> nesnesi.  
  
### <a name="installing-the-snippet-files"></a>Kod parçacığında dosyalar yükleniyor  
 Bir dil için tüm parçacıkları varsayılan olarak, genellikle bir kod parçacığında şablon her dosya, XML dosyalarını şablonlarında olarak depolanır. Kod parçacığı şablonları için kullanılan XML şeması hakkında daha fazla bilgi için bkz: [kod parçacıkları şema başvurusu](../../ide/code-snippets-schema-reference.md). Her kod parçacığında şablonu dil kimliği ile tanımlanır Bu dil kimliği kayıt defterinde belirtilen ve içine yerleştirileceği `Language` özniteliği \<kodu > şablondaki etiketi.  
  
 Kod parçacığında şablon dosyalarının depolandığı iki konum vardır: 1) burada dilinizi yüklendi ve 2) kullanıcının klasöründeki. Bu konumları kayıt defterine bu nedenle, eklenen Visual Studio **kod parçacıkları Yöneticisi** parçacıkları bulabilirsiniz. Kullanıcının kullanıcı tarafından oluşturulmuş parçacıkları depolandığı klasörüdür.  
  
 Yüklü parçacığı şablon dosyalarını normal klasörü düzenini şöyle görünür: *[yüklemekökü]*\\*[TestLanguage]*\Snippets\\*[LCID]*\Snippets.  
  
 *[Yüklemekökü]*  dilinizi yüklü olduğu klasördür.  
  
 *[TestLanguage]*  dilinizi bir klasör adı olarak adıdır.  
  
 *[LCID]*  yerel ayar kimliğidir. Bu, parçacıkları nasıl yerelleştirilmiş sürümleri olan depolanır. Örneğin, İngilizce yerel ayar kimliği 1033, bu nedenle ' *[LCID]* 1033 tarafından değiştirilir.  
  
 Bir ek dosyası sağlanmalıdır ve genellikle SnippetsIndex.xml veya ExpansionsIndex.xml (.xml biten geçerli bir dosya kullanabilirsiniz) adlı bir dizin dosyası. Bu dosya genellikle depolanan *[yüklemekökü]*\\*[TestLanguage]* klasörü ve parçacıkları klasörü yanı sıra dil kimliği tam konumu ve dil GUID belirtir kod parçacıkları kullanan hizmet. Dizin dosyasının tam yolunu, daha sonra "yükleme kayıt defteri girişleri" açıklandığı şekilde kayıt defterine yerleştirilir. Aşağıda, SnippetsIndex.xml dosyası örneği verilmiştir:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<SnippetCollection>  
    <Language Lang="Testlanguage" Guid="{b614a40a-80d9-4fac-a6ad-fc2868fff7cd}">  
        <SnippetDir>  
            <OnOff>On</OnOff>  
            <Installed>true</Installed>  
            <Locale>1033</Locale>  
            <DirPath>%InstallRoot%\TestLanguage\Snippets\%LCID%\Snippets\</DirPath>  
            <LocalizedName>Snippets</LocalizedName>  
        </SnippetDir>  
    </Language>  
</SnippetCollection>  
```  
  
 \<Dil > etiketi, dil kimliği belirtir ( `Lang` özniteliği) ve dil hizmeti GUID.  
  
 Bu örnekte, Visual Studio yükleme klasöründe, dil hizmetinin yüklü olduğu varsayılır. LCID % kullanıcının geçerli yerel ayar kimliği ile değiştirilir Birden çok \<SnippetDir > etiketleri eklenebilir, her farklı dizin ve yerel ayar için bir tane. Bir kod parçacığında klasör her biri ile dizin dosyasında tanımlanır alt klasörler, ayrıca, içerebilir \<SnippetSubDir > içinde katıştırılmış etiketi bir \<SnippetDir > etiketi.  
  
 Kullanıcılar kendi parçacıkları diliniz için de oluşturabilirsiniz. Bunlar genellikle kullanıcının ayarlarını, örneğin klasöründeki *[TestDocs]*\Code parçacıkları\\*[TestLanguage]*\Test kod parçacıkları, burada *[TestDocs]* kullanıcının ayarlarını klasörü Visual Studio için konumdur.  
  
 Aşağıdaki değiştirme öğeleri depolanan yol yerleştirilebilir \<DirPath > Dizin dosyasındaki etiketi.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|LCID %|Yerel ayar kimliği|  
|% Yüklemekökü %|Visual Studio, örneğin, C:\Program Files\Microsoft Visual Studio 8 yükleme klasörünü kök.|  
|% ProjDir %|Geçerli projenin içeren klasör.|  
|% ProjItem %|Geçerli proje öğesi içeren klasör.|  
|% TestDocs %|Klasöründe kullanıcının ayarlarını, örneğin, C:\Documents and Settings\\*[username]*\My Documents\Visual Studio\8.|  
  
### <a name="enabling-code-snippets-for-your-language-service"></a>Kod parçacıkları dil hizmetiniz için etkinleştirme  
 Kod parçacıkları ekleyerek dil hizmetiniz için etkinleştirebilirsiniz <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> özniteliği, VSPackage (bkz [eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md) Ayrıntılar için). <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute.ShowRoots%2A> Ve <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute.SearchPaths%2A> parametreler isteğe bağlıdır, ancak içermesi gerekir `SearchPaths` bildirmek için parametre adlı **kod parçacıkları Yöneticisi** , parçacıkları konumunu.  
  
 Bu öznitelik kullanımına bir örnek verilmiştir:  
  
```  
[ProvideLanguageCodeExpansion(  
         typeof(TestSnippetLanguageService),  
         "Test Snippet Language",          // Name of language used as registry key  
         0,                               // Resource ID of localized name of language service  
         "Test Snippet Language",        // Name of Language attribute in snippet template  
         @"%InstallRoot%\Test Snippet Language\Snippets\%LCID%\SnippetsIndex.xml",  // Path to snippets index  
         SearchPaths = @"%InstallRoot%\Test Snippet Language\Snippets\%LCID%\")]    // Path to snippets  
```  
  
### <a name="calling-the-expansion-provider"></a>Genişletme sağlayıcısı çağırma  
 Dil hizmeti ekleme, ekleme çağrılan şekilde yanı sıra tüm kod parçacığını denetler.  
  
## <a name="calling-the-expansion-provider-for-code-snippets"></a>Kod parçacıkları için genişletme sağlayıcısı çağırma  
 Genişletme sağlayıcı çağırmak için iki yolu vardır: menü komutunu kullanarak veya tamamlanma listesi kısayoldan kullanarak.  
  
### <a name="inserting-a-code-snippet-by-using-a-menu-command"></a>Menü komutunu kullanarak bir kod parçacığı ekleme  
 Parçacığı tarayıcı görüntülenen menü komutu kullanmak için menü komutu ekleyin ve ardından çağıran <xref:Microsoft.VisualStudio.Package.ExpansionProvider.DisplayExpansionBrowser%2A> yönteminde <xref:Microsoft.VisualStudio.Package.ExpansionProvider> bu menü komutuna yanıt olarak arabirimi.  
  
1.  Bir komut ve bir düğme .vsct dosyanıza ekleyin. Bu nedenle de yapmak için yönergeler bulabilirsiniz [uzantı menü komutu ile oluşturma](../../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Öğesinden bir sınıf türetin <xref:Microsoft.VisualStudio.Package.ViewFilter> sınıfı ve geçersiz kılma <xref:Microsoft.VisualStudio.Package.ViewFilter.QueryCommandStatus%2A> yeni menü komutu desteği belirtmek için yöntem. Bu örnekte, her zaman menü komutu sağlar.  
  
    ```csharp  
    using Microsoft.VisualStudio.Package;  
  
    namespace TestLanguagePackage  
    {  
        class TestViewFilter : ViewFilter  
        {  
            public TestViewFilter(CodeWindowManager mgr, IVsTextView view)  
                : base(mgr, view)  
            {  
            }  
  
            protected override int QueryCommandStatus(ref Guid guidCmdGroup,  
                                                      uint nCmdId)  
            {  
                int hr = base.QueryCommandStatus(ref guidCmdGroup, nCmdId);  
                // If the base class did not recognize the command then  
                // see if we can handle the command.  
                if (hr == (int)Microsoft.VisualStudio.OLE.Interop.Constants.OLECMDERR_E_UNKNOWNGROUP)  
                {  
                    if (guidCmdGroup == GuidList.guidTestLanguagePackageCmdSet)  
                    {  
                        if (nCmdId == PkgCmdIDList.InvokeCodeSnippetsBrowser)  
                        {  
                            hr = (int)(OLECMDF.OLECMDF_SUPPORTED | OLECMDF.OLECMDF_ENABLED);  
                        }  
                    }  
                }  
                return hr;  
            }  
        }  
    }  
    ```  
  
3.  Geçersiz kılma <xref:Microsoft.VisualStudio.Package.ViewFilter.HandlePreExec%2A> yönteminde <xref:Microsoft.VisualStudio.Package.ViewFilter> elde etmek için sınıf <xref:Microsoft.VisualStudio.Package.ExpansionProvider> nesne ve çağrı <xref:Microsoft.VisualStudio.Package.ExpansionProvider.DisplayExpansionBrowser%2A> bu nesne üzerinde yöntemi.  
  
    ```csharp  
    using Microsoft.VisualStudio.Package;  
  
    namespace TestLanguagePackage  
    {  
        class TestViewFilter : ViewFilter  
        {  
            public override bool HandlePreExec(ref Guid guidCmdGroup,  
                                               uint nCmdId,  
                                               uint nCmdexecopt,  
                                               IntPtr pvaIn,  
                                               IntPtr pvaOut)  
            {  
                if (base.HandlePreExec(ref guidCmdGroup,  
                                       nCmdId,  
                                       nCmdexecopt,  
                                       pvaIn,  
                                       pvaOut))  
                {  
                    // Base class handled the command.  Do nothing more here.  
                    return true;  
                }  
  
                if (guidCmdGroup == GuidList.guidTestLanguagePackageCmdSet)  
                {  
                    if (nCmdId == PkgCmdIDList.InvokeCodeSnippetsBrowser)  
                    {  
                        ExpansionProvider ep = this.GetExpansionProvider();  
                        if (this.TextView != null && ep != null)  
                        {  
                            bool bDisplayed = ep.DisplayExpansionBrowser(  
                                this.TextView,  
                                "TestLanguagePackage Snippet:",  
                                null,  
                                false,  
                                null,  
                                false);  
                        }  
                        return true;   // Handled the command.  
                    }  
                }  
                return false;   // Did not handle the command.  
            }  
        }  
    }  
  
    ```  
  
     Aşağıdaki yöntemleri <xref:Microsoft.VisualStudio.Package.ExpansionProvider> sınıfı çağrılır Visual Studio tarafından verildikleri sırada kod parçacığını ekleme işlemi sırasında:  
  
4.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnItemChosen%2A>  
  
5.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.IsValidKind%2A>  
  
6.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnBeforeInsertion%2A>  
  
7.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.FormatSpan%2A>  
  
8.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnAfterInsertion%2A>  
  
     Sonra <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnAfterInsertion%2A> yöntemi çağrıldığında, kod parçacığında eklenen ve <xref:Microsoft.VisualStudio.Package.ExpansionProvider> nesnesidir yalnızca eklenmiş bir parçacığını değiştirmek için kullanılan özel düzenleme modunda.  
  
### <a name="inserting-a-code-snippet-by-using-a-shortcut"></a>Kod parçacığı kısayolunu kullanarak ekleme  
 Tamamlanma listesi kısayoldan uyarlamasını menü komutu uygulama daha çok daha karmaşıktır. İlk parçacığı kısayolları IntelliSense Sözcük tamamlama listesine eklemeniz gerekir. Bir kod parçacığında kısayol adı tamamlama sonucunda eklendiğinde sonra algılaması gerekir. Son olarak, kod parçacığında başlık ve kısayol adını kullanarak yolu edinmeli ve bu bilgileri geçirmek <xref:Microsoft.VisualStudio.Package.ExpansionProvider.InsertNamedExpansion%2A> yöntemi <xref:Microsoft.VisualStudio.Package.ExpansionProvider> yöntemi.  
  
 Kod parçacığında kısayolları word tamamlama listesine eklemek için bunları Ekle <xref:Microsoft.VisualStudio.Package.Declarations> nesnesinde, <xref:Microsoft.VisualStudio.Package.AuthoringScope> sınıfı. Kısayol parçacığı adı olarak tanımlayabilirsiniz emin olmanız gerekir. Bir örnek için bkz: [izlenecek yol: bir listesi, yüklü kod parçacıkları (eski uygulama) alma](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md).  
  
 Kod parçacığı kısayoluna ekleme algılayabilir <xref:Microsoft.VisualStudio.Package.Declarations.OnAutoComplete%2A> yöntemi <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı. Kod parçacığında adı kaynak dosyasına eklenen çünkü genişletme takıldığında kaldırılmalıdır. <xref:Microsoft.VisualStudio.Package.ExpansionProvider.InsertNamedExpansion%2A> Yöntemi kod parçacığını ekleme noktası açıklayan bir aralık devralır; aralık kaynak dosyasına tüm parçacığı adı içeriyorsa, bu adı parçacığı tarafından değiştirilir.  
  
 Bir sürümünü İşte bir <xref:Microsoft.VisualStudio.Package.Declarations> bir kısayol adı verilen parçacığı ekleme işleme sınıfı. Diğer yöntemlerle <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı, daha anlaşılır olması için atlanmış. Bu sınıf gereken Not bir <xref:Microsoft.VisualStudio.Package.LanguageService> nesnesi. Bu, sürümünden geçirilebilir <xref:Microsoft.VisualStudio.Package.AuthoringScope> nesne (örneğin, uygulamanıza <xref:Microsoft.VisualStudio.Package.AuthoringScope> sınıfı alabilir <xref:Microsoft.VisualStudio.Package.LanguageService> nesne kurucusunda ve bu nesne için geçirin, `TestDeclarations` sınıf oluşturucu).  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    internal class TestDeclarations : Declarations  
    {  
        private ArrayList       declarations;  
        private LanguageService languageService;  
        private TextSpan        commitSpan;  
  
        public TestDeclarations(LanguageService langService)  
            : base()  
        {  
            languageService = langService;  
            declarations = new ArrayList();  
        }  
  
        // This method is used to add declarations to the internal list.  
        public void AddDeclaration(TestDeclaration declaration)  
        {  
            declarations.Add(declaration);  
        }  
  
        // This method is called to get the string to commit to the source buffer.  
        // Note that the initial extent is only what the user has typed so far.  
        public override string OnCommit(IVsTextView textView,  
                                        string textSoFar,  
                                        char commitCharacter,  
                                        int index,  
                                        ref TextSpan initialExtent)  
        {  
            // We intercept this call only to get the initial extent  
            // of what was committed to the source buffer.  
            commitSpan = initialExtent;  
  
            return base.OnCommit(textView,  
                                 textSoFar,  
                                 commitCharacter,  
                                 index,  
                                 ref initialExtent);  
        }  
  
        // This method is called after the string has been committed to the source buffer.  
        public override char OnAutoComplete(IVsTextView textView,  
                                            string committedText,  
                                            char commitCharacter,  
                                            int index)  
        {  
            TestDeclaration item = declarations[index] as TestDeclaration;  
            if (item != null)  
            {  
                // In this example, TestDeclaration identifies types with a string.  
                // You can choose a different approach.  
                if (item.Type == "snippet")  
                {  
                    Source src = languageService.GetSource(textView);  
                    if (src != null)  
                    {  
                        ExpansionProvider ep = src.GetExpansionProvider();  
                        if (ep != null)  
                        {  
                            string title;  
                            string path;  
                            int commitLength = commitSpan.iEndIndex - commitSpan.iStartIndex;  
                            if (commitLength < committedText.Length)  
                            {  
                                // Replace everything that was inserted  
                                // so calculate the span of the full  
                                // insertion, taking into account what  
                                // was inserted when the commitSpan  
                                // was obtained in the first place.  
                                commitSpan.iEndIndex += (committedText.Length - commitLength);  
                            }  
  
                            if (ep.FindExpansionByShortcut(textView,  
                                                           committedText,  
                                                           commitSpan,  
                                                           true,  
                                                           out title,  
                                                           out path))  
                            {  
                                ep.InsertNamedExpansion(textView,  
                                                        title,  
                                                        path,  
                                                        commitSpan,  
                                                        false);  
                            }  
                        }  
                    }  
                }  
            }  
            return '\0';  
        }  
    }  
}  
```  
  
 Dil hizmeti kısayol adını aldığında, çağıran <xref:Microsoft.VisualStudio.Package.ExpansionProvider.FindExpansionByShortcut%2A> filename ve kod parçacığını başlık elde etmek için yöntemi. Dil hizmeti daha sonra çağırır <xref:Microsoft.VisualStudio.Package.ExpansionProvider.InsertNamedExpansion%2A> yönteminde <xref:Microsoft.VisualStudio.Package.ExpansionProvider> kod parçacığını eklemek için sınıfı. Aşağıdaki yöntemlerden Visual Studio tarafından verilen sırayla adlı <xref:Microsoft.VisualStudio.Package.ExpansionProvider> kod parçacığını ekleme işlemi sırasında sınıfı:  
  
1.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.IsValidKind%2A>  
  
2.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnBeforeInsertion%2A>  
  
3.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.FormatSpan%2A>  
  
4.  <xref:Microsoft.VisualStudio.Package.ExpansionProvider.OnAfterInsertion%2A>  
  
 Dil hizmetiniz için yüklü kod parçacıkları listesini alma ile ilgili daha fazla bilgi için bkz: [izlenecek yol: bir listesi, yüklü kod parçacıkları (eski uygulama) alma](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md).  
  
## <a name="implementing-the-expansionfunction-class"></a>ExpansionFunction sınıfı  
 Bir genişletme işlevi parçacığı şablonda katıştırılır ve bir alana yerleştirilecek bir veya daha fazla değer döndüren bir adlandırılmış bir işlevdir. Dil hizmetinizi genişletme işlevleri desteklemek için öğesinden bir sınıf türetin <xref:Microsoft.VisualStudio.Package.ExpansionFunction> sınıfı ve uygulamanıza <xref:Microsoft.VisualStudio.Package.ExpansionFunction.GetCurrentValue%2A> yöntemi. Ardından geçersiz kılmanız gerekir <xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionFunction%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> yeni bir örneğini oluşturmada sürümünüzün döndürmek için sınıf <xref:Microsoft.VisualStudio.Package.ExpansionFunction> desteklediğiniz her genişletme işlevi için sınıf. Bir genişletme işlevden olası değerler listesini destekliyorsa, geçersiz kılmalısınız <xref:Microsoft.VisualStudio.Package.ExpansionFunction.GetIntellisenseList%2A> yönteminde <xref:Microsoft.VisualStudio.Package.ExpansionFunction> sınıfı bu değerleri listesini döndürür.  
  
 Bağımsız değişken almayan veya diğer alanlar erişmesi gereken bir genişletme işlevi, genişletme sağlayıcısı tam olarak genişletme işlevini çağırdı zamanına göre başlatılmamış olabilir düzenlenebilir bir alanı ile ilişkilendirilmemelidir. Sonuç olarak, genişletme işlev bağımsız değişkenleri veya başka bir alan değeri elde etmek mümkün değil.  
  
### <a name="example"></a>Örnek  
 Bir örneği nasıl basit genişletme işlevini çağırdı işte `GetName` uygulanabilir. Bu genişletme işlevi bir sayı bir temel sınıf adı genişletme işlevi örneği her zaman ekler (her zaman ilişkili kod parçacığında karşılık geldiği eklenir).  
  
```csharp  
using Microsoft.VisualStudio.Package;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private int classNameCounter = 0;  
  
        public override ExpansionFunction CreateExpansionFunction(  
            ExpansionProvider provider,  
            string functionName)  
        {  
            ExpansionFunction function = null;  
            if (functionName == "GetName")  
            {  
                ++classNameCounter;  
                function = new TestGetNameExpansionFunction(provider, classNameCounter);  
            }  
            return function;  
        }  
    }  
  
    internal class TestGetNameExpansionFunction : ExpansionFunction  
    {  
        private int nameCount;  
  
        TestGetNameExpansionFunction(ExpansionProvider provider, int counter)  
            : base(provider)  
        {  
            nameCount = counter;  
        }  
  
        public override string GetCurrentValue()  
        {  
            string name = "TestClass";  
            name += nameCount.ToString();  
            return name;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti özellikleri](../../extensibility/internals/legacy-language-service-features1.md)   
 [Eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md)   
 [Kod parçacıkları](../../ide/code-snippets.md)   
 [İzlenecek Yol: Yüklü Kod Parçacıklarının Listesini Alma (Eski Uygulama)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)