---
title: Visual Studio'da verilere Windows Forms denetimleri bağlama
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- data [Windows Forms], data sources
- Windows Forms, data binding
- Windows Forms, displaying data
- displaying data on forms
- forms, displaying data
- data sources, displaying data
- displaying data, Windows Forms
- data [Windows Forms], displaying
ms.assetid: 243338ef-41af-4cc5-aff7-1e830236f0ec
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 4652d8dd3e9be582bc15c4644711accc06fd283f
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845528"
---
# <a name="bind-windows-forms-controls-to-data-in-visual-studio"></a>Visual Studio'da verilere Windows Forms denetimleri bağlama
Windows Forms veri bağlama tarafından uygulamanızı kullanıcılara verileri görüntüleyebilir. Bu veri bağlama denetimleri oluşturmak için öğelerinden sürükleyin **veri kaynakları** Visual Studio'da Windows Forms tasarımcıya penceresi.

![Veri kaynağı sürükleme işlemi](../data-tools/media/raddata-data-source-drag-operation.png)

Öğeleri sürükleyin önce bağlamak istediğiniz denetim türünü ayarlayabilirsiniz. Farklı değerler tablosu kendisiyle veya tek bir sütun hangisini bağlı olarak görünür.  Özel değerler de ayarlayabilirsiniz. Bir tablo için **ayrıntıları** her sütun için ayrı bir denetim bağlı olduğu anlamına gelir.

![DataGridView için veri kaynağına bağlama](../data-tools/media/raddata-bind-data-source-to-datagridview.png)

## <a name="bindingsource-and-bindingnavigator-controls"></a>BindingSource ve BindingNavigator denetimleri
<xref:System.Windows.Forms.BindingSource> Bileşen iki amaca hizmet eder. İlk olarak, verilere denetimler bağlama sırasında bir soyutlama katmanı sağlar. Form üzerinde denetimleri bağlı <xref:System.Windows.Forms.BindingSource> bir veri kaynağına doğrudan yerine bileşen. İkinci olarak, bu nesneler koleksiyonunu yönetebilirsiniz. Bir türe eklemek <xref:System.Windows.Forms.BindingSource> bu tür bir liste oluşturur.

Hakkında daha fazla bilgi için <xref:System.Windows.Forms.BindingSource> bileşeni, bkz:

-   [BindingSource bileşeni](/dotnet/framework/winforms/controls/bindingsource-component)

-   [BindingSource bileşenine genel bakış](/dotnet/framework/winforms/controls/bindingsource-component-overview)

-   [BindingSource bileşeni mimarisi](/dotnet/framework/winforms/controls/bindingsource-component-architecture)

[BindingNavigator denetimi](/dotnet/framework/winforms/controls/bindingnavigator-control-windows-forms) bir Windows uygulaması tarafından görüntülenen verileri gezinme için bir kullanıcı arabirimi sağlar.

## <a name="bind-to-data-in-a-datagridview-control"></a>DataGridView denetiminde veri bağlama
İçin bir [DataGridView denetimi](/dotnet/framework/winforms/controls/datagridview-control-overview-windows-forms), tablonun tamamını tek denetime bağlı. Sürüklediğinizde bir **DataGridView** forma bir aracı Şerit kayıtları gezinmek için (<xref:System.Windows.Forms.BindingNavigator>) da görüntülenir. A [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür. Aşağıdaki çizimde, bir [TableAdapterManager](https://msdn.microsoft.com/library/bb384426.aspx) Müşteriler tablosunu Siparişler tablosuna bir ilişki içerdiğinden de eklenir. Bu değişkenleri tüm form sınıfında özel üye olarak otomatik olarak oluşturulan kodda bildirilir. Doldurma için otomatik olarak oluşturulan kodu **DataGridView** bulunan `Form_Load` olay işleyicisi. Veritabanını güncelleştirmek için verileri kaydetmek için kod bulunan `Save` için olay işleyicisini **BindingNavigator**. Taşıma veya bu kod gerektiği gibi değiştirin.

![GridView BindingNavigator ile](../data-tools/media/raddata-gridview-with-bindingnavigator.png)

Davranışını özelleştirebilirsiniz **DataGridView** ve **BindingNavigator** sağ üst köşesindeki her akıllı etiket tıklayarak:

![DataGridView ve bağlama Gezgini akıllı etiketler](../data-tools/media/raddata-datagridview-and-binding-navigator-smart-tags.png)

Denetimleri, uygulamanızın ihtiyaçlarını içinde kullanılabilir değilse **veri kaynakları** penceresinde denetimlerini ekleyebilirsiniz. Daha fazla bilgi için bkz: [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).

Öğelerden sürükleyebilirsiniz **veri kaynakları** denetimi veriye bağlamak için zaten bir form üzerinde denetimleri üzerine penceresi. Zaten veriye bağlı bir denetim en son sürüklediğiniz öğesine bağlamaları sıfırlama verileri vardır. Geçerli bırakma hedeflerini olması için denetimleri temel alınan veri türünü buradan oturum öğesi sürüklenen görüntüleyebilen olmalıdır **veri kaynakları** penceresi. Örneğin, bir veri türüne sahip bir öğe sürüklemek için geçerli değil <xref:System.DateTime> üzerine bir <xref:System.Windows.Forms.CheckBox>, çünkü <xref:System.Windows.Forms.CheckBox> bir tarih görüntüleme yeteneğine sahip değil.

## <a name="bind-to-data-in-individual-controls"></a>Tek denetimleri verilere bağlama
Bir veri kaynağına bağladığınızda **ayrıntıları**, kümesindeki her sütun için ayrı bir denetim bağlıdır.

![Ayrıntılar için veri kaynağına bağlama](../data-tools/media/raddata-bind-data-source-to-details.png)

> [!IMPORTANT]
> Önceki çizimde unutmayın, Siparişler tablosundaki müşteriler tablosunun siparişleri özelliğinden sürükleyin. Bağlama tarafından `Customer.Orders` özelliği,'ın gezinti komutları yapılan **DataGridView** ayrıntıları denetimlerinde hemen yansıtılır. Siparişler tablosundan sürüklenen, denetimleri hala veri kümesine bağlı, ancak bunlar ile eşitlenmemesi değil **DataGridView**.

Aşağıdaki çizimde Müşteriler tablosunda siparişleri özelliği bağlı sonra forma eklenen verilere bağlı denetimler varsayılan gösterir **ayrıntıları** içinde **veri kaynakları** penceresi.

![Ayrıntılar için bağlı Siparişler tablosu](../data-tools/media/raddata-orders-table-bound-to-details.png)

Ayrıca, her denetim akıllı etiket olduğunu unutmayın. Bu etiketi yalnızca o denetimine uygulamak özelleştirmeleri sağlar.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Windows Forms (.NET Framework) veri bağlama](/dotnet/framework/winforms/windows-forms-data-binding)