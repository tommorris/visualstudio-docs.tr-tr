---
title: Eski dil Service2 uygulama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services [managed package framework], implementing
ms.assetid: 5bcafdc5-f922-48f6-a12e-6c8507a79a05
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 20dc3cf7b4db090bf7fcd0086b3e72575d8490cd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-a-legacy-language-service"></a>Eski dil hizmeti uygulama
Yönetilen paket framework (MPF) kullanarak bir dil hizmet uygulamak için öğesinden bir sınıf türetin <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı ve aşağıdaki soyut yöntemler ve özellikler uygular:  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> Yöntemi  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> Yöntemi  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> Yöntemi  
  
-   <xref:Microsoft.VisualStudio.Package.LanguageService.Name%2A> Özelliği  
  
 Bu yöntemlere ve özelliklere uygulanmasına aşağıda uygun bölümleri Ayrıntılar için bkz.  
  
 Ek özellikleri destekleyecek şekilde dili hizmetinizi MPF dil hizmeti sınıflarının birinden bir sınıf türetin gerekebilir; Örneğin, ek menü komutlarını desteklemek için bir sınıftan türetilmelidir <xref:Microsoft.VisualStudio.Package.ViewFilter> sınıfı ve birkaç yöntemleri işleme komutunun geçersiz kılma (bkz <xref:Microsoft.VisualStudio.Package.ViewFilter> Ayrıntılar için). <xref:Microsoft.VisualStudio.Package.LanguageService> Sınıfı, bir dizi yeni örneklerini çeşitli sınıfları oluşturmak için çağrılan yöntem sağlar ve sizin sınıfının bir örneği sağlamak için uygun oluşturma yöntemini geçersiz kılın. Örneğin, geçersiz kılmak gereken <xref:Microsoft.VisualStudio.Package.LanguageService.CreateViewFilter%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> kendinize ait bir örnek döndürmeyi sınıfı <xref:Microsoft.VisualStudio.Package.ViewFilter> sınıfı. Daha fazla ayrıntı için "Özel sınıflar örnek oluşturma" bölümüne bakın.  
  
 Dil hizmetinizi aynı zamanda birçok yerde kullanılan kendi simgeler sağlayabilir. Örneğin, bir IntelliSense tamamlanma listesi gösterildiğinde, listedeki her bir öğe, öğe bir yöntemi, sınıf, ad alanı, özelliği işaretleme ilişkili bir simge olabilir veya her dil için gereklidir. Bu simgeleri kullanılan tüm IntelliSense listelerindeki **gezinti çubuğu**hem de **hata listesi** görev penceresi. Ayrıntılar için aşağıdaki "Dil hizmeti görüntüleri" bölümüne bakın.  
  
## <a name="getlanguagepreferences-method"></a>GetLanguagePreferences yöntemi  
 <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> Yöntemi her zaman aynı örneğini döndüren bir <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı. Temel kullanabileceğiniz <xref:Microsoft.VisualStudio.Package.LanguagePreferences> dil hizmetiniz için ek olduğunuz tercihlere gerekmiyorsa sınıfı. MPF dil hizmet sınıfları varlığını en az varsayın temel <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı.  
  
### <a name="example"></a>Örnek  
 Bu örnek, tipik bir uyarlamasını gösterir <xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A> yöntemi. Bu örnek temel kullanır <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private LanguagePreferences m_preferences;  
  
        public override LanguagePreferences GetLanguagePreferences()  
        {  
            if (m_preferences == null)  
            {  
                m_preferences = new LanguagePreferences(this.Site,  
                                                        typeof(TestLanguageService).GUID,  
                                                        this.Name );  
                m_preferences.Init();  
            }  
            return m_preferences;  
        }  
    }  
}  
```  
  
## <a name="getscanner-method"></a>GetScanner yöntemi  
 Bu yöntem bir örneğini döndüren bir <xref:Microsoft.VisualStudio.Package.IScanner> satır yönelimli ayrıştırıcı veya belirteçleri ve türleri ve Tetikleyicileri almak için kullanılan tarayıcı uygulayan nesne. Bu tarayıcı kullanılan <xref:Microsoft.VisualStudio.Package.Colorizer> tarayıcı olarak prelude daha karmaşık bir ayrıştırma işlemi için belirteç türleri ve Tetikleyicileri almak için de kullanılabilir olsa da renklendirme için sınıf. Uygulayan sınıfa sağlamalısınız <xref:Microsoft.VisualStudio.Package.IScanner> arabirimi ve uygulanmalı tüm yöntemleri üzerinde <xref:Microsoft.VisualStudio.Package.IScanner> arabirimi.  
  
### <a name="example"></a>Örnek  
 Bu örnek, tipik bir uyarlamasını gösterir <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> yöntemi. `TestScanner` Uygulayan sınıf <xref:Microsoft.VisualStudio.Package.IScanner> arabirimi (gösterilmez).  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        private TestScanner m_scanner;  
  
        public override IScanner GetScanner(IVsTextLines buffer)  
        {  
            if (m_scanner == null)  
            {  
                m_scanner = new TestScanner(buffer);  
            }  
            return m_scanner;  
        }  
    }  
}  
    internal class TestScanner : IScanner  
    {  
        private IVsTextBuffer m_buffer;  
        string m_source;  
  
        public TestScanner(IVsTextBuffer buffer)  
        {  
            m_buffer = buffer;  
        }  
  
        bool IScanner.ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo, ref int state)  
        {  
            tokenInfo.Type = TokenType.Unknown;  
            tokenInfo.Color = TokenColor.Text;  
            return true;  
        }  
  
        void IScanner.SetSource(string source, int offset)  
        {  
            m_source = source.Substring(offset);  
        }  
    }  
  
```  
  
## <a name="parsesource-method"></a>ParseSource yöntemi  
 Farklı nedenlerle sayısına göre kaynak dosyasını ayrıştırır. Bu yöntem verilen bir <xref:Microsoft.VisualStudio.Package.ParseRequest> belirli bir ayrıştırma işlemi beklenen tanımlayan nesne. <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> Belirteci işlevselliğini ve kapsamı belirler daha karmaşık bir ayrıştırıcı yöntemini çağırır. <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> IntelliSense işlemlerinin yanı sıra eşleşen ayraç yöntemi desteği kullanılır. Gelişmiş gibi işlemleri desteklemeyen olsa bile, yine geçerli bir döndürmelidir <xref:Microsoft.VisualStudio.Package.AuthoringScope> nesne ve, uygulayan bir sınıf oluşturmak gerektirir <xref:Microsoft.VisualStudio.Package.AuthoringScope> arabirim ve bu arabirimdeki tüm yöntemleri uygulamak. Tüm yöntemleri null değerleri döndürebilir ancak <xref:Microsoft.VisualStudio.Package.AuthoringScope> nesnenin kendisini bir null değer olmamalıdır.  
  
### <a name="example"></a>Örnek  
 Bu örnek, en az bir uyarlamasını gösterir <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi ve <xref:Microsoft.VisualStudio.Package.AuthoringScope> sınıfı, derlemek ve gerçekte daha gelişmiş özelliklerden herhangi birini destekleyen olmadan işlev dil hizmeti izin vermek için yeterli.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        public override AuthoringScope ParseSource(ParseRequest req)  
        {  
            return new TestAuthoringScope();  
        }  
    }  
  
    internal class TestAuthoringScope : AuthoringScope  
    {  
        public override string GetDataTipText(int line, int col, out TextSpan span)  
        {  
            span = new TextSpan();  
            return null;  
        }  
  
        public override Declarations GetDeclarations(IVsTextView view,  
                                                     int line,  
                                                     int col,  
                                                     TokenInfo info,  
                                                     ParseReason reason)  
        {  
            return null;  
        }  
  
        public override string Goto(VSConstants.VSStd97CmdID cmd, IVsTextView textView, int line, int col, out TextSpan span)  
        {  
            span = new TextSpan();  
            return null;  
        }  
  
        public override Methods GetMethods(int line, int col, string name)  
        {  
            return null;  
        }  
}  
```  
  
## <a name="name-property"></a>Name özelliği  
 Bu özellik dil hizmetin adını döndürür. Bu dil hizmeti kaydolurken verilen aynı adı olmalıdır. Bu ad en belirgin olan bir dizi bir yerde içinde kullanılan <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı burada adı kayıt defterine erişim için kullanılır. Kayıt defteri girdisini ve anahtar adları için kayıt defterinde kullanılan bu özellik tarafından döndürülen adı yerelleştirilmiş olmalıdır değil.  
  
### <a name="example"></a>Örnek  
 Bu örnek, bir olası uyarlamasını gösterir <xref:Microsoft.VisualStudio.Package.LanguageService.Name%2A> özelliği. Buradaki ad sabit kodlanmış olduğuna dikkat edin: dil hizmeti kaydetme olarak kullanılabilmesi için bir kaynak dosyasından gerçek ad alınan (bkz [eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md)).  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestLanguageService : LanguageService  
    {  
        public override string Name  
        {  
            get { return "Test Language"; }  
        }  
    }  
}  
```  
  
## <a name="instantiating-custom-classes"></a>Özel sınıflar örnek oluşturma  
 Belirtilen sınıflar aşağıdaki yöntemleri her sınıf kendi sürümlerini örneklerini sağlamak üzere geçersiz kılınabilir.  
  
### <a name="in-the-languageservice-class"></a>LanguageService sınıfında  
  
|Yöntem|Döndürülen sınıfı|Açıklama|  
|------------|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateCodeWindowManager%2A>|<xref:Microsoft.VisualStudio.Package.CodeWindowManager>|Metin görünümü özel eklemeler desteklemek için.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateDocumentProperties%2A>|<xref:Microsoft.VisualStudio.Package.DocumentProperties>|Özel belge özelliklerini desteklemek için.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateDropDownHelper%2A>|<xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars>|Desteklemek için **gezinti çubuğu**.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionFunction%2A>|<xref:Microsoft.VisualStudio.Package.ExpansionFunction>|Kod parçacığı şablonlarında işlevleri desteklemek için.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateExpansionProvider%2A>|<xref:Microsoft.VisualStudio.Package.ExpansionProvider>|Kod parçacıkları (Bu yöntem genellikle değil geçersiz kılınır) desteklemek için.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateParseRequest%2A>|<xref:Microsoft.VisualStudio.Package.ParseRequest>|Özelleştirmesini desteklemek için <xref:Microsoft.VisualStudio.Package.ParseRequest> yapısı (Bu yöntemi geçersiz genellikle değil kılınmıştır).|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateSource%2A>|<xref:Microsoft.VisualStudio.Package.Source>|Açıklama karakterleri belirtme ve yöntem imzaları özelleştirme biçimlendirme kaynak kodu desteklemek için.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.CreateViewFilter%2A>|<xref:Microsoft.VisualStudio.Package.ViewFilter>|Ek menü komutlarını desteklemek için.|  
|<xref:Microsoft.VisualStudio.Package.Source.GetColorizer%2A>|<xref:Microsoft.VisualStudio.Package.Colorizer>|(Bu yöntem genellikle değil geçersiz kılınır) sözdizimi vurgulama desteklemek için.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.GetLanguagePreferences%2A>|<xref:Microsoft.VisualStudio.Package.LanguagePreferences>|Dil Tercihleri erişimi desteklemek için. Bu yöntemin uygulanması gerekiyor ancak temel sınıfının bir örneğini döndürebilirsiniz.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A>|<xref:Microsoft.VisualStudio.Package.IScanner>|Satırındaki belirteçleri türlerini tanımlamak için kullanılan bir ayrıştırıcı sağlamak için. Bu yöntemin uygulanması gerekir ve <xref:Microsoft.VisualStudio.Package.IScanner> türetilmiş olmalıdır.|  
|<xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A>|<xref:Microsoft.VisualStudio.Package.AuthoringScope>|İşlevselliği ve tüm kaynak dosyasına boyunca kapsamını tanımlamak için kullanılan bir ayrıştırıcı sağlamak için. Bu yöntem uygulanması gerekiyor ve sürümünüz örneği döndürmelidir <xref:Microsoft.VisualStudio.Package.AuthoringScope> sınıfı. Tüm desteklemek istiyorsanız olan söz dizimi vurgulama (gerektiren <xref:Microsoft.VisualStudio.Package.IScanner> döndürülen ayrıştırıcı <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> yöntemi), bir sürümü bu yönteminin dönüş dışında bir şey yapabilirsiniz <xref:Microsoft.VisualStudio.Package.AuthoringScope> sınıfı olan yöntemleri tüm null değerleri döndürür.|  
  
### <a name="in-the-source-class"></a>Kaynak sınıfı  
  
|Yöntem|Döndürülen sınıfı|Açıklama|  
|------------|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateCompletionSet%2A>|<xref:Microsoft.VisualStudio.Package.CompletionSet>|IntelliSense tamamlanma listeleri (Bu yöntem genellikle değil geçersiz kılınır) görüntüsünü özelleştirmek için.|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateErrorTaskItem%2A>|<xref:Microsoft.VisualStudio.Package.DocumentTask>|Hata listesi görev listesinde işaretçileri desteklemek için; Özellikle, dosyayı açmayı ve hataya neden olan satır atlama ötesinde özellikler için destek.|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateMethodData%2A>|<xref:Microsoft.VisualStudio.Package.MethodData>|IntelliSense parametre bilgileri araç ipuçları görüntüsünü özelleştirmek için.|  
|<xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A>|<xref:Microsoft.VisualStudio.Package.CommentInfo>|Yorum kodu desteklemek için.|  
|<xref:Microsoft.VisualStudio.Package.Source.CreateAuthoringSink%2A>|<xref:Microsoft.VisualStudio.Package.AuthoringSink>|Ayrıştırma işlemi sırasında bilgileri toplamak için.|  
  
### <a name="in-the-authoringscope-class"></a>AuthoringScope sınıfında  
  
|Yöntem|Döndürülen sınıfı|Açıklama|  
|------------|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A>|<xref:Microsoft.VisualStudio.Package.Declarations>|Bildirimleri üyeleri veya türleri gibi bir listesini sağlar. Bu yöntem uygulanması gerekiyor ancak bir null değer döndürür. Bu yöntem, geçerli bir nesne döndürürse, nesne sürümünüz örneği olmalıdır <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı.|  
|<xref:Microsoft.VisualStudio.Package.AuthoringScope.GetMethods%2A>|<xref:Microsoft.VisualStudio.Package.Methods>|Yöntem imzaları listesi için belirli bir bağlam sağlar. Bu yöntem uygulanması gerekiyor ancak bir null değer döndürür. Bu yöntem, geçerli bir nesne döndürürse, nesne sürümünüz örneği olmalıdır <xref:Microsoft.VisualStudio.Package.Methods> sınıfı.|  
  
## <a name="language-service-images"></a>Dil hizmeti görüntüleri  
 Dil hizmeti genelinde kullanılacak simge listesi sağlamak için geçersiz kılma <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı ve dönüş bir <xref:System.Windows.Forms.ImageList> simgeleri içeren. Temel <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı varsayılan bir simge yükler. Simgeler gereken bu yerlerin tam resim dizinini belirtin olduğundan, kendi resim listesi düzenleme nasıl tamamen size bağlıdır.  
  
### <a name="images-used-in-intellisense-completion-lists"></a>IntelliSense tamamlanma listeleri kullanılan görüntüleri  
 IntelliSense tamamlanma listeleri için her öğe için resim dizinini belirtilen <xref:Microsoft.VisualStudio.Package.Declarations.GetGlyph%2A> yöntemi <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı bir görüntü dizini sağlamak istiyorsanız, geçersiz kılmanız gerekir. Döndürülen değer <xref:Microsoft.VisualStudio.Package.Declarations.GetGlyph%2A> yöntemdir için sağlanan resim listesi bir dizine <xref:Microsoft.VisualStudio.Package.CompletionSet> sınıfı oluşturucusu ve bu, aynı resim listesi döndürülen <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> (değiştirebileceğiniz hangi resim listesi sınıfı kullanılmaya <xref:Microsoft.VisualStudio.Package.CompletionSet> , geçersiz kılarsanız <xref:Microsoft.VisualStudio.Package.Source.CreateCompletionSet%2A> yönteminde <xref:Microsoft.VisualStudio.Package.Source> farklı resim listesi temin etmek için sınıf).  
  
### <a name="images-used-in-the-navigation-bar"></a>Gezinme çubuğunda kullanılan görüntüleri  
 **Gezinti çubuğu** türleri ve üyeleri listesini görüntüler ve kullanılan Hızlı gezinme simgeleri gösterebilir için. Bu simgeleri elde edilen <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı ve özel olarak geçersiz kılınamaz **gezinti çubuğu**. Birleşik giriş kutuları temsil eden listeleri doldurulduğunda birleşik giriş kutularında her bir öğe için kullanılan dizinlerini belirtilen <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars.OnSynchronizeDropdowns%2A> yönteminde <xref:Microsoft.VisualStudio.Package.TypeAndMemberDropdownBars> sınıfı (bkz [eski dil hizmetiGezintiçubuğundadesteği](../../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)). Bu görüntü dizinler şekilde genellikle sürümünüz aracılığıyla ayrıştırıcı alanından elde edilen <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı. Dizinler nasıl elde tamamen size bağlıdır.  
  
### <a name="images-used-in-the-error-list-task-window"></a>Hata listesi görev penceresinde kullanılan görüntüleri  
 Her <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi ayrıştırıcı (bkz [eski dil hizmeti Ayrıştırıcı ve tarayıcı](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)) hatayla karşılaşırsa ve bu hata geçirir <xref:Microsoft.VisualStudio.Package.AuthoringSink.AddError%2A> yönteminde <xref:Microsoft.VisualStudio.Package.AuthoringSink> sınıfı, bildirilenhata **Hata listesi** görev penceresi. Simge görev penceresinde görünür her bir öğe ile ilişkili olabilir ve bu simge, döndürülen aynı resim listesi geldiği <xref:Microsoft.VisualStudio.Package.LanguageService.GetImageList%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı. Varsayılan davranışı MPF sınıflarını, hata iletisiyle bir görüntü değil göstermektir. Ancak, bir sınıftan türetilen bu davranışı geçersiz kılabilirsiniz <xref:Microsoft.VisualStudio.Package.Source> sınıfı ve geçersiz kılma <xref:Microsoft.VisualStudio.Package.Source.CreateErrorTaskItem%2A> yöntemi. Bu yöntem, yeni oluşturduğunuz <xref:Microsoft.VisualStudio.Package.DocumentTask> nesnesi. Bu nesne döndürmeden önce kullanabilirsiniz <xref:Microsoft.VisualStudio.Shell.Task.ImageIndex%2A> özellikte <xref:Microsoft.VisualStudio.Package.DocumentTask> resim dizinini ayarlamak için nesne. Bu aşağıdaki örneğe benzer bir şey görünür. Unutmayın `TestIconImageIndex` tüm simgeleri listeler ve bu örnek için belirli bir sabit listesi. Dil hizmetinizi simgeleri tanımlamanın farklı bir şekilde olabilir.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    class TestSource : Source  
    {  
        public override DocumentTask CreateErrorTaskItem(  
            TextSpan          span,  
            string            filename,  
            string            message,  
            TastPriority      priority,  
            TaskCategory      category,  
            MARKERTYPE        markerType,  
            TaskErrorCategory errorCategory)  
        {  
            DocumentTask taskItem = base.CreateErrorTaskItem(  
                                           span,  
                                           filename,  
                                           message,  
                                           priority,  
                                           category,  
                                           markerType,  
                                           errorCategory);  
            if (errorCategory == TaskErrorCategory.Error)  
            {  
                taskItem.ImageIndex = TestIconImageIndex.Error;  
            }  
            return taskItem;  
        }  
    }  
}  
```  
  
## <a name="the-default-image-list-for-a-language-service"></a>Bir dil hizmeti için varsayılan resim listesi  
 Temel MPF dil hizmeti sınıflar ile sağlanan varsayılan görüntü liste daha yaygın dil öğeleri ile ilişkilendirilmiş simgeleri sayısını içerir. Bu simgeleri toplu genel, iç, arkadaş, korumalı, özel ve kısayol erişim kavramlarını karşılık gelen altı çeşitleri kümeler halinde düzenlenir. Örneğin, public, korumalı ya da özel olmasına bağlı olarak bir yöntem için farklı simgeleri olabilir.  
  
 Aşağıdaki numaralandırma her simge kümesi için tipik adları ve ilişkili dizini belirtir. Örneğin, sabit bağlı olarak, korumalı bir yöntem olarak için resim dizini belirleyebileceğiniz `(int)IconImageIndex.Method + (int)IconImageIndex.AccessProtected`. Bu numaralandırma istendiği adlarında değiştirebilirsiniz.  
  
```csharp  
public enum IconImageIndex  
        {  
            // access types  
            AccessPublic = 0,  
            AccessInternal = 1,  
            AccessFriend = 2,  
            AccessProtected = 3,  
            AccessPrivate = 4,  
            AccessShortcut = 5,  
  
            Base = 6,  
            // Each of the following icon type has 6 versions,  
            //corresponding to the access types  
            Class = Base + 0,  
            Constant = Base + 1,  
            Delegate = Base + 2,  
            Enumeration = Base + 3,  
            EnumMember = Base + 4,  
            Event = Base + 5,  
            Exception = Base + 6,  
            Field = Base + 7,  
            Interface = Base + 8,  
            Macro = Base + 9,  
            Map = Base + 10,  
            MapItem = Base + 11,  
            Method = Base + 12,  
            OverloadedMethod = Base + 13,  
            Module = Base + 14,  
            Namespace = Base + 15,  
            Operator = Base + 16,  
            Property = Base + 17,  
            Struct = Base + 18,  
            Template = Base + 19,  
            Typedef = Base + 20,  
            Type = Base + 21,  
            Union = Base + 22,  
            Variable = Base + 23,  
            ValueType = Base + 24,  
            Intrinsic = Base + 25,  
            JavaMethod = Base + 26,  
            JavaField = Base + 27,  
            JavaClass = Base + 28,  
            JavaNamespace = Base + 29,  
            JavaInterface = Base + 30,  
            // Miscellaneous icons with one icon for each type.  
            Error = 187,  
            GreyedClass = 188,  
            GreyedPrivateMethod = 189,  
            GreyedProtectedMethod = 190,  
            GreyedPublicMethod = 191,  
            BrowseResourceFile = 192,  
            Reference = 193,  
            Library = 194,  
            VBProject = 195,  
            VBWebProject = 196,  
            CSProject = 197,  
            CSWebProject = 198,  
            VB6Project = 199,  
            CPlusProject = 200,  
            Form = 201,  
            OpenFolder = 202,  
            ClosedFolder = 203,  
            Arrow = 204,  
            CSClass = 205,  
            Snippet = 206,  
            Keyword = 207,  
            Info = 208,  
            CallBrowserCall = 209,  
            CallBrowserCallRecursive = 210,  
            XMLEditor = 211,  
            VJProject = 212,  
            VJClass = 213,  
            ForwardedType = 214,  
            CallsTo = 215,  
            CallsFrom = 216,  
            Warning = 217,  
        }  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [Eski dil hizmetine genel bakış](../../extensibility/internals/legacy-language-service-overview.md)   
 [Eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md)   
 [Eski Dil Hizmeti Ayrıştırıcısı ve Tarayıcısı](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)