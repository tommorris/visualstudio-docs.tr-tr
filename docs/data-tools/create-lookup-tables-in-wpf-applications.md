---
title: WPF uygulamalarında arama tabloları oluşturma
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
ms.assetid: 56a1fbff-c7e8-4187-a1c1-ffd17024bc1b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 81edef642fd2d83f6bb65c01f9a1726812ba0fca
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="create-lookup-tables-in-wpf-applications"></a>WPF uygulamalarında arama tabloları oluşturma
Terim *arama tablosu* (bazen adlı bir *arama bağlama*) bir veri tablosundaki başka bir tablodaki bir yabancı anahtar alanının değeri temel bilgileri görüntüleyen bir denetim açıklar. Üst tablo ana düğümünün sürükleyerek arama tablosu oluşturma ya da nesne **veri kaynakları** bir sütun veya ilgili alt tabloya bir özellik zaten bağlanmış bir denetim üzerine penceresi.

Örneğin, bir içindekiler göz önünde bulundurun `Orders` bir satış veritabanında. Her bir kayıtta `Orders` tabloyu içeren bir `CustomerID` hangi müşteri siparişin gösterir. `CustomerID` Bir müşteri kaydına işaret eden bir yabancı anahtar `Customers` tablo. Siparişleri listesini görüntülediğinizde `Orders` tablo, gerçek müşteri adı yerine görüntülemek isteyebilirsiniz `CustomerID`. Müşteri adı olduğundan `Customers` tablo, müşteri adını görüntülemek için bir arama tablosu oluşturmanız gerekir. Arama tablosu kullandığı `CustomerID` değeri `Orders` ilişki gitmek için kayıt ve müşteri adını döndürür.

## <a name="to-create-a-lookup-table"></a>Arama tablosu oluşturmak için

1.  Veri kaynakları ile ilgili veriler aşağıdaki türlerinden birini projenize ekleyin:

    -   Veri kümesi veya varlık veri modeli.

    -   WCF veri hizmeti, WCF hizmeti veya Web hizmeti. Daha fazla bilgi için bkz: [nasıl yapılır: bir hizmetteki verilere bağlanma](../data-tools/how-to-connect-to-data-in-a-service.md).

    -   Nesneleri. Daha fazla bilgi için bkz: [Visual Studio'da nesnelere bağlama](bind-objects-in-visual-studio.md).

    > [!NOTE]
    >  Arama tablosu oluşturabilmeniz için önce iki ilişkili tablolar veya nesneler projesi için veri kaynağı olarak mevcut olmalıdır.

2.  Açık **WPF Tasarımcısı**ve tasarımcı geçerli bırakma hedefi öğe için bir kapsayıcı içerdiğinden emin olun **veri kaynakları** penceresi.

     Geçerli bırakma hedefleri hakkında daha fazla bilgi için bkz: [Visual Studio'da verilere WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

3.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster** açmak için **veri kaynakları** penceresi.

4.  Düğümleri genişletin **veri kaynakları** üst tablo veya nesne ve ilgili alt tablo veya nesne görene kadar penceresi.

    > [!NOTE]
    >  İlgili alt tablo veya nesne bir Genişletilebilir alt düğümünde ana tablo veya nesne olarak görünen düğümdür.

5.  Alt düğüm için aşağı açılır menüsünü tıklatın ve seçin **ayrıntıları**.

6.  Alt düğümünü genişletin.

7.  Alt düğümü altında alt ve üst verilerini ilişkili öğe için aşağı açılır menüsünü tıklatın. (Önceki örnekte budur **CustomerID** düğümü.) Arama bağlama destekleyen denetimleri aşağıdaki türlerinden birini seçin:

    -   **ComboBox**

    -   **ListBox**

    -   **ListView**

        > [!NOTE]
        >  Varsa **ListBox** veya **ListView** denetim görünmez listesinde, bu denetimlerin listesine ekleyebilirsiniz. Bilgi için bkz: [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

    -   Türetilen özel bir denetim <xref:System.Windows.Controls.Primitives.Selector>.

        > [!NOTE]
        >  İçin denetimleri listesine özel denetimleri ekleme hakkında bilgi için öğeleri seçin **veri kaynakları** penceresinde bkz [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).

8.  Alt düğümden sürükleyin **veri kaynakları** WPF Tasarımcısı'nda bir kapsayıcı üzerine penceresi. (Önceki örnekte alt düğümüdür **siparişleri** düğümü.)

     Visual Studio her sürüklediğiniz öğeleri için yeni verilere bağlı denetimler oluşturur XAML oluşturur. XAML ayrıca yeni bir ekler <xref:System.Windows.Data.CollectionViewSource> alt tablo veya bırakma hedefi kaynaklarına nesnesi. Bazı veri kaynakları için Visual Studio ayrıca tablo veya nesne verilerini yüklemek için kod oluşturur. Daha fazla bilgi için bkz: [Visual Studio'da verilere WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

9. Üst düğümden sürükleyin **veri kaynakları** daha önce oluşturduğunuz arama bağlama denetimi üzerine penceresi. (Önceki örnekte üst düğümüdür **müşteriler** düğüm).

     Visual Studio arama bağını yapılandırmak için Denetim bazı özellikleri ayarlar. Aşağıdaki tabloda, Visual Studio değiştirir özellikleri listeler. Gerekirse, bu özellikleri XAML veya değiştirebileceğiniz, **özellikleri** penceresi.

    |Özellik|Ayar açıklaması|
    |--------------|----------------------------|
    |<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>|Bu özellik, koleksiyon veya denetimde görüntülenen verileri almak için kullanılan bağlama belirtir. Visual Studio bu özelliği ayarlar <xref:System.Windows.Data.CollectionViewSource> denetime sürüklediğiniz üst veriler için.|
    |<xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A>|Bu özellik denetiminde gösterilen veri öğesi yolunu belirtir. Visual Studio bu özellik bir dize veri türü olan birincil anahtar sonra ilk sütun veya üst veri özelliği için ayarlar.<br /><br /> Farklı bir sütun veya özellik üst verileri görüntülemek istiyorsanız, bu özellik farklı bir özellik yolu değiştirin.|
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>|Visual Studio bu özellik sütun veya özellik Designer'a sürüklenen alt veri bağlar. Üst verileri için yabancı anahtar budur.|
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValuePath%2A>|Visual Studio bu özelliği sütunun yolu veya alt verilerin ana veri yabancı anahtar özelliği için ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [WPF uygulamalarındaki ilgili verileri görüntüleme](../data-tools/display-related-data-in-wpf-applications.md)
- [İzlenecek yol: Bir WPF uygulamasında ilgili verileri görüntüleme](../data-tools/display-related-data-in-wpf-applications.md)