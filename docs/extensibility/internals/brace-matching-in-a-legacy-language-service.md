---
title: "Eski dil hizmet eşlemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- brace matching
- language services [managed package framework], brace matching
ms.assetid: 4e3d0a70-f22f-49dd-92d8-edf48ab62b52
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c496c65244f0ede0c3a6385f6cf1329479a17c22
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="brace-matching-in-a-legacy-language-service"></a>Eski dil hizmet eşlemesi
Ayraç eşleştirme birlikte parantez ve süslü ayraçlar gibi gerçekleşmesi gereken dil öğeleri izleyen Geliştirici yardımcı olur. Bir geliştirici bir kapanış ayracı girdiğinde, açılan parantez vurgulanır.  
  
 Çiftleri ve Üçlü adlı iki veya üç birlikte tekrarlanan öğelerin eşleştirebilirsiniz. Üçlü üç birlikte tekrarlanan öğeleri kümesidir. Örneğin, C# ' ta `foreach` deyimi bir Üçlü forms: "`foreach()`","`{`", ve "`}`". Kapatılan parantez yazıldığında tüm üç öğeler vurgulanır.  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Ayraç eşleştirme uygulamak için yeni yolu hakkında daha fazla bilgi için bkz: [izlenecek yol: görüntüleme eşleşen küme parantezleri](../../extensibility/walkthrough-displaying-matching-braces.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
 <xref:Microsoft.VisualStudio.Package.AuthoringSink> Sınıfı hem çiftleri destekler ve ile triples <xref:Microsoft.VisualStudio.Package.AuthoringSink.MatchPair%2A> ve <xref:Microsoft.VisualStudio.Package.AuthoringSink.MatchTriple%2A> yöntemleri.  
  
## <a name="implementation"></a>Uygulama  
 Dildeki tüm eşleşen öğeleri tanımlamak ve tüm eşleşen çiftlerini bulmak dil hizmeti gerekiyor. Bu uygulama tarafından genellikle gerçekleştirilir <xref:Microsoft.VisualStudio.Package.IScanner> eşleşen dil ve ardından kullanarak algılamak için <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> öğeleri eşleşecek şekilde yöntemi.  
  
 <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Satır simgeleştirilecek ve belirtecin şapka hemen önce geri dönmek için tarayıcı yöntemini çağırır. Bir dil öğesi çifti belirteci tetikleyici değerine ayarlayarak bulundu tarayıcı gösterir <xref:Microsoft.VisualStudio.Package.TokenTriggers> geçerli belirtecine. <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Yöntem çağrılarını <xref:Microsoft.VisualStudio.Package.Source.MatchBraces%2A> sırayla çağıran yöntemi <xref:Microsoft.VisualStudio.Package.LanguageService.BeginParse%2A> ayrıştırma neden değeri yöntemiyle <xref:Microsoft.VisualStudio.Package.ParseReason> eşleşen bir dil öğe bulunamadı. Eşleşen bir dil öğe bulunduğunda, her iki öğeler vurgulanır.  
  
 Nasıl ayraç yazarak parantezi vurgulama tetikler, tam bir açıklaması için "Örnek ayrıştırma işlemi" bölümüne bakın [eski dil hizmeti Ayrıştırıcı ve tarayıcı](../../extensibility/internals/legacy-language-service-parser-and-scanner.md).  
  
## <a name="enabling-support-for-brace-matching"></a>Ayraç eşleştirme için desteğini etkinleştirme  
 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> Özniteliği ayarlayabilirsiniz `MatchBraces`, `MatchBracesAtCaret`, ve `ShowMatchingBrace` adlandırılmış karşılık gelen özellik kümesinin parametreleri <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı. Dil tercihi özellikleri de kullanıcı tarafından ayarlanmış olabilir.  
  
|Kayıt defteri girdisi|Özellik|Açıklama|  
|--------------------|--------------|-----------------|  
|`MatchBraces`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableMatchBraces%2A>|Etkinleştirir Ayraç eşleştirme|  
|`MatchBracesAtCaret`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableMatchBracesAtCaret%2A>|Düzeltme işareti etkinleştirir eşleşen ayraç taşır.|  
|`ShowMatchingBrace`|<xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableShowMatchingBrace%2A>|Eşleşen küme parantezi vurgular.|  
  
## <a name="matching-conditional-statements"></a>Eşleşen koşullu deyimler  
 Koşullu deyimler gibi eşleşen `if`, `else if`, ve `else`, veya `#if`, `#elif`, `#else`, `#endif`, uyumlu ayırıcısı olarak aynı şekilde. Bir alt kümesi için <xref:Microsoft.VisualStudio.Package.AuthoringSink> sınıfı ve metin ekleyebilirsiniz bir yöntem yayılan öğeleri eşleşen iç dizi sınırlayıcıları yanı sıra sağlayın.  
  
## <a name="setting-the-trigger"></a>Tetikleyici ayarlama  
 Aşağıdaki örnek, eşleşen ayraç, süslü ayraçlar ve köşeli ayraçlar ve tetikleyici için tarayıcıda ayarı algılamak gösterilmektedir. <xref:Microsoft.VisualStudio.Package.Source.OnCommand%2A> Yöntemi <xref:Microsoft.VisualStudio.Package.Source> sınıfı tetikleyici algılar ve (Bu konudaki "eşleşme bulma" bölümüne bakın) eşleşen çifti bulmak için ayrıştırıcı çağırır. Bu örnek yalnızca tanım amaçlıdır. Tarayıcınız bir yöntem içerdiğini varsayar `GetNextToken` tanımlar ve bir metin satırından belirteçleri verir.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestScanner : IScanner  
    {  
        private const string braces = "()[]{}";  
        private Lexer lex;  
  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false;  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                foundToken = true;  
                char firstChar = token[0];  
                if (Char.IsPunctuation(firstChar) && token.Length > 0)  
                {  
                    if (braces.IndexOf(firstChar) != -1)  
                    {  
                        tokenInfo.Trigger = TokenTriggers.MatchBraces;  
                    }  
                }  
            }  
            return foundToken;  
        }  
```  
  
## <a name="matching-the-braces"></a>Ayraç eşleştirme  
 Dil öğeleri {}, () ve [] eşleşen ve bunların yayılma ekleme için basitleştirilmiş bir örnek şudur <xref:Microsoft.VisualStudio.Package.AuthoringSink> nesnesi. Bu yaklaşım, kaynak kodu ayrıştırma bir önerilen yaklaşım değildir; Bunu yalnızca tanım amaçlıdır.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class Parser  
    {  
         private IList<TextSpan[]> m_braces;  
         public IList<TextSpan[]> Braces  
         {  
             get { return m_braces; }  
         }  
         private void AddMatchingBraces(TextSpan braceSpan1, TextSpan braceSpan2)  
         {  
             if IsMatch(braceSpan1, braceSpan2)  
                 m_braces.Add(new TextSpan[] { braceSpan1, braceSpan2 });  
         }  
  
         private bool IsMatch(TextSpan braceSpan1, TextSpan braceSpan2)  
         {  
             //definition for matching here  
          }  
    }  
  
    public class TestLanguageService : LanguageService  
    {  
         Parser parser = new Parser();  
         Source source = (Source) this.GetSource(req.FileName);  
  
         private AuthoringScope ParseSource(ParseRequest req)  
         {  
             if (req.Sink.BraceMatching)  
             {  
                 if (req.Reason==ParseReason.MatchBraces)  
                 {  
                     foreach (TextSpan[] brace in parser.Braces)  
                     {  
                         req.Sink.MatchPair(brace[0], brace[1], 1);  
                     }  
                 }  
             }  
             return new TestAuthoringScope();  
         }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti özellikleri](../../extensibility/internals/legacy-language-service-features1.md)   
 [Eski Dil Hizmeti Ayrıştırıcısı ve Tarayıcısı](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)