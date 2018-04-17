---
title: '5. adım: Formunuza denetimler ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-acquisition
ms.topic: conceptual
ms.assetid: dc2746f4-0b5c-4674-9ef7-f40f94150f52
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0636ec38846fbfd591e0c8b6f22af6fd8e043008
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="step-5-add-controls-to-your-form"></a>5. Adım: Formunuza Denetimler Ekleme
Bu adımda, denetimleri gibi eklediğiniz bir `PictureBox` denetim ve `CheckBox` Formunuza denetim. Ardından formunuza düğmeleri ekleyin.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 2 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205211) veya [Öğreticisi 1: Resim Görüntüleyici C# ' - oluşturma Video 2](http://go.microsoft.com/fwlink/?LinkId=205200). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
### <a name="to-add-controls-to-your-form"></a>Formunuza denetimler ekleme  
  
1.  (Visual Studio IDE sol tarafta bulunur) araç kutusu sekmesine gidin ve genişletin **ortak denetimler** grubu. Bu, en yaygın denetimleri formlarında gördüğünüz gösterir.  
  
2.  TableLayoutPanel denetimi form üzerinde seçin. TableLayoutPanel seçildiğini doğrulamak için adının en üstündeki açılır liste kutusunda gösterildiğinden emin olun **özellikleri** penceresi. En üstte açılır liste kutusunu kullanarak form denetimlerini seçebilirsiniz **özellikleri** penceresi. Bir denetim seçme bu şekilde genellikle fare küçük bir denetimle seçme daha kolay olabilir.  
  
3.  Çift **PictureBox** formunuza PictureBox denetimi eklenecek öğe. TableLayoutPanel formunuz doldurmak için yerleşik olduğundan, IDE PictureBox denetimi ilk boş hücreye (sol üst köşesinde) ekler.  
  
4.  Seçmek için yeni PictureBox denetimi seçin ve ardından aşağıdaki resimde gösterildiği gibi görev listesini görüntülemek için yeni PictureBox denetiminde siyah üçgen seçin.  
  
     ![PictureBox görevleri](../ide/media/express_pictureboxtasks.png "Express_PictureBoxTasks")  
PictureBox görevleri  
  
    > [!NOTE]
    >  TableLayoutPanel denetimi yanlış türde yanlışlıkla eklerseniz, silebilirsiniz. Denetimin sağ tıklayın ve ardından **silmek** bağlam menüsünde. Menü Çubuğu'nu kullanarak formdan denetimleri de kaldırabilirsiniz. Menü çubuğunda seçin **Düzenle**, **geri**, veya **Düzenle**, **silmek**.  
  
5.  Seçin **Ana kapsayıcıda yerleştir** bağlantı. Bu otomatik olarak PictureBox ayarlar **yerleştirme** özelliğine **doldurun**. PictureBox denetimi seçin bu görmek için Git **özellikleri** penceresinde, ve emin olun, **yerleştirme** özelliği ayarlanmış **doldurun**.  
  
6.  Her iki sütuna değiştirerek yayılan PictureBox olun kendi **ColumnSpan** özelliği. PictureBox denetimi seçin ve ayarlayın, **ColumnSpan** özelliğine **2**. Ayrıca, PictureBox boş olduğunda, boş bir çerçeve göstermek istiyorsunuz. Ayarlama, **kenarlık stili** özelliğine **Fixed3D**.  
  
    > [!NOTE]
    >  Görmüyorsanız, bir **ColumnSpan** , PictureBox, ardından özelliğidir PictureBox TableLayoutPanel yerine formun eklendiğini büyük olasılıkla. Bu sorunu gidermek için PictureBox seçin, silmek, TableLayoutPanel seçin ve ardından yeni PictureBox ekleyin.  
  
7.  TableLayoutPanel formdaki seçin ve ardından ekleyin bir **onay kutusunu** forma denetim. Çift **onay kutusunu** tablonuz sonraki boş hücreye yeni bir onay kutusu denetimi eklemek için araç kutusu öğesi. Bir PictureBox TableLayoutPanel ilk iki hücrelere yukarı aldığından, onay kutusu denetimi için sol alt hücre eklenir. Seçin **metin** özelliği ve Word türü **Esnetme**, aşağıdaki resimde gösterildiği gibi.  
  
     ![TextBox denetimi Stretch özelliği ile](../ide/media/express_pictureviewercheckbox.png "Express_PictureViewerCheckbox")  
TextBox denetimi Stretch özelliği ile  
  
8.  Formdaki TableLayoutPanel seçin ve ardından Git **kapsayıcıları** çift tıklayın ve Grup (burada aldığınız TableLayoutPanel denetimi) araç kutusunda **FlowLayoutPanel** yeni bir denetim eklemek için öğesi PictureBox (sağ alt) son hücresine. TableLayoutPanel içinde FlowLayoutPanel yerleştirme (seçerek **Ana kapsayıcıda yerleştir** FlowLayoutPanel'ın siyah üçgen görev listesi veya FlowLayoutPanel's ayarlayarak **yerleştirme** özelliğine **doldurun**).  
  
    > [!NOTE]
    >  FlowLayoutPanel diğer denetimlerini sırayla masaüstünüzdeki satırlardaki düzenler bir kapsayıcıdır. Tüm denetimlerindeki tek bir satırı düzenlemek için yer varsa bir FlowLayoutPanel boyutlandırdığınızda, yapar. Aksi takdirde, bunları birbirinin satırlarındaki düzenler. FlowLayoutPanel dört düğme tutmak için kullanır. Düğmeleri biri üzerinde Yerleştir başka eklendiğinde top, FlowLayoutPanel düğmeleri eklemeden önce seçili olduğundan emin olun. Daha önce her bir hücre yalnızca bir denetim tutabilir belirtmiştik rağmen TableLayoutPanel sağ alt hücrenin dört düğmesi denetimleri vardır. Bir denetim diğer denetimleri tutan bir hücreye koyabilirsiniz olmasıdır. Bu tür denetimi bir kapsayıcı adı verilir ve FlowLayoutPanel bir kapsayıcıdır.  
  
### <a name="to-add-buttons"></a>Düğmeler ekleme  
  
1.  Eklediğiniz yeni FlowLayoutPanel seçin. Git **ortak denetimler** araç ve çift **düğmesini** adlı bir düğme denetim eklemek için öğeyi **button1** , FlowLayoutPanel için. Başka bir düğme eklemek için yineleyin. Zaten var olduğu adlı bir düğme IDE belirler **button1** ve bir sonraki çağırır **button2**.  
  
2.  Genellikle, araç kutusunu kullanarak diğer düğmeleri ekleyin. Bu saati seçin **button2**ve ardından menü çubuğunda, **Düzenle**, **kopyalama** (veya Ctrl + C tuşlarına basın). Menü çubuğunda seçin **Düzenle**, **yapıştırın** (veya Ctrl + V tuşlarına basın), düğmesinin bir kopyasını yapıştırın. Şimdi yeniden yapıştırın. IDE şimdi eklendi **button3** ve **button4** FlowLayoutPanel için.  
  
    > [!NOTE]
    >  Kopyalayın ve hiçbir denetim yapıştırın. IDE adları ve yeni denetimleri mantıksal bir şekilde yerleştirir. Bir kapsayıcıya bir denetim yapıştırırsanız, IDE yerleştirme için sonraki mantıksal alan seçer.  
  
3.  İlk düğmesini seçin ve ayarlayın, **metin** özelliğine **resim Göster**. Ardından **metin** sonraki üç düğmelere özelliklerini **resmi temizleyin**, **arka plan rengini ayarlama**, ve **Kapat**.  
  
4.  Düğmeleri boyut ve bölmenin sağ tarafındaki hizalamak için bunları düzenlemek için sonraki adım olacaktır. FlowLayoutPanel seçin ve bakmak kendi **FlowDirection** özelliği. Ayarlanmış şekilde değiştirme **RightToLeft**. Bunu hemen düğmeleri kendilerini hücrenin sağ tarafındaki align ve bunların sırası ters şekilde **resim Göster** düğmesi olan sağ taraftaki.  
  
    > [!NOTE]
    >  Düğmeleri hala yanlış sırayla varsa, bunları herhangi bir sırada yeniden düzenlemek için FlowLayoutPanel çevresindeki düğmeler sürükleyebilirsiniz. Bir düğme seçin ve sola veya sağa sürükleyin.  
  
5.  Seçin **Kapat** düğmesini seçin. CTRL tuşunu basılı tutun ve böylece tüm seçilir diğer üç düğme seçin. Tüm düğmeleri seçili durumdayken Git **özellikleri** penceresini açın ve kaydırma kadar **AutoSize** özelliği. Bu özellik otomatik olarak kendisini tüm kendi metnin sığması için yeniden boyutlandırmak için düğmesini söyler. Ayarlamak **doğru**. Düğmeleri şimdi düzgün şekilde boyutlandırılmalıdır ve doğru sırada olmalıdır. (Tüm dört düğmeleri seçili olduğu sürece, tüm dört değiştirebilirsiniz **AutoSize** özellikleri aynı anda.) Aşağıdaki resimde, dört düğme gösterilmektedir.  
  
     ![Resim Görüntüleyici dört düğmeleriyle](../ide/media/express_autosize.png "Express_AutoSize")  
Dört düğmelerle Resim Görüntüleyici  
  
6.  Şimdi yeniden kullanıma yeni laid formunuz görmek için programı çalıştırın. Düğmeler ve onay kutusunu seçerek herhangi bir şey henüz yapmaz, ancak en kısa sürede çalışır.  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [6. adım: ad bilgisayarınızı düğmesi denetimleri](../ide/step-6-name-your-button-controls.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [4. adım: düzenleme çıkışı bilgisayarınızı Form TableLayoutPanel denetimi ile](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md).