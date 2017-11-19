---
title: "CA3075: Güvensiz DTD işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e9660e2dc94cf23269b923c6ba5426a7cc384161
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca3075-insecure-dtd-processing"></a>CA3075: Güvensiz DTD işleme
|||  
|-|-|  
|TypeName|InsecureDTDProcessing|  
|CheckId|CA3075|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Güvenli olmayan kullanırsanız <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> örneği veya giriş ve saldırganlar için hassas bilgileri ifşa güvenilmeyen Dış varlık kaynakları, ayrıştırıcı kabul başvurusu.  
  
## <a name="rule-description"></a>Kural Tanımı  
 A [belge türü tanımı (DTD)](https://msdn.microsoft.com/en-us/library/aa468547.aspx) bir XML Ayrıştırıcı bir belgenin geçerlilik belirleyebilir iki yoldan biriyle tarafından tanımlanan olan [World Wide Web Konsorsiyumu (W3C) Genişletilebilir İşaretleme Dili (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Bu kural özelliklerini ve burada güvenilmeyen veri tarafından kabul edilir geliştiriciler olası hakkında uyarmak için örnekleri aradığı [bilgilerin açığa çıkmasına](/dotnet/framework/wcf/feature-details/information-disclosure) açabilir tehditleri [hizmet reddi (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) saldırıları. Bu kuralın ne zaman tetikler:  
  
-   DtdProcessing etkin <xref:System.Xml.XmlReader> kullanarak dış XML varlıkları çözümler örneği <xref:System.Xml.XmlUrlResolver>.  
  
-   <xref:System.Xml.XmlNode.InnerXml%2A> XML özelliği ayarlanmış.  
  
-   <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>özelliği için ayrıştırma ayarlanır.  
  
-   Giriş kullanılarak işlenir güvenilmeyen <xref:System.Xml.XmlResolver> yerine <xref:System.Xml.XmlSecureResolver> .  
  
-   XmlReader. <xref:System.Xml.XmlReader.Create%2A> yöntemi ile bir güvenli çağrıldığında <xref:System.Xml.XmlReaderSettings> örneği veya hiç örneği yok.  
  
-   <xref:System.Xml.XmlReader>Güvenli varsayılan ayarları veya değerleri ile oluşturulur.  
  
 Her durumda, sonucu aynıdır: XML işleneceği makineden dosya sistemi veya ağ paylaşımları içeriğini DoS vektör olarak kullanılabilir saldırgana gösterilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
  
-   Catch ve düzgün şekilde yolu bilgilerin açığa çıkmasına önlemek için tüm XmlTextReader özel durumları işler.  
  
-   Kullanım <xref:System.Xml.XmlSecureResolver> XmlTextReader erişebileceği kaynakları sınırlamak için.  
  
-   İzin verme <xref:System.Xml.XmlReader> ayarlayarak herhangi bir dış kaynağa açmak için <xref:System.Xml.XmlResolver> özelliğine **null**.  
  
-   Emin <xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A> özelliği <xref:System.Data.DataViewManager> güvenilir bir kaynaktan atanır.  
  
 .NET 3.5 ve önceki sürümleri  
  
-   DTD ayarlayarak güvenilmeyen kaynakları ile çalışıyorsanız, işleme devre dışı <xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A> özelliğine **doğru** .  
  
-   XmlTextReader sınıfı tam güven devralma talebe sahip. Bkz: [devralma taleplerini](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9) daha fazla bilgi için.  
  
 .NET 4 ve üzeri  
  
-   DtdProcessing özelliğini ayarlayarak güvenilmeyen kaynaklarıyla ilgili varsa DtdProcessing etkinleştirmemeye dikkat edin [Engelle veya yoksay](https://msdn.microsoft.com/en-us/library/system.xml.dtdprocessing.aspx)  
  
-   Load() yöntemi tüm InnerXml durumlarda XmlReader örneği alır emin olun.  
  
> [!NOTE]
>  Bu kural hatalı pozitif sonuç bazı geçerli XmlSecureResolver örneklerinde bildirebilir. Mid 2016'da bu sorunu çözme üzerinde çalışıyoruz.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Giriş güvenilir bir kaynaktan olmadığı biliniyor emin değilseniz, bu uyarı kuralından bastırmak değil.  
  
## <a name="pseudo-code-examples"></a>Sözde kod örnekleri  
  
### <a name="violation"></a>İhlali  
  
```csharp  
using System.IO;   
using System.Xml.Schema;   
  
class TestClass   
{   
    public XmlSchema Test   
    {   
        get   
        {   
            var src = "";   
            TextReader tr = new StreamReader(src);   
            XmlSchema schema = XmlSchema.Read(tr, null); // warn   
            return schema;   
        }   
    }   
}  
```  
  
### <a name="solution"></a>Çözüm  
  
```csharp  
using System.IO;   
using System.Xml;   
using System.Xml.Schema;   
  
class TestClass   
{   
    public XmlSchema Test   
    {   
        get   
        {   
            var src = "";   
            TextReader tr = new StreamReader(src);   
            XmlTextReader reader = new XmlTextReader(tr) { DtdProcessing = DtdProcessing.Prohibit };   
            XmlSchema schema = XmlSchema.Read(reader , null);   
            return schema;   
        }   
    }   
}  
```  
  
### <a name="violation"></a>İhlali  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    public class TestClass   
    {   
        public XmlReaderSettings settings = new XmlReaderSettings();   
        public void TestMethod(string path)   
        {   
            var reader = XmlReader.Create(path, settings);  // warn   
        }   
    }   
}  
```  
  
### <a name="solution"></a>Çözüm  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    public class TestClass   
    {   
        public XmlReaderSettings settings = new XmlReaderSettings()    
        {   
            DtdProcessing = DtdProcessing.Prohibit    
        };   
  
        public void TestMethod(string path)   
        {   
            var reader = XmlReader.Create(path, settings);    
        }   
    }   
}  
```  
  
### <a name="violations"></a>İhlalleri  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    public class DoNotUseSetInnerXml   
    {   
        public void TestMethod(string xml)   
        {   
            XmlDocument doc = new XmlDocument() { XmlResolver = null };   
            doc.InnerXml = xml; // warn   
        }   
    }   
}  
```  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    public class DoNotUseLoadXml   
    {  
        public void TestMethod(string xml)   
        {   
            XmlDocument doc = new XmlDocument(){ XmlResolver = null };   
            doc.LoadXml(xml); // warn   
        }   
    }   
}  
```  
  
### <a name="solution"></a>Çözüm  
  
```csharp  
using System.Xml;   
  
public static void TestMethod(string xml)   
{   
    XmlDocument doc = new XmlDocument() { XmlResolver = null };   
    System.IO.StringReader sreader = new System.IO.StringReader(xml);   
    XmlTextReader reader = new XmlTextReader(sreader) { DtdProcessing = DtdProcessing.Prohibit };   
    doc.Load(reader);   
}  
```  
  
### <a name="violation"></a>İhlali  
  
```csharp  
using System.IO;   
using System.Xml;   
using System.Xml.Serialization;   
  
namespace TestNamespace   
{   
    public class UseXmlReaderForDeserialize   
    {   
        public void TestMethod(Stream stream)   
        {   
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));   
            serializer.Deserialize(stream); // warn   
        }   
    }   
}  
```  
  
### <a name="solution"></a>Çözüm  
  
```csharp  
using System.IO;   
using System.Xml;   
using System.Xml.Serialization;   
  
namespace TestNamespace   
{   
    public class UseXmlReaderForDeserialize   
    {   
        public void TestMethod(Stream stream)   
        {   
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));   
            XmlTextReader reader = new XmlTextReader(stream) { DtdProcessing = DtdProcessing.Prohibit } ;   
            serializer.Deserialize(reader );   
        }   
    }   
}  
```  
  
### <a name="violation"></a>İhlali  
  
```csharp  
using System.Xml;   
using System.Xml.XPath;   
  
namespace TestNamespace   
{   
    public class UseXmlReaderForXPathDocument   
    {   
        public void TestMethod(string path)   
        {   
            XPathDocument doc = new XPathDocument(path); // warn   
        }   
    }   
}  
```  
  
### <a name="solution"></a>Çözüm  
  
```csharp  
using System.Xml;   
using System.Xml.XPath;   
  
namespace TestNamespace   
{   
    public class UseXmlReaderForXPathDocument   
    {   
        public void TestMethod(string path)   
        {   
            XmlTextReader reader = new XmlTextReader(path) { DtdProcessing = DtdProcessing.Prohibit };   
            XPathDocument doc = new XPathDocument(reader);   
        }   
    }   
}  
```  
  
### <a name="violation"></a>İhlali  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        public XmlDocument doc = new XmlDocument() { XmlResolver = new XmlUrlResolver() };   
    }   
}  
```  
  
### <a name="solution"></a>Çözüm  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        public XmlDocument doc = new XmlDocument() { XmlResolver = null }; // or set to a XmlSecureResolver instance   
    }   
}  
```  
  
### <a name="violations"></a>İhlalleri  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    public class TestClass   
    {   
        public void TestMethod(string path)   
        {   
            XmlReaderSettings settings = new XmlReaderSettings(){ DtdProcessing = DtdProcessing.Parse };   
            XmlReader reader = XmlReader.Create(path, settings); // warn   
        }   
    }   
}  
```  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        private static void TestMethod()   
        {   
            var reader = XmlTextReader.Create(""doc.xml""); //warn   
        }   
    }   
}  
```  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    public class TestClass   
    {   
        public void TestMethod(string path)   
        {   
            try {   
                XmlTextReader reader = new XmlTextReader(path); // warn   
            }   
            catch { throw ; }   
            finally {}   
        }   
    }   
}  
```  
  
### <a name="solution"></a>Çözüm  
  
```csharp  
using System.Xml;   
  
namespace TestNamespace   
{   
    public class TestClass   
    {   
        public void TestMethod(string path)   
        {   
            XmlReaderSettings settings = new XmlReaderSettings(){ DtdProcessing = DtdProcessing.Prohibit };   
            XmlReader reader = XmlReader.Create(path, settings);   
        }   
    }   
}  
```