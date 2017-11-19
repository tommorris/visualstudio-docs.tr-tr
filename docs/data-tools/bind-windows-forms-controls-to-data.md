---
redirect_url: /visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio
ms.openlocfilehash: 5ba8ada294275a99aab27ff9c249d6c3d8e17da3
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
Başlık: "veri bağlama Windows Forms denetimlerine | Microsoft Docs"MS.özel:" "ms.date:" 11/04/2016"ms.reviewer:" "MS.Paket:" "ms.tgt_pltfrm:" "ms.topic:"makale"helpviewer_keywords: 
  - "Windows Forms denetimleri verileri görüntüleme"
  - "Windows Forms, verileri görüntüleme"
  - "veri kaynaklarını görüntüleme"
  - "veri görüntüleme [Windows Forms]" ms.assetid: 0163a34a-38cb-40b9-8f38-3058a90caf21 caps.latest.revision: 28 Yazar: "gewarren" ms.author: "gewarren" Yöneticisi: ghogen ms.technology: "vs-data-Araçları"
---
# <a name="bind-windows-forms-controls-to-data"></a>Windows Forms denetimlerini verilere bağlama
Nesnelerden sürükleyerek denetimlerine veri kaynaklarına bağlanabilirsiniz **veri kaynakları** pencere Windows forma veya varolan bir denetim bir form üzerinde üzerine. Öğeleri sürükleyin önce bağlamak istediğiniz denetim türünü ayarlayabilirsiniz. Farklı değerler tablosu kendisiyle veya tek bir sütun hangisini bağlı olarak görünür.  Özel değerler de ayarlayabilirsiniz. Bir tablo için her sütun için ayrı bir denetim bağlandı "Ayrıntılar" anlamına gelir.  

![DataGridView için veri kaynağına bağlama](../data-tools/media/raddata-bind-data-source-to-datagridview.png "raddata DataGridView veri kaynağına bağlama")  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="bind-to--data-in-a-datagridview-control"></a>DataGridView denetiminde veri bağlama  
DataGridView için tek bir denetim için tüm tablo bağlıdır. Forma bir DataGridView sürüklediğinizde, bir aracı Şerit kayıtları gezinmek için (<xref:System.Windows.Forms.BindingNavigator>) da görüntülenir. A [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür. Aşağıdaki çizimde, Müşteriler tablosu Siparişler tablosundaki bir ilişkisine sahip olduğu bir TableAdapterManager de eklenir. Bu değişkenleri tüm form sınıfında özel üye olarak otomatik olarak oluşturulan kodda bildirilir. DataGridView doldurmak için otomatik olarak oluşturulan kodu Page_Load olay işleyicisini bulunur. Veritabanını güncelleştirmek için verileri kaydetmek için kod Kaydet olay işleyicisi için BindingNavigator bulunur. Taşıma veya bu kod gerektiği gibi değiştirin.  
  
 ![BindingNavigator GridView](../data-tools/media/raddata-gridview-with-bindingnavigator.png "raddata GridView BindingNavigator ile")  
  
 Sağ üst köşesindeki her akıllı etiketinde tıklayarak DataGridView ve BindingNavigator davranışını özelleştirebilirsiniz:  
  
 ![DataGridView ve bağlama Gezgini akıllı etiketler](../data-tools/media/raddata-datagridview-and-binding-navigator-smart-tags.png "raddata DataGridView ve bağlama Gezgini akıllı etiketler")  
  
 Denetimleri, uygulamanızın ihtiyaçlarını içinde kullanılabilir değilse **veri kaynakları** penceresinde denetimlerini ekleyebilirsiniz. Daha fazla bilgi için bkz: [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).  
  
 Öğelerden sürükleyebilirsiniz **veri kaynakları** denetimi veriye bağlamak için zaten bir form üzerinde denetimleri üzerine penceresi. Zaten veriye bağlı bir denetim en son sürüklediğiniz öğesine bağlamaları sıfırlama verileri vardır. Geçerli bırakma hedeflerini olması için denetimleri temel alınan veri türünü buradan oturum öğesi sürüklenen görüntüleyebilen olmalıdır **veri kaynakları** penceresi. Örneğin, bir veri türüne sahip bir öğe sürüklemek için geçerli değil <xref:System.DateTime> üzerine bir <xref:System.Windows.Forms.CheckBox>, çünkü <xref:System.Windows.Forms.CheckBox> bir tarih görüntüleme yeteneğine sahip değil.  
  
## <a name="bind-to--data-in-individual-controls"></a>Tek denetimleri verilere bağlama  
 Bir veri kaynağı "Ayrıntılar" bağladığınızda kümesindeki her sütun için ayrı bir denetim bağlıdır.  
  
 ![Ayrıntılar için veri kaynağına bağlama](../data-tools/media/raddata-bind-data-source-to-details.png "raddata bağlı veri kaynağı ayrıntıları")  
  
> [!IMPORTANT]
>  Önceki çizimde unutmayın, Siparişler tablosundaki müşteriler tablosunun siparişleri özelliğinden sürükleyin. Customer.Orders özelliği için bağlama tarafından DataGridView üzerinde yapılan Gezinti komutları hemen ayrıntıları denetimlerinde yansıtılır. Siparişler tablosundan sürüklediyseniz denetimleri hala veri kümesine bağlı, ancak bunlar ile DataGridView eşitlenmemesi değil.  
  
 Aşağıdaki çizimde varsayılan Müşteriler tablosunda siparişleri özelliği "Ayrıntılar" bağlandıktan sonra forma eklenen verilere bağlı denetimler gösterir **veri kaynakları** penceresi.  
  
 ![Siparişler tablosundaki bağlı ayrıntıları](../data-tools/media/raddata-orders-table-bound-to-details.png "raddata Siparişler tablosundaki bağlı ayrıntıları")  
  
 Ayrıca, her denetim akıllı etiket olduğunu unutmayın. Bu etiketi yalnızca o denetimine uygulamak özelleştirmeleri sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)