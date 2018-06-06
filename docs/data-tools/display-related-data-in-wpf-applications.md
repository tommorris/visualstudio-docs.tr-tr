---
title: WPF uygulamalarındaki ilgili verileri görüntüleme
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
ms.assetid: 3aa80194-0191-474d-9d28-5ec05654b426
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 38c25cc1631529895a11af566298ce22930a2e6a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746552"
---
# <a name="display-related-data-in-wpf-applications"></a>WPF uygulamalarındaki ilgili verileri görüntüleme
Bazı uygulamalarda, birden çok tablo veya bir üst-alt ilişkisinde birbiriyle ilişkili olan varlıkların gelen verilerle çalışmak isteyebilirsiniz. Örneğin, müşterilerden görüntüleyen bir kılavuz görüntülemek isteyebilirsiniz bir `Customers` tablo. Kullanıcı belirli bir müşteri seçtiğinde, başka bir kılavuz o müşteriden ilgili siparişleri görüntüler `Orders` tablo.

Konumundan öğeleri sürükleyerek ilgili verileri görüntüleme verilere bağlı denetimler oluşturabilirsiniz **veri kaynakları** WPF Tasarımcısı penceresine.

## <a name="to-create-controls-that-display-related-records"></a>İlişkili kayıtları görüntülemek denetimleri oluşturmak için

1. Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster** açmak için **veri kaynakları** penceresi.

2. Tıklatın **yeni veri kaynağı Ekle**ve tamamlamak **veri kaynağı yapılandırması** Sihirbazı.

3. WPF Tasarımcısı'nı açın ve tasarımcı geçerli bırakma hedefi listesindeki öğeler için bir kapsayıcı içerdiğinden emin olun **veri kaynakları** penceresi.

     Geçerli bırakma hedefleri hakkında daha fazla bilgi için bkz: [Visual Studio'da verilere WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

4. İçinde **veri kaynakları** penceresi, üst tablo gösteren düğümü genişletin veya nesne ilişkisinde. Üst tablo veya nesne bir-çok ilişkisi "bir" tarafında değil.

5. Üst düğümü (veya üst düğümü bireysel öğeleri) sürükleyin **veri kaynakları** geçerli bırakma hedefi Tasarımcısı'nda oturum penceresi.

     Visual Studio sürüklediğiniz her bir öğe için yeni verilere bağlı denetimler oluşturur XAML oluşturur. XAML ayrıca yeni bir ekler <xref:System.Windows.Data.CollectionViewSource> üst tablo veya bırakma hedefi kaynaklarına nesnesi. Bazı veri kaynakları için Visual Studio ayrıca verileri üst tablo veya nesne yüklemek için kod oluşturur. Daha fazla bilgi için bkz: [Visual Studio'da verilere WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

6. İçinde **veri kaynakları** penceresinde, ilgili alt tablo veya nesne bulun. İlgili alt tablolar ve nesneleri veri üst düğümün listesinin altındaki Genişletilebilir düğüm olarak görünür.

7. Alt düğüm (ya da alt düğüm içindeki tüm öğeleri) sürükleyin **veri kaynakları** geçerli bırakma hedefi Tasarımcısı'nda oturum penceresi.

     Visual Studio her sürüklediğiniz öğeleri için yeni verilere bağlı denetimler oluşturur XAML oluşturur. XAML ayrıca yeni bir ekler <xref:System.Windows.Data.CollectionViewSource> alt tablo veya bırakma hedefi kaynaklarına nesnesi. Bu yeni <xref:System.Windows.Data.CollectionViewSource> üst tablo ya da yalnızca Designer'a sürüklediğiniz nesne özelliğine bağlıdır. Bazı veri kaynakları için Visual Studio ayrıca verileri alt tablo veya nesne yüklemek için kod oluşturur.

     Aşağıdaki şekilde ilgili gösterilmektedir **siparişleri** tablosu **müşteriler** bir veri kümesinde tabloda **veri kaynakları** penceresi.

     ![İlişkiyi gösteren veri kaynakları penceresi](../data-tools/media/datasources2.gif)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [WPF uygulamalarında arama tabloları oluşturma](../data-tools/create-lookup-tables-in-wpf-applications.md)