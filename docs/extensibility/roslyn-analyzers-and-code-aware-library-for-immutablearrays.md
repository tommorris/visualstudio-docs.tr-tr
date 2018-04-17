---
title: Roslyn Çözümleyicileri ve ImmutableArrays için kod algılayan kitaplığı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 0b0afa22-3fca-4d59-908e-352464c1d903
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6ebafdd09e6fca0e1266c4eb03c4f6cb66554d06
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="roslyn-analyzers-and-code-aware-library-for-immutablearrays"></a>Roslyn Çözümleyicileri ve ImmutableArrays için kod algılayan kitaplığı

[.NET derleyici platformu](https://github.com/dotnet/roslyn) ("Roslyn"), kod algılayan kitaplıkları oluşturmanıza yardımcı olur.  Kod algılayan bir kitaplık, en iyi şekilde veya hatalarını önlemek için kullanabileceğiniz işlevsellik ve kitaplık kullanmanıza yardımcı olması için (Roslyn çözümleyiciler) araçları sağlar.  Bu konu kullanırken sık karşılaşılan yakalamak için gerçek dünya Roslyn Çözümleyicisi nasıl oluşturulacağını gösterir [System.Collections.Immutable](https://www.nuget.org/packages/System.Collections.Immutable) NuGet paketi.  Bu örnek ayrıca Çözümleyicisi tarafından bulunan bir kod sorunu için bir kod düzeltme sağlamak nasıl gösterir.  Kullanıcıları kod düzeltmeler Visual Studio ampul UI görür ve düzeltmesi kodunun otomatik olarak uygulayabilirsiniz.

## <a name="getting-started"></a>Başlarken

Bu örnek oluşturmak için aşağıdakilere sahip olmanız gerekir:

* Visual Studio 2015 (olmayan bir Express Edition) veya sonraki bir sürümü.  Ücretsiz kullanabileceğiniz [Visual Studio Community Edition](https://www.visualstudio.com/products/visual-studio-community-vs)
* [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  Ayrıca, Visual Studio yüklenirken, Visual Studio genişletilebilirlik araçları aynı anda SDK yüklemek için ortak Araçlar altındaki kontrol edebilirsiniz.  Visual Studio'nun zaten yüklediyseniz, aynı zamanda bu SDK ana menüsüne giderek yükleyebilirsiniz **dosya &#124; yeni &#124;proje...** , C# sol gezinti bölmesinde seçerek ve genişletilebilirlik seçme.  Seçtiğinizde "**Visual Studio genişletilebilirlik Araçları'nı yükleme**" içerik haritası proje şablonu, onu ister indirmenizi ve SDK'sını yükleyin.
* [.NET derleme Platformu ("Roslyn") SDK](http://aka.ms/roslynsdktemplates).  Ana menüsüne giderek bu SDK yükleyebilirsiniz **dosya &#124; yeni &#124; proje...** , seçme **C#** sol gezinti bölmesinde, ve ardından seçme **genişletilebilirlik**.  Seçtiğinizde "**.NET derleyici Platform SDK'sını indirin**" içerik haritası proje şablonu, onu ister indirmenizi ve SDK'sını yükleyin.  Bu SDK'sı içerir [Roslyn sözdizimi Görselleştirici](https://github.com/dotnet/roslyn/wiki/Syntax%20Visualizer).  Hangi kod modeli türleri şekil bu son derece yararlı aracı yardımcı olur, Çözümleyicisi'nde göz önünde bulundurmanız gerekenler.  Çözümleyici altyapı çağrılarını kodunuz için özel kod modeli türleri, böylece kodunuzu yalnızca gerekli olduğunda yürütür ve yalnızca ilgili kod çözümleme üzerinde odaklanabilirsiniz.

## <a name="whats-the-problem"></a>Sorun nedir?

Sağladığınız kitaplığı ile ImmutableArray düşünün (örneğin, <xref:System.Collections.Immutable.ImmutableArray%601?displayProperty=fullName>) destekler.  C# geliştiricileri .NET diziler deneyimiyle çok sayıda vardır.  Ancak, uygulamasında kullanılan ImmutableArrays ve iyileştirme teknikleri yapısı nedeniyle, C# Geliştirici intuitions bozuk kod yazmaya kullanıcıların kitaplığınızın aşağıda açıklandığı gibi neden.  Ayrıca, kullanıcılar için Visual Studio .NET ile kullanıldıkları kaliteyi değil çalıştırma zamana kadar bunların hatalarını görmezsiniz.

Kullanıcılar, aşağıdaki gibi kod yazma ile sahibisiniz:

```csharp
var a1 = new int[0];
Console.WriteLine("a1.Length = { 0}", a1.Length);
var a2 = new int[] { 1, 2, 3, 4, 5 };
Console.WriteLine("a2.Length = { 0}", a2.Length);
```

Sonraki kod satırlarını oturum doldurmak için boş diziler oluşturma ve koleksiyon Başlatıcısı sözdizimi kullanılarak C# geliştiricileri için çok benzer.  Ancak, aynı yazma bir ImmutableArray kodunu çalışma zamanında çöküyor:

```csharp
var b1 = new ImmutableArray<int>();
Console.WriteLine("b1.Length = { 0}", b1.Length);
var b2 = new ImmutableArray<int> { 1, 2, 3, 4, 5 };
Console.WriteLine("b2.Length = { 0}", b2.Length);
```

İlk hata ImmutableArray uygulaması'nın yapı temel alınan veri depolama alanı sarmalamak için nedeniyle kullanmaktır. Yapılar parametresiz oluşturucular olması gerekir böylece `default(T)` ifadeleri tüm yapılar dönebilirsiniz sıfır ya da null üyeleri.  Kod eriştiği `b1.Length`, ImmutableArray yapı içinde hiçbir temel alınan depolama dizisi olduğundan çalışma zamanında null başvuru hata yoktur.  Boş bir ImmutableArray oluşturmak için doğru yolu `ImmutableArray<int>.Empty`.

Koleksiyon başlatıcıları hatasıyla ImmutableArray.Add yöntemi her çağırdığında yeni örnekleri döndürdüğünden olur.  Yeni bir öğe eklediğinizde ImmutableArrays hiçbir zaman, değiştiğinden, performans nedenleriyle depolama ile önceden varolan bir ImmutableArray paylaşabilir) bir yeni ImmutableArray nesnesi (geri alın.  Çünkü `b2` çağırmadan önce ilk ImmutableArray işaret `Add()` beş kez `b2` ImmutableArray varsayılandır.  Uzunluk ayrıca çökme (Crash) bir null ile çağrısından başvuru hatası.  El ile Ekle çağırma kullanmaktır olmadan bir ImmutableArray başlatmak için doğru bir şekilde `ImmutableArray.CreateRange(new int[] {1, 2, 3, 4, 5})`.

## <a name="finding-relevant-syntax-node-types-to-trigger-your-analyzer"></a>İlgili sözdizimi düğüm türleri, Çözümleyicisi tetiklemek için bulma

 Çözümleyici oluşturmaya başlamak için önce ne tür bir SyntaxNode arayın gerek çıkışı şekil. Başlat menüsünde sözdizimi Görselleştirici **Görünüm &#124; diğer pencereler &#124; Roslyn sözdizimi Görselleştirici**.

Düzenleyicinin şapka bildiren satıra yerleştirin `b1`.  Sözdizimi Görselleştirici gösterir bulunduğunuz görürsünüz bir `LocalDeclarationStatement` sözdizimi ağacı düğümü.  Bu düğüm bir `VariableDeclaration`, sırayla sahip olduğu bir `VariableDeclarator`, sırayla sahip olduğu bir `EqualsValueClause`ve son olarak bir `ObjectCreationExpression`.  Düğümleri sözdizimi Görselleştirici ağacında tıkladığınızda, bu düğüm tarafından temsil edilen kod göstermek için sözdizimi Düzenleyicisi penceresinde vurgular.  C# dilbilgisi içinde kullanılan adları SyntaxNode alt türleri adlarıyla.

## <a name="creating-the-analyzer-project"></a>Çözümleyici projesi oluşturma

Ana menüden **dosya &#124; yeni &#124; proje...** .  İçinde **yeni proje** iletişim altında **C#** projeleri sol gezinti çubuğunda genişletilebilirlik seçin ve sağ bölmede seçin **Çözümleyicisi kod düzeltme ile** proje Şablon.  Bir ad girin ve iletişim kutusunda onaylayın.

Şablon DiagnosticAnalyzer.cs dosyasını açar.  Bu düzenleyici arabellek sekmesini seçin.  Bu dosyayı bir Çözümleyicisi sınıfı vardır (biçimlendirilmiş proje verdiğiniz adından), türetilen `DiagnosticAnalyzer` (Roslyn API türü).  Yeni sınıfınıza sahip bir `DiagnosticAnalyzerAttribute` , Çözümleyicisi bildirme C# dili için ilgili böylece derleyici bulur ve, Çözümleyicisi yükler.

```csharp
[DiagnosticAnalyzer(LanguageNames.CSharp)]
public class ImmutableArrayAnalyzerAnalyzer : DiagnosticAnalyzer
{}
```

C# kodunda hedefleyen Visual Basic kullanılarak bir çözümleyiciyi uygulayabilirsiniz ve tersi.  Çözümleyicisi bir dil veya her ikisini de hedefler seçmek için DiagnosticAnalyzerAttribute daha önemlidir.  Ayrıntılı Modelleme Dili gerektiren daha karmaşık çözümleyiciler yalnızca tek bir dil hedefleyebilirsiniz.  Çözümleyicisi Örneğin, yalnızca tür adları veya ortak üye adlarının işaretlerse, Visual Basic ve C# üzerinde Roslyn sunan ortak dil modeli kullanmak mümkün olabilir.  Örneğin, bir sınıf uyguladığını FxCop uyarır <xref:System.Runtime.Serialization.ISerializable>, ancak sınıf yok <xref:System.SerializableAttribute> özniteliği dilden bağımsızdır ve için hem Visual Basic ve C# kod çalışır.

## <a name="initalizing-the-analyzer"></a>Initalizing Çözümleyicisi

 Aşağı biraz haftasına `DiagnosticAnalyzer` görmek için sınıf `Initialize` yöntemi.  Derleyici bir Çözümleyicisi etkinleştirirken bu yöntemi çağırır.  Yöntem alır bir `AnalysisContext` bağlam bilgilerini almak ve analiz etmek istediğiniz kod tür için olaylar için geri aramaları kaydetme, Çözümleyicisi veren nesnesi.

```csharp
public override void Initialize(AnalysisContext context) {}

```

Bu bağlamda yöntemi ve türü"." yeni bir satır açın IntelliSense tamamlanma listesi görmek için.  Vardır birçok tamamlama listesinde görebilirsiniz `Register...` çeşitli olayları işlemek için yöntemleri.  Örneğin, ilk bir `RegisterCodeBlockAction`, kodunuz kodudur süslü ayraçlar arasında genellikle bir blok için geri çağrı.  Bir blok için kaydetme de geri kodunuzu bir alan, bir öznitelik için belirtilen değer ya da isteğe bağlı bir parametre değeri Başlatıcısı çağırır.

Başka bir örnek olarak `RegisterCompilationStartAction`, kodunuzu birçok konumdaki durumunu toplamak gerektiğinde, yararlı olan bir derleme başlangıcında geri çağrı.  Bir veri yapısı söyleyin, kullanıldığında, tüm sembolleri toplamak için oluşturabilir ve sizin Çözümleyicisi geri bazı sözdizimi veya simge, her çağrıldığında, veri yapısında her konumu hakkında bilgi kaydedebilirsiniz.  Derleme bitiş nedeniyle geri adlandırılırlar, kaydettiğiniz, örneğin, kod kullanan her birinden hangi simgeleri bildirmek için tüm konumların çözümleyebilirsiniz `using` deyimi.

Kullanarak **sözdizimi Görselleştirici**, derleyici bir ObjectCreationExpression işlerken çağrılacak istediğiniz öğrendiniz.  Geri çağırma ayarlamak için bu kodu kullanın:

```csharp
context.RegisterSyntaxNodeAction(c => AnalyzeObjectCreation(c),
                                 SyntaxKind.ObjectCreationExpression);
```

Bir sözdizimi düğümü ve filtre yalnızca nesne oluşturma sözdizimi düğümleri için kaydolun.  Kurala göre Çözümleyicisi yazarlar çözümleyiciler durum bilgisiz tutmanıza yardımcı olan eylemler kaydederken bir lambda kullanın.  Visual Studio özelliğini kullanabilirsiniz **kullanımından Oluştur** oluşturmak için `AnalyzeObjectCreation` yöntemi.  Bu bağlam parametresi doğru türde sizin için çok oluşturur.

## <a name="setting-properties-for-users-of-your-analyzer"></a>Kullanıcılar, çözümleyicisinin özelliklerini ayarlama

Visual STUDİO'da uygun şekilde, Çözümleyicisi görünür böylece arayın ve kod, Çözümleyicisi tanımlamak için aşağıdaki satırı değiştirin:

```csharp
internal const string Category = "Naming";
```

Değişiklik `"Naming"` için `"API Guidance"`.

Sonraki bulup açın `Resources.resx` kullanarak proje dosyasını **Çözüm Gezgini**.  Açıklama Analyzer, başlık, vb. için koyabilirsiniz.  Tüm bu değeri değiştirebilirsiniz `"Don't use ImmutableArray<T> constructor"` şimdilik.  Dize, dize ({0}, {1}, vb.), değişkenlerinde biçimlendirme koyabilirsiniz ve çağırdığınızda sonraki `Diagnostic.Create()`, size sağlayabilir bir `params` geçirilecek bağımsız değişkenler dizisi.

## <a name="analyzing-an-object-creation-expression"></a>Bir nesne oluşturma ifadesi analiz etme

`AnalyzeObjectCreation` Yöntemi farklı türde bir kod Çözümleyicisi çerçevesi tarafından sağlanan bağlamını alır.  Initialize yöntemin `AnalysisContext` , Çözümleyicisi ayarlamak için eylem geri aramaları kaydetme olanak tanır.  `SyntaxNodeAnalysisContext`, Örneğin, bir `CancellationToken` , geçici geçirebilirsiniz.  Bir kullanıcı Düzenleyicisi'nde yazarak başlarsa, Roslyn çalışmalarınızı kaydedin ve performansı artırmak için çalışan çözümleyiciler iptal eder.  Başka bir örnek olarak, bu bağlamda nesne oluşturma sözdizimi düğümü döndüren bir düğüm özelliği vardır.

Sözdizimi düğümü eylem filtre türü varsayabilirsiniz düğümü alın:

```csharp
var objectCreation = (ObjectCreationExpressionSyntax)context.Node;
```

### <a name="launching-visual-studio-with-your-analyzer-the-first-time"></a>Visual Studio Analyzer, ilk kez ile başlatma

Derleme ve, Çözümleyicisi yürütme Visual Studio'yu başlatın (basın **F5**).  Başlangıç projesi olarak çünkü **Çözüm Gezgini** kod derlemeleriniz kodunuzu ve bir VSIX çalıştıran VSIX proje ve Visual Studio yüklü o VSIX ile başlatır.  Bu şekilde Visual Studio başlattığında, böylece ana kullanımınız Visual Studio test örnekleri tarafından çözümleyiciler oluşturulurken etkilenmez ayrı kayıt defteri kovanı ile başlatır.  Bu şekilde başlatma ilk kez Visual Studio birkaç başlatmaları olduğunda, önce Visual Studio yüklendikten sonra başlatılan için benzer yapar.

Bir konsol projesi oluşturun ve ardından konsol uygulamaları ana yönteminizin içine dizi kodu girin:

```csharp
var b1 = new ImmutableArray<int>();
Console.WriteLine("b1.Length = {0}", b1.Length);
var b2 = new ImmutableArray<int> { 1, 2, 3, 4, 5 };
Console.WriteLine("b2.Length = {0}", b2.Length);
```

Koduyla satırları `ImmutableArray` değişmez NuGet paketi alma ve eklemeniz gerekir çünkü dalgalı çizgiler sahip bir `using` kodunuzu ifadesine.  Proje düğümüne sağ işaretçi düğmesine basın **Çözüm Gezgini** ve **NuGet paketlerini Yönet...** .  NuGet Yöneticisi'nde, arama kutusuna "Immutable" ve "System.Collections.Immutable" öğesini seçin ("Microsoft.Bcl.Immutable" seçmeyin) sol bölmede ve sağ bölmede yükle düğmesine basın.  Paket yükleme proje başvuruları için bir başvuru ekler.

Kırmızı dalgalı çizgiler altında görmeye devam `ImmutableArray`, bu nedenle bu tanımlayıcısı ve basın düzeltme işareti koyun **CTRL +.** önerilen düzeltme menüsü getirmek ve uygun eklemek için seçin (nokta) `using` deyimi.

**Tümünü Kaydet ve Kapat** devam etmek için temiz bir duruma yerleştirmek için Visual Studio şimdi için ikinci bir örneğini.

## <a name="finishing-the-analyzer-using-edit-and-continue"></a>Düzenle ve devam et Çözümleyicisi kullanarak tamamlama

Visual Studio'nun ilk örneği, başında bir kesme noktası belirleyerek, `AnalyzeObjectCreation` basarak yöntemi **F9** ilk satırda düzeltme işareti ile.

Çözümleyicisi ile yeniden başlatma **F5**ve Visual Studio in ikinci örneğini son zamanı oluşturduğunuz konsol uygulamanızı yeniden açın.

Çünkü Roslyn derleyici bir nesne oluşturma ifadesi gördünüz ve, çözümleyicisine adlı Visual Studio'nun ilk örneği kesme noktasındaki dönün.

**Nesne oluşturma düğümü alın.** Ayarlar hattı üzerinden adım `objectCreation` basarak değişken **F10**hem de **komut penceresi** ifade değerlendirme `"objectCreation.ToString()"`.  Değişkeni işaret sözdizimi düğümü kod olup olmadığını `"new ImmutableArray<int>()"`, yalnızca ne aradığınız.

**ImmutableArray alın < T\> tür nesnesi.** Oluşturulan türü ImmutableArray olup olmadığını denetlemek gerekir.  İlk olarak, bu tür temsil eden nesnesini alın.  Tam olarak sağ türüne sahip ve ToString() dizeden karşılaştırmak yok emin olmak için anlam modeli kullanarak türleri denetleyin.  Aşağıdaki işlevi sonunda kod satırını girin:

```csharp
var immutableArrayOfTType =
    context.SemanticModel
           .Compilation
           .GetTypeByMetadataName("System.Collections.Immutable.ImmutableArray`1");
```

Genel türler backquotes (') ile meta verileri ve genel parametreler sayısını belirtin.  Görüyor musunuz nedenle "... ImmutableArray\<T > "meta veri adı.

Anlam modeli yararlı pek çok sembolleri, veri akışı, değişken ömrü vb. hakkında sorular sormak olanak tanıyan üzerindeki sahiptir.  Roslyn sözdizimi düğümleri anlam modeli çeşitli mühendislik nedenlerle (modelleme hatalı kod, vb. performans,.) ayırır.  Doğru karşılaştırma için başvurular içinde yer alan bilgileri aramak için derleme modeli istiyor.

Sarı yürütme işaretçi Düzenleyicisi penceresinin sol tarafta sürükleyebilirsiniz.  Ayarlar satır kadar sürükleyin `objectCreation` değişkeni ve kod kullanarak, yeni bir satırla Adımlama **F10**.  Fare işaretçisini değişkeninden getirirseniz `immutableArrayOfType`, biz türünü tam anlamsal modelde bulunan bakın.

**Nesne oluşturma ifadenin türünü alır.** "Type" Bu makalede birkaç şekilde kullanılır, ancak "Yeni Foo" olup olmadığını yani ifadesi Foo modelinin almanız gereken.  ImmutableArray olup olmadığını görmek için nesne oluşturma ifadesi türü almanız gereken\<T > türü.  Anlam modeli yeniden nesne oluşturma ifadesinde tür simgesi (ImmutableArray) için Sembol bilgilerini almak için kullanın.  Aşağıdaki işlevi sonunda kod satırını girin:

```csharp
var symbolInfo = context.SemanticModel.GetSymbolInfo(objectCreation.Type).Symbol as INamedTypeSymbol;
```

Düzenleyici arabellekleri eksik veya hatalı kodda işlemek, Çözümleyicisi gerektiği için (örneğin, eksik bir `using` deyimi), için denetlemelisiniz `symbolInfo` olan `null`.  Analiz tamamlamak için Sembol bilgileri nesneden bir adlandırılmış türü (INamedTypeSymbol) almanız gerekir.

**Türleri karşılaştırın.** Açık genel tür arıyoruz için t yoktur ve kodda türü somut genel bir tür olduğundan, türüne (bir açık genel türünden) oluşturulan için Sembol bilgileri sorgulamak ve bu sonucu ile karşılaştırmak `immutableArrayOfTType`.  Yönteminin sonuna aşağıdaki girin:

```csharp
if (symbolInfo != null &&
    symbolInfo.ConstructedFrom.Equals(immutableArrayOfTType))
{}
```

**Tanılama raporu.** Tanı raporlama oldukça kolaydır.  İçin önce Initialize yöntemini tanımlanan proje şablonu oluşturduğunuz kural kullanın.  Bu durum kodu bir hata olduğundan, değiştirmek için kural başlatılmış satır değiştirebilirsiniz `DiagnosticSeverity.Warning` (yeşil dalgalı) ile `DiagnosticSeverity.Error` (kırmızı dalgalı).  Gözden geçirme başlangıcı yakınında düzenlenebilir kaynaklardan gelen kuralı kalan başlatır.  Nesne oluşturma expresssion's tür belirtimi konumudur dalgalı konumunu rapor gerekir.  Bu kodu girin `if` engelle:

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, objectCreation.Type.GetLocation()));
```

İşlevinizi (belki farklı şekilde biçimlendirilmiş) aşağıdaki gibi görünmelidir:

```csharp
private void AnalyzeObjectCreation(SyntaxNodeAnalysisContext context)
{
    var objectCreation = (ObjectCreationExpressionSyntax)context.Node;
    var immutableArrayOfTType =
        context.SemanticModel
               .Compilation
               .GetTypeByMetadataName(
                   "System.Collections.Immutable.ImmutableArray`1");
    var symbolInfo = context.SemanticModel.GetSymbolInfo(objectCreation.Type).Symbol as
        INamedTypeSymbol;
    if (symbolInfo != null &&
        symbolInfo.ConstructedFrom.Equals(immutableArrayOfTType))
    {
        context.ReportDiagnostic(
            Diagnostic.Create(Rule, objectCreation.Type.GetLocation()));
    }
}
```

Kesme noktası Çözümleyicisi bkz (ve Visual Studio ilk örneğine döndürmeyi kesmesine böylece) kaldırın.  Yürütme işaretçiyi yöntemi ve tuşuna başlangıcına sürükleyin **F5** yürütme devam etmek için.  Visual Studio ikinci örneğine geçiş yaptığınızda, derleyici kodunu yeniden inceleme başlatılır ve sizin çözümleyicisine çağırır.  Dalgalı altında görebilirsiniz `ImmutableType<int>`.

## <a name="adding-a-code-fix-for-the-code-issue"></a>Kod sorunu için "Kod Düzelt" ekleme

Başlamadan önce Visual Studio ikinci bir örneğini kapatın ve hizmetin ilk örneği (burada Çözümleyicisi geliştirdiğiniz) Visual Studio hata ayıklamayı durdurun.

**Yeni bir sınıf ekleyin.** Çözüm Gezgini'nde, proje düğümüne (sağ işaretçi düğmesi) kısayol menüsünü kullanın ve yeni bir öğe eklemek için seçin.  Adlı bir sınıf ekleyin `BuildCodeFixProvider`.  Bu sınıf türetin gerekiyor `CodeFixProvider`, ve kullanmanız gerekecektir **CTRL +.** doğru ekler kod düzeltme çağrılacak (nokta) `using` deyimi.  Bu sınıf ayrıca ile Açıklama gerekir `ExportCodeFixProvider` özniteliği ve eklemeniz gerekiyor bir `using` çözümlemek için deyimi `LanguageNames` enum.  Aşağıdaki kodda sınıf dosyasıyla olmalıdır:

```csharp
using Microsoft.CodeAnalysis;
using Microsoft.CodeAnalysis.CodeFixes;

namespace ImmutableArrayAnalyzer
{
    [ExportCodeFixProvider(LanguageNames.CSharp)]
    class BuildCodeFixProvider : CodeFixProvider
    {}

```

**Saplama çıkışı üyeleri türetilmiş.** Şimdi, tanımlayıcıda düzenleyicisinin düzeltme işareti koyun `CodeFixProvider` ve basın **CTRL +.** (Bu Özet temel sınıf uygulamasını kullanıma saplama için dönemi).  Bu özellik ve yöntemi sizin için oluşturur.

**Özellik uygulayın.** Doldurmak `FixableDiagnosticIds` özelliğin `get` aşağıdaki kodla gövdesi:

```csharp
return ImmutableArray.Create(ImmutableArrayAnalyzerAnalyzer.DiagnosticId);
```

Roslyn tanılama bir araya getirir ve yalnızca dizeler şunlardır: Bu tanımlayıcılar eşleştirerek giderir.  Proje şablonu tanılama kimliği sizin için oluşturulur ve bunu değiştirmek ücretsizdir.  Özellik kodda yalnızca Çözümleyicisi sınıfından Kimliğini döndürür.

**RegisterCodeFixAsync yöntemi bir bağlamı alır.** Bağlam kod düzeltme için birden çok tanılama uygulayabilir veya bir kod satırında birden çok sorun olabilir çünkü önemlidir.  "Bağlamı." yazarsanız, yöntemin gövdesine IntelliSense tamamlanma listesi bazı yararlı üyeleri gösterir.  Bir şey düzeltme iptal etmek isteyip istemediğini görmek için kontrol edebilirsiniz CancellationToken üyesi yok.  Çok sayıda kullanışlı üyeleri olan ve proje ve çözüm modeli nesnelere alabilmenizi sağlar belge üyesi yok.  Başlangıç aralık bir üye yoktur ve ne zaman tanı raporlanacağını kod konumunun sonuna belirtilmiş.

**Zaman uyumsuz olması yöntemi olun.** Yapmanız gereken ilk şey oluşturulan yöntem bildirimi olacak şekilde düzeltin bir `async` yöntemi.  Soyut bir sınıf uygulama stubbing için kod düzeltme içermeyen `async` anahtar sözcüğü yöntem olsa bile bir `Task`.

**Sözdizimi ağacı kök alın.** Yeni bir sözdizimi ağacı değişikliklerle üretmek için ihtiyacınız kodunu değiştirmek için kod düzeltme yapar.  Gereksinim duyduğunuz `Document` çağırmak için bağlamından `GetSyntaxRootAsync`.  Bu, büyük olasılıkla diskten dosya alma, ayrıştırma ve Roslyn kod modeli için derleme çeşitli sözdizimi ağacı almak için bilinmeyen iş olduğundan bir zaman uyumsuz yöntemidir.  Visual Studio kullanıcı arabirimini kullanarak hangi bu süre boyunca yanıt olmalıdır `async` sağlar.  Yöntemindeki kod satırı aşağıdaki satırla değiştirin:

```csharp
var root = await context.Document
                        .GetSyntaxRootAsync(context.CancellationToken);
```

**Sorunu düğümü bulunamıyor.** Bağlamın aralık, ancak değiştirmek zorunda kodu olmayabilir Bul düğümü geçirin.  Bildirilen tanılama aralık türü tanımlayıcısı (burada dalgalı ait) yalnızca sağlanan. ancak tüm nesne oluşturma ifadesi değiştirmeniz gerekiyor dahil olmak üzere `new` anahtar sözcüğü başında ve sonunda parantez.  Aşağıdaki kodu yönteminize ekleyin (ve **CTRL +.** eklemek için bir `using` bildirimi `ObjectCreationExpressionSyntax`):

```csharp
var objectCreation = root.FindNode(context.Span)
                         .FirstAncestorOrSelf<ObjectCreationExpressionSyntax>();
```

**Ampul UI, kod düzeltme kaydedin.** Kod düzeltme kaydederken Roslyn UI Visual Studio ampul otomatik olarak takılan.  Son kullanıcılar, kullanabilecekleri görürsünüz **CTRL +.** (süre), Çözümleyicisi bozuk squiggles zaman `ImmutableArray<T>` Oluşturucusu kullanın.  Bir sorun olduğunda kod düzeltme sağlayıcınız yalnızca çalıştırdığından, aradığınız nesne oluşturma deyimine sahip varsayabilirsiniz.  Bağlam parametresinden sonuna aşağıdaki kodu ekleyerek yeni kod düzeltme kaydedebilirsiniz `RegisterCodeFixAsync` yöntemi:

```csharp
context.RegisterCodeFix(
            CodeAction.Create("Use ImmutableArray<T>.Empty",
                              c => ChangeToImmutableArrayEmpty(objectCreation,
                                                               context.Document,
                                                               c)),
            context.Diagnostics[0]);
```

Düzenleyicinin şapka tanımlayıcıda yerleştirmek gereken `CodeAction`, ardından **CTRL +.** uygun eklemek için (nokta) `using` bu türü bildirimi.

Düzenleyicinin şapka yerleştirin `ChangeToImmutableArrayEmpty` tanımlayıcısı ve kullanım **CTRL +.** Bu yöntem saplama yeniden oluşturmak için.

Eklediğiniz son Bu kod parçacığını kod düzeltme geçirerek kaydeder bir `CodeAction` ve sorun bulundu tür tanılama kimliği.  Bu örnekte, olmadığından tek bu kodu sağlar tanılama kimliği giderir tanılama kimlikleri dizisinin ilk öğesi geçirmeniz yeterlidir.  Oluşturduğunuzda `CodeAction`, ampul UI kod düzeltme açıklaması kullanması gereken metin geçirin.  Ayrıca bir CancellationToken alan ve yeni bir belge döndüren bir işlev geçirdiğiniz.  Yeni belge çağırır düzeltme kodunuzu içeren yeni bir sözdizimi ağacı sahip `ImmutableArray.Empty`.  Bu kod parçacığını bir lambda kullanır, böylece nesne yaratımı düğümü ve bağlamın belge kapatabilirsiniz.

**Yeni bir sözdizimi ağacı oluşturun.** İçinde `ChangeToImmutableArrayEmpty` yöntemi daha önce oluşturulan, saplama kod satırını girin: `ImmutableArray<int>.Empty;`.  Sözdizimi Görselleştirici araç penceresi yeniden görüntülediğinizde, bu söz dizimini SimpleMemberAccessExpression düğümü olduğunu görebilirsiniz.  Bu yöntem oluşturmak ve yeni bir belgede dönmek gerekli olmasıdır.

İlk değişiklik `ChangeToImmutableArrayEmpty` eklemektir `async` önce `Task<Document>` kod oluşturucuları yöntemi zaman uyumsuz olmalıdır varsayın yapılamıyor çünkü.

Yönteminizi aşağıdakine benzer şekilde, aşağıdaki kod ile gövde doldurun:

```csharp
private async Task<Document> ChangeToImmutableArrayEmpty(
    ObjectCreationExpressionSyntax objectCreation, Document document,
    CancellationToken c)
{
    var generator = SyntaxGenerator.GetGenerator(document);
    var memberAccess =
        generator.MemberAccessExpression(objectCreation.Type, "Empty");
    var oldRoot = await document.GetSyntaxRootAsync(c);
    var newRoot = oldRoot.ReplaceNode(objectCreation, memberAccess);
    return document.WithSyntaxRoot(newRoot);
}
```

Düzenleyicinin düzeltme işareti koyun gerekecek `SyntaxGenerator` tanımlayıcısı ve kullanım **CTRL +.** uygun eklemek için (nokta) `using` bu türü bildirimi.

Bu kodu kullanır `SyntaxGenerator`, yeni kod oluşturma için çok kullanışlı bir tür olduğu.  Belge için bir oluşturucuyu alma kod sorunu sahip olduktan sonra `ChangeToImmutableArrayEmpty` çağrıları `MemberAccessExpression`istiyoruz erişmek için üye olan bir tür geçirme ve üyenin adı bir dize olarak geçirme.

Ardından, belgenin kökü yöntemi getirir ve bu genel durumda rasgele iş içerebildiğinden, kodu bu çağrıyı bekler ve iptal belirteci geçirir.  Roslyn kodu modelleri .NET dizesiyle çalışma gibi değişmez; dize güncelleştirdiğinizde, yeni bir dize nesnesi iade alırsınız.  Çağırdığınızda `ReplaceNode`, yeni bir kök düğümü ulaşırsınız.  Sözdizimi ağacı çoğunu paylaşılan (sabit olması nedeniyle), ancak `objectCreation` düğümü ile değiştirilir `memberAccess` sözdizimi ağacı kök kadar tüm üst düğümlerin yanı sıra, düğüm.

## <a name="trying-your-code-fix"></a>Kod düzeltme çalışıyor

Şimdi basabilirsiniz **F5** Visual Studio ikinci bir kopyası, Çözümleyicisi yürütülecek.  Önce kullanılan konsol projesini açın.  Artık, yeni nesne oluşturma ifadesi için olduğu görünür ampul görmelisiniz `ImmutableArray<int>`.  Basarsanız **CTRL +.** (nokta), ardından düzeltme kodunuzu görür ve ampul UI otomatik olarak oluşturulan kodu fark önizlemede görürsünüz.  Roslyn sizin için oluşturur.

**Pro İpucu:** Visual Studio, ikinci bir örneğini başlatın ve kod düzeltmeyle ampul görmüyorum durumunda Visual Studio bileşen önbelleğini temizlemek gerekebilir.  Önbellek Temizleme Visual Studio sonra en son bileşeniniz seçmeniz gerekir böylece bileşenleri yeniden incelemek için Visual Studio zorlar.  İlk olarak, Visual Studio ikinci örneğini kapatın.  Ardından Windows Gezgini'nde, kullanıcı dizinine gidin (c:\users\\< UserID\>) ve AppData\Local\Microsoft\VisualStudio\14.0Roslyn Bul\\.  Bu dizinde ComponentModelCache alt dizini silin.  Visual Studio ile sürüme "14" değişir.

## <a name="talk-video-and-finish-code-project"></a>Konuşma Video ve bitiş kodu projesi

Bu örnek geliştirilen ve ele alınan görebilirsiniz daha ayrıntılı olarak [Bu konuşma](http://channel9.msdn.com/events/Build/2015/3-725).  Konuşma çalışma Çözümleyicisi gösterir ve oluşturma sürecinde size yardımcı olur.

Tüm tamamlanan kodu görebilirsiniz [burada](https://github.com/DustinCampbell/CoreFxAnalyzers/tree/master/Source/CoreFxAnalyzers).  Alt klasörleri DoNotUseImmutableArrayCollectionInitializer ve DoNotUseImmutableArrayCtor sorunları ve Visual Studio ampul içinde UI görünmesini kod düzeltmeler uygulayan bir C# dosyası bulmak için bir C# dosyasına sahip.  Not, tamamlanmış koduna sahip ImmutableArray getirme önlemek için biraz daha fazla soyutlama\<T > Nesne tekrar tekrar yazın.  İç içe geçmiş kayıtlı Eylemler bağlamında kullanılabilir bir tür nesneyi kaydetmek için kullandığı her alt Eylemler (nesne oluşturma çözümlemek ve koleksiyon başlatmaları analiz) yürütün.

## <a name="see-also"></a>Ayrıca Bkz.

* [\\\Build 2015 konuşması](http://channel9.msdn.com/events/Build/2015/3-725)
* [Tamamlanan kodu github'da](https://github.com/DustinCampbell/CoreFxAnalyzers/tree/master/Source/CoreFxAnalyzers)
* [Üç tür çözümleyiciler gruplandırılır github'da çeşitli örnekler](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)
* [Diğer belgeler GitHub OSS sitesinde](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
* [Github'da Roslyn çözümleyiciler ile uygulanan FxCop kuralları](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)
