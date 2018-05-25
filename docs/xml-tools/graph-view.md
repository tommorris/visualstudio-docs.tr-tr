---
title: XML şema Tasarımcısı grafik görünümü
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: 5881afde-3f24-4eb9-bff8-6cb3fc8aade7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b95d8396cd96741187ae0146d2f727c3433b3ef
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="graph-view"></a>Grafik görünümü

Grafik görünümü genel şeması düğümlerin ve düğümler arasındaki ilişkileri grafik bir gösterimini sağlar. Grafik görünümü, tasarım yüzeyine ayarlamak şema düzenini değiştirmek izin vermediğini unutmayın. Grafik görünümü, XML şema Tasarımcısı araç ve içerik haritası çubuğunu de içerir.

 Aşağıdaki resimde, tasarım yüzeyine altı genel düğümlerle grafik görünümü gösterir.

 ![XML şema Tasarımcısı grafik görünümü](../xml-tools/media/xsddesigner_graphview.gif "XSDDesigner_GraphView")

## <a name="design-surface"></a>Tasarım yüzeyi

 Grafik görünümünün tasarım yüzeyi içeriğini görüntüler [XML şema Tasarımcısı çalışma alanı](../xml-tools/xml-schema-designer-workspace.md). Çalışma alanı şema kümesinden genel tüm düğümleri içeriyorsa, grafik görünümü tasarım yüzeyine düğümleri gösterilir ve ilişkilerine sahip düğümler arasında oklarla çizilir.

 Grafik görünümünde bir düğüm çift XML düzenleyicisini getirir.

 Seçili düğümler çalışma alanından silmek için XSD Designer araç kullanın veya **silmek** anahtarı.

 Tasarım yüzeyine boşsa, XML Düzenleyicisi'ni **XML Şeması Explorer**, ve filigran gösterilir. *Filigran* tüm XSD Tasarımcısı görünümleri bağlanan bir listesi verilmiştir.

 ![XSD Tasarımcısı; Grafik görünümü](../xml-tools/media/xsdgraphviewwatermark.gif "XSDGraphViewWatermark")

 Şema kümesini hata varsa, aşağıdaki metni listesinin sonunda görüntülenir: "Görüntülemek ve kümesinde hataları düzeltmek için hata listesi kullanın."

## <a name="breadcrumb-bar"></a>İçerik haritası çubuğu

 İçerik haritası çubuk grafik görünümü altındaki seçili düğümün şema kümesinde nerede bulunduğunu gösterir. Birden çok öğe seçildiğinde, içerik haritası çubuğunda boş olacaktır.

## <a name="context-menu"></a>Bağlam menüsü

 Aşağıdaki tablo, grafik görünümü tasarım yüzeyine tüm düğümler için kullanılabilir seçenekler açıklanmaktadır.

|Seçenek|Açıklama|
|------------|-----------------|
|**XML şema Gezgini'nde Göster**|Odağı üzerinde şema Explorer koyar ve şema kümesi düğümü vurgular.|
|**Grafik görünümünde göster**|(Gri) grafik görünümü geçer.|
|**Örnek XML oluştur**|Yalnızca genel öğeler için kullanılabilir. Bir genel öğesi için örnek bir XML dosyası oluşturur.|
|**Çalışma alanını temizleyin**|Çalışma alanı ve tasarım yüzeyine temizler.|
|**Çalışma alanından kaldırın**|Çalışma alanı ve tasarım yüzeyine seçilen düğümleri kaldırır.|
|**Çalışma alanından seçimi dışında tümünü Kaldır**|Çalışma alanı ve tasarım yüzeyine seçili olmadığında düğümlerini kaldırır.|
|**Görüntü olarak dışarı aktarma diyagramı**|Tasarım yüzeyine bir XPS dosyasına kaydeder.|
|**Tümünü Seç**|Tasarım yüzeyine tüm düğümlerde seçer.|
|**Görünümü Kodu**|Seçili düğümün XML Düzenleyicisi'nde içeren dosyayı açar. Seçili öğeyi **XML Şeması Explorer** XML Düzenleyicisi'nde da seçilir.|
|**Özellik Penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|

 Yukarıda açıklanan ortak seçeneklerin yanı sıra genel öğeleri için bağlam menüsünde de aşağıdaki seçenekler vardır:

|Seçenek|Açıklama|
|------------|-----------------|
|**Tür tanımı Ekle**|Temel türü diyagrama ekler.|
|**Tüm başvurular ekleyin**|Öğesine bakın ve aralarındaki ilişkilerin göstermek amacıyla oklar çizer tüm düğümleri ekler.|
|**Değiştirme grubunun üyeleri Ekle**|Tüm değiştirme grup üyelerine ekler. Öğe head veya bir değiştirme grubunun üyesi ise bu seçenek görünümünde görüntülenir.|
|**Örnek XML oluştur**|Bir genel öğesi için örnek bir XML dosyası oluşturur.|

 Yukarıda açıklanan ortak seçeneklerin yanı sıra genel basit ve genel karmaşık türler için bağlam menüsünde de aşağıdaki seçenekler vardır:

|Seçenek|Açıklama|
|------------|-----------------|
|**Temel türü ekleme**|Seçilen tür genel bir türden türetilmiş, seçili türün temel türünü ekler.|
|**Tüm başvurular ekleyin**|Seçilen türündeki tüm başvuruları ekler. Bu öğeleri ve özniteliklerinin seçilen tür ve seçilen türden türetilmiş türler içerir.|
|**Tüm türetilmiş türler ekleme**|Doğrudan ve dolaylı olarak seçilen türünden türetilen tüm türleri ekler.|
|**Tüm üst öğelerinden ekleme**|Tüm üst (Temel) türleri ekler.|

 Yukarıda açıklanan ortak seçeneklerin yanı sıra genel gruplar ve öznitelik grupları için bağlam menüsünde de aşağıdaki seçenekler vardır:

|Seçenek|Açıklama|
|------------|-----------------|
|**Tüm başvurular ekleyin**|Grubu ve aralarındaki ilişkilerin göstermek amacıyla oklar çizer tüm düğümleri ekler.|
|**Tüm üyeleri Ekle**|Aralarındaki ilişkilerin göstermek amacıyla oklar çizer ve grubun tüm üyelerini ekler.|

 Yukarıda açıklanan ortak seçeneklerine addtion içinde genel öznitelikler için bağlam menüsünde de aşağıdaki seçenekler vardır:

|Seçenek|Açıklama|
|------------|-----------------|
|**Tüm başvurular ekleyin**|Grubu ve aralarındaki ilişkilerin göstermek amacıyla oklar çizer tüm düğümleri ekler.|

## <a name="properties-window"></a>Özellik penceresi

 Başlangıçta açmak için bağlam menüsünü kullanın **özellikleri** penceresi. Varsayılan olarak, **özellikleri** penceresi Visual Studio'nun sağ alt köşesinde görüntülenir. İçerik modeli görünümünde işlenen bir düğümüne tıkladığınızda, bu düğüm özelliklerini görüntülenmesi **özellikleri** penceresi.

## <a name="xsd-toolbar"></a>XSD araç çubuğu

 Grafik görünümü etkin olduğunda aşağıdaki XSD araç çubuğu düğmeleri etkinleştirilir.

 ![XML şema Tasarımcısı araç](../xml-tools/media/xsdgraphviewtoolbar.gif "XSDGraphViewToolbar")

|Seçenek|Açıklama|
|------------|-----------------|
|**Başlangıç görünümü göster**|Geçiş yapar [Başlat Görünüm](../xml-tools/start-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **Ctrl**+**1**.|
|**İçerik modeli görünümü göster**|Geçiş yapar [içerik modeli Görünüm](../xml-tools/content-model-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **Ctrl**+**2**.|
|**Grafik Görünümü Göster**|Geçiş yapar [grafik görünümü](../xml-tools/graph-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **Ctrl**+**3**.|
|**Çalışma alanını temizleyin**|Çalışma alanı ve tasarım yüzeyine temizler.|
|**Çalışma alanından kaldırın**|Çalışma alanı ve tasarım yüzeyine seçilen düğümleri kaldırır.|
|**Çalışma alanından seçimi dışında tümünü Kaldır**|Çalışma alanı ve tasarım yüzeyine seçili olmadığında düğümlerini kaldırır. Bu seçenek, içerik modeli görünümü ve grafik görünümünde etkindir.|
|**Soldan sağa**|Grafik görünümü düzeninde bir soldan sağa hiyerarşik gösterimine düğümlerinin değiştirir. Bu seçenek, klavye kısayolunu kullanarak erişilebilir: **Alt**+**sağ ok**.|
|**Sağdan sola**|Grafik görünümü düzeninde bir sağdan sola hiyerarşik gösterimine düğümlerinin değiştirir. Bu seçenek, klavye kısayolunu kullanarak erişilebilir: **Alt**+**sol ok**.|
|**Üstten alta**|Grafik görünümü düzeninde bir üst-alt hiyerarşik gösterimine düğümlerinin değiştirir. Bu seçenek, klavye kısayolunu kullanarak erişilebilir: **Alt**+**aşağı ok**.|
|**Aşağıdan yukarıya**|Grafik görünümü düzende bottom-to-top hiyerarşik gösterimini düğümler için değiştirir. Bu seçenek, klavye kısayolunu kullanarak erişilebilir: **Alt**+**yukarı ok**.|

## <a name="panscroll"></a>PAN/kaydırma

 Kaydırma çubukları kullanarak veya tutarak tasarım yüzeyine kaydırabilirsiniz **Ctrl** anahtar'ı tıklatın ve fareyi sürükleyin. ' I tıklatın ve sürükleyin kullanarak tasarım yüzeyi PAN imleci dört yönde çapraz dört oklar değiştirilir.

## <a name="undoredo"></a>Geri alma/yineleme

 Geri alma/yineleme yeteneği, aşağıdaki eylemler için Grafik görünümünde etkinleştirilir:

-   Tek bir düğüm sürükleme ve bırakma ekleniyor.

-   Şema Explorer veya başlangıç'ı sorgularda arama sonuçları penceresinden birden çok düğüm ekleme.

-   Tek veya birden çok düğüm siliniyor.

## <a name="zoom"></a>Yakınlaştır

 Yakınlaştırma grafik görünümü sağ alt köşesinde kullanılabilir.

 Yakınlaştırma aşağıdaki yollarla denetlenebilir:

-   Tutarak **Ctrl** anahtar ve fare dönmesini Tekerlek fare grafik görünümü yüzeyini getirildiğinde.

-   Kaydırıcı denetimi kullanarak. Kaydırıcı geçerli yakınlaştırma düzeyini gösterir.

Bunu seçtiğinizde, üzerine getirin veya kullanmak yakınlaştırma kaydırıcıyı donuk **Ctrl** yakınlaştırma için fare tekerleğinin; her zaman saydamdır.

## <a name="xml-editor-integration"></a>XML Düzenleyicisi tümleştirme

 Bir düğüm tıklayarak ve Görünüm Kodu bağlam menüsünü kullanarak grafik görünümü ve XML düzenleyicisini arasında ileri ve geri geçebilirsiniz.

 XML Düzenleyicisi'nde ayarlamak şema değişiklik yaparsanız, değişiklikleri Grafik görünümünde eşitlenir. Daha fazla bilgi için bkz: [XML Düzenleyicisi ile tümleştirme](../xml-tools/integration-with-xml-editor.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Tasarım yüzeyi](../xml-tools/xml-schema-designer-workspace.md)