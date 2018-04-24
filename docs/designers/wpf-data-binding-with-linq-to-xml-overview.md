---
title: WPF veri bağlama ile LINQ-XML genel bakış
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 3bf80845-891b-41de-a71b-4080b5bd3ea6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81c7a8debabd83f335b1d465495618f28e3db0cd
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="wpf-data-binding-with-linq-to-xml-overview"></a>WPF veri bağlama ile LINQ-XML genel bakış

Bu konu içinde dinamik veri bağlama özellikleri tanıtır <xref:System.Xml.Linq> ad alanı. Bu özellikler Windows Presentation Foundation (WPF) uygulamaları kullanıcı arabirimi (UI) öğeleri için bir veri kaynağı olarak kullanılabilir. Bu senaryo özel dayanır *dinamik özellikleri* , <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> ve <xref:System.Xml.Linq.XElement?displayProperty=fullName>.

## <a name="xaml-and-linq-to-xml"></a>XAML ve LINQ-XML

Genişletilebilir uygulama biçimlendirme dili (XAML) .NET Framework 3.0 teknolojilerini desteklemek için Microsoft tarafından oluşturulan bir XML dialect ' dir. WPF içinde kullanıcı arabirimi öğeleri ve olayları ve veri bağlama gibi ilgili özellikleri göstermek için kullanılır. Windows Workflow Foundation ' XAML program denetimi gibi program yapısı temsil etmek için kullanılır (*iş akışları*). XAML bildirim temelli bir teknoloji daha bireyselleştirilmiş bir programın davranışını tanımlayan ilgili yordamsal koddan ayrılması yönlerini sağlar.

XAML ve LINQ-XML etkileşim kurabilen geniş iki yolu vardır:

- Çünkü XAML dosyaları doğru biçimlendirilmiş XML, bunlar kullanılabilir sorgulanan ve LINQ-XML gibi XML teknolojilerle yönetilebilir.

- LINQ-XML sorgularını temsil ettiği için bir veri kaynağı, bu sorguları WPF kullanıcı Arabirimi öğeleri için veri bağlama için bir veri kaynağı olarak kullanılabilir.

Bu belgede ikinci senaryo açıklanmaktadır.

## <a name="data-binding-in-the-windows-presentation-foundation"></a>Veri Windows Presentation Foundation'da bağlama

WPF veri bağlama özelliklerinden biri bir veri kaynağı ile ilişkilendirmek bir kullanıcı Arabirimi öğeleri sağlar. Bu basit bir örnektir bir <xref:System.Windows.Controls.Label> metni bir genel özelliğinin değeri bir kullanıcı tarafından tanımlanan nesnesinde gösterir. WPF veri bağlama aşağıdaki bileşenlerini dayanır:

|Bileşen|Açıklama|
|---------------|-----------------|
|Bağlama hedefi|Veri kaynağı ile ilişkili olması için kullanıcı Arabirimi öğesi. WPF görsel öğeleri türetilir <xref:System.Windows.UIElement> sınıfı.|
|Target özelliği|*Bağımlılık özelliği* bağlama hedefinin bağlama veri kaynağı değeri yansıtır. Bağımlılık özellikleri tarafından desteklendiği doğrudan <xref:System.Windows.DependencyObject> sınıfı, hangi <xref:System.Windows.UIElement> türetir.|
|Bağlama kaynağı|Sunu için kullanıcı Arabirimi öğesi için sağlanan bir veya daha fazla değerler için kaynak nesnesi. WPF otomatik olarak kaynakları bağlama olarak aşağıdaki türlerini destekler: CLR nesneleri, ADO.NET veri nesneleri, XML (XPath veya verileri LINQ-XML sorgularını) veya başka bir <xref:System.Windows.DependencyObject>.|
|Kaynak yolu|Değer veya bağlanacağını değerleri kümesi çözümler bağlama kaynağı özelliği.|

Bir kullanıcı Arabirimi öğesi dinamik olarak hesaplanan bir özelliği temsil eden WPF için belirli bir kavram bir bağımlılık özelliğidir. Örneğin, bağımlılık özellikleri genellikle varsayılan değerler veya bir üst öğe tarafından sağlanan değerler içeriyor. Bu özel özellikleri örnekleri tarafından yedeklenen <xref:System.Windows.DependencyProperty> sınıfı (ve olmayan alanlar olarak standart özellikleri ile). Daha fazla bilgi için bkz: [bağımlılık özelliklerine genel bakış](/dotnet/framework/wpf/advanced/dependency-properties-overview).

### <a name="dynamic-data-binding-in-wpf"></a>WPF içinde dinamik veri bağlama

Yalnızca hedef UI öğesi başlatıldığında varsayılan olarak, veri bağlama gerçekleşir. Bu adlı *tek seferlik* bağlama. Çoğu amaç için yetersiz budur; Genellikle, bir veri bağlama çözüm değişiklikleri aşağıdakilerden birini kullanarak çalışma zamanında dinamik olarak dağıtılmasını gerektirir:

- *Tek yönlü* bağlama otomatik olarak dağıtılmasını sütunlardan değişiklikleri neden olur. En yaygın olarak, hedef kaynak değişiklikler yansıtılır ancak ters bazen yararlı olabilir.

- İçinde *iki yönlü* bağlama, kaynağına değişiklikler otomatik olarak hedef yayılan ve hedef değişiklikler kaynak otomatik olarak yayılır.

Tek veya çift yönlü ortaya bağlamak için kaynağı bir değişiklik bildirim mekanizması, örneğin uygulayarak uygulamalıdır <xref:System.ComponentModel.INotifyPropertyChanged> kullanarak veya arabirim bir *PropertyNameChanged* desteklenen her bir özellik için desen.

WPF veri bağlama hakkında daha fazla bilgi için bkz: [veri bağlama (WPF)](/dotnet/framework/wpf/data/data-binding-wpf).

## <a name="dynamic-properties-in-linq-to-xml-classes"></a>LINQ to XML sınıfları Dinamik Özellikler

Çoğu LINQ XML sınıfları için uygun değil uygun WPF dinamik veri kaynakları. Bazı en yararlı bilgiler yalnızca yöntemleri, özellikleri, kullanılabilir ve bu sınıfların özelliklerinde değişiklik bildirimleri kullanılmaz. WPF veri bağlama desteklemek için bir dizi LINQ-XML sunan *dinamik özellikleri*.

Bu dinamik varolan yöntemleri işlevlerin birer yinelemesidir özel çalışma zamanı özellikleri ve özelliklerinde özelliklerdir <xref:System.Xml.Linq.XAttribute> ve <xref:System.Xml.Linq.XElement> sınıfları. Bunlar yalnızca bunları WPF için dinamik veri kaynakları olarak davranmak üzere etkinleştirmek için bu sınıfların eklenmiştir. Bu gereksinimi karşılamak için değişiklik bildirimlerinin bu dinamik özelliklerin uygulayın. Bu dinamik özelliklerin ayrıntılı başvuru sonraki bölümde, sağlanan [LINQ-XML dinamik özellikleri](../designers/linq-to-xml-dynamic-properties.md).

> [!NOTE]
> Standart genel özelliklerin çoğu bulunan çeşitli sınıflarda <xref:System.Xml.Linq> ad alanı, tek seferlik veri bağlaması için kullanılabilir. Bununla birlikte, kaynak ne hedef dinamik olarak bu düzeni altında güncelleştirileceği olduğunu unutmayın.

### <a name="accessing-dynamic-properties"></a>Dinamik özelliklerine erişme

Dinamik Özellikler <xref:System.Xml.Linq.XAttribute> ve <xref:System.Xml.Linq.XElement> sınıfları gibi standart özellikler erişilemiyor. Örneğin, C# gibi CLR uyumlu dillerde, bunlar olamaz:

- Doğrudan derleme zamanında erişilir. Dinamik özellikler, derleyici ve Visual Studio IntelliSense görünmez.

- .NET yansıma kullanarak bulunan veya adresindeki erişilen çalışma süresi. Çalışma zamanında bile temel CLR algılama özelliklerinde değiller.

C# ' ta dinamik özellikleri yalnızca çalışma zamanında tarafından sağlanan özellikleri aracılığıyla erişilebilir <xref:System.ComponentModel> ad alanı.

Buna karşılık, ancak, bir XML kaynak dinamik özellikleri aşağıdaki biçimde basit bir gösterim aracılığıyla erişilebilir:

```
<object>.<dynamic-property>
```

Bu iki sınıf ya da doğrudan kullanılabilmesi için bir değer veya sonuç değeri veya değerler koleksiyonu elde etmek için bir dizin ile sağlanan bir dizin oluşturucu çözümlemek için dinamik özellikler. İkinci sözdizimi biçimdedir:

```
<object>.<dynamic-property>[<index-value>]
```

Daha fazla bilgi için bkz: [LINQ-XML dinamik özellikleri](../designers/linq-to-xml-dynamic-properties.md).

WPF dinamik bağlama uygulamak için dinamik özellikleri tarafından sağlanan özellikleri ile kullanılacak <xref:System.Windows.Data> ad alanı, özellikle <xref:System.Windows.Data.Binding> sınıfı.

## <a name="see-also"></a>Ayrıca bkz.

- [LINQ to XML ile WPF Verilerini Bağlama](../designers/wpf-data-binding-with-linq-to-xml-overview.md)
- [LINQ to XML Dinamik Özellikleri](../designers/linq-to-xml-dynamic-properties.md)
- [WPF'de XAML](/dotnet/framework/wpf/advanced/xaml-in-wpf)
- [Veri bağlama (WPF)](/dotnet/framework/wpf/data/data-binding-wpf)
- [İş akışı biçimlendirmesi kullanma](http://go.microsoft.com/fwlink/?LinkId=98685)
