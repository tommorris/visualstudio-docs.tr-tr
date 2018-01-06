---
title: "Visual Studio'da verilere Windows Forms denetimleri bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/03/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 7ade7aa6e103a8637d26b10029faabc434ce3a83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bind-windows-forms-controls-to-data-in-visual-studio"></a>Visual Studio'da verilere Windows Forms denetimleri bağlama
Windows Forms veri bağlama tarafından uygulamanızı kullanıcılara verileri görüntüleyebilir. Bu veri bağlama denetimleri oluşturmak için öğelerinden sürükleyebilirsiniz **veri kaynakları** Visual Studio'da Windows Forms tasarımcıya penceresi.
  
![Veri kaynağı sürükleme işlemi](../data-tools/media/raddata-data-source-drag-operation.png "raddata veri kaynağı işlemi sürükleyin")

Öğeleri sürükleyin önce bağlamak istediğiniz denetim türünü ayarlayabilirsiniz. Farklı değerler tablosu kendisiyle veya tek bir sütun hangisini bağlı olarak görünür.  Özel değerler de ayarlayabilirsiniz. Bir tablo için her sütun için ayrı bir denetim bağlandı "Ayrıntılar" anlamına gelir.  

![DataGridView için veri kaynağına bağlama](../data-tools/media/raddata-bind-data-source-to-datagridview.png "raddata DataGridView veri kaynağına bağlama")  
  
## <a name="bindingsource-and-bindingnavigator-controls"></a>BindingSource ve BindingNavigator denetimleri
<xref:System.Windows.Forms.BindingSource> Bileşen iki amaca hizmet eder. İlk olarak, verilere denetimler bağlama sırasında bir soyutlama katmanı sağlar. Form üzerinde denetimleri bağlı <xref:System.Windows.Forms.BindingSource> bir veri kaynağına doğrudan yerine bileşen. İkinci olarak, bu nesneler koleksiyonunu yönetebilirsiniz. Bir türe eklemek <xref:System.Windows.Forms.BindingSource> bu tür bir liste oluşturur.  
  
Hakkında daha fazla bilgi için <xref:System.Windows.Forms.BindingSource> bileşeni, bkz:  
  
-   [BindingSource Bileşeni](/dotnet/framework/winforms/controls/bindingsource-component)  
  
-   [BindingSource Bileşenine Genel Bakış](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
-   [BindingSource Bileşeni Mimarisi](/dotnet/framework/winforms/controls/bindingsource-component-architecture)  
  
[BindingNavigator denetimi](/dotnet/framework/winforms/controls/bindingnavigator-control-windows-forms) bir Windows uygulaması tarafından görüntülenen verileri gezinme için bir kullanıcı arabirimi sağlar.

## <a name="bind-to-data-in-a-datagridview-control"></a>DataGridView denetiminde veri bağlama  
İçin bir [DataGridView denetimi](/dotnet/framework/winforms/controls/datagridview-control-overview-windows-forms), tablonun tamamını tek denetime bağlı. Forma bir DataGridView sürüklediğinizde, bir aracı Şerit kayıtları gezinmek için (<xref:System.Windows.Forms.BindingNavigator>) da görüntülenir. A [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür. Aşağıdaki çizimde, Müşteriler tablosu Siparişler tablosundaki bir ilişkisine sahip olduğu bir TableAdapterManager de eklenir. Bu değişkenleri tüm form sınıfında özel üye olarak otomatik olarak oluşturulan kodda bildirilir. DataGridView doldurmak için otomatik olarak oluşturulan kodu Page_Load olay işleyicisini bulunur. Veritabanını güncelleştirmek için verileri kaydetmek için kod Kaydet olay işleyicisi için BindingNavigator bulunur. Taşıma veya bu kod gerektiği gibi değiştirin.  
  
![BindingNavigator GridView](../data-tools/media/raddata-gridview-with-bindingnavigator.png "raddata GridView BindingNavigator ile")  
  
Sağ üst köşesindeki her akıllı etiketinde tıklayarak DataGridView ve BindingNavigator davranışını özelleştirebilirsiniz:  
  
![DataGridView ve bağlama Gezgini akıllı etiketler](../data-tools/media/raddata-datagridview-and-binding-navigator-smart-tags.png "raddata DataGridView ve bağlama Gezgini akıllı etiketler")  
  
Denetimleri, uygulamanızın ihtiyaçlarını içinde kullanılabilir değilse **veri kaynakları** penceresinde denetimlerini ekleyebilirsiniz. Daha fazla bilgi için bkz: [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).  
  
Öğelerden sürükleyebilirsiniz **veri kaynakları** denetimi veriye bağlamak için zaten bir form üzerinde denetimleri üzerine penceresi. Zaten veriye bağlı bir denetim en son sürüklediğiniz öğesine bağlamaları sıfırlama verileri vardır. Geçerli bırakma hedeflerini olması için denetimleri temel alınan veri türünü buradan oturum öğesi sürüklenen görüntüleyebilen olmalıdır **veri kaynakları** penceresi. Örneğin, bir veri türüne sahip bir öğe sürüklemek için geçerli değil <xref:System.DateTime> üzerine bir <xref:System.Windows.Forms.CheckBox>, çünkü <xref:System.Windows.Forms.CheckBox> bir tarih görüntüleme yeteneğine sahip değil.  
  
## <a name="bind-to-data-in-individual-controls"></a>Tek denetimleri verilere bağlama  
Bir veri kaynağı "Ayrıntılar" bağladığınızda kümesindeki her sütun için ayrı bir denetim bağlıdır.  
  
![Ayrıntılar için veri kaynağına bağlama](../data-tools/media/raddata-bind-data-source-to-details.png "raddata bağlı veri kaynağı ayrıntıları")  
  
> [!IMPORTANT]
> Önceki çizimde unutmayın, Siparişler tablosundaki müşteriler tablosunun siparişleri özelliğinden sürükleyin. Customer.Orders özelliği için bağlama tarafından DataGridView üzerinde yapılan Gezinti komutları hemen ayrıntıları denetimlerinde yansıtılır. Siparişler tablosundan sürüklediyseniz denetimleri hala veri kümesine bağlı, ancak bunlar ile DataGridView eşitlenmemesi değil.  
  
Aşağıdaki çizimde varsayılan Müşteriler tablosunda siparişleri özelliği "Ayrıntılar" bağlandıktan sonra forma eklenen verilere bağlı denetimler gösterir **veri kaynakları** penceresi.  
  
![Siparişler tablosundaki bağlı ayrıntıları](../data-tools/media/raddata-orders-table-bound-to-details.png "raddata Siparişler tablosundaki bağlı ayrıntıları")  
  
Ayrıca, her denetim akıllı etiket olduğunu unutmayın. Bu etiketi yalnızca o denetimine uygulamak özelleştirmeleri sağlar.
  
## <a name="see-also"></a>Ayrıca bkz.
[Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)  
[Windows Forms (.NET Framework) veri bağlama](/dotnet/framework/winforms/windows-forms-data-binding)