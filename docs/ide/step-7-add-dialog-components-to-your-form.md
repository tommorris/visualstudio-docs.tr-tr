---
title: "7. adım: Formunuza iletişim kutusu bileşenleri ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea98c55e-6213-4893-ba7b-f19d7f119527
caps.latest.revision: "15"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: da81862b736605b93d4429e0e574ca5558a529c9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="step-7-add-dialog-components-to-your-form"></a>7. Adım: Formunuza İletişim Kutusu Bileşenleri Ekleme
Resim dosyaları açmak ve bu adımda, bir arka plan rengi seçin, programı etkinleştirmek için eklediğiniz bir **OpenFileDialog** bileşeni ve bir **ColorDialog** formunuza bileşen.  
  
 Bazı yollarını denetiminde gibi bir bileşenidir. Formunuz için bir bileşen eklemek için araç kutusunu kullanın ve özelliklerini kullanarak ayarlayın **özellikleri** penceresi. Ancak bir denetim, bir bileşen formunuza kullanıcı formdaki görebilir görünür bir öğe ekleme değil. Bunun yerine, tetikleyicinin belirli davranışlarını koduyla sağlar. Açılır bir bileşen olan bir **Dosya Aç** iletişim kutusu.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 3 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205213) veya [Eğitmen 1: bir resim görüntüleyici oluşturma C# - Video 3](http://go.microsoft.com/fwlink/?LinkId=205202). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
### <a name="to-add-dialog-components-to-your-form"></a>Formunuza iletişim kutusu bileşenleri ekleme  
  
1.  Windows Forms Tasarımcısı (Form1.cs [Design] veya [tasarım] Form1.vb) seçin ve ardından açın **iletişim kutularını** araç grubu.  
  
    > [!NOTE]
    >  **İletişim kutularını** araç grubunda açılarak ve dosyaları kaydetme, klasörlere göz atma ve yazı tipleri ve renkler için kullanılan pek çok yararlı iletişim kutuları için açtığınız bileşeni vardır. Bu projede iki iletişim kutusu bileşenleri kullanın: **OpenFileDialog** ve **ColorDialog**.  
  
2.  Adlı bir bileşen eklemek için **openFileDialog1** formunuza, çift **OpenFileDialog**. Adlı bir bileşen eklemek için **colorDialog1** formunuza, çift **ColorDialog** araç kutusunda. (Bir sonraki öğretici adımında kullanın.) Windows Forms Tasarımcısı (altındaki resim görüntüleyici formu) aşağıdaki resimde gösterildiği gibi bir simge her eklediğiniz iki iletişim kutusu bileşenleri için sahip altındaki bir alanı görmeniz gerekir.  
  
     ![İletişim kutusu bileşenleri](../ide/media/express_dialogsadded.png "Express_DialogsAdded")  
İletişim kutusu bileşenleri  
  
3.  Seçin **openFileDialog1** Windows Form Tasarımcısı ekranın alt kısmındaki alanında simgesi. İki özellikleri ayarlayın:  
  
    -   Ayarlama **filtre** (kopyalayın ve yapıştırın) aşağıdaki özellik:  
  
        ```  
        JPEG Files (*.jpg)|*.jpg|PNG Files (*.png)|*.png|BMP Files (*.bmp)|*.bmp|All files (*.*)|*.*  
        ```  
  
    -   Ayarlama **başlık** aşağıdaki özelliğine: **bir resim dosyası seçin**  
  
         **Filtre** özellik ayarlarını belirleyin görüntüleyecek dosya türlerini türlerini **Resim Seç** dosya iletişim kutusu.  
  
    > [!NOTE]
    >  Bir örnek görmek için **Dosya Aç** iletişim kutusu farklı bir uygulama Not Defteri'nde veya boyama açın ve menü çubuğunda seçin **dosya**, **açmak**. Nasıl olduğuna dikkat edin bir **dosya türü** altındaki aşağı açılan listeden. Yalnızca kullanılan **filtre** özelliğinde **OpenFileDialog** , ayarlamak için bileşen. Ayrıca, fark nasıl **başlık** ve **filtre** özellikleri kalın **özellikleri** penceresi. IDE varsayılan değerlerine değiştirilmiş özellikleri göstermek için gerçekleştirir.  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [adım 8: kod için bir resim Göster düğmesi olay işleyicisi yazma](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [6. adım: ad bilgisayarınızı düğmesi denetimleri](../ide/step-6-name-your-button-controls.md).