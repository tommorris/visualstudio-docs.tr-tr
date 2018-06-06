---
title: '8. adım: Resim düğmesi olay işleyicisi Göster için kod yazma'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 07f4ec00-cda4-42f4-98bb-37edc7167de7
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc9bc3e5b0c3a61e911f7e49395f940ac07e2548
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748610"
---
# <a name="step-8-write-code-for-the-show-a-picture-button-event-handler"></a>8. adım: Resim düğmesi olay işleyicisi Göster için kod yazma
Bu adımda, yaptığınız **resim Göster** düğmesini iş şuna benzer:

-   Bir kullanıcı o düğmesini seçtiğinde programı açar bir <xref:System.Windows.Forms.OpenFileDialog> kutusu.

-   Bir kullanıcının bir resim dosyası açılırsa, program o resmi gösterir <xref:System.Windows.Forms.PictureBox>.

 IDE kod yazmanıza yardımcı olur IntelliSense adlı güçlü bir araç vardır. Kod girerken, IDE girdiğiniz kısmi sözcükler için önerilen tamamlamalar içeren bir kutusu açar. Sonraki yapmak istediğinizi belirlemek çalışır ve otomatik olarak son öğeyi listeden seçin atlar. Yukarı veya aşağı taşımak için okları veya seçimleri daraltmak için harf yazarak tutmak. Seçimi gördüğünüzde, seçmek istediğiniz **sekmesini** seçmek için anahtar. Veya, öneriler yoksayabilirsiniz değilse gerekli.

 ![video bağlantı](../data-tools/media/playvideo.gif)bu konuda video sürümü için bkz: [Öğreticisi 1: Visual Basic'te - Video 4 Resim Görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205215) veya [Eğitmen 1: Resim Görüntüleyici C# ' - Video 4 oluşturma](http://go.microsoft.com/fwlink/?LinkId=205203). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.

## <a name="to-write-code-for-the-show-a-picture-button-event-handler"></a>Bir resim düğmesi olay işleyicisi Göster için kod yazma

1.  Git **Windows Form Tasarımcısı** çift tıklayın ve **resim Göster** düğmesi. IDE hemen kod Designer'a gider ve içinde olacak şekilde imlecinizi taşır `showButton_Click()` daha önce eklediğiniz yöntemi.

2.  Tür bir `i` iki ayraçlar arasında boş satırdaki `{ }`. (Visual Basic'te arasında boş satır yazın `Private Sub...` ve `End Sub`.) Bir **IntelliSense** aşağıdaki resimde gösterildiği gibi penceresi açılır.

     ![Visual C IntelliSense&#35; kod](../ide/media/express_ifintellisense.png)
**IntelliSense** Visual C# kodu

3.  **IntelliSense** penceresi sözcüğü vurgulamanın `if`. (Aksi takdirde, küçük harf girin `f`, ve çıkarır.) Biraz nasıl dikkat edin *araç ipucu* yanına kutusunda **IntelliSense** penceresi görünür açıklamasıyla **IF için kod parçacığını deyimi**. (Visual Basic'te, araç ipucu de bunun bir parçası olduğunu bildiren ancak biraz farklı ifadesi.) Bu kod parçacığında kullanın, böylece seçin istediğiniz **sekmesini** eklemek için anahtar `if` kodunuzu içine. Ardından **sekmesini** yeniden kullanmak için anahtarı `if` parçacığı. (Başka bir yere seçerseniz ve **IntelliSense** penceresi üzerinden kayboldu, geri `i` ve onu yeniden yazın ve **IntelliSense** penceresi açılır yeniden.)

     ![Visual C&#35; kod](../ide/media/express_highlighttrue.png) Visual C# kodu

4.  Ardından, IntelliSense açmak için daha fazla kodu girmek için kullandığınız bir **Dosya Aç** iletişim kutusu. Kullanıcı seçerseniz **Tamam** düğmesini PictureBox kullanıcı seçilen dosyayı yükler. Aşağıdaki adımlar kodu girmek nasıl gösterir ve çok sayıda adımları olmasına rağmen yalnızca birkaç tuş vuruşları alır:

    1.  Seçili metni ile Başlat **true** parçacığında bulunan. Tür `op` üzerine yazmak. (Visual Basic'te bir ilk harf ile başlatın, böylece yazın `Op`.)

    2.  **IntelliSense** penceresi açar ve görüntüler **openFileDialog1**. Seçin **sekmesini** seçmek için anahtar. (Visual Basic'te gördüğünüz şekilde ilk bir harf ile başlar **OpenFileDialog1**. Emin **OpenFileDialog1** seçilir.)

         Daha fazla bilgi edinmek için `OpenFileDialog`, bkz: [OpenFileDialog](http://msdn.microsoft.com/library/system.windows.forms.openfiledialog.aspx).

    3.  Bir süre yazın (`.`) (birçok Programcı bu nokta çağırın.) Nokta hemen sonraki yazdığınızdan **openFileDialog1**, bir **IntelliSense** penceresi açılır, tüm oturum doldurulmuş **OpenFileDialog** bileşenin özellikleri ve yöntemleri. Bu görünen, aynı özelliklerdir **özellikleri** içinde seçtiğinizde penceresi **Windows Form Tasarımcısı**. Bileşen (bir iletişim kutusu açmak gibi) şeyler anlatın yöntemleri de seçebilirsiniz.

        > [!NOTE]
        >  **IntelliSense** penceresi gösterebilir, özellikleri ve yöntemleri. Ne gösterilen belirlemek için her öğenin sol tarafındaki simgesini arayın **IntelliSense** penceresi. Her özelliğin yanındaki her yöntem yanındaki bloğunun resim ve resim İngiliz anahtarı (veya spanner) bakın. Her olay yanındaki Şimşek Cıvata simgesi yoktur. Bu resimler şu şekilde görüntüler.

         ![Yöntem simgesi](../ide/media/express_iconmethod.png)
**yöntemi** simgesi

         ![Özellik simgesi](../ide/media/express_iconproperty.png)
**özelliği** simgesi

         ![Olay simgesi](../ide/media/express_iconevent.png)
**olay** simgesi

    4.  Türü başlangıç `ShowDialog` (büyük/küçük harf için IntelliSense önemli). `ShowDialog()` Yöntemi gösterilir **Dosya Aç** iletişim kutusu. Pencerenin vurgulanmış olan sonra **ShowDialog**, seçin **sekmesini** anahtarı. Ayrıca "ShowDialog" vurgulayın ve seçin **F1** onun için Yardım almak için anahtar.

         Daha fazla bilgi edinmek için `ShowDialog()` yöntemi, bkz: [ShowDialog yöntemi](http://msdn.microsoft.com/library/c7ykbedk.aspx).

    5.  Kullandığınızda, bir yöntem bir denetimi veya bileşeni (olarak adlandırılan *bir yöntemi çağırmak*), parantez eklemeniz gerekir. Bu nedenle açma ve parantez hemen "g sonra" kapatma girin `ShowDialog`: `()` "openFileDialog1.ShowDialog()" gibi görünmelidir.

        > [!NOTE]
        >  Yöntemleri herhangi bir programı önemli bir parçası olan ve bu öğreticinin yöntemlerini kullanmak için çeşitli yollar göstermiştir. Aradığınız nasıl gibi şeyler yapmak için bildirmek için bir bileşenin yöntemini çağırabilir **OpenFileDialog** bileşenin `ShowDialog()` yöntemi. Programınızı oluşturmakta şimdi gibi şeyler yapmak için kendi yöntemleri oluşturabilirsiniz adlı `showButton_Click()` bir kullanıcı bir düğmesini seçtiğinde, bir iletişim kutusu ve bir resim açan yöntemi.

    6.  Visual C# için bir alan ekleyin ve sonra iki eşittir işareti ekleyin (`==`). Visual Basic, bir boşluk eklemek ve tek bir eşittir işareti kullanın (`=`). (Visual C# ve Visual Basic farklı eşitlik işleçleri kullanın.)

    7.  Başka bir alan ekleyin. Bunu hemen ardından başka bir **IntelliSense** penceresi açılır. Türü başlangıç `DialogResult` ve **sekmesini** eklemek için anahtar.

        > [!NOTE]
        >  Bazen bir yöntemi çağırmak için kodu yazarken bir değer döndürür. Bu durumda, **OpenFileDialog** bileşenin <xref:System.Windows.Forms.CommonDialog.ShowDialog> yöntemi döndürür bir <xref:System.Windows.Forms.DialogResult> değeri. DialogResult iletişim kutusunda neler olduğunu bildiren özel bir değerdir. Bir **OpenFileDialog** bileşen seçerek kullanıcı sonuçlanabilir **Tamam** veya **iptal**, bu nedenle, `ShowDialog()` yöntemi döndürür ya da `DialogResult.OK` veya `DialogResult.Cancel`.

    8.  DialogResult değeri açmak için bir nokta yazın **IntelliSense** penceresi. Harf girin `O` ve **sekmesini** eklemek için anahtar **Tamam**.

         DialogResult hakkında daha fazla bilgi için bkz: [DialogResult](http://msdn.microsoft.com/library/system.windows.forms.dialogresult.aspx).

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

## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için

-   Öğretici bir sonraki adıma dönmek için bkz: [adım 9: gözden geçirme, açıklama ve kodunuzu test](../ide/step-9-review-comment-and-test-your-code.md).

-   Eğitmen önceki adıma dönmek için bkz: [adım 7: formunuza iletişim kutusu bileşenleri ekleme](../ide/step-7-add-dialog-components-to-your-form.md).
