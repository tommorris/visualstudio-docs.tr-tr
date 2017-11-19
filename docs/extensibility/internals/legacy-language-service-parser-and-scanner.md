---
title: "Eski dil hizmeti Ayrıştırıcı ve tarayıcı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsers, language services [managed package framework]
- language services [managed package framework], Parsers
ms.assetid: 1ac3de27-a23b-438d-9593-389e45839cfa
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 30453237dcd95607a4f3524f115d16bc1cf4859a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="legacy-language-service-parser-and-scanner"></a>Eski dil hizmeti Ayrıştırıcı ve tarayıcı
Ayrıştırıcının dili hizmet Kalp ' dir. Yönetilen paket Framework (MPF) dil sınıfları görüntülenen kodu hakkında bilgi seçmek için bir dil Çözümleyicisi gerektirir. Bir Ayrıştırıcı metin sözcük belirteçlere ayırır ve türü ve işlevleri tarafından konusu belirteçleri tanımlar.  
  
## <a name="discussion"></a>Tartışma  
 Bir C# yöntemi verilmiştir.  
  
```csharp  
namespace MyNamespace  
{  
    class MyClass  
    {  
        public void MyFunction(int arg1)  
        {  
            int var1 = arg1;  
        }  
    }  
}  
```  
  
 Bu örnekte, sözcük ve noktalama işaretlerini belirteçleridir. Tür belirteçleri aşağıdaki gibidir.  
  
|Belirteç adı|Belirteç türü|  
|----------------|----------------|  
|ad alanı, sınıf, ortak, void, int|Anahtar sözcüğü|  
|=|operator|  
|{ } ( ) ;|sınırlayıcı|  
|MyNamespace, MyClass, MyFunction, arg1, var1|tanımlayıcı|  
|MyNamespace|ad alanı|  
|MyClass|sınıf|  
|MyFunction|yöntemi|  
|arg1|parametre|  
|var1|Yerel değişken|  
  
 Ayrıştırıcının rol belirteçleri belirlemektir. Bazı belirteçleri birden fazla tür var. Ayrıştırıcının belirteçleri belirledi sonra dil hizmeti sözdizimi vurgulama gibi yararlı özellikleri, eşleşen küme parantezi sağlamak için bilgi ve IntelliSense işlemleri kullanabilirsiniz.  
  
## <a name="types-of-parsers"></a>Ayrıştırıcıları türleri  
 Bir dil hizmeti ayrıştırıcısı derleyici bir parçası olarak kullanılan bir Ayrıştırıcıyı ile aynı değil. Ancak, bu tür bir ayrıştırıcı derleyici ayrıştırıcı aynı şekilde bir tarayıcı ve bir Ayrıştırıcıyı kullanması gerekir.  
  
-   Bir tarayıcı belirteçleri türlerini tanımlamak için kullanılır. Bu bilgiler, sözdizimi vurgulama ve diğer işlemler, örneğin, tetikleyebilir belirteç türleri Ayraç eşleştirme hızlı bir şekilde tanımlamak için kullanılır. Bu tarayıcı tarafından temsil edilen <xref:Microsoft.VisualStudio.Package.IScanner> arabirimi.  
  
-   Bir Ayrıştırıcı işlevler ve belirteçleri kapsamını tanımlamak için kullanılır. Bu bilgiler IntelliSense işlemlerinde yöntemleri, değişkenleri, parametreler ve bildirimleri, gibi dil öğeleri tanımlamak ve üyeleri ve yöntem imzaları bağlamına dayalı listelerini sağlamak için kullanılır. Bu çözümleyici küme parantezleri ve parantez gibi eşleşen dil öğesi çiftlerini bulmak için de kullanılır. Bu çözümleyici üzerinden erişilen <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı.  
  
 Tarayıcı ve ayrıştırıcı dil hizmetiniz için nasıl uygulama size bağlıdır. Bazı kaynaklar kullanılabilir ayrıştırıcıları nasıl çalıştığını ve nasıl kendi ayrıştırıcı yazılacağını açıklar. Ayrıca, bazı ücretsiz ve ticari ürünleri kullanılabilir Yardım bir Ayrıştırıcıyı oluşturma.  
  
### <a name="the-parsesource-parser"></a>ParseSource ayrıştırıcı  
 (Burada belirteçleri yürütülebilir kod bazı biçimine dönüştürülür) derleyici bir parçası olarak kullanılan bir Ayrıştırıcıyı, bir dil hizmeti ayrıştırıcısı birçok farklı nedenlerle ve birçok farklı bağlamlarda çağrılabilir. Bu yaklaşımın nasıl uygulayacağınıza <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> sınıftır size kalmıştır. Göz önünde bulundurmanız önemlidir, <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi arka plan iş parçacığında adlı.  
  
> [!CAUTION]
>  <xref:Microsoft.VisualStudio.Package.ParseRequest> Yapısı için bir başvuru içeriyor <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> nesnesi. Bu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> nesne arka plan iş parçacığı içinde kullanılamaz. Aslında, temel MPF sınıfların çoğu arka plan iş parçacığı içinde kullanılamaz. Bunlar <xref:Microsoft.VisualStudio.Package.Source>, <xref:Microsoft.VisualStudio.Package.ViewFilter>, <xref:Microsoft.VisualStudio.Package.CodeWindowManager> sınıfları ve doğrudan veya dolaylı olarak görünümü ile iletişim kurar başka bir sınıf.  
  
 Bu çözümleyici genellikle çağrılır veya ne zaman ayrıştırma neden değerini bütün kaynak dosya ilk kez ayrıştırır <xref:Microsoft.VisualStudio.Package.ParseReason> verilir. Sonraki çağrılar <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi ayrıştırılmış kodu küçük bir bölümünü işler ve çok daha hızlı bir şekilde önceki tam ayrıştırma işlemi sonucunu kullanarak çalıştırılabilir. <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> Yöntemi iletişim kurar ayrıştırma işlemi sonuçlarını <xref:Microsoft.VisualStudio.Package.AuthoringSink> ve <xref:Microsoft.VisualStudio.Package.AuthoringScope> nesneleri. <xref:Microsoft.VisualStudio.Package.AuthoringSink> Nesnesi bilgi belirli ayrıştırma için bir neden, kuşak ya da parametre listeleri sahip yöntem imzaları eşleşen örneğin yayılma hakkında bilgi toplamak için kullanılır. <xref:Microsoft.VisualStudio.Package.AuthoringScope> Bildirimleri ve yöntem imzaları ve ayrıca destek koleksiyonları gitmek için Gelişmiş için Düzenle seçeneği sağlar (**Tanıma Git**, **bildirimine Git**, **gidin Başvuru**).  
  
### <a name="the-iscanner-scanner"></a>IScanner tarayıcı  
 Ayrıca uygulayan bir tarayıcı uygulamalıdır <xref:Microsoft.VisualStudio.Package.IScanner>. Ancak, bu tarayıcı satır satır temelinde çalıştığından <xref:Microsoft.VisualStudio.Package.Colorizer> sınıfı, onu uygulamak genellikle daha kolay. Her satırın başındaki MPF verir <xref:Microsoft.VisualStudio.Package.Colorizer> tarayıcıya geçirilen bir durum değişkeninin olarak kullanmak için bir değer sınıfı. Her satırın sonuna tarayıcı güncelleştirilen durumu değişkeni döndürür. Tarayıcı kaynak dosyasının en başından gerek kalmadan herhangi satırından ayrıştırma başlayabilmeniz MPF her satır için bu durum bilgileri önbelleğe alır. Bu hızlı tarama tek satırlık bir kullanıcıya hızlı geri bildirim sağlamak üzere Düzenleyicisi sağlar.  
  
## <a name="parsing-for-matching-braces"></a>Ayraç eşleştirme için ayrıştırma  
 Bu örnek, kullanıcının girdiği bir kapanış ayracı eşleştirmek için denetim akışı gösterilmektedir. Bu işlem, renklendirme için kullanılan tarayıcı türünü belirteç ve belirtecin eşleşen ayraç işlemi olup olmadığını tetikleyebilir belirlemek için de kullanılır. Tetikleyici bulunursa, <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi, eşleşen küme parantezi bulmak için çağrılır. Son olarak, iki küme ayraçları vurgulanır.  
  
 Küme ayraçları Tetikleyicileri adlarında kullanılır ve nedenleri ayrıştırma olsa bile, bu işlem için gerçek kaşlı sınırlı değildir. Eşleşen bir olması için belirttiğiniz eşleştirin karakterden oluşan herhangi bir çifti desteklenir. Örnekler (ve) \< ve >, ve [ve].  
  
 Dil hizmeti eşleşen küme ayraçları destekler varsayalım.  
  
1.  Kullanıcı bir kapanış kaşlı ayraç (}) yazar.  
  
2.  Kaynak dosyasında imlecin kuşak eklenir ve imleci tarafından Gelişmiş.  
  
3.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Yönteminde <xref:Microsoft.VisualStudio.Package.Source> sınıfı ile yazılan kapanış ayracı çağrılır.  
  
4.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Yöntem çağrılarını <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> yönteminde <xref:Microsoft.VisualStudio.Package.Source> geçerli imleç konumu hemen önce bir konumda belirteci alması için sınıf. Bu belirteç yazılan kapanış parantezi karşılık gelir).  
  
    1.  <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> Yöntem çağrılarını <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> yöntemi <xref:Microsoft.VisualStudio.Package.Colorizer> geçerli satırdaki tüm belirteçleri elde etmek için nesne.  
  
    2.  <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> Yöntem çağrılarını <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> yöntemi <xref:Microsoft.VisualStudio.Package.IScanner> geçerli satır metin içeren nesne.  
  
    3.  <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> Yöntemi art arda çağırır <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> yöntemi <xref:Microsoft.VisualStudio.Package.IScanner> tüm belirteçleri geçerli satırından toplamak için nesne.  
  
    4.  <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> Yöntemi çağrıları özel bir yöntem <xref:Microsoft.VisualStudio.Package.Source> istenilen içeren belirteci almak için sınıf ve belirteç listesi geçişlerinde elde <xref:Microsoft.VisualStudio.Package.Colorizer.GetLineInfo%2A> yöntemi.  
  
5.  <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Yöntemi için bir belirteç tetikleyici bayrağı görünür <xref:Microsoft.VisualStudio.Package.TokenTriggers> sunucudan döndürülen belirtecine <xref:Microsoft.VisualStudio.Package.Source.GetTokenInfo%2A> yöntemi; diğer bir deyişle, kapanış ayracı temsil eden belirteci).  
  
6.  Tetikleyici işareti varsa <xref:Microsoft.VisualStudio.Package.TokenTriggers> bulunan <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> yönteminde <xref:Microsoft.VisualStudio.Package.Source> sınıfı çağrılır.  
  
7.  <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> Yöntemi ayrıştırma neden değeri ile bir ayrıştırma işlemi başlatır <xref:Microsoft.VisualStudio.Package.ParseReason>. Bu işlem sonunda çağırır <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı. Zaman uyumsuz ayrıştırma etkinse, bu çağrı <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi arka plan iş parçacığında oluşur.  
  
8.  Ayrıştırma işlemi tamamlandığında, adlandırılmış bir iç tamamlama işleyicisi (geri çağırma yöntemi olarak da bilinir) `HandleMatchBracesResponse` olarak adlandırılır <xref:Microsoft.VisualStudio.Package.Source> sınıfı. Bu çağrı tarafından otomatik olarak yapılır <xref:Microsoft.VisualStudio.Package.LanguageService> temel sınıfı, ayrıştırıcı tarafından değil.  
  
9. `HandleMatchBracesResponse` Yöntemi alır yayılma listesini <xref:Microsoft.VisualStudio.Package.AuthoringSink> depolanan nesne <xref:Microsoft.VisualStudio.Package.ParseRequest> nesne. (Bir aralık olan bir <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> kaynak dosyasına bir dizi satırları ve karakterleri belirten yapısı.) Yayılma listesi genellikle her biri için açılış ve kapanış köşeli parantez iki yayılma içerir.  
  
10. `HandleBracesResponse` Yöntem çağrılarını <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A> yöntemi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> depolanan nesne <xref:Microsoft.VisualStudio.Package.ParseRequest> nesne. Verilen yayılma vurgular.  
  
11. Varsa <xref:Microsoft.VisualStudio.Package.LanguagePreferences> özelliği <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> etkin, `HandleBracesResponse` yöntemi tarafından eşleşen aralık çevrelenmiş ve bu aralık, ilk 80 karakter durum çubuğunda görüntüleyen metni alır. Bu en iyi şekilde çalışır <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntem eşleşen çift eşlik language öğesi içerir. Daha fazla bilgi için bkz: <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A> özelliği.  
  
12. Bitti.  
  
### <a name="summary"></a>Özet  
 Eşleşen küme parantezleri işlemi genellikle dil öğeleri basit çiftlerini sınırlıdır. Üçlü eşleşen gibi daha karmaşık öğeleri ("`if(...)`","`{`"ve"`}`", veya "`else`","`{`"ve"`}`"), bir sözcük tamamlama işleminin bir parçası vurgulanır. Örneğin, "başka" word tamamlandığında eşleşen "`if`" deyimi vurgulanan. Bir dizi olsaydı `if` / `else if` deyimleri, bunların tümünün vurgulanmış Ayraç eşleştirme olarak aynı mekanizmayı kullanarak. <xref:Microsoft.VisualStudio.Package.Source> Temel sınıf zaten destekler, aşağıdaki gibi: tarayıcı belirteci tetikleme değerini döndürmelidir <xref:Microsoft.VisualStudio.Package.TokenTriggers> tetikleyici değeri ile birlikte <xref:Microsoft.VisualStudio.Package.TokenTriggers> önce imleç konumu belirteci.  
  
 Daha fazla bilgi için bkz: [eşleşen ayraç eski dil hizmetindeki](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md).  
  
## <a name="parsing-for-colorization"></a>İçin renklendirme ayrıştırma  
 Kaynak kodu renklendirme basittir, yalnızca rengi belirteci ve dönüş türü hakkında bilgileri türünü tanımlayın. <xref:Microsoft.VisualStudio.Package.Colorizer> Sınıfı Düzenleyicisi ve tarayıcı renk her belirteç bilgilerini sağlamak için arasında aracı görevi görür. <xref:Microsoft.VisualStudio.Package.Colorizer> Sınıfını kullanan <xref:Microsoft.VisualStudio.Package.IScanner> nesnesi bir satır renklendirme yardımcı olması ve kaynak dosyasındaki tüm satırlar için durum bilgilerini toplamak için. MPF dil hizmeti sınıflardaki <xref:Microsoft.VisualStudio.Package.Colorizer> sınıfı tarayıcıyla kurduğundan geçersiz kılınacak sahip değil yalnızca aracılığıyla <xref:Microsoft.VisualStudio.Package.IScanner> arabirimi. Uygulayan nesnenin sağladığınız <xref:Microsoft.VisualStudio.Package.IScanner> kılarak arabirimi <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> yöntemi <xref:Microsoft.VisualStudio.Package.LanguageService> sınıfı.  
  
 <xref:Microsoft.VisualStudio.Package.IScanner> Tarayıcı kaynak kod satırı verilen <xref:Microsoft.VisualStudio.Package.IScanner.SetSource%2A> yöntemi. Çağrılar <xref:Microsoft.VisualStudio.Package.IScanner.ScanTokenAndProvideInfoAboutIt%2A> yöntemi yinelenen satır belirteçleri ulaşana kadar satırda sonraki belirteç elde edilir. Renklendirme için MPF tüm kaynak kodun bir dizi satır değerlendirir. Bu nedenle, tarayıcı adresinden çizgilerle gelen kaynağıyla başa kurabilmesi gerekir. Ayrıca, her satırın tarayıcıya herhangi bir zamanda iletilebilir ve tarayıcı yaklaşık taranacak satırından önce satırından durum değişkeninin alır tek garantisi yoktur.  
  
 <xref:Microsoft.VisualStudio.Package.Colorizer> Sınıfı belirteci Tetikleyicileri tanımlamak için de kullanılır. Belirli bir belirteç Sözcük tamamlama gibi daha karmaşık bir işlemi başlatabilir MPF tetikler söyleyin veya Ayraç eşleştirme. Böyle Tetikleyicileri tanımlama hızlı olması gerekir ve herhangi bir yere gerçekleşmesi gerekir çünkü tarayıcı bu görev için uygundur.  
  
 Daha fazla bilgi için bkz: [söz dizimi renklendirme eski dil hizmetindeki](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md).  
  
## <a name="parsing-for-functionality-and-scope"></a>İşlevsellik ve kapsam için ayrıştırma  
 İşlevsellik ve kapsam için ayrıştırma yalnızca karşılaşılan belirteçleri türlerini tanımlayan'den daha fazla çaba gerektirir. Yalnızca Belirtecin türü, aynı zamanda belirteç kullanılan işlevselliği tanımlamak ayrıştırıcı sahiptir. Örneğin, yalnızca bir adı bir tanımlayıcıdır ancak sizin dilinizde tanımlayıcı sınıfı, ad alanı, yöntemi veya bağlam bağlı olarak değişkeni adı olabilir. Belirtecin genel bir tür tanımlayıcı olabilir, ancak tanımlayıcısı nedir bağlı olarak ve tanımlandığı gibi diğer anlamları da sahip olabilirsiniz. Bu kimliği ayrıştırıcının Ayrıştırılmakta olan dili ile ilgili daha kapsamlı bilgi olmasını gerektirir. Bu yerdir <xref:Microsoft.VisualStudio.Package.AuthoringSink> sınıfı devreye girer. <xref:Microsoft.VisualStudio.Package.AuthoringSink> Sınıfı tanımlayıcıları, yöntemleri, (örneğin, küme parantezleri ve parantez) eşleşen dil çiftleri ve dil Üçlü hakkında bilgi toplar (dil çiftleri için benzer ancak bu üç bölüm, örneğin, "`foreach()`" "`{`"ve"`}`"). Ayrıca, kılabilirsiniz <xref:Microsoft.VisualStudio.Package.AuthoringSink> erken kesme noktalarını doğrulamada kullanılan ve böylece hata ayıklayıcı yüklenmesi gerekmez kod kimliği desteklemek için sınıf ve **otomobiller** yerel gösterir hata ayıklama penceresi değişkenleri ve parametreleri otomatik olarak ne zaman bir programı ayıklanacak ve uygun yerel değişkenleri ve parametreleri hata ayıklayıcı sunan listelenenlere tanımlamak için ayrıştırıcı gerektirir.  
  
 <xref:Microsoft.VisualStudio.Package.AuthoringSink> Nesne ayrıştırıcıya parçası olarak geçirilir <xref:Microsoft.VisualStudio.Package.ParseRequest> nesne ve yeni bir <xref:Microsoft.VisualStudio.Package.AuthoringSink> nesne her zaman oluşturulan yeni bir <xref:Microsoft.VisualStudio.Package.ParseRequest> nesnesi oluşturulur. Ayrıca, <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi döndürmelidir bir <xref:Microsoft.VisualStudio.Package.AuthoringScope> çeşitli IntelliSense işlemlerini işlemek için kullanılan nesne. <xref:Microsoft.VisualStudio.Package.AuthoringScope> Nesne tutar bildirimler için bir listesi ve bir liste yöntemleri için ya da hangi, ayrıştırma nedeni bağlı olarak doldurulur. <xref:Microsoft.VisualStudio.Package.AuthoringScope> Sınıfı uygulanan.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service1.md)   
 [Eski dil hizmetine genel bakış](../../extensibility/internals/legacy-language-service-overview.md)   
 [Eski dil hizmetinde söz dizimi renklendirme](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)   
 [Eski dil hizmet eşlemesi](../../extensibility/internals/brace-matching-in-a-legacy-language-service.md)