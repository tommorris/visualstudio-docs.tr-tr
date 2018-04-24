---
title: 'CA3076: Güvensiz XSLT komut dosyası yürütme'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c918f3a69fcafd751dad61b5291db3b891a4ccf9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: Güvensiz XSLT komut dosyası yürütme

|||
|-|-|
|TypeName|InsecureXSLTScriptExecution|
|CheckId|CA3076|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep

.NET uygulamalarında güvenli şekilde Genişletilebilir Stil sayfaları Dil Dönüşümleri (XSLT) yürütüyorsa işlemci saldırganlar, hizmet reddi ve siteler arası yol hassas bilgileri ifşa güvenilmeyen URI başvuruları çözümlenemedi saldırıları. Daha fazla bilgi için bkz: [XSLT güvenlik Considerations(.NET Guide)](/dotnet/standard/data/xml/xslt-security-considerations).

## <a name="rule-description"></a>Kural Tanımı

**XSLT** XML verileri dönüştürme World Wide Web Konsorsiyumu (W3C) standardıdır. XSLT genellikle sabit uzunluk metin, virgülle ayrılmış metin veya farklı bir XML biçim HTML gibi diğer biçimlere XML verileri dönüştürmek için stil sayfaları yazmak için kullanılır. Varsayılan olarak yasaklanmış rağmen projeniz için etkinleştirmeyi seçebilirsiniz.

Tetikleyiciler olduğunda bu kural, değil gösterme bir saldırı yüzeyini emin olmak için XslCompiledTransform.<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> güvenli olmayan birleşimi örneklerini alan <xref:System.Xml.Xsl.XsltSettings> ve <xref:System.Xml.XmlResolver>, kötü amaçlı komut dosyası işleme izin verir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?

- Güvenli olmayan XsltSettings bağımsız değişkeni XsltSettings ile değiştirin.<xref:System.Xml.Xsl.XsltSettings.Default%2A> veya bir örneğiyle, belge işlev ve betik yürütme devre dışı bıraktı.

- Değiştir <xref:System.Xml.XmlResolver> bağımsız değişkeni null ile veya bir <xref:System.Xml.XmlSecureResolver> örneği.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında

Giriş güvenilir bir kaynaktan olmadığı biliniyor emin değilseniz, bu uyarı kuralından bastırmak değil.

## <a name="pseudo-code-examples"></a>Sözde kod örnekleri

### <a name="violationmdashuses-xsltsettingstrustedxslt"></a>İhlali&mdash;XsltSettings.TrustedXslt kullanır

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
         void TestMethod()
        {
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
             var settings = XsltSettings.TrustedXslt;
             var resolver = new XmlUrlResolver();
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
        }
    }
}
```

### <a name="solutionmdashuse-xsltsettingsdefault"></a>Çözüm&mdash;XsltSettings.Default kullanın

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        void TestMethod()
        {
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
            var settings = XsltSettings.Default;
            var resolver = new XmlUrlResolver();
            xslCompiledTransform.Load("testStylesheet", settings, resolver);
        }
    }
}
```

### <a name="violationmdashdocument-function-and-script-execution-not-disabled"></a>İhlali&mdash;belge devre dışı işlev ve betik yürütme

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
            }
            catch { throw; }
            finally { }
        }
    }
}
```

### <a name="solutionmdashdisable-document-function-and-script-execution"></a>Çözüm&mdash;belge işlev ve betik yürütme devre dışı bırak

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                settings.EnableDocumentFunction = false;
                settings.EnableScript = false;
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver);
            }
            catch { throw; }
            finally { }
        }
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

[XSLT güvenlik konuları (.NET Kılavuzu)](/dotnet/standard/data/xml/xslt-security-considerations)