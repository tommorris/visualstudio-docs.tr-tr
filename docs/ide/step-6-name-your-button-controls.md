---
title: '6. adım: Düğme denetimlerinizi adlandırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-acquisition
ms.topic: conceptual
ms.assetid: 56b3baa3-651e-4ad4-8942-e334c5c57158
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d5c402439ccb30b4803a4b1863254287bc7c2dd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="step-6-name-your-button-controls"></a>6. Adım: Düğme Denetimlerinizi Adlandırma
Formunuzda tek PictureBox yoktur. Eklendiğinde, IDE otomatik olarak da adlandırılan **pictureBox1**. Adlı yalnızca bir onay kutusu yok **checkBox1**. En kısa sürede, biraz kod yazılır ve bu kod onay kutusunu ve PictureBox başvurur. Her bu denetimlerin yalnızca biri, çünkü gördüğünüzde ne anlama geldiğini bilirsiniz **pictureBox1** veya **checkBox1** kodunuzda.  
  
> [!NOTE]
>  Adları Visual Basic'te, herhangi bir denetim adı varsayılan ilk harfini ilk harf olduğundan **PictureBox1**, **CheckBox1**ve benzeri.  
  
 Formunuzda dört düğme vardır ve bunları IDE adlı **button1**, **button2**, **button3**, ve **button4**. Yalnızca geçerli adlarını bakarak hangi düğme bilmiyorsanız **Kapat** düğmesi ve hangisinin olduğuna **resim Göster** düğmesi. İşte bu nedenle daha bilgilendirici adları düğme denetimlerinizi vermek yararlıdır.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 3 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205213) veya [Öğreticisi 1: Resim Görüntüleyici C# ' - oluşturma Video 3](http://go.microsoft.com/fwlink/?LinkId=205202). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
### <a name="to-name-your-button-controls"></a>Düğme denetimlerinizi adlandırma için  
  
1.  Form üzerinde seçin **Kapat** düğmesi. (Seçili tüm düğmeleri hala varsa, seçimini iptal etmek için ESC tuşuna seçin.) Haftasına **özellikleri** görene kadar penceresi **(ad)** özelliği. ( **(Ad)** özelliği olduğunda en üstüne yakın özellikleri alfabetik.) Adına değiştirme **Kapat düğmesi**, aşağıdaki resimde gösterildiği gibi.  
  
     ![Özellikler penceresini kapat düğmesi adla](../ide/media/express_setnameproperty.png "Express_SetNameProperty")  
Kapat düğmesi adıyla Özellikler penceresi  
  
    > [!NOTE]
    >  Düğmesinin adını değiştirmeyi deneyin, **Kapat düğmesi**, sözcük kapatın ve düğmesi arasında bir boşluk ile IDE bir hata iletisi görüntüler: "özelliğinin değeri geçerli değil." Boşluk (ve diğer birkaç karakterler) denetim adlarında izin verilmiyor.  
  
2.  Diğer üç düğmelere yeniden adlandırma **backgroundButton**, **clearButton**, ve **showButton**. Denetim Seçici açılan listeden seçerek adlarını doğrulayabilirsiniz **özellikleri** penceresi. Yeni düğmesi adları görüntülenir.  
  
3.  Çift **resim Göster** formundaki düğmesi. Alternatif olarak, seçin **resim Göster** formda'düğmesine tıklayın ve ardından ENTER tuşuna seçin. Bunu yaptığınızda, IDE ek bir sekme adlı ana penceresinde açar. **Form1.cs** (**Form1.vb** Visual Basic kullanıyorsanız). Bu sekme, aşağıdaki resimde gösterildiği gibi formun arkasındaki kod dosyası gösterir.  
  
     ![Visual C ile Form1.cs sekmesini&#35; kod](../ide/media/express_showbuttoncode.png "Express_ShowButtonCode")  
Visual C# kodu Form1.cs sekmesi  
  
4.  Bu kod parçası, üzerinde odaklanın. (Seçin **VB** Visual Basic kodu Visual Basic sürümünü görüntülemek için kullanıyorsanız, aşağıda sekmesinde.)  
  
     [!code-vb[VbExpressTutorial1Step6#1](../ide/codesnippet/VisualBasic/step-6-name-your-button-controls_1.vb)]
     [!code-csharp[VbExpressTutorial1Step6#1](../ide/codesnippet/CSharp/step-6-name-your-button-controls_1.cs)]  
  
     Adlı kodu aradığınız `showButton_Click()`. İçin kod dosyası açıldığında IDE bu formun kodu eklenen **showButton** düğmesi. Bir formda bir denetim için kod dosyası açtığınızda tasarım zamanında, zaten yoksa denetim için kodu oluşturulur. Olarak bilinen bu kodu bir *yöntemi*, programınızı çalıştırma ve control - bu durumda, seçin ne zaman çalışacağını **resim Göster** düğmesi.  
  
    > [!NOTE]
    >  Bu öğreticide, otomatik olarak oluşturulan Visual Basic kodu parantez () arasındaki her şeyi kaldırarak basitleştirilmiştir. Bu olduğunda, aynı kod kaldırabilirsiniz. Programınız her iki durumda da çalışır. Öğreticiler geri kalanı için mümkün olduğunda otomatik olarak oluşturulan kod basitleştirilmiştir.  
  
5.  Windows Forms Tasarımcısı sekmesini yeniden seçin (**Form1.cs [Design]** Visual C# ' ta, **Form1.vb [tasarım]** Visual Basic'te) ve kod dosyasını açın **resmi temizleyin** Formun kodunda bir yöntem oluşturmak için düğmesi. Bu, kalan iki düğmeleri için işlemi yineleyin. Her zaman IDE yeni bir yöntemi formun kod dosyasına ekler.  
  
6.  Daha fazla yöntem eklemek için onay kutusu denetimi için kod dosyası ekleme IDE yapmak için Windows Formları tasarımcısında açın bir `checkBox1_CheckedChanged()` yöntemi. Bu yöntem, her kullanıcı seçer veya onay kutusunu temizler çağrılır.  
  
    > [!NOTE]
    >  Bir programda çalışırken Kod Düzenleyicisi'ni ve Windows Forms Tasarımcısı arasında genellikle taşıyın. IDE projenizde gidin kolay hale getirir. Kullanım **Çözüm Gezgini** çift tıklayarak Windows Form Tasarımcısı açmak için **Form1.cs** Visual C# veya **Form1.vb** Visual Basic veya menü çubuğunda, seçin**Görünüm**, **Tasarımcısı**.  
  
     Aşağıdaki yeni kod, Kod Düzenleyicisi'nde gördüğünüz gösterir.  
  
     [!code-vb[VbExpressTutorial1Step6#2](../ide/codesnippet/VisualBasic/step-6-name-your-button-controls_2.vb)]
     [!code-csharp[VbExpressTutorial1Step6#2](../ide/codesnippet/CSharp/step-6-name-your-button-controls_2.cs)]  
  
     Eklediğiniz beş yöntem adlı *olay işleyicileri*, (örneğin, bir kutusunu işaretleyerek veya bir düğmesini seçerek bir kullanıcı) bir olay gerçekleştiğinde her programınızı bunları çağırır.  
  
     Tasarım zamanında IDE içinde bir denetim için kod görüntülediğinizde, bir yoksa Visual Studio denetim için bir olay işleyicisi yöntemi ekler. Örneğin, bir düğme çift tıkladığınızda, IDE (kullanıcı düğmesini seçer olduğunda çağrılan) Click olayını için bir olay işleyicisi ekler. Bir onay kutusu çift tıkladığınızda, IDE (kullanıcı kutusunu seçer veya temizler her olarak adlandırılır), CheckedChanged olayı için bir olay işleyicisi ekler.  
  
     Bir denetim için bir olay işleyicisi ekledikten sonra kendisine herhangi bir zamanda Windows Forms Tasarımcısı'ndan denetimi çift tıklatarak veya menü çubuğu seçme dönebilirsiniz **Görünüm**, **kod**.  
  
     Programları derleme ve yöntemler (olay işleyicileri dahil), istediğiniz herhangi bir ad olabilir adları önemlidir. IDE ile olay işleyici eklediğinizde, denetimin adını ve işlenen olay dayalı bir ad oluşturur. Örneğin, adlı bir düğmeye Click olayını **showButton** çağrılır `showButton_Click()` olay işleyicisi yöntemi. Ayrıca, açma ve kapama parantez () genellikle yöntemlerini ele belirtmek için yöntem adından sonra eklenir. Kod değişken adını değiştirmek istediğiniz karar verirseniz, kodda değişkeni sağ tıklatın ve ardından **yeniden düzenlemeniz**, **yeniden adlandırma**. Bu değişken kodda tüm örneklerini yeniden adlandırılmıştır. Bkz: [yeniden düzenlemeyi yeniden adlandırma](../ide/reference/rename.md) daha fazla bilgi için.
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [adım 7: Ekle iletişim kutusu bileşenleri bilgisayarınızı formuna](../ide/step-7-add-dialog-components-to-your-form.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [5. adım: bilgisayarınızı Form denetimlerine ekleme](../ide/step-5-add-controls-to-your-form.md).