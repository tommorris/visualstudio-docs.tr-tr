---
title: XML şemaları ve verileri belge düzeyi özelleştirmelerinde | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML schemas [Office development in Visual Studio]
- schemas [Office development in Visual Studio]
- XML [Office development in Visual Studio], XML schemas
- XML schemas [Office development in Visual Studio], about XML schemas and data
- Office development in Visual Studio, XML
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a2706e3c83ea06e707d58cb84b31c8983d515798
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/08/2018
ms.locfileid: "35237607"
---
# <a name="xml-schemas-and-data-in-document-level-customizations"></a>Belge Düzeyi Özelleştirmelerde XML Şemaları ve Verileri
  **Önemli** Microsoft Word ile ilgili bu konudaki ayarlanan bilgileri avantajı ve kişiler ve kimlerin bulunur Amerika Birleşik Devletleri ve alt bölgeleri dışında veya kullanan kuruluşlar için özel olarak sunulan ya da geliştirme çalışan programlar Ocak Microsoft uygulaması belirli işlevlerin ne zaman kaldırıldı 2010'dan önce Microsoft tarafından lisanslanan Microsoft Word ürünleri için özel XML Microsoft Word içinden ilgili. Bu bilgiler Microsoft Word ile ilgili okumak veya kişiler veya Amerika Birleşik Devletleri ya da kimin kullanarak veya Microsoft tarafından 10 Ocak 2010 sonra lisanslı Microsoft Word ürünleri hakkında çalışan programlar geliştirme kendi bölgeleri kuruluşlar tarafından kullanılan ; Bu ürün bu tarihten önce lisanslı veya satın alınan ve Amerika Birleşik Devletleri dışında kullanmak için lisanslı ürünleri ile aynı davranır değil.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Microsoft Office Excel ve Microsoft Office Word belgelerinize şemaları eşleme yeteneği sağlar. Bu özellik, belge ve XML veri alma ve verme basitleştirebilirsiniz.

 Visual Studio çıkarır şema öğeleri belge düzeyi özelleştirmelerinde programlama modeli denetimler olarak eşlenmiş. Excel için Visual Studio veritabanları, Web Hizmetleri ve nesneleri verilere denetimler bağlama için destek ekler. Word ve Excel için Visual Studio şema eşlenmiş bir belgeyle çözümleriniz için bir Gelişmiş son kullanıcı deneyimi oluşturmak için kullanılabilir Eylemler bölmeleri için destek ekler. Daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md).

> [!NOTE]
>  Excel çözümleri, çok parçalı XML şemaları kullanamazsınız.

## <a name="objects-created-when-schemas-are-attached-to-excel-workbooks"></a>Excel çalışma kitaplarına şemaları eklendiğinde oluşturulan nesneler
 Bir çalışma kitabına bir şema eklediğinizde, Visual Studio, otomatik olarak birçok nesne oluşturur ve projenize ekler. Excel tarafından yönetildiğinden bu nesneler, Visual Studio araçları kullanarak silinmemelidir. Bunları silmek için çalışma sayfasından eşlenmiş öğeleri kaldırmak veya Excel araçlarını kullanarak şema ayırma.

 İki ana nesne vardır:

-   XML Şeması (XSD dosyası). Çalışma kitabındaki her şema için Visual Studio şema projeye ekler. Bu, bir XSD uzantı ile bir proje öğesi olarak görünür **Çözüm Gezgini**.

-   Yazılmış bir <xref:System.Data.DataSet> sınıfı. Bu sınıf şema üzerinde temel alınarak oluşturulur. Bu veri kümesi sınıfı görünürdür **sınıf görünümü**.

## <a name="objects-created-when-schema-elements-are-mapped-to-excel-worksheets"></a>Şema öğeleri Excel çalışma sayfalarına eşlendiğinde oluşturulan nesneler
 Bir şema öğesinden eşlediğinizde **XML kaynağı** görev bölmesi bir çalışma sayfasına, Visual Studio otomatik olarak birçok nesne oluşturur ve bunları projenize ekler:

-   Denetler. Çalışma kitabı eşlenen her nesne için bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> denetimi (şema öğeleri için yinelenmeyen) veya bir <xref:Microsoft.Office.Tools.Excel.ListObject> (tekrarlayan şema öğeleri için) denetim programlama modelinde oluşturulur. <xref:Microsoft.Office.Tools.Excel.ListObject> Denetimi sadece eşlemeler ve eşlenen nesneler çalışma kitabından silindiğinde silinebilir. Denetimleri hakkında daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).

-   BindingSource. Oluştururken bir <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> çalışma sayfasına yinelenmeyen şema öğesi eşleyerek bir <xref:System.Windows.Forms.BindingSource> oluşturulur ve <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> denetimin bağlı <xref:System.Windows.Forms.BindingSource>. Bağlamanız gerekir <xref:System.Windows.Forms.BindingSource> yazılı örneği gibi belge eşlenmiş şema eşleşen veri kaynağı örneği <xref:System.Data.DataSet> oluşturulan sınıf. Bağlama ayarlayarak oluşturmak <xref:System.Windows.Forms.BindingSource.DataSource%2A> ve <xref:System.Windows.Forms.BindingSource.DataMember%2A> sunulan özellikler **özellikleri** penceresi.

    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource> İçin oluşturulmamış <xref:Microsoft.Office.Tools.Excel.ListObject> nesneleri. El ile bağlamanız gerekir <xref:Microsoft.Office.Tools.Excel.ListObject> ayarlayarak veri kaynağına <xref:System.Windows.Forms.BindingSource.DataSource%2A> ve <xref:System.Windows.Forms.BindingSource.DataMember%2A> özelliklerinde **özellikleri** penceresi.

### <a name="office-mapped-schemas-and-the-visual-studio-data-sources-window"></a>Office eşlenmiş şemaları ve Visual Studio veri kaynakları penceresi
 Her iki eşlenmiş şema işlevselliğini Office ve Visual Studio **veri kaynakları** penceresi, raporlama ya da düzenlemek için bir Excel çalışma sayfasındaki verileri sunmalarına yardımcı olabilir. Her iki durumda da Excel çalışma sayfasına veri öğeleri sürükleyebilirsiniz. Her iki yöntemi yoluyla veri bağlaması denetimleri oluşturmak bir <xref:System.Windows.Forms.BindingSource> gibi bir veri kaynağına bir <xref:System.Data.DataSet> veya bir Web hizmeti.

> [!NOTE]
>  Bir çalışma sayfasına tekrarlanan bir şema öğesi eşlediğinizde, Visual Studio oluşturur bir <xref:Microsoft.Office.Tools.Excel.ListObject>. <xref:Microsoft.Office.Tools.Excel.ListObject> Otomatik olarak verilerine bağlı <xref:System.Windows.Forms.BindingSource>. El ile bağlamanız gerekir <xref:Microsoft.Office.Tools.Excel.ListObject> ayarlayarak veri kaynağına <xref:System.Windows.Forms.BindingSource.DataSource%2A> ve <xref:System.Windows.Forms.BindingSource.DataMember%2A> özelliklerinde **özellikleri** penceresi.

 Aşağıdaki tabloda bazı iki yöntem arasındaki farklar gösterilmektedir.

|XML Şeması|Veri Kaynakları penceresi|
|----------------|-------------------------|
|Office arabirimini kullanır.|Kullanan **veri kaynakları** Visual Studio'daki.|
|Veri alma ve XML dosyalarından verme için yerleşik Office özelliklerini etkinleştirir.|İçeri aktarma sağlamak ve işlevselliği programlı olarak dışarı aktarma.|
|Oluşturulan denetimleri verilerle doldurmak için kod yazmanız gerekir.|Konsolundan denetimleri **veri kaynakları** penceresi sahip onları, veritabanı sunucularını kullandığınızda gerekli bağlantı dizeleri birlikte doldurmak için otomatik olarak oluşturulan kod.|

## <a name="behavior-when-schemas-are-attached-to-word-documents"></a>Word belgelerine şemaları eklendiğinde davranışı
 Belge düzeyi Office projesinde kullanılan bir Word belgesi için bir şema eklediğinizde veri nesneleri oluşturulmaz. Ancak, bir şemasını belgenize eşlediğinizde denetimleri oluşturulur. Denetim türünü hangi eşledikten öğesi türüne bağlıdır; öğeleri oluşturmak yinelenen <xref:Microsoft.Office.Tools.Word.XMLNodes> denetimleri ve yinelenmeyen öğeleri oluşturmak <xref:Microsoft.Office.Tools.Word.XMLNode> kontrol eder. Daha fazla bilgi için bkz: [XMLNodes denetimi](../vsto/xmlnodes-control.md) ve [XMLNode denetimi](../vsto/xmlnode-control.md).

## <a name="deployment-of-solutions-that-include-xml-schemas"></a>XML şemaları dahil çözümleri dağıtımı
 Belgeye eşlenen bir XML Şeması kullanan bir çözümü dağıtmak için bir yükleyici oluşturmanız gerekir. Yükleyici, kullanıcının bilgisayarındaki şema kitaplığındaki şema kaydetmelisiniz. Şema kaydettirmezseniz Word belgesinde kullanıcı açıldığında olan öğelere dayanmaktadır geçici bir şema oluşturduğundan çözümü çalışmaya devam edecektir. Ancak, kullanıcı karşı veya projesi oluşturmak için kullanılan şema doğrulama gerçekleştirmek mümkün olmayacaktır. Yükleyiciler hakkında daha fazla bilgi için bkz: [dağıtma uygulamaları, hizmetleri ve bileşenleri](../deployment/deploying-applications-services-and-components.md).

 Kod projenize Şema Kitaplığı'nda ve kayıtlı olup olmadığını denetlemek için de ekleyebilirsiniz. Değilse, kullanıcıyı uyarır.

 [!code-vb[Trin_VstcoreDataWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataWordVB/ThisDocument.vb#1)]
 [!code-csharp[Trin_VstcoreDataWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreDataWordCS/ThisDocument.cs#1)]

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: Şemaları Visual Studio İçindeki Word Belgeleriyle Eşleştirme](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)
- [Nasıl Yapılır: Şemaları Visual Studio İçindeki Çalışma Sayfalarıyla Eşleştirme](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)