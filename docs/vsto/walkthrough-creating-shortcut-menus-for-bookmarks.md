---
title: 'İzlenecek yol: Yer işaretleri için kısayol menüleri oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context menus, Word
- Bookmark control, events
- shortcut menus, Word
- menus, creating in Office applications
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6d54d23330c6d5fab836f168a291b15b90379117
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-shortcut-menus-for-bookmarks"></a>İzlenecek Yol: Yer İşaretleri İçin Kısayol Menüleri Oluşturma
  Bu anlatımda için kısayol menüleri oluşturma gösterilir <xref:Microsoft.Office.Tools.Word.Bookmark> Word için belge düzeyi özelleştirmelerinde kontrol eder. Bir kullanıcı bir yer işareti metinde tıklattığında bir kısayol menüsü görüntülenir ve metin biçimlendirme için kullanıcı seçenekler sunar.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   [Proje oluşturma](#BKMK_CreateProject).  
  
-   [Metin ve yer işaretleri belgeye ekleyerek](#BKMK_addtextandbookmarks).  
  
-   [Komut için kısayol menüsü ekleme](#BKMK_AddCmndsShortMenu).  
  
-   [Yer işareti metni Biçimlendir](#BKMK_formattextbkmk).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] Veya [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]  
  
##  <a name="BKMK_CreateProject"></a> Proje oluşturma  
 İlk adım, Visual Studio'da bir Word belgesi projesi oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
-   Adına sahip bir Word belgesi projesi oluşturma **My yer işareti kısayol menüsünü**. Sihirbazı'nda seçin **bir yeni belge oluşturun**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio tasarımcıda yeni Word belgesini açar ve ekler **My yer işareti kısayol menüsünü** için proje **Çözüm Gezgini**.  
  
##  <a name="BKMK_addtextandbookmarks"></a> Belgeye metin ve yer işaretleri ekleme  
 Bazı metinleri belgenize ekleyin ve sonra iki örtüşen yer işareti ekleyin.  
  
#### <a name="to-add-text-to-your-document"></a>Metin belgenize eklemek için  
  
-   Proje Tasarımcısı'nda görüntülenen belgede aşağıdaki metni yazın.  
  
     **Bu, bir yer işareti metni sağ tıklattığınızda bir kısayol menüsü oluşturma bir örnektir.**  
  
#### <a name="to-add-a-bookmark-control-to-your-document"></a>Bir yer işareti denetimi belgenize eklemek için  
  
1.  İçinde **araç**, gelen **Word denetimleri** sekmesinde, sürükleyin bir <xref:Microsoft.Office.Tools.Word.Bookmark> belgenize denetimi.  
  
     **Yer işareti Denetimi Ekle** iletişim kutusu görüntülenir.  
  
2.  "Metni sağ tıklattığınızda bir kısayol menüsü oluşturma" sözcükler seçin ve ardından **Tamam**.  
  
     `bookmark1` belgeye eklenir.  
  
3.  Başka bir tane eklemek <xref:Microsoft.Office.Tools.Word.Bookmark> "yer işareti metnin sağ" sözcükleri denetim.  
  
     `bookmark2` belgeye eklenir.  
  
    > [!NOTE]  
    >  "Metnin sağ tıklayın", olan hem de sözcükler `bookmark1` ve `bookmark2`.  
  
 Tasarım zamanında bir belge için bir yer işareti eklediğinizde bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetimi oluşturulur. Yer işareti birkaç olaylara karşı programlama yapabilirsiniz. Kod yazabilirsiniz <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick> olay işaretinin kullanıcı yer işareti metinde tıklattığında bir kısayol menüsü görüntülenir.  
  
##  <a name="BKMK_AddCmndsShortMenu"></a> Komut için kısayol menüsü ekleme  
 Düğme belge sağ tıklattığınızda görüntülenen kısayol menüsü ekleme.  
  
#### <a name="to-add-commands-to-a-shortcut-menu"></a>Bir kısayol menü komutları eklemek için  
  
1.  Ekleme bir **Şerit XML** proje öğesi. Daha fazla bilgi için bkz: [nasıl yapılır: Get Şerit özelleştirme başlatılan](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
2.  İçinde **Çözüm Gezgini**seçin **ThisDocument.vb** veya **ThisDocument.vb**.  
  
3.  Menü çubuğunda seçin **Görünüm**, **kod**.  
  
     **ThisDocument** sınıf dosyası Kod Düzenleyicisi'nde açar.  
  
4.  Aşağıdaki kodu ekleyin **ThisDocument** sınıfı. Bu kod yöntemini geçersiz kılar ve Şerit XML sınıfını Office uygulamaya döndürür.  
  
     [!code-csharp[Trin_Word_Document_Menus#1](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#1)]
     [!code-vb[Trin_Word_Document_Menus#1](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#1)]  
  
5.  İçinde **Çözüm Gezgini**, Şerit XML dosyası seçin. Varsayılan olarak, Ribbon1.xml Şerit XML dosyasının adı.  
  
6.  Menü çubuğunda seçin **Görünüm**, **kod**.  
  
     Şerit xml dosyası Kod Düzenleyicisi'nde açılır.  
  
7.  Kod Düzenleyicisi'nde Şerit XML dosyasının içeriğini aşağıdaki kodla değiştirin.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?>  
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui" onLoad="Ribbon_Load">  
      <contextMenus>  
        <contextMenu idMso="ContextMenuText">  
          <button id="BoldButton" label="Bold" onAction="ButtonClick"          
               getVisible="GetVisible" />  
          <button id="ItalicButton" label="Italic" onAction="ButtonClick"   
              getVisible="GetVisible"/>  
        </contextMenu>  
      </contextMenus>  
    </customUI>  
    ```  
  
     Bu kod, belgeyi sağ tıklattığınızda görüntülenen kısayol menüsü iki düğmeleri ekler.  
  
8.  İçinde **Çözüm Gezgini**, sağ `ThisDocument`ve ardından **görünümü kodu**.  
  
9. Aşağıdaki değişkenler ve sınıf düzeyinde bir yer işareti değişken bildirin.  
  
     [!code-csharp[Trin_Word_Document_Menus#2](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#2)]
     [!code-vb[Trin_Word_Document_Menus#2](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#2)]  
  
10. İçinde **Çözüm Gezgini**, Şerit kod dosyasını seçin. Varsayılan olarak, Şerit kod dosyası adlı **Ribbon1.cs** veya **Ribbon1.vb**.  
  
11. Menü çubuğunda seçin **Görünüm**, **kod**.  
  
     Şerit kod dosyası Kod Düzenleyicisi'nde açılır.  
  
12. Şerit kod dosyasında aşağıdaki yöntemi ekleyin. Bu belge kısayol menüsüne eklenen iki düğmeleri için bir geri çağırma yöntemidir. Bu yöntem, bu düğmeleri kısayol menüsünde görünüp görünmeyeceğini belirler. Yalnızca yer işareti içinde metnin sağ tıklattığınızda, kalın ve italik düğmeleri görünür.  
  
     [!code-csharp[Trin_Word_Document_Menus#5](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/ribbon1.cs#5)]
     [!code-vb[Trin_Word_Document_Menus#5](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/ribbon1.vb#5)]  
  
##  <a name="BKMK_formattextbkmk"></a> Yer işareti metni biçimlendirme  
  
#### <a name="to-format-the-text-in-the-bookmark"></a>Yer işareti metinde biçimlendirmek için  
  
1.  Şerit kod dosyasına ekleyin bir `ButtonClick` işaretine biçimlendirme uygulamak için olay işleyicisi.  
  
     [!code-csharp[Trin_Word_Document_Menus#6](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/ribbon1.cs#6)]
     [!code-vb[Trin_Word_Document_Menus#6](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/ribbon1.vb#6)]  
  
2.  **Çözüm Gezgini**seçin **ThisDocument.vb** veya **ThisDocument.vb**.  
  
3.  Menü çubuğunda seçin **Görünüm**, **kod**.  
  
     **ThisDocument** sınıf dosyası Kod Düzenleyicisi'nde açar.  
  
4.  Aşağıdaki kodu ekleyin **ThisDocument** sınıfı.  
  
     [!code-csharp[Trin_Word_Document_Menus#3](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#3)]
     [!code-vb[Trin_Word_Document_Menus#3](../vsto/codesnippet/VisualBasic/trin_word_document_menus.vb/thisdocument.vb#3)]  
  
    > [!NOTE]  
    >  Yer işaretleri çakıştığı durumu işlemek için kod yazmanız gerekir. Varsayılan olarak, istemiyorsanız kodu Seçimdeki tüm yer işaretleri için çağrılır.  
  
5.  C# ' ta yer işareti denetimleri için olay işleyicileri eklemelisiniz <xref:Microsoft.Office.Tools.Word.Document.Startup> olay. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_Word_Document_Menus#4](../vsto/codesnippet/CSharp/trin_word_document_menus.cs/thisdocument.cs#4)]  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Yer işareti metinde sağ tıklattığınızda kalın ve italik menü öğelerini kısayol menüsünde görünen ve metin doğru şekilde yapılandırıldığını doğrulamak için belgenizi sınayın.  
  
#### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  İlk işaretinin sağ tıklayın ve ardından **kalın**.  
  
3.  Doğrulayın tüm metni `bookmark1` kalın olarak biçimlendirilir.  
  
4.  Yer işaretleri çakıştığı, metnin sağ tıklayın ve ardından **italik**.  
  
5.  Doğrulayın tüm metni `bookmark2` italik ve yalnızca metin parçası `bookmark1` çakışan `bookmark2` italik.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Excel konak denetimleri olaylarına tepki vermek için kod yazın. Daha fazla bilgi için bkz: [izlenecek yol: programlama karşı olayları NamedRange denetimi](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md).  
  
-   Bir yer işaretine biçimlendirme değiştirmek için onay kutusunu kullanın. Daha fazla bilgi için bkz: [izlenecek yol: değiştirme belgenin biçimlendirme kullanarak onay kutusu denetimleri](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Word kullanımında izlenecek yollar](../vsto/walkthroughs-using-word.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Yer işareti denetimi](../vsto/bookmark-control.md)   
 [Office Çözümlerinde İsteğe Bağlı Parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  