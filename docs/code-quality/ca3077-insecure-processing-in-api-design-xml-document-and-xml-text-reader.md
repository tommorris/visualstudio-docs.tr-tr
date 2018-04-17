---
title: 'CA3077: API tasarımı, XML belgesi ve XML metin okuyucu güvensiz işlemede | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 7f33771b-f3c8-4c02-bef6-f581b623c303
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f660ee98462b46e5ac5a8ab23cdf17288c995c87
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077: API tasarımı, XML belgesi ve XML metin okuyucu güvensiz işlemede
|||  
|-|-|  
|TypeName|InsecureDTDProcessingInAPIDesign|  
|CheckId|CA3077|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Bir API tasarlama XMLDocument ve XMLTextReader türetilmiş olduğunda, dikkatli olmanızı <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>.  Güvenli olmayan DTDProcessing örnekleri başvuran veya dış varlık kaynakları çözme veya XML dosyasında güvenli olmayan değerleri ayarlama bilgileri açığa çıkmasına neden olabilir kullandığınızda.  
  
## <a name="rule-description"></a>Kural Tanımı  
 A *belge türü tanımı (DTD)* bir XML Ayrıştırıcı bir belgenin geçerlilik belirleyebilir iki yoldan biriyle tarafından tanımlanan olan [World Wide Web Konsorsiyumu (W3C) Genişletilebilir İşaretleme Dili (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/). Bu kural özelliklerini ve burada güvenilmeyen veri tarafından kabul edilir geliştiriciler olası hakkında uyarmak için örnekleri aradığı [bilgilerin açığa çıkmasına](/dotnet/framework/wcf/feature-details/information-disclosure) açabilir tehditleri [hizmet reddi (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) saldırıları. Bu kuralın ne zaman tetikler:  
  
-   <xref:System.Xml.XmlDocument> veya <xref:System.Xml.XmlTextReader> sınıflarını DTD işleme için varsayılan çözümleyici değerleri kullanın.  
  
-   Oluşturucu yok XmlDocument için tanımlı değil veya XmlTextReader türetilmiş sınıfları veya güvenli bir değerle için kullanılan <xref:System.Xml.XmlResolver>.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
  
-   Catch ve düzgün şekilde yolu bilgilerin açığa çıkmasına önlemek için tüm XmlTextReader özel durumları işler.  
  
-   Kullanım <xref:System.Xml.XmlSecureResolver>XmlTextReader erişebileceği kaynakları sınırlamak için XmlResolver yerine.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Giriş güvenilir bir kaynaktan olmadığı biliniyor emin değilseniz, bu uyarı kuralından bastırmak değil.  
  
## <a name="pseudo-code-examples"></a>Sözde kod örnekleri  
  
### <a name="violation"></a>İhlali  
  
```csharp  
using System;   
using System.Xml;   
  
namespace TestNamespace   
{   
    class TestClass : XmlDocument    
    {   
        public TestClass () {} // warn   
    }   
  
    class TestClass2 : XmlTextReader    
    {       
        public TestClass2() // warn   
        {   
        }   
    }   
}  
```  
  
### <a name="solution"></a>Çözüm  
  
```csharp  
using System;   
using System.Xml;   
  
namespace TestNamespace   
{   
    class TestClass : XmlDocument    
    {   
        public TestClass ()    
        {   
            XmlResolver = null;   
        }   
    }   
  
    class TestClass2 : XmlTextReader    
    {       
        public TestClass2()    
        {   
               XmlResolver = null;   
        }   
    }   
}  
```