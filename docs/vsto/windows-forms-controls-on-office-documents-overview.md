---
title: Windows Forms denetimleri Office belgeleri genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- old data showing in error [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], Word
- Windows Forms controls [Office development in Visual Studio], adding
- Windows Forms controls [Office development in Visual Studio], arranging
- data [Office development in Visual Studio], old data showing in error
- user controls [Office development in Visual Studio], Windows Forms
- Windows Forms controls [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], removing
- application development [Office development in Visual Studio], Windows Forms controls
- controls [Office development in Visual Studio], Windows Forms controls
- Office [Office development in Visual Studio], Windows Forms controls
- Office documents [Office development in Visual Studio, controls
- documents [Office development in Visual Studio], Windows Forms controls
- document-level customizations [Office development in Visual Studio], Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], about Windows Forms controls
- Office applications [Office development in Visual Studio], Windows Forms
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2693c31d06edc621f355749f76caf04e44fb28e1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="windows-forms-controls-on-office-documents-overview"></a>Office Belgelerindeki Windows Forms Denetimlerine Genel Bakış
  Windows Forms denetimleri kullanıcıları girin ya da verileri işlemek için etkileşim kurabildikleri nesneleridir. Microsoft Office Excel ve Microsoft Office Word için belge düzeyi projelerine, Windows Forms denetimleri belge veya çalışma kitabını projenizde tasarım zamanında ekleyebileceğiniz veya çalışma zamanında bu denetimlerini programlı olarak ekleyebilirsiniz. Program aracılığıyla bu denetimleri herhangi bir açık belgeye veya çalışma zamanında VSTO eklenti Excel veya Word'den ekleyebilirsiniz.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: Office belgelerine Windows Forms denetimleri ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="using-windows-forms-controls"></a>Windows Forms denetimlerini kullanma  
 Windows Forms denetimleri belgelere ve Eylemler bölmeleri, özel görev bölmeleri ve Windows Forms dahil olmak üzere özelleştirilebilir kullanıcı arabirimi (UI) öğeleri ekleyebilirsiniz. Windows Forms denetimleri genellikle bu bir kullanıcı Arabirimi öğeleri belgelerde üzerinde aynı davranışı sahiptir, ancak bazı farklar vardır. Bilgi için bkz: [sınırlamalar, Windows Forms denetimleri Office belgelerindeki](../vsto/limitations-of-windows-forms-controls-on-office-documents.md).  
  
 Windows Forms denetimleri bir belge veya başka bir kullanıcı Arabirimi öğesi eklemek birkaç etkene bağlıdır karar. Windows Forms denetimleri kullanımlarını UI çözümünüzü tasarlarken, aşağıdaki tabloda açıklandığı gibi göz önünde bulundurun.  
  
 Belge üzerinde.  
 -   % 100'zaman denetimlerini görüntülemek istediğinizde.  
  
-   Kullanıcıların doğrudan belgedeki verileri, örneğin, form tabanlı belgeleri düzenleme yüzeyini Kilitlediğiniz girmesini istediğinizde.  
  
-   Belgedeki verileri uygun olarak göstermek için denetimleri istediğinizde. Örneğin, bir liste nesnesi her satır için düğmeler ekliyorsanız, bunları uygun olarak her liste öğesi istersiniz.  
  
 Eylemler bölmesinde veya özel görev bölmesi.  
 -   Kullanıcıya bağlamsal bilgi sağlamak istediğinizde.  
  
-   Belge ve değil sorgu denetimleri ve veri görünmesini yalnızca sonuçları istediğinizde.  
  
-   Denetimleri belgeyle yazdırılır emin olmak istediğinizde değil.  
  
-   Denetimleri belgenin görüntüsüyle karışmadığına karışmaması sağlamak istediğinizde.  
  
 Bir Windows formunda.  
 -   Kullanıcı arabirimini boyutunu denetlemek istediğinizde.  
  
-   Kullanıcıların gizleme veya denetimleri silme engellemek istediğinizde.  
  
-   Kullanıcıdan giriş almak ve kullanıcının giriş alınana kadar belgede bir şey yapmasını önlemek istediğinizde.  
  
## <a name="adding-windows-forms-controls-programmatically"></a>Windows Forms denetimlerini programlı olarak ekleme  
 Windows Forms denetimlerini çalışma zamanında Word belgelerini ve Excel çalışma sayfalarına ekleyebilirsiniz. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] En yaygın Windows Forms denetimlerini eklemek için yardımcı yöntemleri sağlar. Bu yardımcı yöntemler, hızlı bir şekilde Office belge ve erişim birleşik Windows Forms Denetim işlevselliği için denetimleri ve bu denetimlerin Office ilgili işlevselliğini eklemenize olanak tanır.  
  
 Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
## <a name="using-windows-forms-controls-in-document-level-projects"></a>Windows Forms denetimlerini kullanma belge düzeyi projelerine  
 Bazı yönlerini belgelerindeki Windows Forms denetimleri kullanarak etkinleştirmeniz Visual Studio tasarımcısını kullanarak belgeyi UI tasarlamak belge düzeyi projelerine benzersizdir.  
  
### <a name="creating-custom-user-controls"></a>Özel kullanıcı denetimleri oluşturma  
 Bir kullanıcı denetimi projenize ekleyin ve ardından ekleyin **araç**. Bir Windows Forms denetimi belgenize eklediğiniz aynı şekilde doğrudan belgenize kullanıcı denetimini sonra sürükleyebilirsiniz. Kullanıcı denetimleri oluştururken göz önünde bulundurmanız gereken bazı şeyler vardır:  
  
-   Oluşturmayın bir **korumalı** kullanıcı denetimi. Belgenize denetimi sürüklediğinizde, Visual Studio genişletmek ve belge üzerinde kullanımını desteklemek için kullanıcı denetimi türetilmiş bir sarmalayıcı sınıfı oluşturur. Kullanıcı denetimi ise **korumalı**, Visual Studio sarmalayıcı sınıfı oluşturulamıyor.  
  
-   Kullanıcı denetimleri olmalıdır <xref:System.Runtime.InteropServices.ComVisibleAttribute> özniteliğini **doğru**. Bir Office projesi içinde oluşturulan kullanıcı denetimleri ayarlamak bu özniteliğe sahip **true** dış projelerin parçası olan denetimleri ayarlamak bu öznitelik olabilir, bu varsayılan, ancak kullanıcı tarafından değil **doğru**.  
  
-   Bir kullanıcı denetimi belgeye ekledikten sonra yeniden adlandırmak silmeyin veya <xref:System.Windows.Forms.UserControl> projeden sınıfı. Bir kullanıcı denetimi adını değiştirmeniz gerekiyorsa belgeden silmeniz ve ad değiştikten sonra yeniden ekleyin.  
  
### <a name="arranging-controls-at-design-time"></a>Tasarım zamanında denetimleri düzenleme  
 Tasarım zamanında Word ve Excel birden çok denetim eklerseniz, hızlı bir şekilde tüm seçili denetimlerin hizalamasını kullanarak ayarlayabilirsiniz **Microsoft Office Word** ve **Microsoft Office Excel**Visual Studio içinde araç çubukları. Bu araç çubukları, yalnızca belge veya çalışma tasarımcıda açık olduğunda kullanılabilir.  
  
 Birden çok denetim Tasarımcısı'nda seçtiğinizde denetimleri düzenlemek için bu araç çubuklarında aşağıdaki düğmeler kullanabilirsiniz:  
  
-   **Sola hizalayın**  
  
-   **Merkezleri hizalayın**  
  
-   **Sağa Hizala**  
  
-   **Üste hizalama**  
  
-   **Ortaya Hizala**  
  
-   **Alta Hizala**  
  
-   **Yatay boşluğu eşit yap**  
  
-   **Dikey aralığı eşit yap**  
  
> [!NOTE]  
>  Yalnızca Seçili denetimleri metinle değilse Word projelerinde bu düğmeleri etkinleştirilir. Varsayılan olarak, belgeye çalışma zamanında ekleme denetimleri metinle bulunur.  
  
### <a name="preventing-old-data-from-appearing-in-excel-workbooks-during-loading"></a>Eski veri yüklemesi sırasında Excel çalışma kitaplarını görünmesini engelleme  
 Windows Forms denetimleri belgeleri veya çalışma sayfalarına tasarım zamanında eklerken, kullanıcı belgenin kapandığında denetimleri belgede kalır. Tasarım zamanında eklenen denetimler de denir *statik denetimleri*.  
  
 Statik denetimleri içeren bir Excel çalışma kitabı açıldığında, çalışma kitabını ActiveX denetiminde bir bit eşlem denetimi özelleştirme kodu çalıştırır ve yükler gerçek denetim kadar görüntüler. Excel bu bit eşlemi oluşturur ve çalışma kitabı kaydedildiği zaman çalışma kitabında depolar. Denetimin görüntüleme herhangi bir veri dahil olmak üzere çalışma kitabını kaydedilmiş en son ne zaman göründüğü gibi bit eşlem denetimi gösterir. Windows Forms denetimleri ve bit eşlemler içeren ActiveX denetimi hakkında daha fazla bilgi için bkz: [sınırlamalar, Windows Forms denetimleri Office belgelerindeki](../vsto/limitations-of-windows-forms-controls-on-office-documents.md).  
  
 Bazı durumlarda, kod yüklemez ve sadece bit eşlemi, kullanıcı çalışma kitabını Tasarım modunda açtığında gibi görüntülenir. Ayrıca, kullanıcının sahip olmayan bir bilgisayarda çalışma kitabını açar, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yüklü, özelleştirme denetimleri yüklemek için çalışamaz ve bu nedenle yalnızca denetimin bit eşlemi görünür. Her zaman, çalışma kitabını kaydetmeden ve kişisel bilgilerinizi değil yanlışlıkla açıklanmasını emin olmak için başka bir kullanıcıya göndermeden önce çalışma kitaplarının denetimlerden kişisel bilgileri kaldırmalısınız.  
  
### <a name="matching-control-size-to-cell-size-on-an-excel-worksheet"></a>Excel çalışma sayfasındaki hücre boyutuna eşleşen denetim boyutu  
 Üst hücrenin boyutu değiştirildiğinde, otomatik olarak yeniden boyutlandırılıp denetimi ayarlayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: yeniden boyutlandırma denetimleri içinde çalışma sayfası hücreleri](../vsto/how-to-resize-controls-within-worksheet-cells.md).  
  
### <a name="adding-components-that-are-shared-by-all-worksheets"></a>Tüm çalışma sayfaları tarafından paylaşılan bileşenleri ekleme  
 Tüm çalışma sayfaları arasında gibi paylaşmak istediğiniz bileşenleri ekleyebilirsiniz bir <xref:System.Data.DataSet>, çalışma kitabı tasarımcısına çalışma sayfaları. Bileşen bileşen alanında görüntülenir.  
  
### <a name="formula-for-embedding-controls-on-an-excel-worksheet"></a>Excel çalışma sayfasındaki denetimleri katıştırma için formülü  
 Excel'de denetim seçtiğinizde göreceğiniz **=EMBED("WinForms.Control.Host","")** içinde **formül çubuğu**. Bu metin gereklidir ve silinmemelidir.  
  
### <a name="layout-style-of-controls-on-a-word-document"></a>Düzen Stili denetimlerin bir Word belgesi  
 Bir denetim bir belge düzeyi projede Word belgesi için Visual Studio tasarımcısını kullanarak eklerken, Denetim metin uygun olarak eklenir. Denetimin düzen stilini değiştirmek için denetimi sağ tıklatın ve ardından **biçimi Denetim**. Bir kaydırma stilini seçin **düzeni** sayfasında **biçimi nesne** iletişim kutusu.  
  
 Çalışma zamanında bir Word belgesi için bir denetim eklediğinizde, farklı kullanarak yeni denetimin düzen stilini belirtebilirsiniz `Add` \< *kontrol sınıfı*> yöntemi aşırı yüklemeleri <xref:Microsoft.Office.Tools.Word.ControlCollection> sınıfı:  
  
-   Denetim metin uygun olarak eklemek için kabul eden bir aşırı yüklemesini kullanın bir <xref:Microsoft.Office.Interop.Word.Range> denetimin konumunu belirtir.  
  
-   Kayan şekilli denetim eklemek için Denetim sol ve üst koordinatlarını kabul eden bir aşırı yüklemesini kullanın.  
  
 Daha fazla bilgi için bkz: [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Visual Studio Tasarımcısı'nda bir Word şablonu açarsanız, Visual Studio şablon açtığı için şablonda satır içi olmayan denetimler görünür olmayabilir **Normal** görünümü. Denetimleri görüntülemek için görünümü değiştirin **yazdırma düzeni**.  
  
### <a name="controls-outside-the-main-document-body"></a>Ana Belge gövdesi dışındaki denetimler  
 Windows Forms denetimleri üstbilgisinde veya altbilgisinde içinde ya da bir alt içinde desteklenmez.  
  
### <a name="adding-components-at-design-time"></a>Tasarım zamanında bileşenleri ekleme  
 Bazı denetimler veya bileşenden belge üzerinde görünür değildir ve bunun yerine bir bileşen tepsisinde görüntülenir. Visual Studio her belge penceresi için bileşen alanı sağlar. Yalnızca bileşenleri belge üzerinde varsa bileşen ekranında görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md)   
 [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index)   
 [Office belgelerindeki Windows Forms denetimleri sınırlamaları](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)   
 [Nasıl yapılır: Windows Forms denetimleri Office belgelerine ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Nasıl yapılır: çalışma sayfası hücreleri içinde denetimleri yeniden boyutlandırma](../vsto/how-to-resize-controls-within-worksheet-cells.md)   
 [Nasıl yapılır: yazdırırken çalışma sayfası denetimlerini gizleme](../vsto/how-to-hide-controls-on-worksheets-when-printing.md)   
 [İzlenecek yol: CheckBox denetimlerini kullanarak çalışma sayfası biçimlendirmesini değiştirme](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)   
 [İzlenecek yol: CheckBox denetimlerini kullanarak belge biçimlendirmesini değiştirme](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md)   
 [İzlenecek yol: Düğme kullanarak çalışma sayfasındaki metin kutusunda metin görüntüleme](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button.md)   
 [İzlenecek yol: Bir belgeyi bir düğme kullanarak metin kutusunda metin görüntüleme](../vsto/walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button.md)   
 [Office belgelerindeki Windows Forms denetimleri sınırlamaları](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)   
 [İzlenecek yol: radyo düğmelerini kullanarak belgede grafik güncelleme](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md)   
 [İzlenecek Yol: Radyo Düğmelerini Kullanarak Çalışma Sayfasında Grafik Güncelleme](../vsto/walkthrough-updating-a-chart-in-a-worksheet-using-radio-buttons.md)  
  
  