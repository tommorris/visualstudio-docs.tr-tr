---
title: Eski dil Service2 parametre bilgilerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense, Parameter Info tool tip
- language services [managed package framework], IntelliSense Parameter Info
- Parameter Info (IntelliSense), supporting in language services [managed package framework]
ms.assetid: a117365d-320d-4bb5-b61d-3e6457b8f6bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6aaf8ba9be9e16eeb979b0d64d3e80e8d70b564f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="parameter-info-in-a-legacy-language-service"></a>Eski dil hizmetindeki parametre bilgisi
IntelliSense parametre bilgisi, kullanıcı parametre listesi yazdığında bir yöntem imzası görüntüleyen bir araç ipucu başlangıç yöntemi parametre listesi için (genellikle açık parantez) karakteri ' dir. Her bir parametreyi girilir ve parametre ayırıcı (genellikle bir virgül) yazıldığından, araç ipucu sonraki parametrenin kalın olarak göstermek için güncelleştirilir.  
  
 Yönetilen paket framework (MPF) sınıfları parametre bilgisi araç ipucu yönetmek için destek sağlar. Ayrıştırıcı tespit parametresi Başlat parametre ardından, ve parametre son karakterler ve yöntem imzaları ve bunların ilişkili parametrelerin listesi sağlamalısınız gerekir.  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Daha fazla bilgi bulmak için bkz: [Düzenleyicisi ve dil Hizmetleri genişletme](../../extensibility/extending-the-editor-and-language-services.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
## <a name="implementation"></a>Uygulama  
 Ayrıştırıcının tetikleme değerini ayarlamalısınız <xref:Microsoft.VisualStudio.Package.TokenTriggers> bir parametre listesi başlangıç karakteri (genellikle açık parantez) bulduğunda ayarlayın. Ayarlaması gereken bir <xref:Microsoft.VisualStudio.Package.TokenTriggers> tetikleyen bir parametre ayırıcı (genellikle bir virgül) bulduğunda. Bu güncelleştirilmesi ve sonraki parametrenin kalın olarak göstermek bir parametre bilgisi araç ipucu neden olur. Ayrıştırıcının tetikleme değerini ayarlamalısınız <xref:Microsoft.VisualStudio.Package.TokenTriggers> olduğunda, parametre listesi bitiş karakteri (genellikle bir kapatma ayracı) bulur.  
  
 <xref:Microsoft.VisualStudio.Package.TokenTriggers> Tetikleyici değeri için bir çağrı başlatır <xref:Microsoft.VisualStudio.Package.Source.MethodTip%2A> sırayla çağırır yöntemi <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> yöntemi ayrıştırıcı bir ayrıştırma nedeni ile <xref:Microsoft.VisualStudio.Package.ParseReason>. Ayrıştırıcının parametre listesi başlamadan önce karakter tanımlayıcı bir tanınan bir yöntem adı olduğunu belirlerse, yöntem imzalarında eşleşen bir liste döndürür <xref:Microsoft.VisualStudio.Package.AuthoringScope> nesnesi. Hiçbir yöntemi imza bulunamadı, parametre bilgisi araç ipucu listedeki ilk imzayla görüntülenir. Bu araç ipucu imza birkaçını yazıldığında sonra güncelleştirilir. Parametre listesi son karakter yazıldığında parametre bilgisi araç ipucu görünümünden kaldırılır.  
  
> [!NOTE]
>  Parametre bilgisi araç ipucu düzgün biçimlendirildiğinden, özellikleri geçersiz kılmalısınız emin olmak için <xref:Microsoft.VisualStudio.Package.Methods> uygun karakterleri sağlamak için sınıf. Temel <xref:Microsoft.VisualStudio.Package.Methods> sınıfı varsayar C#-stil yöntem imzası. Bkz: <xref:Microsoft.VisualStudio.Package.Methods> nasıl bu yapılabilir Ayrıntılar için sınıf.  
  
## <a name="enabling-support-for-the-parameter-info"></a>Parametre bilgisi desteğini etkinleştirme  
 Parametre bilgisi araç ipuçları desteklemek için ayarlamalısınız `ShowCompletion` parametresinin adlı <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> için `true`. Bu kayıt defteri girdisinden değerini dil hizmeti okur <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> özelliği.  
  
 Ayrıca, <xref:Microsoft.VisualStudio.Package.LanguagePreferences.ParameterInformation%2A> özelliği ayarlanmalıdır `true` için gösterilecek parametre bilgisi araç ipucu.  
  
### <a name="example"></a>Örnek  
 Burada, parametre listesi karakter algılama ve uygun Tetikleyicileri ayarı basitleştirilmiş bir örnek verilmiştir. Bu örnek yalnızca tanım amaçlıdır. Tarayıcınız bir yöntem içerdiğini varsayar `GetNextToken` tanımlar ve bir metin satırından belirteçleri verir. Karakter sağ türü görür her kod örneği yalnızca Tetikleyiciler ayarlar.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
using Microsoft.VisualStudio.TextManager.Interop;  
  
namespace TestLanguagePackage  
{  
    public class TestScanner : IScanner  
    {  
        private Lexer lex;  
        private const char parameterListStartChar = '(';  
        private const char parameterListEndChar   = ')';  
        private const char parameterNextChar      = ',';  
  
        public bool ScanTokenAndProvideInfoAboutIt(TokenInfo tokenInfo,  
                                                   ref int state)  
        {  
            bool foundToken = false  
            string token = lex.GetNextToken();  
            if (token != null)  
            {  
                foundToken = true;  
                char c = token[0];  
                if (Char.IsPunctuation(c))  
                {  
                    tokenInfo.Type = TokenType.Operator;  
                    tokenInfo.Color = TokenColor.Keyword;  
                    tokenInfo.EndIndex = index;  
  
                    if (c == parameterListStartChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterStart;  
                    }  
                    else if (c == parameterListNextChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterNext;  
                    else if (c == parameterListEndChar)  
                    {  
                        tokenInfo.Trigger |= TokenTriggers.ParameterEnd;  
                    }  
                }  
            return foundToken;  
        }  
    }  
}  
```  
  
## <a name="supporting-the-parameter-info-tooltip-in-the-parser"></a>Parametre bilgisi araç ipucu ayrıştırıcısını destekleme  
 <xref:Microsoft.VisualStudio.Package.Source> Sınıfı yapacağı içeriğini hakkında bazı varsayımlar <xref:Microsoft.VisualStudio.Package.AuthoringScope> ve <xref:Microsoft.VisualStudio.Package.AuthoringSink> sınıfları parametre bilgisi araç ipucu görüntülenir ve güncelleştirilmiş.  
  
-   Ayrıştırıcının verilen <xref:Microsoft.VisualStudio.Package.ParseReason> parametre listesi başlangıç karakteri zaman yazıldığında.  
  
-   Verilen konumu <xref:Microsoft.VisualStudio.Package.ParseRequest> nesnesidir hemen parametre listesi başlattıktan sonra karakter. Ayrıştırıcının getirin ve bunları sürümünüz listesinde depolayan tüm yöntem bildirimleri adresinde imzalarını toplamanız gerekir <xref:Microsoft.VisualStudio.Package.AuthoringScope> nesnesi. Bu liste yöntem adını içeren yöntemi türü (veya dönüş türü) ve olası parametrelerin bir listesi. Bu liste, daha sonra yöntem imzası veya parametre bilgisi İpucunda görüntülenecek imzalar için aranır.  
  
 Ayrıştırıcı tarafından belirtilen satır sonra ayrıştırma gerekir <xref:Microsoft.VisualStudio.Package.ParseRequest> girilmesini yönteminin yanı sıra kullanıcı boyunca ne kadar adı toplamak için nesnesidir parametrelerini yazarak. Bu yöntemin adını geçirerek gerçekleştirilir <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartName%2A> yöntemi <xref:Microsoft.VisualStudio.Package.AuthoringSink> nesnesi ve ardından çağırma <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartParameters%2A> parametre listesi karakter başlattığınızda yöntemi ayrıştırılır, çağırma <xref:Microsoft.VisualStudio.Package.AuthoringSink.NextParameter%2A> yöntemi zaman parametre listesi sonraki karakteri ayrıştırılmış ve son olarak arama <xref:Microsoft.VisualStudio.Package.AuthoringSink.EndParameters%2A> parametre listesi son karakter ayrıştırıldığında yöntemi. Bu yöntem çağrılarının sonuçları tarafından kullanılan <xref:Microsoft.VisualStudio.Package.Source> parametre bilgisi araç ipucu uygun şekilde güncelleştirmek için sınıf.  
  
### <a name="example"></a>Örnek  
 Bir kullanıcı girebilir metin satırı aşağıda verilmiştir. Satırın aşağıdaki sayıları, hangi adımın (ayrıştırma taşır soldan sağa varsayılarak) satır bu konumda ayrıştırıcı tarafından gerçekleştirilecek gösterir. Burada satırından önce her şeyi zaten "testfunc" yöntem imzası dahil olmak üzere yöntemi imzaları çözümlenmemiş olduğunu varsayılır.  
  
```  
testfunc("a string",3);  
     ^^          ^ ^  
     12          3 4  
```  
  
 Ayrıştırıcının alır gereken adımları aşağıda özetlenen:  
  
1.  Ayrıştırıcı çağrıları <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartName%2A> "testfunc" metni ile.  
  
2.  Ayrıştırıcı çağrıları <xref:Microsoft.VisualStudio.Package.AuthoringSink.StartParameters%2A>.  
  
3.  Ayrıştırıcı çağrıları <xref:Microsoft.VisualStudio.Package.AuthoringSink.NextParameter%2A>.  
  
4.  Ayrıştırıcı çağrıları <xref:Microsoft.VisualStudio.Package.AuthoringSink.EndParameters%2A>.