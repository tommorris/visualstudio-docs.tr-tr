---
title: "İzlenecek yol: içerik denetimlerini kullanarak şablon oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- building blocks [Office development in Visual Studio]
- Word [Office development in Visual Studio], creating documents
- content controls [Office development in Visual Studio], adding to documents
ms.assetid: 88fb9a60-dcc3-4a5f-a8c9-7aff01ca4b4b
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7edb589551f888427be6abcbb8f86c2e86b4349c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-template-by-using-content-controls"></a>İzlenecek Yol: İçerik Denetimlerini Kullanarak Şablon Oluşturma
  Bu kılavuzda nasıl yapılandırılmış ve yeniden kullanılabilir içerik bir Microsoft Office Word şablonu oluşturmak için içerik denetimleri kullanan bir belge düzeyi özelleştirme oluşturulacağını gösterir.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word'ün adı yeniden kullanılabilir belge kısımlarının bir koleksiyonunu oluşturmanızı sağlar *yapı taşları*. Bu kılavuzda yapı taşları olarak iki tablo oluşturulacağını gösterir. Her tablo içerik düz metin veya tarihleri gibi farklı türlerde tutabilir birçok içerik denetimi içerir. Tablolardan biri bir çalışan hakkındaki bilgileri içerir ve diğer tablo müşteri geri bildirimi içerir.  
  
 Belge şablonu oluşturduktan sonra tablo ya da belgeye birkaç kullanarak ekleyebilirsiniz <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> kullanılabilir yapı taşlarını şablonda görüntüleme nesneleri.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   İçeriği içeren tablolar oluşturma Word şablonu tasarım zamanında denetler.  
  
-   Birleşik giriş kutusu içerik denetimini ve aşağı açılan liste program aracılığıyla doldurma.  
  
-   Kullanıcıların, belirtilen bir tablodaki düzenlemelerini engelleme.  
  
-   Bir şablon Yapı bloğu koleksiyonuna tablolar ekleme.  
  
-   İçerik denetimi oluşturma kullanılabilir yapı taşlarını şablonda görüntüler.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word.  
  
## <a name="creating-a-new-word-template-project"></a>Yeni bir Word şablonu projesi oluşturma  
 Word şablonu oluşturun, böylece kullanıcılar kendi kopyalarını kolayca oluşturabilirsiniz.  
  
#### <a name="to-create-a-new-word-template-project"></a>Yeni bir Word şablonu projesi oluşturmak için  
  
1.  Adlı bir Word şablonu projesi oluşturun **ne MyBuildingBlockTemplate**. Sihirbazda, çözümdeki yeni belge oluşturun. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Yeni Word şablonu Tasarımcısı'nda açılır ve ekler **ne MyBuildingBlockTemplate** için proje **Çözüm Gezgini**.  
  
## <a name="creating-the-employee-table"></a>Çalışan tablosu oluşturma  
 Kullanıcı bir çalışan hakkındaki bilgileri girebilecekleri içerik denetimleri dört farklı türde içeren bir tablo oluşturun.  
  
#### <a name="to-create-the-employee-table"></a>Çalışan tablosu oluşturmak için  
  
1.  İçinde barındırılan Word şablonunda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Şerit üzerindeki Tasarımcısı'nı tıklatın **Ekle** sekmesi.  
  
2.  İçinde **tabloları** grubunda **tablo**ve 2 ve 4 sütun içeren bir tablo ekleyin.  
  
3.  Böylece aşağıdaki sütunun benzer ilk sütunda metni yazın:  
  
    ||  
    |-|  
    |**Çalışan adı**|  
    |**İşe alma tarihi**|  
    |**Başlık**|  
    |**Resmi**|  
  
4.  İkinci sütundaki ilk hücreyi tıklatın (yanına **çalışan adı**).  
  
5.  Şerit'te tıklatın **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
6.  İçinde **denetimleri** grubunda **metin** düğmesini ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") bir eklemekiçin<xref:Microsoft.Office.Tools.Word.PlainTextContentControl>ilk hücrenin.  
  
7.  İkinci sütunda ikinci hücreyi tıklatın (yanına **işe alma tarihi**).  
  
8.  İçinde **denetimleri** grubunda **tarih seçici** düğmesini ![DatePickerContentControl](../vsto/media/datepicker.gif "DatePickerContentControl") bir eklemekiçin<xref:Microsoft.Office.Tools.Word.DatePickerContentControl> ikinci hücreye.  
  
9. İkinci sütunda üçüncü hücreyi tıklatın (yanına **başlık**).  
  
10. İçinde **denetimleri** grubunda **birleşik giriş kutusu** düğmesini ![ComboBoxContentControl](../vsto/media/combobox.gif "ComboBoxContentControl") bir eklemekiçin<xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>üçüncü hücre.  
  
11. İkinci sütundaki son hücreyi tıklatın (yanına **resim**).  
  
12. İçinde **denetimleri** grubunda **resim içerik denetimi** düğmesini ![PictureContentControl](../vsto/media/pictcontentcontrol.gif "PictureContentControl") eklemek için bir <xref:Microsoft.Office.Tools.Word.PictureContentControl> son hücreye.  
  
## <a name="creating-the-customer-feedback-table"></a>Müşteri geri bildirimi tablosu oluşturma  
 İçerik denetimleri kullanıcı müşteri geri bildirim bilgilerini girebilecekleri üç farklı türde içeren bir tablo oluşturun.  
  
#### <a name="to-create-the-customer-feedback-table"></a>Müşteri geri bildirimi tablosu oluşturmak için  
  
1.  Word şablonu daha önce eklediğiniz çalışan tablosunun satırına tıklayın ve yeni bir paragraf eklemek için ENTER tuşuna basın.  
  
2.  Şerit'te tıklatın **Ekle** sekmesi.  
  
3.  İçinde **tabloları** grubunda **tablo**ve 2 ve 3 sütun içeren bir tablo ekleyin.  
  
4.  Böylece aşağıdaki sütunun benzer ilk sütunda metni yazın:  
  
    ||  
    |-|  
    |**Müşteri adı**|  
    |**Memnuniyet derecesi**|  
    |**Açıklamaları**|  
  
5.  İkinci sütunun ilk hücreyi tıklatın (yanına **müşteri adı**).  
  
6.  Şerit'te tıklatın **Geliştirici** sekmesi.  
  
7.  İçinde **denetimleri** grubunda **metin** düğmesini ![PlainTextContentControl](../vsto/media/plaintextcontrol.gif "PlainTextContentControl") bir eklemekiçin<xref:Microsoft.Office.Tools.Word.PlainTextContentControl>ilk hücrenin.  
  
8.  İkinci sütun ikinci hücreye tıklayın (yanına **memnuniyet derecelendirme**).  
  
9. İçinde **denetimleri** grubunda **aşağı açılan liste** düğmesini ![DropDownListContentControl](../vsto/media/dropdownlist.gif "DropDownListContentControl") eklemek için bir <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> ikinci hücreye.  
  
10. İkinci sütun son hücreye tıklayın (yanına **açıklamaları**).  
  
11. İçinde **denetimleri** grubunda **zengin metin** düğmesini ![RichTextContentControl](../vsto/media/richtextcontrol.gif "RichTextContentControl") bir eklemekiçin<xref:Microsoft.Office.Tools.Word.RichTextContentControl>son hücreye.  
  
## <a name="populating-the-combo-box-and-drop-down-list-programmatically"></a>Doldurma birleşik giriş kutusu ve açılan listeyi programlı olarak  
 Tasarım zamanında içerik denetimlerini kullanarak başlatabilirsiniz **özellikleri** penceresinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Bunları ilk durumlarını dinamik olarak ayarlamanıza olanak tanır, çalışma zamanında da başlatabilirsiniz. Bu kılavuzda yer alan girişleri doldurmak üzere kod kullanabilirsiniz <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> ve <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> çalışma zamanında nesnelerin nasıl çalıştığını görebilmeniz için.  
  
#### <a name="to-modify-the-ui-of-the-content-controls-programmatically"></a>İçerik denetimleri UI programlı olarak değiştirmek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **ThisDocument.vb** veya **ThisDocument.vb**ve ardından **görünümü kodu**.  
  
2.  Aşağıdaki kodu ekleyin `ThisDocument` sınıfı. Bu kod, bu kılavuzda daha sonra kullanacağınız birkaç nesneleri bildirir.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#1](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#1)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#1](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#1)]  
  
3.  Aşağıdaki kodu ekleyin `ThisDocument_Startup` yöntemi `ThisDocument` sınıfı. Bu kod girişlere ekler <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> ve <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> tabloları ve ayarlar her kullanıcı önce bu denetimlerin görüntülenen yer tutucu metnini bunları düzenler.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#2](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#2)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#2](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#2)]  
  
## <a name="preventing-users-from-editing-the-employee-table"></a>Kullanıcıların çalışan tablosunu düzenlemelerini engelleme  
 Kullanım <xref:Microsoft.Office.Tools.Word.GroupContentControl> çalışan tablosunu korumak için daha önce bildirilen nesne. Tabloyu koruduktan sonra kullanıcılar hala tablosundaki içerik denetimleri düzenleyebilirsiniz. Ancak, bunlar ilk sütunundaki metni düzenleyemez veya tablo ekleme veya satırları ve sütunları silme gibi diğer yollarla değiştirin. Nasıl kullanılacağı hakkında daha fazla bilgi için bir <xref:Microsoft.Office.Tools.Word.GroupContentControl> bir parçası olan bir belgeyi korumak için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
#### <a name="to-prevent-users-from-editing-the-employee-table"></a>Kullanıcıların çalışan tablosunu düzenlemesini engellemek için  
  
1.  Aşağıdaki kodu ekleyin `ThisDocument_Startup` yöntemi `ThisDocument` sınıfı, önceki adımda eklediğiniz koddan sonra. Bu kod kullanıcıların içine tabloyu koyarak çalışan tablosunu düzenlemesini engeller <xref:Microsoft.Office.Tools.Word.GroupContentControl> önceden bildirdiğiniz nesnesi.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#3](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#3)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#3](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#3)]  
  
## <a name="adding-the-tables-to-the-building-block-collection"></a>Yapı taşları koleksiyonuna tablolar ekleme  
 Böylece kullanıcılar, oluşturduğunuz tabloları belgeye ekleyebilirsiniz tabloları şablondaki belge yapı taşları koleksiyonuna ekleyin. Belge yapı taşları hakkında daha fazla bilgi için bkz: [içerik denetimleri](../vsto/content-controls.md).  
  
#### <a name="to-add-the-tables-to-the-building-blocks-in-the-template"></a>Yapı taşları şablondaki tabloları eklemek için  
  
1.  Aşağıdaki kodu ekleyin `ThisDocument_Startup` yöntemi `ThisDocument` sınıfı, önceki adımda eklediğiniz koddan sonra. Bu kod şablondaki tüm yeniden kullanılabilir yapı taşlarını içerir Microsoft.Office.Interop.Word.BuildingBlockEntries koleksiyonuna tablolar içeren yeni yapı taşları ekler. Yeni yapı taşları adlı yeni bir kategoride tanımlanan **çalışan ve müşteri bilgisi** ve yapı taşı türüne Microsoft.Office.Interop.Word.WdBuildingBlockTypes.wdTypeCustom1 atanır.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#4](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#4)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#4](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#4)]  
  
2.  Aşağıdaki kodu ekleyin `ThisDocument_Startup` yöntemi `ThisDocument` sınıfı, önceki adımda eklediğiniz koddan sonra. Bu kod şablondan tabloları siler. Tablo artık şablondaki yeniden kullanılabilir yapı taşları Galerisine eklediğiniz için gereklidir. Böylece korunan çalışan tablosunun silinebilmesi için kodu belge ilk tasarım moduna geçirir.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#5](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#5)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#5](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#5)]  
  
## <a name="creating-a-content-control-that-displays-the-building-blocks"></a>Yapı taşlarını görüntüleyen bir içerik denetimi oluşturma  
 Daha önce oluşturduğunuz yapı taşları (tablolar) erişim sağlayan bir içerik denetimi oluşturun. Kullanıcılar, belgeye tabloları eklemek için bu denetim tıklatabilirsiniz.  
  
#### <a name="to-create-a-content-control-that-displays-the-building-blocks"></a>Yapı taşlarını görüntüleyen bir içerik denetimi oluşturmak için  
  
1.  Aşağıdaki kodu ekleyin `ThisDocument_Startup` yöntemi `ThisDocument` sınıfı, önceki adımda eklediğiniz koddan sonra. Bu kod başlatır <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> önceden bildirdiğiniz nesnesi. <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> Kategorisinde tanımlanan tüm yapı taşlarını görüntüler **çalışan ve müşteri bilgisi** ve Microsoft.Office.Interop.Word.WdBuildingBlockTypes.wdTypeCustom1 yapı taşı türüne sahip.  
  
     [!code-vb[Trin_ContentControlTemplateWalkthrough#6](../vsto/codesnippet/VisualBasic/ContentControlTemplateWalkthrough/ThisDocument.vb#6)]
     [!code-csharp[Trin_ContentControlTemplateWalkthrough#6](../vsto/codesnippet/CSharp/ContentControlTemplateWalkthrough/ThisDocument.cs#6)]  
  
## <a name="testing-the-project"></a>Projeyi test etme  
 Kullanıcılar çalışan veya müşteri geri bildirim tablosunda eklemek için Belge Yapı Taşı Galerisi denetimlerinde tıklatabilirsiniz. Kullanıcıların tabloların hem de içerik denetimlerinde yanıtları seçin veya yazın. Kullanıcıların diğer bölümleri müşteri geri bildirimi tablosu değiştirebilirsiniz, ancak bunlar çalışan tablonun diğer bölümleri değiştiremez olmamalıdır.  
  
#### <a name="to-test-the-employee-table"></a>Çalışan tablosunu sınamak için  
  
1.  Projeyi çalıştırmak için F5 tuşuna basın.  
  
2.  Tıklatın **ilk yapı taşı seçmeniz** ilk Yapı Taşı Galerisi içerik denetimi görüntülemek için.  
  
3.  Aşağı açılan oku tıklatın **Özel Galeri 1** denetiminde başlık ve seçin **çalışan tablosu**.  
  
4.  Sağındaki hücreyi tıklatın **çalışan adı** hücre ve bir ad yazın.  
  
     Bu hücreyi yalnızca metin ekleyebilirsiniz doğrulayın. <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> Kullanıcıların yalnızca metin, resim veya bir tablo gibi içerik olmayan diğer türleri eklemesini sağlar.  
  
5.  Sağındaki hücreyi tıklatın **işe alma tarihi** hücre ve tarih seçiciden bir tarih seçin.  
  
6.  Sağındaki hücreyi tıklatın **başlık** hücre ve açılan kutuda iş başlıklarından birini seçin.  
  
     İsteğe bağlı olarak, listede olmayan bir iş unvanı adını yazın. Bu olasıdır çünkü <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> girişleri listeden seçin ya da kendi girişler yazmak için kullanıcılar sağlar.  
  
7.  Hücre sağındaki simgeyi tıklatın **resim** hücre ve görüntülemek için bir görüntüye göz atın.  
  
8.  Tabloya satır veya sütun eklemeyi deneyin ve satırları ve sütunları tablodan silmeyi deneyin. Tablo değiştirilemiyor doğrulayın. <xref:Microsoft.Office.Tools.Word.GroupContentControl> Herhangi bir değişiklik yapmanızı önler.  
  
#### <a name="to-test-the-customer-feedback-table"></a>Müşteri geri bildirimi tablosunu sınamak için  
  
1.  Tıklatın **ikinci yapı taşı seçmeniz** ikinci Yapı Taşı Galerisi içerik denetimi görüntülemek için.  
  
2.  Aşağı açılan oku tıklatın **Özel Galeri 1** denetiminde başlık ve seçin **müşteri tablosu**.  
  
3.  Sağındaki hücreyi tıklatın **müşteri adı** hücre ve bir ad yazın.  
  
4.  Sağındaki hücreyi tıklatın **memnuniyet derecelendirme** hücre ve kullanılabilir seçeneklerden birini seçin.  
  
     Kendi giriş yazamazsınız doğrulayın. <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> Kullanıcıların yalnızca bir girdi listesinden seçmesine izin verir.  
  
5.  Sağındaki hücreyi tıklatın **açıklamaları** hücre ve bir açıklama yazın.  
  
     İsteğe bağlı olarak, metin, resim veya katıştırılmış bir tablo gibi dışındaki bazı içeriği ekleyin. Bu olasıdır çünkü <xref:Microsoft.Office.Tools.Word.RichTextContentControl> kullanıcıların metin dışındaki içerikleri eklemesine olanak sağlar.  
  
6.  Tabloya satır veya sütun ekleyebilir ve tablodan satırları ve sütunları silebilirsiniz doğrulayın. Bu olasıdır, tablonun koyarak koruduğu değil çünkü bir <xref:Microsoft.Office.Tools.Word.GroupContentControl>.  
  
7.  Şablonu kapatın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu konuda içerik denetimlerini kullanma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   İçerik denetimleri, bir belgeye katıştırılmış özel XML parçaları olarak da adlandırılan XML parçalarının bağlar. Daha fazla bilgi için bkz: [izlenecek yol: içerik denetimlerini özel XML bölümlerine bağlama](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [İçerik denetimleri](../vsto/content-controls.md)   
 [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Nasıl yapılır: içerik denetimlerini kullanarak belge bölümlerini koruma](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  