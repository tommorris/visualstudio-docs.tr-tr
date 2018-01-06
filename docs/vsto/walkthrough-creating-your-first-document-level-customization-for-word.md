---
title: "İzlenecek yol: Word için ilk belge düzeyi özelleştirmeyi oluşturma | Microsoft Docs"
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
- Office development in Visual Studio, creating your first project
- Word [Office development in Visual Studio], creating your first project
- document-level customizations [Office development in Visual Studio], creating your first project
ms.assetid: ec9f5173-0923-4aee-985a-e760e80eaae3
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6d732f16d6794fbe59dd6f67fa904fcee916ce69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-your-first-document-level-customization-for-word"></a>İzlenecek Yol: Word İçin İlk Belge Düzeyi Özelleştirmeyi Oluşturma
  Bu tanıtıcı kılavuz Microsoft Office Word için belge düzeyi özelleştirme oluşturulacağını gösterir. Bu tür bir çözüm içinde oluşturduğunuz özellikler, yalnızca belirli bir belge açık olduğunda kullanılabilir. Belge düzeyi özelleştirme uygulama çapında değişiklik yapmak için kullanamazsınız, örneğin, herhangi bir belge açık olduğunda yeni bir Şerit sekmesi görüntüleme gibi.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Bir Word belgesi projesi oluşturma.  
  
-   Visual Studio Tasarımcısı'nda barındırılan belgeye metin ekleme.  
  
-   Açıldığında özelleştirilmiş belgeye metin eklemek için Word nesne modelini kullanan kod yazma.  
  
-   Derleme ve test etmek için proje çalışıyor.  
  
-   Gereksiz yapı dosyalarını ve güvenlik ayarlarını Geliştirme bilgisayarınızdan kaldırmak için projeyi temizleniyor.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
  
#### <a name="to-create-a-new-word-document-project-in-visual-studio"></a>Visual Studio'da yeni bir Word belgesi projesi oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Genişletilmiş altında **Office/SharePoint** düğümü, select **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde bir Word VSTO belgesi projesini seçin.  
  
6.  İçinde **adı** kutusuna **FirstDocumentCustomization**.  
  
7.  **Tamam**'ı tıklatın.  
  
     **Office Proje Sihirbazı için Visual Studio Araçları** açar.  
  
8.  Seçin **bir yeni belge oluşturun**, tıklatıp **Tamam**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]oluşturur **FirstDocumentCustomization** proje ve ekler **FirstDocumentCustomization** belge ve ThisDocument kod dosyası projeye. **FirstDocumentCustomization** belge otomatik olarak Tasarımcısı'nda açılır.  
  
## <a name="closing-and-reopening-the-document-in-the-designer"></a>Tasarımcısı'nda belgeyi yeniden açmayı  
 Projenizi geliştirirken kasıtlı olarak veya yanlışlıkla tasarımcısındaki belgede kapatırsanız, yeniden açabilirsiniz.  
  
#### <a name="to-close-and-reopen-the-document-in-the-designer"></a>Belgenin Tasarımcısı'nda kapatıp yeniden yükleme için  
  
1.  Tıklayarak belgeyi kapatın **Kapat** Tasarımcısı penceresinin düğmesine (X).  
  
2.  İçinde **Çözüm Gezgini**, sağ **ThisDocument** tıklayın ve kod dosyası **Görünüm Tasarımcısı**.  
  
     \-veya -  
  
     İçinde **Çözüm Gezgini**, çift **ThisDocument** kod dosyası.  
  
## <a name="adding-text-to-the-document-in-the-designer"></a>Tasarımcıda belgeye metin ekleme  
 Tasarımcıda açık olan belgeyi değiştirerek özelleştirmenizin kullanıcı arabirimi (UI) tasarlayabilirsiniz. Örneğin, metin, tablolar veya Word denetimleri ekleyebilirsiniz. Tasarımcıyı kullanma hakkında daha fazla bilgi için bkz: [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
#### <a name="to-add-text-to-your-document-by-using-the-designer"></a>Tasarımcı kullanarak, belgeye metin ekleme  
  
1.  Tasarımcıda açık belgede aşağıdaki metni yazın.  
  
     **Bu metin, tasarımcıyı kullanarak eklendi.**  
  
## <a name="adding-text-to-the-document-programmatically"></a>Program aracılığıyla belgeye metin ekleme  
 Ardından, kodu ThisDocument kod dosyasına ekleyin. Yeni kod, ikinci bir paragraf metni belgeye eklemek için Word nesne modelini kullanır. Varsayılan olarak, ThisDocument kod dosyası aşağıdaki oluşturulmuş kodu içerir:  
  
-   Kısmi tanımının `ThisDocument` belgenin programlama modelini gösteren ve Word nesne modeline erişim sağlayan sınıf. Daha fazla bilgi için bkz: [belge konak öğesi](../vsto/document-host-item.md) ve [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md). Geri kalan `ThisDocument` sınıfı değiştirmemeniz gereken gizli kod dosyasında tanımlanır.  
  
-   `ThisDocument_Startup` Ve `ThisDocument_Shutdown` olay işleyicileri. Belge açılır ve bu olay işleyicileri çağırılır. Bu olay işleyicileri belge açıldığında Eklentinizi başlatmak ve belge kapatıldığında özelleştirmeniz tarafından kullanılan kaynakları temizlemek için kullanın. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-a-second-paragraph-of-text-to-the-document-by-using-code"></a>Kod kullanarak belgeye metin ikinci bir paragraf eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **ThisDocument**ve ardından **görünümü kodu**.  
  
     Visual Studio'da kod dosyasını açar.  
  
2.  Değiştir `ThisDocument_Startup` aşağıdaki kod ile olay işleyicisi. Belge açıldığında, bu kod belgeye ikinci bir paragraf metni ekler.  
  
     [!code-vb[Trin_WordDocumentTutorial#1](../vsto/codesnippet/VisualBasic/FirstDocumentCustomization/ThisDocument.vb#1)]
     [!code-csharp[Trin_WordDocumentTutorial#1](../vsto/codesnippet/CSharp/FirstDocumentCustomization/ThisDocument.cs#1)]  
  
    > [!NOTE]  
    >  Bu kod, ilk paragrafa erişmek için dizin değeri 1 kullanır <xref:Microsoft.Office.Tools.Word.Document.Paragraphs%2A> özelliği. Visual Basic ve Visual C# 0 tabanlı diziler kullansa da, Word nesne modelindeki birçok koleksiyonun düşük dizi sınırları 1'dir. Daha fazla bilgi için bkz: [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md).  
  
## <a name="testing-the-project"></a>Projeyi test etme  
  
#### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Tuşuna **F5** oluşturun ve projenizin çalıştırın.  
  
     Projeyi derlerken belge ile ilişkili bütünleştirilmiş kodu derlenir. Visual Studio projesi için derleme çıktısı klasöründeki belgeyi ve derleme bir kopyasını koyar ve çalıştırmak özelleştirmeyi etkinleştirmek için geliştirme bilgisayarınızda güvenlik ayarlarını yapılandırır. Daha fazla bilgi için bkz: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
2.  Belgede, aşağıdaki metni gördüğünüzü doğrulayın.  
  
     **Bu metin, tasarımcıyı kullanarak eklendi.**  
  
     **Bu metin, kod kullanarak eklendi.**  
  
3.  Belgeyi kapatın.  
  
## <a name="cleaning-up-the-project"></a>Projeyi temizleme  
 Projeyi geliştirmeyi bitirdiğinizde yapı çıktı klasörüne ve yapı işlemi tarafından oluşturulan güvenlik ayarlarını dosyaları kaldırmanız gerekir.  
  
#### <a name="to-clean-up-the-completed-project-on-your-development-computer"></a>Geliştirme bilgisayarınızda tamamlanmış projeyi temizlemek için  
  
1.  Visual Studio'da üzerinde **yapı** menüsünde tıklatın **temiz çözüm**.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Word için temel bir belge düzeyi özelleştirme oluşturduğunuza göre aşağıdaki konulardan özelleştirmeleri geliştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Belge düzeyi özelleştirmelerinde gerçekleştirebileceğiniz genel programlama görevleri: [belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md).  
  
-   Word için belge düzeyi özelleştirmelerine özel programlama görevleri: [Word çözümleri](../vsto/word-solutions.md).  
  
-   Word nesne modelini kullanarak: [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md).  
  
-   Word UI'ını özelleştirme, örneğin, göre Şerite özel bir sekme ekleme veya kendi Eylemler bölmesi oluşturma: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
-   Word nesne modeli (örneğin, belgelerdeki yönetilen denetimleri ve Windows Forms veri kullanarak veriye Word denetimi bağlama kullanarak mümkün olmayan görevleri gerçekleştirmek için Visual Studio'da Office çözümleri tarafından sağlanan genişletilmiş Word nesnelerini kullanma bağlama modelini): [genişletilmiş nesneleri kullanarak Word otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md).  
  
-   Derleme ve Word için belge düzeyi özelleştirmeleri hata ayıklama: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
-   Word için belge düzeyi özelleştirmelerini dağıtma: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Word çözümleri](../vsto/word-solutions.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office Proje Şablonlarına Genel Bakış](../vsto/office-project-templates-overview.md)  
  
  