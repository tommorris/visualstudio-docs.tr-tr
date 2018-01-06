---
title: "İzlenecek yol: Bir belgeyi bir düğme kullanarak metin kutusunda metin görüntüleme | Microsoft Docs"
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
helpviewer_keywords: text boxes, displaying text in documents
ms.assetid: 04c54ed7-9f00-4068-aaec-1f3200110116
caps.latest.revision: "60"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 28d755d6123b2911bccd10e668212e1ea6a54484
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-text-in-a-text-box-in-a-document-using-a-button"></a>İzlenecek Yol: Belgedeki Metin Kutusunda Düğme Kullanarak Metin Görüntüleme
  Bu anlatımda düğmeleri ve belge düzeyi özelleştirmelerinde metin kutuları için Microsoft Office Word nasıl kullanılacağı gösterilir.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Tasarım zamanında bir belge düzeyi projede Word belgesine denetimler ekleme.  
  
-   Düğme tıklatıldığında metin kutusunu doldurma.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 İlk adım bir Word belgesi proje oluşturmaktır.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Adlı bir Word belgesi proje oluşturun **My Word Button**. Sihirbazı'nda seçin **bir yeni belge oluşturun**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio tasarımcıda yeni Word belgesini açar ve ekler **My Word Button** için proje **Çözüm Gezgini**.  
  
## <a name="adding-controls-to-the-word-document"></a>Word belgesine denetimler ekleme  
 Kullanıcı arabirimi denetimlerini bir düğmeyi ve bir metin kutusu Word belgesinde oluşur.  
  
#### <a name="to-add-a-button-and-a-text-box"></a>Bir düğme ve bir metin kutusu eklemek için  
  
1.  Belge Visual Studio Tasarımcısı'nda açık olduğunu doğrulayın.  
  
2.  Gelen **ortak denetimler** sekmesinde **araç**, sürükleyin bir <xref:Microsoft.Office.Tools.Word.Controls.TextBox> belgeye denetim.  
  
    > [!NOTE]  
    >  Word'de denetimleri bırakılan satır içi varsayılan metin. Yol denetimleri değiştirebilir ve şekil nesneleri üzerinde varsayılan değiştirerek eklenir **Düzenle** sekmesinde **seçenekleri** Word iletişim kutusu.  
  
3.  Üzerinde **Görünüm** menüsünde tıklatın **Özellikler penceresini**.  
  
4.  Bul **TextBox1** içinde **özellikleri** pencere açılan kutusu ve değişiklik **adı** özelliği metin kutusunun **görüntü metni**.  
  
5.  Sürükleme bir **düğmesini** denetlemek için belge ve aşağıdaki özellikleri değiştirin.  
  
    |Özellik|Değer|  
    |--------------|-----------|  
    |**Ad**|**E:System.Windows.Forms.Control.Click**|  
    |**Metin**|**Metin ekleme**|  
  
 Şimdi düğmesine tıklandığında, çalıştırılacak olan kodu yazabilirsiniz.  
  
## <a name="populating-the-text-box-when-the-button-is-clicked"></a>Düğme tıklatıldığında metin kutusunu doldurma  
 Kullanıcı düğmesine tıklar her zaman **Merhaba Dünya!** metin kutusuna eklenir.  
  
#### <a name="to-write-to-the-text-box-when-the-button-is-clicked"></a>Düğmesine tıklandığında metin kutusuna yazmak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **ThisDocument**ve ardından **görünümü kodu** kısayol menüsünde.  
  
2.  Aşağıdaki kodu ekleyin <xref:System.Windows.Forms.Control.Click> düğmesi olay işleyicisi.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsWord#7](../vsto/codesnippet/VisualBasic/my chart options/ThisDocument.vb#7)]
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#7)]  
  
3.  C# ' ta düğme için bir olay işleyicisi eklemelisiniz <xref:Microsoft.Office.Tools.Word.Document.Startup> olay. Olay işleyicileri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsWord#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsWordCS/ThisDocument.cs#8)]  
  
## <a name="testing-the-application"></a>Uygulamayı Test Etme  
 Belgenizi emin olmak için şimdi sınayabilirsiniz ileti **Merhaba Dünya!** Düğmeye tıkladığınızda metin kutusunda görüntülenir.  
  
#### <a name="to-test-your-document"></a>Belgenizi test etmek için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Düğmesini tıklatın.  
  
3.  Onaylayın **Merhaba Dünya!** metin kutusunda görüntülenir.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu anlatımda düğmeleri ve metin kutuları Word belgelerini kullanma temelleri gösterilir. Sonradan gelebilecek bazı görevler şunlardır:  
  
-   Birleşik giriş kutusu biçimlendirmeyi değiştirmek için kullanma. Daha fazla bilgi için bkz: [izlenecek yol: değiştirme belgenin biçimlendirme kullanarak onay kutusu denetimleri](../vsto/walkthrough-changing-document-formatting-using-checkbox-controls.md).  
  
-   Grafik türlerini seçmek için radyo düğmelerini kullanarak. Daha fazla bilgi için bkz: [izlenecek yol: belge kullanarak radyo düğmeleri grafik güncelleme](../vsto/walkthrough-updating-a-chart-in-a-document-using-radio-buttons.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Forms denetimleri Office belgeleri genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Word kullanımında izlenecek yollar](../vsto/walkthroughs-using-word.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Nasıl yapılır: Windows Forms denetimleri Office belgelerine ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  