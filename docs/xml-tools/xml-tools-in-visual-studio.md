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
ms.openlocfilehash: 38d933199c85bee3fa85a533f9c61c08bee898ea
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="xml-tools-in-visual-studio"></a>Visual Studio'daki XML Araçları

*Genişletilebilir İşaretleme Dili (XML)* veri tanımlamak için bir biçim sağlayan bir biçimlendirme dilidir. Bu içerik ve daha anlamlı arama sonuçlarının daha kesin bildirimleri birden çok platform genelinde kolaylaştırır. Ayrıca, XML verileri sunudan ayrımı sağlar. Örneğin, HTML etiketleri kalın veya Yatık olarak verileri görüntülemek için tarayıcı bildirmek için kullandığınız; XML'de yalnızca şehir adı, sıcaklık ve barometric baskısı gibi verileri tanımlamak için etiketleri kullanın. XML'de, stil sayfaları Genişletilebilir Stil sayfası Dili'nin (XML) gibi ve geçişli stil sayfaları (CSS) bir tarayıcıda verileri sunmak için kullanın. XML verileri sunu ve işlem ayırır. Bu, farklı stil sayfaları ve uygulamaları uygulayarak istediğiniz gibi verileri işlemek ve görüntülemesini sağlar.

XML Web üzerinden teslimat için optimize edilmiştir SGML alt kümesidir. World Wide Web Konsorsiyumu (W3C) tarafından tanımlanır. Bu Standartlaştırma yapılandırılmış veri Tekdüzen ve uygulamaları veya satıcılar bağımsız olarak olacağını garanti eder.

Visual Studio ve .NET Framework özelliklerinin çoğu özünde XML'dir. Aşağıdaki konu listesi adları araçları ve Visual Studio ve .NET Framework sunulan XML ilgili özellikler.

Daha fazla bilgi için bkz: <xref:System.Xml?displayProperty=fullName> belgeleri.

## <a name="in-this-section"></a>Bu Bölümde

[XML Verileriyle Çalışma](../xml-tools/working-with-xml-data.md)  
XML veri Visual Studio'da işlenme içindeki rolü ele alınmıştır.

[XSLT Hatalarını Ayıklama](../xml-tools/debugging-xslt.md)  
XSLT hata ayıklamak için Visual Studio hata ayıklayıcısı kullanmayla ilgili konulara bağlantılar sağlar.

## <a name="reference"></a>Başvuru

[Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699)  
Sunan [XML Düzenleyicisi](http://go.microsoft.com/fwlink/?LinkId=228249) ayrıştırma ağacı aracılığıyla [System.Xml.Linq](http://go.microsoft.com/fwlink/?LinkId=228250) XML belgeleri için.

[XML standartları başvurusu](http://msdn.microsoft.com/79c78508-c9d0-423a-a00f-672e855de401)  
XML, belge türü tanımı (DTD), XML Şeması Tanım Dili (XSD) ve XSLT dahil olmak üzere XML teknolojileri hakkında bilgi sağlar.

<xref:System.Xml?displayProperty=fullName>  
Sınıfları ve oluşturan diğer öğeleri açıklar <xref:System.Xml> ad alanı ve her bir öğede daha ayrıntılı bilgi için bağlantılar sağlar.

<xref:System.Xml.Serialization?displayProperty=fullName>  
Sınıfları ve oluşturan diğer öğeleri açıklar <xref:System.Xml.Serialization> ad alanı ve her öğe hakkında daha ayrıntılı bilgi için bağlantılar sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[XML Belge Nesne Modeli (DOM)](/dotnet/standard/data/xml/xml-document-object-model-dom)  
Açıklar nasıl <xref:System.Xml.XmlDocument> ve onun ilişkili sınıfları W3C belge nesne modeli (Temel) Düzey 1 ve Düzey 2 ad alanı destek belirtimleri uymak.

[XmlReader ve XmlWriter ile XML verileri işleme](https://msdn.microsoft.com/library/cc189001(v=vs.95).aspx)

[XSLT Dönüşümleri](/dotnet/standard/data/xml/xslt-transformations)  
Açıklar nasıl <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı XSLT 1.0 öneri uygular.

[XPath Veri Modelini Kullanarak XML Verilerini İşleme](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model)  
Açıklar nasıl <xref:System.Xml.XPath.XPathNavigator> sınıfı tarafından depolanan XML veri işlenebilecek bir <xref:System.Xml.XPath.XPathDocument> veya bir <xref:System.Xml.XmlDocument> nesnesi. <xref:System.Xml.XPath.XPathNavigator> Sınıfı XQuery 1.0 ve XPath 2.0 veri modelini temel alır ve gidin ve XML verileri düzenlemek için kullanılabilir.

[XML Şema Nesne Modeli (SOM)](/dotnet/standard/data/xml/xml-schema-object-model-som)  
XML şemaları sağlayarak düzenleme ve oluşturmak için kullanılan sınıflar açıklanmaktadır bir <xref:System.Xml.Schema.XmlSchema> yüklemek ve bir şema düzenlemek için sınıf.