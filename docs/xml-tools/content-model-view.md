---
title: "İçerik modeli View | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8db7c7d-31cf-479e-9dcc-299759891795
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 582082504b713988039af609d59150715f75ecfe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="content-model-view"></a>İçerik modeli görünümü
İçerik modeli görünümü yerel ve genel şema düğümleri ve basit ve karmaşık türleri, öğeleri, model grupları, öznitelikleri ve öznitelik grupları dahil olmak üzere bileşenleri, grafik bir gösterimini sağlar. XML açıklamaları ve işleme talimatları içerik modeli görünümünde görüntülenemiyor. İçerik modeli görünümü iki bölme içerir: bir **çalışma** düğümlerin listesini içeren paneli [XML şema Tasarımcısı çalışma](../xml-tools/xml-schema-designer-workspace.md)ve burada görebilirsiniz şema içerik modeli tasarım yüzeyi Seçili düğümleri **çalışma** paneli. İçerik modeli görünümü, XML şema Tasarımcısı araç ve içerik haritası çubuğunu de içerir.  
  
 Aşağıdaki görüntüde, çalışma Masası altı şema düğümleri içerir. `purchaseOrder` Düğüm Workpace panelinde seçilir ve tasarım yüzeyine görüntülenir.  
  
 ![XML şema Tasarımcısı içerik modeli görünümü](../xml-tools/media/xsddesigner_contentmodelview.gif "XSDDesigner_ContentModelView")  
  
## <a name="workspace-panel"></a>Çalışma alanı paneli  
 Düğümler için çalışma alanına ekledikten sonra düğüm listesi görünür **çalışma** içerik modeli görünümü panelini. Düğümler seçtiğinizde **çalışma** paneli, içerik modeli görünümü tasarım yüzeyine görünürler. Workpsace düğümleri silmek için XSD Designer araç kullanmak **çalışma** Masası bağlam menüsü veya DELETE anahtar.  
  
 Düğümler ekleme hakkında daha fazla bilgi için "Ekleme düğümler için çalışma alanı" bölümüne bakın [XML şema Tasarımcısı çalışma](../xml-tools/xml-schema-designer-workspace.md).  
  
## <a name="design-surface"></a>Tasarım yüzeyi  
 Çalışma Masası'ndaki bir düğümü seçildiğinde, düğümün ayrıntılarını görüntüleyebileceğiniz içerik modeli görünümü tasarım yüzeyine eklenir.  
  
 Bir düğümün içerik modeli öğeleri ve özniteliklerinin ağaç düğümleri olarak görünen içeren genişletilebilir bir grafik ağacı temsil edilir. Varsayılan olarak, yalnızca bir düzey genişletilir. Compositors, tür adları, grupları ve diğer kapsayıcılar gibi diğer bilgileri öğeleri ve bunların içine öznitelikleri (genişletildiğinde) içinde dikey çubuk yerleştirilir. Dikey çubuk çift tıkladığınızda, yatay haline gelir ve ağaç daraltır. Yatay çubuk çift tıkladığınızda dikey haline gelir ve ağacını genişletir. Dikey çubuk seçilmesi tüm düğümleri kapsayıcısında seçer. Bir öğenin genişletilmiş veya daraltılmış Genişleticileri bir düğüme sağ tarafta görünür.  
  
 Tasarım yüzeyine boş ise, XML Düzenleyicisi'ni, XML Şeması Gezgini ve filigran gösterilir. *Filigran* tüm XSD Tasarımcısı görünümleri bağlanan bir listesi verilmiştir. Şema kümesini hata varsa, aşağıdaki metni listesinin sonunda görüntülenir: "Görüntülemek ve kümesinde hataları düzeltmek için hata listesi kullanın."  
  
## <a name="breadcrumb-bar"></a>İçerik haritası çubuğu  
 Seçili düğümün şema kümesinde bulunduğu içerik modeli görünümü altındaki içerik haritası çubuğunu gösterir.  
  
## <a name="context-menus"></a>Bağlam menüleri  
 Tasarım yüzeyi veya çalışma panelinde bir öğeyi sağ tıklattığınızda, bağlam menüsü görüntülenir. Aşağıdaki tabloda, içerik modeli görünümü tasarım yüzeyi için kullanılabilir olan seçenekler açıklanmaktadır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**XML şema Gezgini'nde Göster**|Odağı üzerinde şema Explorer koyar ve şema kümesi düğümü vurgular.|  
|**Grafik görünümünde göster**|Grafik görünümü geçer.|  
|**Örnek XML oluştur**|Yalnızca genel öğeler için kullanılabilir. Bir genel öğesi için örnek bir XML dosyası oluşturur.|  
|**Belge Göster**|Gösterir veya gizler ek açıklama/belge düğümü içeriği.|  
|**Diyagram görüntü olarak dışarı aktar...**|Tasarım yüzeyine bir XPS dosyasına kaydeder.|  
|**Görünümü Kodu**|Seçili düğümün XML Düzenleyicisi'nde içeren dosyayı açar. XML şema Explorer'da seçili öğe ayrıca XML Düzenleyicisi'nde seçili olur.|  
|**Özellik Penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|  
  
 Aşağıdaki tabloda çalışma paneli kullanılabilir seçenekler açıklanmaktadır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**XML şema Gezgini'nde Göster**|Odağı üzerinde şema Explorer koyar ve şema kümesi düğümü vurgular.|  
|**Grafik görünümünde göster**|Görünüm grafik geçirir.|  
|**Çalışma alanını temizleyin**|Çalışma alanı ve tasarım yüzeyine temizler.|  
|**Çalışma alanından kaldırın**|Çalışma alanı ve tasarım yüzeyine seçilen düğümleri kaldırır.|  
|**Çalışma alanından seçimi dışında tümünü Kaldır**|Çalışma alanı ve tasarım yüzeyine seçili olmadığında düğümlerini kaldırır.|  
|**Örnek XML oluştur**|Yalnızca genel öğeler için kullanılabilir. Bir genel öğesi için örnek bir XML dosyası oluşturur.|  
|**Tümünü Seç**|Tüm düğümleri çalışma panelinde seçer.|  
|**Görünümü Kodu**|Seçili düğümün XML Düzenleyicisi'nde içeren dosyayı açar. XML şema Explorer'da seçili öğe ayrıca XML Düzenleyicisi'nde seçili olur.|  
|**Özellik Penceresi**|Açılır **özellikleri** (Bu zaten açık değilse) penceresi. Bu pencere düğüm hakkındaki bilgileri görüntüler.|  
  
## <a name="properties-window"></a>Özellikler Penceresi  
 Başlangıçta açmak için bağlam menüsünü kullanın **özellikleri** penceresi. Varsayılan olarak, **özellikleri** penceresi Visual Studio'nun sağ alt köşesinde görüntülenir. İçerik modeli görünümünde işlenen bir düğümüne tıkladığınızda, bu düğüm özelliklerini görüntülenmesi **özellikleri** penceresi.  
  
## <a name="xsd-designer-toolbar"></a>XSD tasarımcı araç çubuğu  
 İçerik modeli görünümü etkin olduğunda aşağıdaki XSD Designer araç çubuğu düğmeleri etkinleştirilir.  
  
 ![XML şema Tasarımcısı araç](../xml-tools/media/xsdcontentmodelviewtoolbar.gif "XSDContentModelViewToolbar")  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Başlangıç görünümü göster**|Geçiş yapar [Başlat Görünüm](../xml-tools/start-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **CTRL + 1**.|  
|**İçerik modeli görünümü göster**|Geçiş yapar [içerik modeli Görünüm](../xml-tools/content-model-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **CTRL + 2**.|  
|**Grafik Görünümü Göster**|Geçiş yapar [grafik görünümü](../xml-tools/graph-view.md). Bu görünüm, klavye kısayolunu kullanarak erişilebilir: **CTRL + 3**.|  
|**Çalışma alanını temizleyin**|Çalışma alanı ve tasarım yüzeyine temizler.|  
|**Çalışma alanından kaldırın**|Çalışma alanı ve tasarım serface seçilen düğümleri kaldırır.|  
|**Çalışma alanından seçimi dışında tümünü Kaldır**|Çalışma alanı ve tasarım serface seçili olmadığında düğümlerini kaldırır.|  
|**Belge Göster**|Gösterir veya gizler ek açıklama/belge düğümü içeriği.|  
  
## <a name="panscroll"></a>PAN/kaydırma  
 Kaydırma çubukları kullanarak veya fare sürükleyip sırasında CTRL tuşunu basılı tutarak tasarım yüzeyine kaydırma yapabilirsiniz. ' I tıklatın ve sürükleyin kullanarak tasarım yüzeyi PAN imleci dört yönde çapraz dört oklar değiştirilir.  
  
## <a name="undoredo"></a>Geri alma/yineleme  
 Geri alma/yineleme yeteneği, aşağıdaki eylemler için içerik modeli görünümünde etkinleştirilir:  
  
-   Tek bir düğüm sürükleme ve bırakma ekleniyor.  
  
-   Şema Explorer'da arama sonuçları penceresinden birden çok düğüm ekleme.  
  
-   Düğüm başlangıç görünümünden ekleme.  
  
-   Tek veya birden çok düğüm siliniyor.  
  
## <a name="zoom"></a>Yakınlaştır  
 Yakınlaştırma bulunan içerik modeli görünümü alt sağ köşesindeki.  
  
 Yakınlaştırma aşağıdaki yollarla denetlenebilir:  
  
-   CTRL tuşunu basılı tutarak ve fare içerik modeli görünümü yüzeyini getirildiğinde fare tekerleği dönmesini.  
  
-   Kaydırıcı denetimi kullanarak. Kaydırıcı geçerli yakınlaştırma düzeyini gösterir.  
  
Bu da, üzerine getirin seçtiğinizde veya CTRL yakınlaştırma için fare tekerleğinin ile kullanın yakınlaştırma kaydırıcıyı donuk; diğer tüm zamanlarda saydamdır.  
  
## <a name="xml-editor-integration"></a>XML Düzenleyicisi tümleştirme  
 XSD Tasarımcısı ve XML düzenleyicisini arasında bağlam menüsünü kullanarak İleri ve geri geçebilirsiniz.  
  
 XML Düzenleyicisi'nde ayarlamak şema değişiklik yaparsanız, değişiklikleri içerik modeli görünümünde eşitlenir. Daha fazla bilgi için bkz: [tümleştirme XML Düzenleyicisi ile](../xml-tools/integration-with-xml-editor.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Şema Tasarımcısı Çalışma Alanı](../xml-tools/xml-schema-designer-workspace.md)