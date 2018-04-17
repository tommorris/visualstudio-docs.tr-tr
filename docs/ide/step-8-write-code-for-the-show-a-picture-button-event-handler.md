---
title: '8. adım: Kodu için bir resim Göster düğmesi olay işleyicisi yazma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-acquisition
ms.topic: conceptual
ms.assetid: 07f4ec00-cda4-42f4-98bb-37edc7167de7
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d72997e827db9842761aadbb70a7e464995d2d74
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="step-8-write-code-for-the-show-a-picture-button-event-handler"></a>8. Adım: Resim Göster Düğmesi Olay İşleyicisi için Kod Yazma
Bu adımda, yaptığınız **resim Göster** düğmesini iş şuna benzer:  
  
-   Bir kullanıcı o düğmesini seçtiğinde programı açar bir **Dosya Aç** iletişim kutusu.  
  
-   Bir kullanıcının bir resim dosyası açılırsa, program o resmi PictureBox içinde gösterir.  
  
 IDE kod yazmanıza yardımcı olur IntelliSense adlı güçlü bir araç vardır. Kod girerken, IDE girdiğiniz kısmi sözcükler için önerilen tamamlamalar içeren bir kutusu açar. Sonraki yapmak istediğinizi belirlemek çalışır ve otomatik olarak son öğeyi listeden seçin atlar. Yukarı veya aşağı taşımak için okları veya seçimleri daraltmak için harf yazarak tutmak. İstediğiniz seçimi gördüğünüzde, seçmek için SEKME tuşunu seçin. Veya, öneriler yoksayabilirsiniz değilse gerekli.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 4 Resim Görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205215) veya [Öğreticisi 1: Resim Görüntüleyici C# ' - oluşturma Video 4](http://go.microsoft.com/fwlink/?LinkId=205203). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
### <a name="to-write-code-for-the-show-a-picture-button-event-handler"></a>Kod için bir resim Göster düğmesi olay işleyicisi yazma için  
  
1.  Windows Forms Tasarımcısı gidin ve çift **resim Göster** düğmesi. IDE hemen kod Designer'a gider ve içinde olacak şekilde imlecinizi taşır `showButton_Click()` daha önce eklediğiniz yöntemi.  
  
2.  Tür bir `i` ikisi arasındaki boş satırdaki küme ayraçları {}. (Visual Basic'te özel alternatifi.. ve End Sub arasında boş satırdaki yazın.) Bir **IntelliSense** aşağıdaki resimde gösterildiği gibi penceresi açılır.  
  
     ![Visual C IntelliSense&#35; kod](../ide/media/express_ifintellisense.png "Express_IfIntellisense")  
Visual C# koduyla IntelliSense  
  
3.  **IntelliSense** penceresi sözcüğü vurgulamanın **varsa**. (Aksi takdirde, küçük harf girin `f`, ve çıkarır.) Biraz nasıl dikkat edin *araç ipucu* yanına kutusunda **IntelliSense** penceresi görünür açıklamasıyla **IF için kod parçacığını deyimi**. (Visual Basic'te, araç ipucu de bunun bir parçası olduğunu bildiren ancak biraz farklı ifadesi.) Bu kod parçacığında kullanın, böylece eklemek için SEKME tuşunu seçin istediğiniz **varsa** kodunuzu içine. Daha sonra yeniden kullanmak için SEKME tuşunu seçin **,** parçacığı. (Başka bir yere seçerseniz ve **IntelliSense** penceresi üzerinden kayboldu, geri **ı** ve onu yeniden yazın ve **IntelliSense** penceresi açılır yeniden.)  
  
     ![Visual C&#35; kod](../ide/media/express_highlighttrue.png "Express_HighlightTrue")  
Visual C# kodu  
  
4.  Ardından, IntelliSense açmak için daha fazla kodu girmek için kullandığınız bir **Dosya Aç** iletişim kutusu. Kullanıcı seçerseniz **Tamam** düğmesini PictureBox kullanıcı seçilen dosyayı yükler. Aşağıdaki adımlar kodu girmek nasıl gösterir ve çok sayıda adımları olmasına rağmen yalnızca birkaç tuş vuruşları alır:  
  
    1.  Seçili metni ile Başlat **true** parçacığında bulunan. Tür `op` üzerine yazmak. (Visual Basic'te bir ilk harf ile başlatın, böylece yazın `Op`.)  
  
    2.  **IntelliSense** penceresi açar ve görüntüler **openFileDialog1**. Seçmek için SEKME tuşunu seçin. (Visual Basic'te gördüğünüz şekilde ilk bir harf ile başlar **OpenFileDialog1**. Emin **OpenFileDialog1** seçilir.)  
  
         Daha fazla bilgi edinmek için `OpenFileDialog`, bkz: [OpenFileDialog](http://msdn.microsoft.com/library/system.windows.forms.openfiledialog.aspx).  
  
    3.  Bir süre yazın (`.`) (birçok Programcı bu nokta çağırın.) Nokta hemen sonraki yazdığınızdan **openFileDialog1**, bir **IntelliSense** penceresi açılır, tüm oturum doldurulmuş **OpenFileDialog** bileşenin özellikleri ve yöntemleri. Bu görünen, aynı özelliklerdir **özellikleri** Windows Forms Tasarımcısı'nda seçtiğinizde penceresi. Bileşen (bir iletişim kutusu açmak gibi) şeyler anlatın yöntemleri de seçebilirsiniz.  
  
        > [!NOTE]
        >  **IntelliSense** penceresi gösterebilir, özellikleri ve yöntemleri. Ne gösterilen belirlemek için her öğenin sol tarafındaki simgesini arayın **IntelliSense** penceresi. Her özelliğin yanındaki her yöntem yanındaki bloğunun resim ve resim İngiliz anahtarı (veya spanner) bakın. Her olay yanındaki Şimşek Cıvata simgesi yoktur. Bu resimler şu şekilde görüntüler.  
  
         ![Yöntem simgesi](../ide/media/express_iconmethod.png "Express_IconMethod")  
Yöntem simgesi  
  
         ![Özellik simgesi](../ide/media/express_iconproperty.png "Express_IconProperty")  
Özellik simgesi  
  
         ![Olay simgesi](../ide/media/express_iconevent.png "Express_IconEvent")  
Olay simgesi  
  
    4.  Türü başlangıç `ShowDialog` (büyük/küçük harf için IntelliSense önemli). `ShowDialog()` Yöntemi gösterilir **Dosya Aç** iletişim kutusu. Pencerenin vurgulanmış olan sonra **ShowDialog**, SEKME tuşunu seçin. Ayrıca, "ShowDialog" vurgulayın ve onun için Yardım almak için F1 tuşuna seçin.  
  
         Daha fazla bilgi edinmek için `ShowDialog()` yöntemi, bkz: [ShowDialog yöntemi](http://msdn.microsoft.com/library/c7ykbedk.aspx).  
  
    5.  Kullandığınızda, bir yöntem bir denetimi veya bileşeni (olarak adlandırılan *bir yöntemi çağırmak*), parantez eklemeniz gerekir. Bu nedenle açma ve parantez hemen "g sonra" kapatma girin `ShowDialog`: `()` "openFileDialog1.ShowDialog()" gibi görünmelidir.  
  
        > [!NOTE]
        >  Yöntemleri herhangi bir programı önemli bir parçası olan ve bu öğreticinin yöntemlerini kullanmak için çeşitli yollar göstermiştir. Aradığınız nasıl gibi şeyler yapmak için bildirmek için bir bileşenin yöntemini çağırabilir **OpenFileDialog** bileşenin `ShowDialog()` yöntemi. Programınızı oluşturmakta şimdi gibi şeyler yapmak için kendi yöntemleri oluşturabilirsiniz adlı `showButton_Click()` bir kullanıcı bir düğmesini seçtiğinde, bir iletişim kutusu ve bir resim açan yöntemi.  
  
    6.  Visual C# için bir alan ekleyin ve sonra iki eşittir işareti ekleyin (`==`). Visual Basic, bir boşluk eklemek ve tek bir eşittir işareti kullanın (`=`). (Visual C# ve Visual Basic farklı eşitlik işleçleri kullanın.)  
  
    7.  Başka bir alan ekleyin. Bunu hemen ardından başka bir **IntelliSense** penceresi açılır. Türü başlangıç `DialogResult` ve eklemek için SEKME tuşunu seçin.  
  
        > [!NOTE]
        >  Bazen bir yöntemi çağırmak için kodu yazarken bir değer döndürür. Bu durumda, **OpenFileDialog** bileşenin `ShowDialog()` yöntemi DialogResult değeri döndürür. DialogResult iletişim kutusunda neler olduğunu bildiren özel bir değerdir. Bir **OpenFileDialog** bileşen seçerek kullanıcı sonuçlanabilir **Tamam** veya **iptal**, bu nedenle, `ShowDialog()` yöntemi döndürür ya da DialogResult.OK veya DialogResult.Cancel.  
  
    8.  DialogResult değeri açmak için bir nokta yazın **IntelliSense** penceresi. Harf girin `O` ve eklemek için SEKME tuşunu seçin **Tamam**.  
  
         Daha fazla bilgi edinmek için `DialogResult`, bkz: [DialogResult](http://msdn.microsoft.com/library/system.windows.forms.dialogresult.aspx).  
  
        > [!NOTE]
        >  Kodun ilk satırı tamamlanmış olmalıdır. Visual C# için aşağıdaki olmalıdır.  
        >   
        >  `if (openFileDialog1.ShowDialog() == DialogResult.OK)`  
        >   
        >  Visual Basic için aşağıdakiler olmalıdır.  
        >   
        >  `If OpenFileDialog1.ShowDialog() = DialogResult.OK Then`  
  
    9. Şimdi bir veya daha fazla satır kod ekleyin. Bunu yazın (veya kopyalayıp yapıştırın), ancak bunu eklemek için IntelliSense kullanmayı düşünün. Daha tanıdık, IntelliSense ile daha hızlı bir şekilde kendi kodunuzu yazabilirsiniz demektir. Son `showButton_Click()` yöntemi aşağıdaki gibi görünür. (Seçin **VB** kodunun Visual Basic sürümünü görüntülemek için.)  
  
         [!code-csharp[VbExpressTutorial1Step8#1](../ide/codesnippet/CSharp/step-8-write-code-for-the-show-a-picture-button-event-handler_1.cs)]
         [!code-vb[VbExpressTutorial1Step8#1](../ide/codesnippet/VisualBasic/step-8-write-code-for-the-show-a-picture-button-event-handler_1.vb)]  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [adım 9: gözden geçirme, açıklama ve Test kodunuzu](../ide/step-9-review-comment-and-test-your-code.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [adım 7: Ekle iletişim kutusu bileşenleri bilgisayarınızı formuna](../ide/step-7-add-dialog-components-to-your-form.md).