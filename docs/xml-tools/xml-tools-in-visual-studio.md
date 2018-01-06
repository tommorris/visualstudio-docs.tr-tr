---
title: "Visual Studio'daki XML araçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.xmldesigner
helpviewer_keywords:
- XML [Visual Studio], resources
- Enterprise Templates, XML and
- discovery files, XML
- server controls, XML and
- Web server controls, XML
- XSL
- XML [Visual Studio], data sources
- XML schemas
- XML [Visual Studio], SGML relationship to
- CSS, style sheets for XML
- XML [Visual Studio], .NET Framework classes
- data [Visual Studio], XML
- classes [Visual Studio], XML
- style sheets, for XML
- Web services
- SGML, XML
- XML [Visual Studio]
- datasets [Visual Basic], XML Schemas
- XSD schemas
- XSL, style sheets
- XMLDataDocument class
ms.assetid: 1fd5de47-2d61-4180-9539-c2c4bf9ab768
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 29407d3f8d95f815b588fff30a4e1268904eb54d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="xml-tools-in-visual-studio"></a>Visual Studio'daki XML Araçları
*Genişletilebilir İşaretleme Dili (XML)* veri tanımlamak için bir biçim sağlayan bir biçimlendirme dilidir. Bu içerik ve daha anlamlı arama sonuçlarının daha kesin bildirimleri birden çok platform genelinde kolaylaştırır. Ayrıca, XML verileri sunudan ayrımı sağlar. Örneğin, HTML etiketleri kalın veya Yatık olarak verileri görüntülemek için tarayıcı bildirmek için kullandığınız; XML'de yalnızca şehir adı, sıcaklık ve barometric baskısı gibi verileri tanımlamak için etiketleri kullanın. XML'de, stil sayfaları Genişletilebilir Stil sayfası Dili'nin (XML) gibi ve geçişli stil sayfaları (CSS) bir tarayıcıda verileri sunmak için kullanın. XML verileri sunu ve işlem ayırır. Bu, farklı stil sayfaları ve uygulamaları uygulayarak istediğiniz gibi verileri işlemek ve görüntülemesini sağlar.  
  
 XML Web üzerinden teslimat için optimize edilmiştir SGML alt kümesidir. World Wide Web Konsorsiyumu (W3C) tarafından tanımlanır. Bu Standartlaştırma yapılandırılmış veri Tekdüzen ve uygulamaları veya satıcılar bağımsız olarak olacağını garanti eder.  
  
 XML'dir özelliklerinin çoğu özünde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Aşağıdaki konu listesi içinde sunulan XML ilgili özellikler ve Araçlar adları [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Daha fazla bilgi için bkz: [XML Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkID=100176), sağlayan en son belgeleri, teknik bilgileri, yüklemeleri, haber grupları ve diğer kaynakları XML geliştiriciler için.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [XML Verileriyle Çalışma](../xml-tools/working-with-xml-data.md)  
 XML rolü verileri işlenir şekilde ele alınmıştır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 [XSLT Hatalarını Ayıklama](../xml-tools/debugging-xslt.md)  
 XSLT hata ayıklamak için Visual Studio hata ayıklayıcısı kullanmayla ilgili konulara bağlantılar sağlar.  
  
## <a name="reference"></a>Başvuru  
 [Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699)  
 Sunan [XML Düzenleyicisi](http://go.microsoft.com/fwlink/?LinkId=228249) ayrıştırma ağacı aracılığıyla [System.Xml.Linq](http://go.microsoft.com/fwlink/?LinkId=228250) XML belgeleri için.  
  
 [XML standartları başvurusu](http://msdn.microsoft.com/en-us/79c78508-c9d0-423a-a00f-672e855de401)  
 XML, belge türü tanımı (DTD), XML Şeması Tanım Dili (XSD) ve XSLT dahil olmak üzere XML teknolojileri hakkında bilgi sağlar.  
  
 <xref:System.Xml?displayProperty=fullName>  
 Sınıfları ve oluşturan diğer öğeleri açıklar <xref:System.Xml> ad alanı ve her bir öğede daha ayrıntılı bilgi için bağlantılar sağlar.  
  
 <xref:System.Xml.Serialization?displayProperty=fullName>  
 Sınıfları ve oluşturan diğer öğeleri açıklar <xref:System.Xml.Serialization> ad alanı ve her öğe hakkında daha ayrıntılı bilgi için bağlantılar sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [XML Belge Nesne Modeli (DOM)](/dotnet/standard/data/xml/xml-document-object-model-dom)  
 Açıklar nasıl <xref:System.Xml.XmlDocument> ve onun ilişkili sınıfları W3C belge nesne modeli (Temel) Düzey 1 ve Düzey 2 ad alanı destek belirtimleri uymak.  
  
 [XmlReader XML okuma](http://msdn.microsoft.com/en-us/3029834c-a27e-4331-b7aa-711924062182)  
 Açıklar nasıl <xref:System.Xml.XmlReader> Önbelleklenmemiş, iletme yalnızca, salt okunur erişim XML verilerini bir XML akışı sağlar.  
  
 [XML XmlWriter ile yazma](http://msdn.microsoft.com/en-us/ea41f72c-e1d3-4e0a-ab0f-f0eb1c27ab86)  
 Açıklar nasıl <xref:System.Xml.XmlWriter> Önbelleklenmemiş, sağlar yalnızca XML akışları ve W3C standart uyumlu XML belgelerini yapı yardımcı oluşturma yolu iletin.  
  
 [XSLT Dönüşümleri](/dotnet/standard/data/xml/xslt-transformations)  
 Açıklar nasıl <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı XSLT 1.0 öneri uygular.  
  
 [XPath Veri Modelini Kullanarak XML Verilerini İşleme](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model)  
 Açıklar nasıl <xref:System.Xml.XPath.XPathNavigator> sınıfı tarafından depolanan XML veri işlenebilecek bir <xref:System.Xml.XPath.XPathDocument> veya bir <xref:System.Xml.XmlDocument> nesnesi. <xref:System.Xml.XPath.XPathNavigator> Sınıfı XQuery 1.0 ve XPath 2.0 veri modelini temel alır ve gidin ve XML verileri düzenlemek için kullanılabilir.  
  
 [XML Şema Nesne Modeli (SOM)](/dotnet/standard/data/xml/xml-schema-object-model-som)  
 XML şemaları sağlayarak düzenleme ve oluşturmak için kullanılan sınıflar açıklanmaktadır bir <xref:System.Xml.Schema.XmlSchema> yüklemek ve bir şema düzenlemek için sınıf.