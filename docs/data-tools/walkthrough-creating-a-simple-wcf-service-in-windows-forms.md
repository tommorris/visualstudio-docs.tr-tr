---
title: "İzlenecek yol: Windows Forms'ta basit bir WCF hizmeti oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: c45ea549f17d71fd524a96e7d019c2b0d86bc628
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-simple-wcf-service-in-windows-forms"></a>İzlenecek yol: Windows Forms'ta basit bir WCF hizmeti oluşturma
Bu kılavuzda nasıl basit bir oluşturulduğunu gösteren [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] hizmet, test ve bir Windows Forms uygulamasında erişebilir.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-service"></a>Hizmeti Oluşturma  
  
#### <a name="to-create-a-wcf-service"></a>Bir WCF hizmeti oluşturmak için  
  
1.  Üzerinde **dosya** menüsündeki **yeni** ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual Basic** veya **Visual C#** düğümü ve tıklatın **WCF**, ardından **WCF Hizmet Kitaplığı**. Tıklatın **Tamam** projeyi açın.  
  
     ![WCF hizmet kitaplığı proje](../data-tools/media/wcf1.PNG "wcf1")  
  
    > [!NOTE]
    >  Bu, test ve erişilen bir çalışma hizmet oluşturur. Aşağıdaki iki adımı, farklı veri türünü kullanmak için varsayılan yöntemi nasıl değiştirileceği göstermektedir. Gerçek bir uygulamada kendi işlevleri hizmete eklersiniz.  
  
3.  ![IService1 dosya](../data-tools/media/wcf2.png "wcf2")  
  
     İçinde **Çözüm Gezgini**, IService1.vb veya IService1.cs çift tıklayın ve aşağıdaki satırı bulun:  
  
     [!code-csharp[WCFWalkthrough#4](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.cs)]
     [!code-vb[WCFWalkthrough#4](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.vb)]  
  
     Türünü değiştir `value` dizeye parametre:  
  
     [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.cs)]
     [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.vb)]  
  
     Yukarıdaki kodda Not `<OperationContract()>` veya `[OperationContract]` öznitelikleri. Bu öznitelikler hizmeti tarafından sunulan herhangi bir yöntem gereklidir.  
  
4.  ![Service1 dosyayı](../data-tools/media/wcf3.png "wcf3")  
  
     İçinde **Çözüm Gezgini**Service1.vb veya service1.cs dosyasını çift tıklatın ve aşağıdaki satırı bulun:  
  
     [!code-vb[WCFWalkthrough#5](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.vb)]
     [!code-csharp[WCFWalkthrough#5](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.cs)]  
  
     Değer parametresinin türü için bir dize değiştirin:  
  
     [!code-csharp[WCFWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.cs)]
     [!code-vb[WCFWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.vb)]  
  
## <a name="testing-the-service"></a>Hizmet test etme  
  
#### <a name="to-test-a-wcf-service"></a>Bir WCF Hizmeti sınamak için  
  
1.  Tuşuna **F5** hizmetini çalıştırmak için. A **WCF Test istemcisi** form görüntülenir ve hizmet yüklenir.  
  
2.  İçinde **WCF Test istemcisi** formunda, çift **GetData()** yöntemi altında **IService1**. **GetData** sekmesi görüntülenir.  
  
     ![GetData &#40; &#41; yöntem](../data-tools/media/wcf4.png "wcf4")  
  
3.  İçinde **isteği** kutusunda **değeri** alanı ve türü `Hello`.  
  
     ![Değer alanı](../data-tools/media/wcf5.png "wcf5")  
  
4.  Tıklatın **Invoke** düğmesi. Varsa bir **Güvenlik Uyarısı** iletişim kutusu görüntülenir, tıklatın **Tamam**. Sonuç görüntülenir **yanıt** kutusu.  
  
     ![Sonucun yanıt kutusunda](../data-tools/media/wcf6.png "wcf6")  
  
5.  Üzerinde **dosya** menüsünde tıklatın **çıkış** test formunu kapatmak için.  
  
## <a name="accessing-the-service"></a>Hizmete erişim  
  
#### <a name="to-reference-a-wcf-service"></a>Bir WCF Hizmeti referansı  
  
1.  Üzerinde **dosya** menüsündeki **Ekle** ve ardından **yeni proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual Basic** veya **Visual C#** düğümü ve seçin **Windows**ve ardından **Windows Forms uygulamasına**. Tıklatın **Tamam** projeyi açın.  
  
     ![Windows Forms uygulaması projesi](../data-tools/media/wcf7.png "wcf7")  
  
3.  Sağ **WindowsApplication1** tıklatıp **hizmet Başvurusu Ekle**. **Hizmet Başvurusu Ekle** iletişim kutusu görüntülenir.  
  
4.  İçinde **hizmet Başvurusu Ekle** iletişim kutusu, tıklatın **bulma**.  
  
     ![Hizmet Başvurusu Ekle iletişim kutusu](../data-tools/media/wcf8.png "wcf8")  
  
     **Service1** görüntülenmesi **Hizmetleri** bölmesi.  
  
5.  Tıklatın **Tamam** hizmet başvurusu eklemek için.  
  
#### <a name="to-build-a-client-application"></a>Bir istemci uygulaması oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, çift **Form1.vb** veya **Form1.cs** Windows Form Tasarımcısı zaten açık değilse açın.  
  
2.  Gelen **araç**, sürükleyin bir `TextBox` denetimi, bir `Label` denetimi ve `Button` forma denetim.  
  
     ![Forma denetim ekleme](../data-tools/media/wcf9.png "wcf9")  
  
3.  Çift `Button`ve aşağıdaki kodu ekleyin `Click` olay işleyicisi:  
  
     [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.cs)]
     [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.vb)]  
  
4.  İçinde **Çözüm Gezgini**, sağ **WindowsApplication1** tıklatıp **başlangıç projesi olarak ayarla**.  
  
5.  Tuşuna **F5** projeyi çalıştırın. Bazı metinleri girin ve düğmesini tıklatın. Etiketini görüntüler "girdiğiniz:" ve girdiğiniz metin.  
  
     ![Sonuç gösteren form](../data-tools/media/wcf10.png "wcf10")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Communication Foundation Hizmetleri ve Visual Studio'da WCF Veri Hizmetleri](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)