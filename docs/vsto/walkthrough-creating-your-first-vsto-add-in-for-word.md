---
title: "İzlenecek yol: Word için ilk VSTO eklentinizi oluşturma | Microsoft Docs"
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
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- add-ins [Office development in Visual Studio], creating your first project
- Word [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3452bd5e550ab724dc6c236515579869814a9237
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-creating-your-first-vsto-add-in-for-word"></a>İnceleme: Word için İlk VSTO Eklentinizi Oluşturma
  Bu tanıtıcı kılavuz nasıl Microsoft Office Word için VSTO eklentisi oluşturulacağını gösterir. Bu tür bir çözüm içinde oluşturduğunuz özellikler uygulamanın kendisinin belgeler açık olan bağımsız olarak kullanılabilir.  
  
 [!INCLUDE[appliesto_wdallapp](../vsto/includes/appliesto-wdallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Word VSTO eklenti projesi oluşturma.  
  
-   Kaydedildiğinde bir belgeye metin eklemek için Word nesne modelini kullanan kod yazma.  
  
-   Derleme ve test etmek için proje çalışıyor.  
  
-   VSTO eklenti artık otomatik olarak geliştirme bilgisayarınızda çalışmaması için tamamlanmış projeyi temizleme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
  
#### <a name="to-create-a-new-word-vsto-add-in-project-in-visual-studio"></a>Visual Studio'da yeni bir Word VSTO eklenti projesi oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Genişletilmiş altında **Office/SharePoint** düğümü, select **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde bir Word VSTO eklenti projesini seçin.  
  
6.  İçinde **adı** kutusuna **FirstWordAddIn**.  
  
7.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]oluşturur **FirstWordAddIn** proje ve düzenleyicide ThisAddIn kod dosyasını açar.  
  
## <a name="writing-code-to-add-text-to-the-saved-document"></a>Kaydedilmiş belgeye metin eklemek için kod yazma  
 Ardından, kodu ThisAddIn kod dosyasına ekleyin. Yeni kod, kaydedilen her belge için standart bir metin eklemek için Word nesne modeli kullanır. Varsayılan olarak, aşağıdaki oluşturulmuş kodu ThisAddIn kod dosyasını içerir:  
  
-   Kısmi tanımının `ThisAddIn` sınıfı. Bu sınıf kodunuz için giriş noktası sağlar ve Word nesne modeline erişim sağlar. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md). Geri kalan `ThisAddIn` sınıfı değiştirmemeniz gereken gizli kod dosyasında tanımlanır.  
  
-   `ThisAddIn_Startup` Ve `ThisAddIn_Shutdown` olay işleyicileri. Bu olay işleyicileri Word yüklediğinde ve VSTO eklentinizi bellekten denir. Bu olay işleyicilerini VSTO eklentinizi yüklendiğinde başlatmak ve kaldırıldığında VSTO eklentinizi tarafından kullanılan kaynakları temizlemek için kullanın. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-a-paragraph-of-text-to-the-saved-document"></a>Paragraf metni kaydedilmiş belgeye eklemek için  
  
1.  ThisAddIn kod dosyasında aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Yeni kod için olay işleyicisini tanımlar <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> bir Belge kaydedildiğinde oluşan olayı,.  
  
     Kullanıcı bir belge kaydettiğinde, olay işleyicisi belge listesinin başında yeni metin ekler.  
  
     [!code-vb[Trin_WordAddInTutorial#1](../vsto/codesnippet/VisualBasic/FirstWordAddIn/ThisAddIn.vb#1)]
     [!code-csharp[Trin_WordAddInTutorial#1](../vsto/codesnippet/CSharp/FirstWordAddIn/ThisAddIn.cs#1)]  
  
    > [!NOTE]  
    >  Bu kod bir dizin değeri 1'in ilk paragrafa erişmek için kullanır. <xref:Microsoft.Office.Interop.Word._Document.Paragraphs%2A> koleksiyonu. Visual Basic ve Visual C# 0 tabanlı diziler kullansa da, Word nesne modelindeki birçok koleksiyonun düşük dizi sınırları 1'dir. Daha fazla bilgi için bkz: [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md).  
  
2.  C# kullanıyorsanız aşağıdaki gerekli kodu eklemek `ThisAddIn_Startup` olay işleyicisi. Bu kod bağlanmak için kullanılan `Application_DocumentBeforeSave` olay işleyicisi ile <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> olay.  
  
     [!code-csharp[Trin_WordAddInTutorial#2](../vsto/codesnippet/CSharp/FirstWordAddIn/ThisAddIn.cs#2)]  
  
 Belge kaydedildiğinde değiştirmek için önceki kod örnekleri aşağıdaki nesneleri kullanır:  
  
-   `Application` Alanını `ThisAddIn` sınıfı. `Application` Alan döndürür bir <xref:Microsoft.Office.Interop.Word.Application> Word geçerli örneği temsil eden nesne.  
  
-   `Doc` İçin olay işleyicisini parametresinin <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> olay. `Doc` Parametresi bir <xref:Microsoft.Office.Interop.Word.Document> kaydedilmiş belgeyi temsil eden nesne. Daha fazla bilgi için bkz: [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md).  
  
## <a name="testing-the-project"></a>Projeyi test etme  
  
#### <a name="to-test-the-project"></a>Projeyi test etmek için  
  
1.  Tuşuna **F5** oluşturun ve projenizin çalıştırın.  
  
     Projeyi derlerken kodunu projeyi derleme çıktı dosyasına dahil bütünleştirilmiş derlenir. Visual Studio ayrıca Word'ün bulmak ve VSTO eklenti etkinleştirmek kayıt defteri girdileri kümesini oluşturur ve VSTO eklenti çalıştırmak, geliştirici bilgisayarının güvenlik ayarlarını yapılandırır. Daha fazla bilgi için bkz: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
2.  Word'de etkin belgeyi Kaydet.  
  
3.  Aşağıdaki metni belgeye eklendiğini doğrulayın.  
  
     **Bu metin, kod kullanarak eklendi.**  
  
4.  Word'ü kapatın.  
  
## <a name="cleaning-up-the-project"></a>Projeyi temizleme  
 Projeyi geliştirmeyi bitirdiğinizde VSTO eklenti derlemesi, kayıt defteri girdileri ve güvenlik ayarlarını Geliştirme bilgisayarınızdan kaldırın. Aksi takdirde, VSTO eklenti geliştirme bilgisayarınızda Word'ü açın her zaman çalışmaya devam eder.  
  
#### <a name="to-clean-up-the-completed-project-on-your-development-computer"></a>Geliştirme bilgisayarınızda tamamlanmış projeyi temizlemek için  
  
1.  Visual Studio'da üzerinde **yapı** menüsünde tıklatın **temiz çözüm**.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Word için temel bir VSTO eklentisi oluşturduğunuza göre VSTO eklentileri aşağıdaki konulardan geliştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   VSTO eklentileri gerçekleştirebileceğiniz genel programlama görevleri: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
-   Word VSTO eklentileri için belirli programlama görevleri: [Word çözümleri](../vsto/word-solutions.md).  
  
-   Word nesne modelini kullanarak: [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md).  
  
-   Word UI'ını özelleştirme, örneğin, göre Şerite özel bir sekme ekleme veya kendi özel görev bölmesi oluşturma: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
-   Derleme ve Word için VSTO eklentileri hata ayıklama: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
-   Word için VSTO eklentileri dağıtma: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Word çözümleri](../vsto/word-solutions.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office Proje Şablonlarına Genel Bakış](../vsto/office-project-templates-overview.md)  
  
  