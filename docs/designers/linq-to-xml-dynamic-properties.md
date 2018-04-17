---
title: LINQ-XML dinamik özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: 0455f47c-4a68-4f2e-a3f8-dd1d85b99012
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d54a37b58f46d8c3d1de145cc623ac3138621da
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="linq-to-xml-dynamic-properties"></a>LINQ-XML Dinamik Özellikler
Bu bölümde, XML LINQ dinamik özellikleri hakkında başvuru bilgileri sağlar. Özellikle, bu özellikler tarafından kullanıma sunulan <xref:System.Xml.Linq.XAttribute> ve <xref:System.Xml.Linq.XElement> bulunan sınıflar <xref:System.Xml.Linq> ad alanı.  
  
 Konu başlığı altında açıklandığı gibi [genel bakış, WPF veri bağlama LINQ-XML ile](../designers/wpf-data-binding-with-linq-to-xml-overview.md), dinamik özelliklerin her biri bir standart ortak özelliği veya yöntemi aynı sınıfta eşdeğerdir. Bu standart üyeleri çoğu amaç için kullanılması gereken; Dinamik özellikler LINQ-XML veri bağlama senaryoları için özel olarak sağlanır. Bu sınıfların standart üyeleri hakkında daha fazla bilgi için bkz: <xref:System.Xml.Linq.XAttribute> ve <xref:System.Xml.Linq.XElement> başvuru konuları.  
  
 Çözümlenen değerlerine göre dinamik özellikler bu bölümdeki iki kategoriye ayrılır:  
  
-   Basit olanlar gibi `Value` özelliklerinde <xref:System.Xml.Linq.XAttribute> ve <xref:System.Xml.Linq.XElement> tek bir değer çözmek sınıflar.  
  
-   Değerleri gibi dizine [öğeleri](../designers/elements-xelement-dynamic-property.md) ve [alt öğeleri](../designers/descendants-xelement-dynamic-property.md) özelliklerini <xref:System.Xml.Linq.XElement>, bir dizin oluşturucu türünü çözümleyin. Dizin oluşturucu türleri istenen değeri veya koleksiyon çözülmesi için bir genişletilmiş name parametresi geçirilmelidir.  
  
 Dizinli bir değer türü döndüren dinamik özellikleri <xref:System.Collections.Generic.IEnumerable%601> deffered yürütme kullanın. Ertelenmiş yürütme hakkında daha fazla bilgi için bkz: [LINQ sorgularını (C#) giriş](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries).  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Konu|Açıklama|  
|-----------|-----------------|  
|[XAttribute Sınıfı Dinamik Özellikleri](../designers/xattribute-class-dynamic-properties.md)|Tarafından sunulan dinamik özellikleri hakkında ayrıntılı bilgi sağlar <xref:System.Xml.Linq.XAttribute> sınıfı.|  
|[XElement Sınıfı Dinamik Özellikleri](../designers/xelement-class-dynamic-properties.md)|Tarafından sunulan dinamik özellikleri hakkında ayrıntılı bilgi sağlar <xref:System.Xml.Linq.XElement> sınıfı.|  
  
## <a name="reference"></a>Başvuru  
 <xref:System.Xml.Linq>  
  
 <xref:System.Xml.Linq.XElement?displayProperty=fullName>  
  
 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ-XML ile WPF veri bağlama](../designers/wpf-data-binding-with-linq-to-xml.md)   
 [WPF veri bağlama ile LINQ-XML genel bakış](../designers/wpf-data-binding-with-linq-to-xml-overview.md)   
 [Giriş LINQ sorgularını (C#)](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries)