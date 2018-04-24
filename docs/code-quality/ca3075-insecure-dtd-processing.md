---
title: 'CA3075: Güvensiz DTD işleme'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b288ba61a4e5ee1d8df60d9ac4c250f2ec7081d2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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
 A *belge türü tanımı (DTD)* bir XML Ayrıştırıcı bir belgenin geçerlilik belirleyebilir iki yoldan biriyle tarafından tanımlanan olan [World Wide Web Konsorsiyumu (W3C) Genişletilebilir İşaretleme Dili (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Bu kural özelliklerini ve burada güvenilmeyen veri tarafından kabul edilir geliştiriciler olası hakkında uyarmak için örnekleri aradığı [bilgilerin açığa çıkmasına](/dotnet/framework/wcf/feature-details/information-disclosure) açabilir tehditleri [hizmet reddi (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) saldırıları. Bu kuralın ne zaman tetikler:

-   DtdProcessing etkin <xref:System.Xml.XmlReader> kullanarak dış XML varlıkları çözümler örneği <xref:System.Xml.XmlUrlResolver>.

-   <xref:System.Xml.XmlNode.InnerXml%2A> XML özelliği ayarlanmış.

-   <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> özelliği için ayrıştırma ayarlanır.

-   Giriş kullanılarak işlenir güvenilmeyen <xref:System.Xml.XmlResolver> yerine <xref:System.Xml.XmlSecureResolver> .

-   XmlReader.<xref:System.Xml.XmlReader.Create%2A> yöntemi, bir güvenli çağrılır <xref:System.Xml.XmlReaderSettings> örneği veya hiç örneği yok.

-   <xref:System.Xml.XmlReader> Güvenli varsayılan ayarları veya değerleri ile oluşturulur.

 Her durumda, sonucu aynıdır: XML işleneceği makineden dosya sistemi veya ağ paylaşımları içeriğini DoS vektör olarak kullanılabilir saldırgana gösterilir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?

-   Catch ve düzgün şekilde yolu bilgilerin açığa çıkmasına önlemek için tüm XmlTextReader özel durumları işler.

-   Kullanım <xref:System.Xml.XmlSecureResolver> XmlTextReader erişebileceği kaynakları sınırlamak için.

-   İzin verme <xref:System.Xml.XmlReader> ayarlayarak herhangi bir dış kaynağa açmak için <xref:System.Xml.XmlResolver> özelliğine **null**.

-   Emin <xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A> özelliği <xref:System.Data.DataViewManager> güvenilir bir kaynaktan atanır.

 .NET 3.5 ve önceki sürümleri

-   DTD ayarlayarak güvenilmeyen kaynakları ile çalışıyorsanız, işleme devre dışı <xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A> özelliğine **doğru** .

-   XmlTextReader sınıfı tam güven devralma talebe sahip.

 .NET 4 ve üzeri

-   Ayarlayarak güvenilmeyen kaynaklarıyla ilgili varsa DtdProcessing etkinleştirmemeye dikkat edin <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType> özelliğine **yasakla** veya **Yoksay**.

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