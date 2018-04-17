---
title: XML şema Explorer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 2fc39e98-b194-456b-a452-cfafb0a52d66
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 84aead3cf496a28e67e6440fb77b8cbf4aca6462
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="xml-schema-explorer"></a>XML şema Gezgini
XML şema Explorer XML Şeması Tanım Dili (XSD) şemalarda çalışmanıza olanak sağlamak için Microsoft Visual Studio ve XML düzenleyicisini tümleşiktir. Bir XML Şeması dosyayı açtığınızda **şema ayarlamak** düğümü XML Şeması Gezgini'nde görüntülenir. Tüm dahil, içe aktarılan ya da yeniden tanımlanan şemaları aracılığıyla başvurulan herhangi bir dosya yanı sıra, hedef dosya için bir `include` veya `import` deyimi, ayrıca XML Şeması Gezgini'nde görünür.  
  
 XML şema Explorer aşağıdakileri sağlar:  
  
-   Şema kümesini hızlı bir genel bakış alın.  
  
-   Gözat ve ağaç gidin.  
  
-   Anahtar sözcüğü ve şema özgü aramaları gerçekleştirin. Daha fazla bilgi için bkz: [şema ayarlamak arama](../xml-tools/searching-the-schema-set.md).  
  
-   Arama sonuçlarını grafik görünümü veya içerik Modle görünümü ekleme  
  
-   Belge sipariş, türü veya ad ağacında sıralayın. Daha fazla bilgi için bkz: [sıralama, filtreleme ve gruplandırma](../xml-tools/sorting-filtering-and-grouping-xml-schema-explorer.md).  
  
-   XML Düzenleyicisi'ni açın ve XSD dosyası kodu konumlarda atlanacak. Daha fazla bilgi için bkz: [tümleştirme XML Düzenleyicisi ile](../xml-tools/integration-with-xml-editor.md).  
  
-   Genel öğeler için XML örneği oluşturur.  
  
XML şema Gezgini ağaç görünümü ayarlamak şemanın hiyerarşik bir görünümü sağlar. XML şema Explorer arama, filtreleme, gezinti ve sıralama de sağlar. XML şema Explorer erişmek için aşağıdakilerden birini yapın:  
  
-   Kullanıyorsanız [Başlangıç'ı](../xml-tools/start-view.md), tıklatın **XML Şeması Explorer** bağlantı.  
  
-   Kullanıyorsanız [grafik görünümü](../xml-tools/graph-view.md) veya [içerik modeli görünümü](../xml-tools/content-model-view.md) ve çalışma alanınızda düğümünüz, bağlam menüsü XML Şeması Explorer seçmek için kullanın.  
  
-   XML şema Explorerfrom öğesini de seçebilirsiniz **Görünüm** menüsü.  
  
-   XML şema Explorerfrom bir Visual Basic bir .xsd dosyasıyla ilişkili XML değişmez değer içeren bir .vb dosyası erişebilir. Şemanın XML Şeması Explorer'da ayarlayın, bir XML düğümü sabit bir XML veya XML ad alanı içe sağ tıklatın ve seçin görmek için **Göster şema Explorer'da** komutu. Daha fazla bilgi için bkz: [XML Şeması Gezgini ile XML değişmez tümleştirme](../xml-tools/integration-of-xml-literals-with-xml-schema-explorer.md).  
  
## <a name="tree-view"></a>Ağaç görünümü  
 XML şema Explorer ağaç yapısında önceden derlenmiş şema kümesi bilgilerini görüntüler. Ağaç yapısı şu şekilde düzenlenmiştir:  
  
-   En üst düzeyinde şema düğümü ayarlanır.  
  
-   İkinci düzey ad alanları içerir.  
  
-   Üçüncü düzey dosyaları içerir.  
  
-   Dördüncü düzey genel düğümleri içerir. Bu içerebilir öğeleri, gruplar, karmaşık türler, basit türler, öznitelikler, öznitelik grupları ve `include`, `import`, ve `redefine` deyimleri.  
  
Bir ağaç yapısı örneği verilmiştir:  
  
![XML şema Explorer](../xml-tools/media/xmlschemaexplorer.gif "XMLSchemaExplorer")  
  
## <a name="selection-and-activation"></a>Seçim ve etkinleştirme  
 Vurgulayın ve bir düğümü seçmek için bir kez şema Explorer'ın tıklatın.  
  
 Bir düğüm etkinleştirmek için çift tıklayın veya basın **Enter** düğümü seçildiğinde.  
  
-   Bir düğüm etkinleştirme dosyayı açar, bu düğüm tanımlanır (dosya zaten açık değilse) ve düğüm dosyasında seçer.  
  
-   Bir dosya düğümü etkinleştirme (zaten açık değilse) seçili dosyayı açar ve vurgular `<schema>` düğümü.  
  
-   Bir SchemaSet veya bir ad alanı düğümü etkinleştirme hiçbir şey yapmaz.  
  
## <a name="draging-and-dropping-nodes"></a>Draging ve düğümler bırakma  
 Sürükleme ve genel düğümleri, dosya düğümleri ve ad alanı düğümleri bir XSD Tasarımcısı görünümü üzerine bırakın. Geçerli Görünüm ise [Başlangıç'ı](../xml-tools/start-view.md), görünümü açın bir düğüm sürükleme açılır [grafik görünümü](../xml-tools/graph-view.md). Geçerli Görünüm ise [içerik modeli görünümü](../xml-tools/content-model-view.md) veya grafik görünümü, görünümün bir düğüm üzerine bıraktığınızda değiştirmez.  
  
 Görünüm dosyalarda bırakarak ekleyecek genel tüm düğümleri dosyasında [XSD Designer çalışma](../xml-tools/xml-schema-designer-workspace.md). Ad alanları görünümünden bırakmayı tüm genel düğümlerini ad alanında çalışma alanına ekleyecek. Çalışma alanı görünüm arasında paylaşılır.  
  
 Sürükleme ve yerel düğümler veya içeri aktarmalar bırakın.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
-   [Şema Kümesini Arama](../xml-tools/searching-the-schema-set.md)  
  
-   [Sıralama, filtreleme ve gruplandırma](../xml-tools/sorting-filtering-and-grouping-xml-schema-explorer.md)  
  
-   [Bağlam menüleri](../xml-tools/context-menus-xml-schema-explorer.md)  
  
-   [XML Değişmez Değerlerinin XML Şeması Gezgini ile Tümleştirilmesi](../xml-tools/integration-of-xml-literals-with-xml-schema-explorer.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl Yapılır: XML Şema Gezgininden Çalışma Alanına Düğüm Ekleme](../xml-tools/how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer.md)