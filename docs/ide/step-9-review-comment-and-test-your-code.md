---
title: "9. adım: Gözden geçirme, açıklama ve kodunuzu Test | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f26f79ba-c91b-4164-b87f-679a1b231c09
caps.latest.revision: "29"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 181462529b4e66f894328d099298408a91145c6b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="step-9-review-comment-and-test-your-code"></a>9. Adım: Kodunuzu Gözden Geçirme, Açıklama ve Test Etme
Sonraki kodunuz için bir açıklama ekleyin. Bir açıklamadır programın davranışını değiştirmez unutmayın. Ne yapacağını anlamak için kodunuzu okuyan yapılandırabilecek için kolaylaştırır. Kodunuz için açıklama ekleme almak için iyi bir alışkanlıktır. Visual C# ' ta iki eğik (/ /) satırını açıklama olarak işaretleyin. Visual Basic'te, tek tırnak işareti ('), bir satırı açıklama olarak işaretlemek için kullanılır. Açıklama ekledikten sonra programınızı sınayın. Çalıştırmak ve catch ve kodu daha karmaşık büyümeden sorunları erken, düzeltmek için sık projelerinizi üzerinde çalışırken kodunuzu test etmek için iyi bir uygulamadır. Bu adlı *yinelemeli test*.  
  
 Çalışan bir şey yalnızca yerleşik ve henüz belirtilmez ancak zaten resmi yükleyebilir. Kodunuz için bir açıklama ekleyin ve test için önce bu kavramları sık kullanacağından kod kavramlarını gözden geçirme zaman:  
  
-   Tıklattığınız zaman **resim Göster** düğmesini Windows Forms Tasarımcısı'nda IDE otomatik olarak eklenen bir *yöntemi* programınızın kodu.  
  
-   Yöntemlerdir kodunuzu nasıl organize: nasıl kodunuz gruplandırılmış olan.  
  
-   Çoğu zaman, bir yöntemi nasıl gibi belirli bir sırada şeyler az sayıda yapar, `showButton_Click()` yöntemi bir iletişim kutusu gösterir ve resim yükler.  
  
-   Bir yöntem kodunu yapılır *deyimleri*, veya kod satırı bulunmaktadır. Bir yöntem kod deyimleri birlikte gruplamak için bir yol olarak düşünün.  
  
-   Bir yöntemi yürütüldüğünde veya *adlı*, yöntem deyimlerinde birbiri ardına, birinci ile başlayan sırada yürütülür.  
  
     Deyiminin bir örnek verilmiştir.  
  
    ```csharp  
    pictureBox1.Load(openFileDialog1.FileName);  
    ```  
  
    ```vb  
    pictureBox1.Load(openFileDialog1.FileName)  
    ```  
  
     Deyimler ne şeyler programlarınızı olun şunlardır. Visual C# ' ta her zaman bir deyimi noktalı virgül sonlandırır. Visual Basic'te bir satırın sonuna bir deyim sonudur. (Hiçbir noktalı Visual Basic'te gerekli değildir.) Önceki deyimi söyler, `PictureBox` ile kullanıcı seçilen dosyasını yüklemek için Denetim **OpenFileDialog** bileşeni.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 5 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205216) veya [Eğitmen 1: bir resim görüntüleyici oluşturma C# - Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
### <a name="to-add-comments"></a>Açıklama eklemek için  
  
1.  Aşağıdaki açıklama kodunuzu ekleyin.  
  
     [!code-vb[VbExpressTutorial1Step9_10#1](../ide/codesnippet/VisualBasic/step-9-review-comment-and-test-your-code_1.vb)]
     [!code-csharp[VbExpressTutorial1Step9_10#1](../ide/codesnippet/CSharp/step-9-review-comment-and-test-your-code_1.cs)]  
  
    > [!NOTE]
    >  **ShowButton** düğmenin Click olay işleyicisi şimdi tamamlandı ve onu çalışır. Kod, yazma başlayarak başlattığınız bir `if` deyimi. Bir `if` açıklamadır programınızı nasıl size, "Bu tek şey denetleyin ve true ise, bu eylemleri gerçekleştirebilirsiniz." Bu durumda, açmak için program söyleyin **Dosya Aç** iletişim kutusu, ve kullanıcı bir dosya seçiyor ve seçer, **Tamam** düğmesini tıklatın, bu dosyada PictureBox yük.  
  
    > [!TIP]
    >  IDE kod yazmayı kolaylaştırır için yerleşik olarak bulunur ve *kod parçacıkları* , mevcut bir yoludur. Parçacık küçük bir kod bloğu genişletilmiş bir kısayol'dir.  
    >   
    >  Tüm kullanılabilir parçacıkları görebilirsiniz. Menü çubuğunda seçin **Araçları**, **kod parçacıkları Yöneticisi**. Visual C# için `if` parçacığı konusu **Visual C#** . Visual Basic `if` parçacıklarıdır içinde **koşulları ve döngüleri**, **kod düzenleri**. Varolan parçacıkları göz atın veya kendi parçacıkları eklemek için bu Yöneticisi'ni kullanabilirsiniz.  
    >   
    >  Kod yazarken parçacık etkinleştirmek için bunu yazın ve TAB tuşuna seçin. Birçok parçacıkları görünür **IntelliSense** SEKME tuşuna iki kez seçtiğiniz neden olan penceresi: ilk önce gelen kod parçacığını seçmek için **IntelliSense** penceresinde ve ardından kod parçacığını kullanmak için IDE söyleyin. (IntelliSense'i desteklediğine `if` kod parçacığında, ama `ifelse` parçacığı.)  
  
2.  Programınızı çalıştırmadan önce programınızı seçerek kaydetmek **Tümünü Kaydet** aşağıdaki gibi görünür araç çubuğu düğmesi.  
  
     ![Kaydet tüm araç çubuğu düğmesi](../ide/media/express_iconsaveall.png "Express_IconSaveAll")  
Kaydet tüm düğmesi  
  
     Menü çubuğunda, programınızı kaydetmek için alternatif olarak, seçin **dosya**, **Tümünü Kaydet**. Erken ve genellikle kaydetmek için en iyi bir uygulamadır.  
  
     Programınız çalışırken, aşağıdaki resimde gibi görünmelidir.  
  
     ![Resim Görüntüleyici](../ide/media/express_pictureviewerdonerun.png "Express_PictureViewerDoneRun")  
Resim Görüntüleyici  
  
### <a name="to-test-your-program"></a>Programınızı sınamak için  
  
1.  F5 tuşuna seçin veya seçin **hata ayıklamayı Başlat** araç çubuğu düğmesi.  
  
2.  Seçin **resim Göster** yalnızca yazdığınız kodun çalıştırmak için düğmesi. İlk olarak, programı açar bir **Dosya Aç** iletişim kutusu. Filtrelerinizi göründüğünü doğrulayın **dosya türü** iletişim kutusunun altındaki aşağı açılan listeden. Ardından bir resme gidin ve açın. Genellikle Windows işletim sistemi ile birlikte gönderilen örnek resimleri bulmak için **Belgelerim** klasörü, iç **Pictures\Sample resimler** klasör.  
  
    > [!NOTE]
    >  Tüm görüntüleri görmüyorsanız, **bir resim dosyası seçin** iletişim kutusunda, emin olun, "tüm dosyalar (*.\*)" filtre iletişim kutusunun alt sağ tarafında açılan listesinde belirlendiğinde.  
  
3.  Resim yükleme ve PictureBox içinde görünür. Kenarlıkları sürükleyerek formunuzu yeniden boyutlandırmayı deneyin. TableLayoutPanel içinde yuvalanmış, PictureBox bulunduğundan, böylece form olarak kadar geniştir ve form üst yüzde 90 doldurur kendisi formun içine yerleştirildiğini resim alanınızı kendisini yeniden boyutlandırılır. İşte bu nedenle TableLayoutPanel ve FlowLayoutPanel kapsayıcıları kullandığınız: formunuza kullanıcı yeniden boyutlandırır zaman doğru boyutta tutun.  
  
     Şimdi Right, büyük resim, resim görüntüleyici Kenarlıklar gidin. Sonraki adımda penceresine sığacak resimler yapmak için kod ekleyeceksiniz.  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [adım 10: ek düğmeler ve onay kutusu için kod yazma](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [adım 8: kod için bir resim Göster düğmesi olay işleyicisi yazma](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md).