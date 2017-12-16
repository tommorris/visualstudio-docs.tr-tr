---
title: "CA3076: Güvensiz XSLT komut dosyası yürütme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53cb7a46-c564-488f-bc51-0e210a7853c9
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a304d5b405431bca78b3978e25b00d3cf7cc96c2
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: Güvensiz XSLT komut dosyası yürütme
|||  
|-|-|  
|TypeName|InsecureXSLTScriptExecution|  
|CheckId|CA3076|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Yürütüyorsa [Genişletilebilir Stil sayfaları Dil Dönüşümleri (XSLT)](https://support.microsoft.com/en-us/kb/313997) güvenli şekilde, işlemci .NET uygulamalarında neden saldırganlar, hassas bilgileri ifşa güvenilmeyen URI başvuruları çözümlenemedi Hizmet ve siteler arası saldırıları reddi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 **XSLT** XML verileri dönüştürme World Wide Web Konsorsiyumu (W3C) standardıdır. XSLT genellikle sabit uzunluk metin, virgülle ayrılmış metin veya farklı bir XML biçim HTML gibi diğer biçimlere XML verileri dönüştürmek için stil sayfaları yazmak için kullanılır. Varsayılan olarak yasaklanmış rağmen projeniz için etkinleştirmeyi seçebilirsiniz.  
  
 Tetikleyiciler olduğunda bu kural, değil gösterme bir saldırı yüzeyini emin olmak için XslCompiledTransform. <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> güvensiz birleşimi örneklerini alan <xref:System.Xml.Xsl.XsltSettings> ve <xref:System.Xml.XmlResolver>, kötü amaçlı komut dosyası işleme izin verir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
  
-   Güvenli olmayan XsltSettings bağımsız değişkeni XsltSettings ile değiştirin. <xref:System.Xml.Xsl.XsltSettings.Default%2A> veya örneğiyle belge işlev ve betik yürütme devre dışı bıraktı.  
  
-   Değiştir <xref:System.Xml.XmlResolver> bağımsız değişkeni null ile veya bir <xref:System.Xml.XmlSecureResolver> örneği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Giriş güvenilir bir kaynaktan olmadığı biliniyor emin değilseniz, bu uyarı kuralından bastırmak değil.  
  
## <a name="pseudo-code-examples"></a>Sözde kod örnekleri  
  
### <a name="violation"></a>İhlali  
  
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
  
### <a name="solution"></a>Çözüm  
  
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
  
### <a name="violation"></a>İhlali  
  
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
  
### <a name="solution"></a>Çözüm  
  
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