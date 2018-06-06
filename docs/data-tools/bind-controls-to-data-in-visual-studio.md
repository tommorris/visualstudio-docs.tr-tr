---
title: Visual Studio'da verilere denetimler bağlama
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data, displaying
- data sources, displaying data
- Data Sources window
- dislaying data
ms.assetid: be8b6623-86a6-493e-ab7a-050de4661fd6
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d27975cf387c92e5afcc61bd267f383a6bed414a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747397"
---
# <a name="bind-controls-to-data-in-visual-studio"></a>Visual Studio'da verilere denetimler bağlama
Denetimlere veri bağlama tarafından uygulamanızı kullanıcılara verileri görüntüleyebilir. Bu veri bağlama denetimleri konumundan öğeleri sürükleyerek oluşturabileceğiniz **veri kaynakları** tasarım yüzeyi veya Visual Studio'da yüzeyinde denetimleri penceresi.

 Bu konu, veri bağlama denetimleri oluşturmak için kullanabileceğiniz veri kaynakları açıklar. Ayrıca bazı veri bağlama ilgili genel görevler açıklanmaktadır. Verilere bağlı denetimler oluşturma hakkında daha belirli Ayrıntılar için bkz: [bağlamak Windows Forms denetimleri Visual Studio'da verilere](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md) ve [Visual Studio'da verilere WPF bağlama denetimleri](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md).

## <a name="data-sources"></a>Veri kaynakları
 Veri bağlama bağlamında, bir veri kaynağı Kullanıcı Arabiriminizin bağlı bellek verileri temsil eder. Pratikteki, bir veri kaynağı bir Entity Framework sınıfı, bir veri kümesi, bir .NET proxy nesnesi, bir LINQ to SQL sınıfı veya herhangi bir .NET nesne veya koleksiyonda kapsüllenmiş bir hizmet uç noktası olabilir. Bazı veri kaynakları konumundan öğeleri sürükleyerek verilere bağlı denetimler oluşturmanıza olanak sağlaması **veri kaynakları** kullanırken diğer veri kaynakları penceresi. Aşağıdaki tabloda, hangi veri kaynaklarını desteklendiğini gösterir.

|Veri kaynağı|Sürükle ve bırak desteği **Windows Form Tasarımcısı**|Sürükle ve bırak desteği **WPF Tasarımcısı**|Sürükle ve bırak desteği **Silverlight Tasarımcısı**|
|-----------------|---------------------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------------|
|Veri kümesi|Evet|Evet|Hayır|
|Varlık Veri Modeli|Evet<sup>1</sup>|Evet|Evet|
|LINQ-SQL sınıfları|Hayır<sup>2</sup>|Hayır<sup>2</sup>|Hayır<sup>2</sup>|
|Hizmetler (de dahil olmak üzere [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], WCF hizmetleri ve web Hizmetleri)|Evet|Evet|Evet|
|Nesne|Evet|Evet|Evet|
|SharePoint|Evet|Evet|Evet|

 1. Kullanarak modeli oluşturmak **varlık veri modeli** sihirbazını sonra bu nesneleri tasarımcıya sürükleyin.

 2. LINQ-SQL sınıflar olarak görünmez **veri kaynakları** penceresi. Ancak, LINQ üzerinde SQL'e sınıflarını temel alan yeni bir nesne veri kaynağı ekleyin ve bu nesnelere veri bağlama denetimleri oluşturmak için Designer'a sürükleyin. Daha fazla bilgi için bkz: [izlenecek yol: oluşturma LINQ-SQL sınıfları (O R Tasarımcısı)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md).

## <a name="data-sources-window"></a>Veri Kaynakları penceresi
 Veri kaynakları projenize kullanılabilir öğeleri olarak **veri kaynakları** penceresi. Bu pencere görünür ya da erişilebilir **Görünüm** form Tasarım yüzeyi projenizdeki etkin pencereyi olduğunda menüsü. Temel alınan verilere bağlı denetimler oluşturmak için bu penceresinden öğeleri sürükleyin ve sağ tıklayarak veri kaynakları da yapılandırabilirsiniz.

 ![Veri Kaynakları penceresi](../data-tools/media/raddata-data-sources-window.png)

 Görünür her bir veri türü için **veri kaynakları** penceresinde varsayılan denetimi Designer'a öğesi sürüklediğinizde oluşturulur. Bir öğeden sürükleyerek önce **veri kaynakları** penceresinde oluşturulacak denetim değiştirebilirsiniz. Daha fazla bilgi için bkz: [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

## <a name="tasks-involved-in-binding-controls-to-data"></a>Verilere denetimler bağlama içinde görevleri
 Aşağıdaki tabloda bazı listeler, en yaygın görevleri verilere denetimler bağlama için gerçekleştirin.

|Görev|Daha fazla bilgi|
|----------|----------------------|
|Açık **veri kaynakları** penceresi.|Tasarım yüzeyi düzenleyicisinde açın ve seçin **Görünüm** > **veri kaynakları**.|
|Bir veri kaynağı projenize ekleyin.|[Yeni veri kaynakları ekleyin](../data-tools/add-new-data-sources.md)|
|Bir öğeden sürüklediğinizde, oluşturduğunuz denetimini ayarlama **veri kaynakları** Tasarımcı penceresine.|[Deneti veri kaynakları penceresinden sürüklendiğinde oluşturulacak şekilde ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)|
|Öğeleri ile ilişkili denetimleri listesini değiştirmek **veri kaynakları** penceresi.|[Veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md)|
|Verilere bağlı denetimler oluşturun.|[Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)<br /><br /> [Visual Studio'da verilere WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)|
|Bir nesnede veya koleksiyonda bağlayın.|[Visual Studio'da nesne bağlama](../data-tools/bind-objects-in-visual-studio.md)|
|Kullanıcı Arabiriminde görünen verileri filtreleyin.|[Bir Windows Forms uygulamasındaki verileri filtreleme ve sıralama](../data-tools/filter-and-sort-data-in-a-windows-forms-application.md)|
|Denetimler için resim yazıları özelleştirin.|[Visual Studio'nun verilere bağlı denetimler için başlık oluşturma biçimini özelleştirme](../data-tools/customize-how-visual-studio-creates-captions-for-data-bound-controls.md)|

## <a name="see-also"></a>Ayrıca Bkz.

- [.NET için Visual Studio veri araçları](../data-tools/visual-studio-data-tools-for-dotnet.md)
- [Windows Forms Veri Bağlama](/dotnet/framework/winforms/windows-forms-data-binding)