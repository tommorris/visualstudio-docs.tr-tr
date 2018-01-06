---
title: "Eğitmen 1: Resim Görüntüleyici oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3071d6df-2b2f-4e95-ab68-bef727323136
caps.latest.revision: "19"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b0537b1f335d46854dd43727ade695909db421ff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="tutorial-1-create-a-picture-viewer"></a>Eğitmen 1: Resim Görüntüleyici Oluşturma
Bu öğreticide, bir dosyadan bir resim yükler ve bir pencerede görüntüleyen bir program oluşturun. Düğmelerin ve resim kutularının formunuzda, bunların özelliklerini ayarlamak ve sorunsuz formu yeniden boyutlandırmak için kapsayıcılar kullanma gibi denetimleri sürükleyin öğrenin. Ayrıca, kod yazmaya başlayın. Aşağıdakilerin nasıl yapıldığını öğreneceksiniz:  
  
-   Yeni bir proje oluşturun.  
  
-   Test (hata ayıklama) bir uygulama.  
  
-   Onay kutuları ve düğmeleri gibi temel denetimleri forma ekleyin.  
  
-   Düzenleri kullanarak bir form üzerinde denetimleri getirin.  
  
-   Ekleme **açık dosya** ve **renk** bir forma iletişim kutuları.  
  
-   IntelliSense ve kod parçacıkları kod yazın.  
  
-   Olay işleyici yöntemleri yazma.  
  
 İşiniz bittiğinde, programınızı aşağıdaki resimde gibi görünecektir.  
  
 ![Bu öğreticide oluşturduğunuz resim](../ide/media/express_pictureviewerdone.png "Express_PictureViewerDone")  
Bu öğreticide oluşturduğunuz resmi  
  
 Tamamlanmış bir örnek sürümünü indirmek için bkz: [tam resim görüntüleyici öğretici örnek](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [nasıl I: oluşturmak Resim Görüntüleyici'de Visual Basic?](http://go.microsoft.com/fwlink/?LinkId=205207) veya [nasıl I: oluşturmak resim görüntüleyici C#?](http://go.microsoft.com/fwlink/?LinkId=205198).  
  
> [!NOTE]
>  Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır. Visual C# ve Visual Basic hem de Bu öğretici kapsamında olduğunu, kullanmakta olduğunuz programlama diline özgü bilgileri böylece odaklanır.  
>   
>  Visual Basic kodu görmek için seçin **VB** sekmesinde kod blokları üstünde ve kod Visual C# için görmek için seçin **C#** sekmesi. Visual C++ öğrenmeye ilginizi çekiyorsa bkz [Başlarken](../ide/getting-started-with-cpp-in-visual-studio.md) ve [C++ dili Öğreticisi](http://www.cplusplus.com/doc/tutorial/).  
>   
>  Visual C# veya Visual Basic UWP uygulamaları yazmak için bkz: öğrenmek, [yapı UWP uygulamaları](https://developer.microsoft.com/windows/apps).
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[1. Adım: Windows Forms Uygulaması Projesi Oluşturma](../ide/step-1-create-a-windows-forms-application-project.md)|Bir Windows Forms uygulaması projesi oluşturarak başlayın.|  
|[2. Adım: Programınızı Çalıştırma](../ide/step-2-run-your-program.md)|Önceki adımda oluşturduğunuz Windows Forms uygulaması programını çalıştırın.|  
|[3. Adım: Form Özelliklerinizi Ayarlama](../ide/step-3-set-your-form-properties.md)|Formunuz kullanarak görünüşünü değiştirme **özellikleri** penceresi.|  
|[4. Adım: TableLayoutPanel Denetimi ile Formunuzu Düzenleme](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)|Ekleme bir `TableLayoutPanel` Formunuza denetim.|  
|[5. Adım: Formunuza Denetimler Ekleme](../ide/step-5-add-controls-to-your-form.md)|Denetimleri gibi ekleme bir `PictureBox` denetim ve `CheckBox` Formunuza denetim. Düğmeleri formunuza ekleyin.|  
|[6. Adım: Düğme Denetimlerinizi Adlandırma](../ide/step-6-name-your-button-controls.md)|Düğmeleri daha anlamlı yeniden adlandırın.|  
|[7. Adım: Formunuza İletişim Kutusu Bileşenleri Ekleme](../ide/step-7-add-dialog-components-to-your-form.md)|Ekleme bir **OpenFileDialog** bileşeni ve bir **ColorDialog** formunuza bileşen.|  
|[8. Adım: Resim Göster Düğmesi Olay İşleyicisi için Kod Yazma](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)|IntelliSense aracını kullanarak bir kod yazın.|  
|[9. Adım: Kodunuzu Gözden Geçirme, Açıklama ve Test Etme](../ide/step-9-review-comment-and-test-your-code.md)|Gözden geçirin ve kodunuzu test etmek. Açıklamaları gerektiği gibi ekleyin.|  
|[10. Adım: Ek Düğmeler ve Onay Kutusu için Kod Yazma](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md)|Diğer düğmeleri ve IntelliSense kullanarak onay kutusu çalışma yapmak için kod yazma.|  
|[11. Adım: Programınızı Çalıştırma ve Diğer Özellikleri Deneme](../ide/step-11-run-your-program-and-try-other-features.md)|Programınızı çalıştırma ve arka plan rengini ayarlayın. Renkleri, yazı tipi ve kenarlıkları değiştirme gibi diğer özellikleri deneyin.|