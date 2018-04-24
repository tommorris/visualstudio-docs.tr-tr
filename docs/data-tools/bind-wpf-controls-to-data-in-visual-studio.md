---
title: Visual Studio - 1. Bölüm verilere WPF denetimleri bağlama | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: e05a1e0c-5082-479d-bbc9-d395b0bc6580
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: c753c3818ac97fc353a90d4c7ae58f5f84f89b4b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="bind-wpf-controls-to-data-in-visual-studio"></a>Visual Studio'da verilere WPF denetimleri bağlama
Veri bağlama tarafından uygulamanızı kullanıcılara verileri görüntüleyebilir [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] kontrol eder. Bu veri bağlama denetimleri oluşturmak için öğelerinden sürükleyebilirsiniz **veri kaynakları** penceresi üzerine [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)] içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bu konuda en yaygın görevleri, Araçlar ve veri bağlama oluşturmak için kullanabileceğiniz sınıfları bazıları açıklanmaktadır [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] uygulamalar.

 Verilere bağlı denetimler oluşturma hakkında genel bilgiler için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], bkz: [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md). Hakkında daha fazla bilgi için [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] veri bağlama, bkz: [veri bağlama genel bakış](/dotnet/framework/wpf/data/data-binding-overview).

## <a name="tasks-involved-in-binding-wpf-controls-to-data"></a>Verilere WPF denetimleri bağlama içinde görevleri
 Aşağıdaki tabloda konumundan öğeleri sürükleyerek gerçekleştirilebilir görevleri listeler **veri kaynakları** penceresine [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)].

|Görev|Daha fazla bilgi|
|----------|----------------------|
|Yeni verilere bağlı denetimler oluşturun.<br /><br /> Varolan denetimleri verilere bağlayın.|[Bir veri kümesine WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-a-dataset.md)|
|Bir üst-alt ilişkisinde ilgili verileri görüntüleyen denetimler oluşturma: Kullanıcı bir denetimde üst veri kaydını seçtiğinde, bir diğer denetim seçili kayıt ile ilgili alt verileri görüntüler.|[WPF uygulamalarındaki ilgili verileri görüntüleme](../data-tools/display-related-data-in-wpf-applications.md)|
|Oluşturma bir *arama tablosu* başka bir tabloda bir yabancı anahtar alanı değerini temel alan bir tablodan daha fazla bilgi görüntüler.|[WPF uygulamalarında arama tabloları oluşturma](../data-tools/create-lookup-tables-in-wpf-applications.md)|
|Veritabanında bir denetimi görüntüye bağlayın.|[Bir veritabanından resimlere denetim bağlama](../data-tools/bind-controls-to-pictures-from-a-database.md)|

## <a name="valid-drop-targets"></a>Geçerli bırakma hedefleri
 Öğeleri sürükleyebilirsiniz **veri kaynakları** geçerli bırakma hedeflerini yalnızca penceresine [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)]. İki tür geçerli bırakma hedefi vardır: kapsayıcılar ve denetimler. Kapsayıcı, genellikle denetimleri içeren bir kullanıcı arabirimi öğesidir. Örneğin, bir kılavuz bir kapsayıcıdır ve dolasıyla da bir penceredir.

## <a name="generated-xaml-and-code"></a>Oluşturulan XAML ve kod
 Bir öğeden sürüklediğinizde **veri kaynakları** penceresine [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)], [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oluşturur [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] , yeni bir veri bağlama denetimi tanımlar (veya varolan bir denetim veri kaynağına bağlar). Bazı veri kaynakları için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] de verileriyle veri kaynağını doldurur arka plan kod dosyasına kod oluşturur.

 Aşağıdaki tabloda [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] ve kodunu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] her veri kaynağı türü için oluşturur **veri kaynakları** penceresi.

|Veri kaynağı|Bir denetimi veri kaynağına bağlayan XAML oluşturma|Veri kaynağını verilerle dolduran kod oluşturma|
|-----------------|-----------------------------------------------------------|--------------------------------------------------------|
|Veri kümesi|Evet|Evet|
|[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]|Evet|Evet|
|Hizmet|Evet|Hayır|
|Nesne|Evet|Hayır|

### <a name="datasets"></a>Veri kümeleri
 Bir tablo veya sütun sürüklediğinizde **veri kaynakları** designer penceresine [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oluşturur [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] şunları yapar:

-   Veri kümesi ve yeni bir ekler <xref:System.Windows.Data.CollectionViewSource> kapsayıcı kaynaklarına öğesine sürüklenebilir. <xref:System.Windows.Data.CollectionViewSource> Gidin ve veri kümesinde göstermek için kullanılan bir nesnedir.

-   Denetim için bir veri bağlama oluşturur. Öğeyi tasarımcıda varolan bir denetime sürüklerseniz, XAML denetimi öğeye bağlar. Bir kapsayıcıya öğeyi sürükleyin, XAML için sürüklenen öğe seçilmedi denetimi oluşturur ve denetimi öğesine bağlar. Denetim içinde yeni oluşturulan <xref:System.Windows.Controls.Grid>.

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ayrıca arka plan kod dosyasına aşağıdaki değişiklikleri yapar:

-   Oluşturur bir <xref:System.Windows.FrameworkElement.Loaded> için olay işleyicisini [!INCLUDE[TLA2#tla_ui](../data-tools/includes/tla2sharptla_ui_md.md)] denetimi içeren öğe. Olay işleyicisi verilerle alır tabloyu doldurur <xref:System.Windows.Data.CollectionViewSource> kapsayıcının kaynakları ve yapar sonra geçerli öğenin ilk veri öğesi. Varsa bir <xref:System.Windows.FrameworkElement.Loaded> olay işleyicisi zaten var, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mevcut olay işleyicisine bu kodu ekler.

### <a name="entity-data-models"></a>Varlık veri modeli
 Bir varlık veya bir varlık özelliğinden sürüklediğinizde **veri kaynakları** designer penceresine [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oluşturur [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] şunları yapar:

-   Yeni bir ekler <xref:System.Windows.Data.CollectionViewSource> kapsayıcı kaynaklarına öğesine sürüklenebilir. <xref:System.Windows.Data.CollectionViewSource> Gidin ve varlıkta verileri görüntülemek için kullanılan bir nesnedir.

-   Denetim için bir veri bağlama oluşturur. Tasarımcısı'nda var olan bir denetim için öğe sürüklediğinizde [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] denetimi öğesine bağlar. Öğe bir kapsayıcıya sürüklediğinizde [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] denetimi oluşturur sürüklenen öğe için seçildi ve denetimi öğesine bağlar. Denetim içinde yeni oluşturulan <xref:System.Windows.Controls.Grid>.

Visual Studio arka plan kod dosyasında aşağıdaki değişiklikleri de yapar:

-   Tasarımcıya sürüklediğiniz varlık (veya tasarımcıya sürüklediğiniz özelliği içeren varlık) için bir sorgu döndüren yeni bir yöntem ekler. Yeni yöntemi Get adına sahip*EntityName*sorgu, burada *EntityName* varlık adıdır.

-   Oluşturur bir <xref:System.Windows.FrameworkElement.Loaded> için olay işleyicisini [!INCLUDE[TLA2#tla_ui](../data-tools/includes/tla2sharptla_ui_md.md)] denetimi içeren öğe. Olay işleyicisi Get çağrıları*EntityName*sorgu varlığı alır verileri ile doldurmak için yöntemi <xref:System.Windows.Data.CollectionViewSource> kapsayıcının kaynakları ve yapar sonra geçerli öğenin ilk veri öğesi. Varsa bir <xref:System.Windows.FrameworkElement.Loaded> olay işleyicisi zaten var, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mevcut olay işleyicisine bu kodu ekler.

### <a name="services"></a>Hizmetler
 Bir hizmet nesnesi veya özelliğinden sürüklediğinizde **veri kaynakları** designer penceresine [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oluşturur [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] , bir veri bağlama denetimi oluşturur (veya varolan bir denetimi nesne veya özelliğin bağlar). Ancak, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] verilerle proxy hizmet nesnesini doldurur kod oluşturmaz. Bu kodu kendiniz yazmalısınız. Bunun nasıl yapılacağını gösteren bir örnek için bkz: [bir WCF veri hizmetine WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md).

 Visual Studio aşağıdakileri yapan XAML oluşturur:

-   Yeni bir ekler <xref:System.Windows.Data.CollectionViewSource> öğesine sürüklenen kapsayıcısının kaynaklarına. <xref:System.Windows.Data.CollectionViewSource> Gidin ve hizmet tarafından döndürülen nesnedeki verileri görüntülemek için kullanılan bir nesnedir.

-   Denetim için bir veri bağlama oluşturur. Tasarımcısı'nda var olan bir denetim için öğe sürüklediğinizde [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] denetimi öğesine bağlar. Öğe bir kapsayıcıya sürüklediğinizde [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] denetimi oluşturur sürüklenen öğe için seçildi ve denetimi öğesine bağlar. Denetim içinde yeni oluşturulan <xref:System.Windows.Controls.Grid>.

### <a name="objects"></a>Nesneler
 Bir nesne veya özelliğinden sürüklediğinizde **veri kaynakları** designer penceresine [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oluşturur [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] , bir veri bağlama denetimi oluşturur (veya varolan bir denetimi nesne veya özelliğin bağlar). Ancak, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nesne verilerle doldurmak için kod oluşturmaz. Bu kodu kendiniz yazmalısınız.

> [!NOTE]
>  Özel sınıflar gerekir ortak ve, varsayılan olarak, parametresiz bir oluşturucusu olmalıdır. Bunlar, kendi sözdiziminde "nokta" olan can'tbe iç içe geçmiş sınıf. Daha fazla bilgi için bkz: [XAML ve WPF için özel sınıfları](/dotnet/framework/wpf/advanced/xaml-and-custom-classes-for-wpf).

 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] oluşturur [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] şunları yapar:

-   Yeni bir ekler <xref:System.Windows.Data.CollectionViewSource> öğesine sürüklenen kapsayıcısının kaynaklarına. <xref:System.Windows.Data.CollectionViewSource> Gidin ve nesne verileri görüntülemek için kullanılan bir nesnedir.

-   Denetim için bir veri bağlama oluşturur. Öğeyi tasarımcıda varolan bir denetime sürüklerseniz, XAML denetimi öğeye bağlar. Bir kapsayıcıya öğeyi sürükleyin, XAML için sürüklenen öğe seçilmedi denetimi oluşturur ve denetimi öğesine bağlar. Denetim içinde yeni oluşturulan <xref:System.Windows.Controls.Grid>.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)