---
title: XML şema Tasarımcısı içerik modeli görünümü
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: e8db7c7d-31cf-479e-9dcc-299759891795
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d7f04c482149cbc063a3788dd6be44c643bae6a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751799"
---
# <a name="content-model-view"></a>İçerik Modeli Görünümü

İçerik modeli görünümü yerel ve genel şema düğümleri ve basit ve karmaşık türleri, öğeleri, model grupları, öznitelikleri ve öznitelik grupları dahil olmak üzere bileşenleri, grafik bir gösterimini sağlar. XML açıklamaları ve işleme talimatları içerik modeli görünümünde görüntülenemiyor. İçerik modeli görünümü iki bölme içerir: bir **çalışma** düğümlerin listesini içeren paneli [XML şema Tasarımcısı çalışma alanı](../xml-tools/xml-schema-designer-workspace.md)ve burada görebilirsiniz şema içerik modeli tasarım yüzeyi Seçili düğümleri **çalışma** paneli. İçerik modeli görünümü, XML şema Tasarımcısı araç ve içerik haritası çubuğunu de içerir.

 Aşağıdaki görüntüde **çalışma** paneli altı şema düğümleri içerir. `purchaseOrder` Düğümü seçildiğinde, **çalışma** panel ve tasarım yüzeyine görüntülenir.

 ![XML şema Tasarımcısı içerik modeli görünümü](../xml-tools/media/xsddesigner_contentmodelview.gif)

## <a name="workspace-panel"></a>Çalışma alanı paneli

 Düğümler için çalışma alanına ekledikten sonra düğüm listesi görünür **çalışma** içerik modeli görünümü panelini. Düğümler seçtiğinizde **çalışma** paneli, içerik modeli görünümü tasarım yüzeyine görünürler. Çalışma alanından düğümleri silmek için XSD Designer araç kullanın **çalışma** Masası bağlam menüsü veya **silmek** anahtarı.

 Düğümler ekleme hakkında daha fazla bilgi için "Ekleme düğümler için çalışma alanı" bölümüne bakın [XML şema Tasarımcısı çalışma alanı](../xml-tools/xml-schema-designer-workspace.md).

## <a name="design-surface"></a>Tasarım yüzeyi

 İçinde bir düğümü seçildiğinde **çalışma** paneli, düğümün ayrıntılarını görüntüleyebileceğiniz içerik modeli görünümü tasarım yüzeyine eklenir.

 Bir düğümün içerik modeli öğeleri ve özniteliklerinin ağaç düğümleri olarak görünen içeren genişletilebilir bir grafik ağacı temsil edilir. Varsayılan olarak, yalnızca bir düzey genişletilir. Compositors, tür adları, grupları ve diğer kapsayıcılar gibi diğer bilgileri öğeleri ve bunların içine öznitelikleri (genişletildiğinde) içinde dikey çubuk yerleştirilir. Dikey çubuk çift tıkladığınızda, yatay haline gelir ve ağaç daraltır. Yatay çubuk çift tıkladığınızda dikey haline gelir ve ağacını genişletir. Tüm düğümleri, dikey çubuk seçerek kapsayıcısında seçer. Bir öğenin genişletilmiş veya daraltılmış Genişleticileri bir düğüme sağ tarafta görünür.

 Tasarım yüzeyine boşsa, XML Düzenleyicisi'ni **XML Şeması Explorer**, ve filigran gösterilir. *Filigran* tüm XSD Tasarımcısı görünümleri bağlanan bir listesi verilmiştir. Şema kümesini hata varsa, aşağıdaki metni listesinin sonunda görüntülenir: "Görüntülemek ve kümesinde hataları düzeltmek için hata listesi kullanın."

## <a name="breadcrumb-bar"></a>İçerik haritası çubuğu

 Seçili düğümün şema kümesinde bulunduğu içerik modeli görünümü altındaki içerik haritası çubuğunu gösterir.

## <a name="context-menus"></a>Bağlam menüleri

 Tasarım yüzeyine bir öğeyi sağ veya **çalışma** panelinde, bir bağlam menüsü görüntülenir. Aşağıdaki tabloda, içerik modeli görünümü tasarım yüzeyi için kullanılabilir olan seçenekler açıklanmaktadır.

|Seçenek|Açıklama|
|------------|-----------------|
|**XML şema Gezgini'nde Göster**|Odağı üzerinde şema Explorer koyar ve şema kümesi düğümü vurgular.|
|**Grafik görünümünde göster**|Grafik görünümü geçer.|
|**Örnek XML oluştur**|Yalnızca genel öğeler için kullanılabilir. Bir genel öğesi için örnek bir XML dosyası oluşturur.|
|**Belge Göster**|Gösterir veya gizler ek açıklama/belge düğümü içeriği.|
|**Görüntü olarak dışarı aktarma diyagramı**|Tasarım yüzeyine bir XPS dosyasına kaydeder.|
|**Görünümü Kodu**|Seçili düğümün XML Düzenleyicisi'nde içeren dosyayı açar. Seçili öğeyi **XML Şeması Explorer** XML Düzenleyicisi'nde da seçilir.|
|**Özellik Penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|

 Aşağıdaki tabloda kullanılabilir seçenekler açıklanmaktadır **çalışma** paneli.

|Seçenek|Açıklama|
|------------|-----------------|
|**XML şema Gezgini'nde Göster**|Odağı üzerinde şema Explorer koyar ve şema kümesi düğümü vurgular.|
|**Grafik görünümünde göster**|Görünüm grafik geçirir.|
|**Çalışma alanını temizleyin**|Çalışma alanı ve tasarım yüzeyine temizler.|
|**Çalışma alanından kaldırın**|Çalışma alanı ve tasarım yüzeyine seçilen düğümleri kaldırır.|
|**Çalışma alanından seçimi dışında tümünü Kaldır**|Çalışma alanı ve tasarım yüzeyine seçili olmadığında düğümlerini kaldırır.|
|**Örnek XML oluştur**|Yalnızca genel öğeler için kullanılabilir. Bir genel öğesi için örnek bir XML dosyası oluşturur.|
|**Tümünü Seç**|Tüm düğümlerin seçer **çalışma** paneli.|
|**Görünümü Kodu**|Seçili düğümün XML Düzenleyicisi'nde içeren dosyayı açar. Seçili öğeyi **XML Şeması Explorer** XML Düzenleyicisi'nde da seçilir.|
|**Özellik Penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|

## <a name="properties-window"></a>Özellik penceresi

 Başlangıçta açmak için bağlam menüsünü kullanın **özellikleri** penceresi. Varsayılan olarak, **özellikleri** penceresi Visual Studio'nun sağ alt köşesinde görüntülenir. İçerik modeli görünümünde işlenen bir düğümüne tıkladığınızda, bu düğüm özelliklerini görüntülenir **özellikleri** penceresi.

## <a name="xsd-designer-toolbar"></a>XSD tasarımcı araç çubuğu

 İçerik modeli görünümü etkin olduğunda aşağıdaki XSD Designer araç çubuğu düğmeleri etkinleştirilir.

 ![XML şema Tasarımcısı araç çubuğu](../xml-tools/media/xsdcontentmodelviewtoolbar.gif)

|Seçenek|Açıklama|
|------------|-----------------|
|**Başlangıç görünümü göster**|Geçiş yapar [Başlat Görünüm](../xml-tools/start-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **Ctrl**+**1**.|
|**İçerik modeli görünümü göster**|Geçiş yapar [içerik modeli Görünüm](../xml-tools/content-model-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **Ctrl**+**2**.|
|**Grafik Görünümü Göster**|Geçiş yapar [grafik görünümü](../xml-tools/graph-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **Ctrl**+**3**.|
|**Çalışma alanını temizleyin**|Çalışma alanı ve tasarım yüzeyine temizler.|
|**Çalışma alanından kaldırın**|Çalışma alanı ve tasarım yüzeyine seçilen düğümleri kaldırır.|
|**Çalışma alanından seçimi dışında tümünü Kaldır**|Çalışma alanı ve tasarım yüzeyine seçili olmadığında düğümlerini kaldırır.|
|**Belge Göster**|Gösterir veya gizler ek açıklama/belge düğümü içeriği.|

## <a name="panscroll"></a>PAN/kaydırma

 Kaydırma çubukları kullanarak veya tutarak tasarım yüzeyine kaydırabilirsiniz **Ctrl** anahtar'ı tıklatın ve fareyi sürükleyin. ' I tıklatın ve sürükleyin kullanarak tasarım yüzeyi PAN imleci dört yönde çapraz dört oklar değiştirir.

## <a name="undoredo"></a>Geri alma/yineleme

 Geri alma/yineleme yeteneği, aşağıdaki eylemler için içerik modeli görünümünde etkinleştirilir:

-   Tek bir düğüm sürükleme ve bırakma ekleniyor.

-   Şema Explorer'da arama sonuçları penceresinden birden çok düğüm ekleme.

-   Düğüm başlangıç görünümünden ekleme.

-   Tek veya birden çok düğüm siliniyor.

## <a name="zoom"></a>Yakınlaştır

 Yakınlaştırma içerik modeli görünümün sağ alt köşesinde kullanılabilir.

 Yakınlaştırma aşağıdaki yollarla denetlenebilir:

-   Tutarak **Ctrl** anahtar ve fare dönmesini Tekerlek fare içerik modeli görünümü yüzeyini getirildiğinde.

-   Kaydırıcı denetimi kullanarak. Kaydırıcı geçerli yakınlaştırma düzeyini gösterir.

Bunu seçtiğinizde, üzerine getirin veya kullanmak yakınlaştırma kaydırıcıyı donuk **Ctrl** yakınlaştırma için fare tekerleğinin; her zaman saydamdır.

## <a name="xml-editor-integration"></a>XML Düzenleyicisi tümleştirme

 İleri ve geri arasında geçiş yapabilirsiniz **XSD Tasarımcısı** ve bağlam menüsünü kullanarak XML Düzenleyicisi'ni.

 XML Düzenleyicisi'nde ayarlamak şema değişiklik yaparsanız, değişiklikleri içerik modeli görünümünde eşitlenir. Daha fazla bilgi için bkz: [XML Düzenleyicisi ile tümleştirme](../xml-tools/integration-with-xml-editor.md).

## <a name="see-also"></a>Ayrıca bkz.

- [XML Şema Tasarımcısı Çalışma Alanı](../xml-tools/xml-schema-designer-workspace.md)