---
title: '4. Adım: TableLayoutPanel Denetimi ile Formunuzu Düzenleme'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 61acde79-e115-4bad-bb06-1fbe37717a3e
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 983bbd00eb3ae24ef0b3c3ed932e469dbf138a2e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="step-4-lay-out-your-form-with-a-tablelayoutpanel-control"></a>4. Adım: TableLayoutPanel Denetimi ile Formunuzu Düzenleme
Bu adımda eklediğiniz bir `TableLayoutPanel` Formunuza denetim. TableLayoutPanel daha sonra eklersiniz formdaki denetimlerin düzgün şekilde hizalayın yardımcı olur.  

 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 2 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205211) veya [Öğreticisi 1: Resim Görüntüleyici C# ' - oluşturma Video 2](http://go.microsoft.com/fwlink/?LinkId=205200). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  

### <a name="to-lay-out-your-form-with-a-tablelayoutpanel-control"></a>TableLayoutPanel denetimi ile formunuzu düzenleme  

1.  Visual Studio IDE sol tarafında bulun **araç** sekmesi. Seçin **araç** sekmesi ve araç kutusu görünür. (Veya menü çubuğunda seçin **Görünüm**, **araç**.)  

2.  Küçük bir üçgen simgesiyle seçin **kapsayıcıları** , aşağıdaki resimde gösterildiği gibi açmak için Grup.  

     ![Kapsayıcılar grubu](../ide/media/express_toolbox.png "Express_Toolbox")  
Kapsayıcılar grubu  

3.  Formunuza denetimler düğmeleri, onay kutularını ve etiketler gibi ekleyebilirsiniz. Çift `TableLayoutPanel` araç kutusu denetiminde. (Veya araç forma denetim sürükleyebilirsiniz.) Bunu yaptığınızda, IDE ekler bir `TableLayoutPanel` aşağıdaki resimde gösterildiği gibi formunuza, denetim.  

     ![TableLayoutPanel denetimi](../ide/media/express_formtablelayout.png "Express_FormTableLayout")  
TableLayoutPanel denetimi  

    > [!NOTE]
    >  Bir pencere formunuz başlıkla içinde görünürse, TableLayoutPanel ekledikten sonra **TableLayoutPanel görevleri**, herhangi bir yere kapatmak için formun içine seçin. Bu pencere hakkında daha fazla daha sonra öğreticide öğreneceksiniz.  

     Araç kutusu kendi sekmesini seçtiğinizde formunuz kapsayacak şekilde genişletir ve nasıl dışında herhangi bir yere seçtikten sonra kapatır dikkat edin. IDE otomatik gizleme özelliğini olmasıdır. Açmak veya kapatmak için herhangi bir windows otomatik gizleme değiştirme ve yerinde kilitlemek için pencerenin sağ üst köşesindeki Raptiye simgesini seçerek açabilirsiniz. Raptiye simgesinin aşağıdaki gibi görünür.  

     ![Raptiye simgesinin](../ide/media/express_pushpintoolbox.png "Express_PushpinToolbox")  
İğne simgesi  

4.  Mutlaka **TableLayoutPanel** seçme tarafından seçilir. Açılan listenin en üstündeki bakarak hangi denetim seçilen doğrulayabilirsiniz **özellikleri** penceresinde, aşağıdaki resimde gösterildiği gibi.  

     ![TableLayoutPanel denetimi gösteren Özellikler penceresi](../ide/media/express_controlspropwin.png "Express_ControlsPropWin")  
TableLayoutPanel denetimi gösteren Özellikler penceresi  

5.  Seçin **alfabetik** araç çubuğunda **özellikleri** penceresi. Bu özellikler listesini neden **özellikleri** Bu öğreticide özellikleri bulmak daha kolay hale getirir alfabetik sırada görüntülemek için penceresi.  

6.  Denetim Seçici açılan en üstündeki listesidir **özellikleri** penceresi. Bu örnekte, bir denetim adlı gösterir `tableLayoutPanel1` seçilir. Windows Forms Tasarımcısı'nda bir alanı seçerek veya denetim seçicisini seçme denetimleri seçebilirsiniz. Şimdi `TableLayoutPanel` olan seçili Bul **yerleştirme** özelliği ve seçin **yerleştirme**, hangi ayarlanmalıdır **hiçbiri**. Aşağı açılan okunu değerin yanındaki görüntülendiğine dikkat edin. Oku seçin ve ardından **doldurun** düğmesini (büyük düğmesi ortasında), aşağıdaki resimde gösterildiği gibi.  

     ![Özellikleri penceresinde seçili dolgulu](../ide/media/express_docktable.png "Express_DockTable")  
Seçili dolgulu Özellikler penceresi  

     *Yerleştirme* Visual Studio'da bir pencere başka bir pencere veya IDE alanına bağlı olduğunda başvuruyor. Örneğin, Özellikler penceresini - diğer bir deyişle, eklenmemiş ve Visual Studio içinde-serbest kaydırılan veya takılmamış karşı yerleşik **Çözüm Gezgini**.  

7.  TableLayoutPanel ayarladıktan sonra **yerleştirme** özelliğine **doldurun**, formun tamamı paneli doldurur. Formu yeniden boyutlandırmak yeniden TableLayoutPanel yerleşik kalır ve kendisini uyacak şekilde yeniden boyutlandırır.  

    > [!NOTE]
    >  Microsoft Office Word tablosunda gibi bir TableLayoutPanel çalışır: satırları ve sütunları olan ve tek bir hücre birden çok satır ve sütunları yayılabilir. Her bir hücre (düğme, onay kutusu veya bir etiket gibi) bir denetim basılı tutabilirsiniz. TableLayoutPanel olacaktır bir `PictureBox` , tüm üst satırda kapsayıcı denetimi bir `CheckBox` sol alt hücresini ve dört denetimi `Button` sağ alt hücresini denetimlerinde.  

8.  Şu anda, TableLayoutPanel iki eşit büyüklükteki satır ve iki eşit büyüklükteki sütun yok. Üst satırda ve sağ sütun hem; bu nedenle bunları yeniden boyutlandırmak çok büyük gerekir. Windows Forms Tasarımcısı'nda TableLayoutPanel seçin. Sağ üst köşesinde şu şekilde görünen bir küçük siyah üçgen düğme vardır.  

     ![Üçgen düğme](../ide/media/express_iconblacktriangle.gif "Express_IconBlackTriangle")  
Üçgen düğmesi  

     Bu düğme denetimi yardımcı görevleri sahip olduğunu gösterir özelliklerini otomatik olarak ayarlayın.  

9. Aşağıdaki resimde gösterildiği gibi üçgen denetimin görev listesini görüntülemek için seçin.  

     ![TableLayoutPanel görevleri](../ide/media/express_tablepanel.png "Express_TablePanel")  
TableLayoutPanel görevleri  

10. Seçin **Düzenle satırları ve sütunları** görüntülemek için görev **sütun ve satır stilleri** penceresi. Seçin **Column1**ve boyutuna yüzde 15 emin olarak ayarlanıyor **yüzde** düğmesi seçilen ve girme `15` içinde **yüzde** kutusu. (Bu bir `NumericUpDown` bir sonraki öğreticide kullanacaksınız denetimi.) Seçin **Column2** ve yüzde 85'e ayarlayın. Seçmeyin **Tamam** pencere kapanacaktır çünkü henüz düğmesine tıklayın. (Ancak bunu yaparsanız, bu görev listesini kullanarak yeniden açabilirsiniz.)  

     ![TableLayoutPanel sütun ve satır stilleri](../ide/media/vs_tablelayoutpanel_setup.png "VS_TableLayoutPanel_Setup")  
TableLayoutPanel sütun ve satır stilleri  

11. Gelen **Göster** aşağı açılan liste penceresinin en üstünde seçin **satırları**. Ayarlama **Row1** yüzde 90'e ve **satırı 2** yüzde 10 için.  

12. Seçin **Tamam** düğmesi. TableLayoutPanel şimdi büyük üst satır, bir küçük alt satır, küçük bir sol sütunda ve büyük sağ sütun olmalıdır. TableLayoutPanel sütunları ve satırları tableLayoutPanel1 biçiminde seçme ve satır ve sütun kenarlıkları sürükleyerek yeniden boyutlandırabilirsiniz.  

     ![Yeniden boyutlandırılan TableLayoutPanel ile Form1](../ide/media/vs_formafterlayoutpanel.png "VS_FormAfterLayoutPanel")  
Yeniden boyutlandırılan TableLayoutPanel ile Form1  

### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  

-   Öğretici bir sonraki adıma dönmek için bkz: [5. adım: bilgisayarınızı Form denetimlerine ekleme](../ide/step-5-add-controls-to-your-form.md).  

-   Eğitmen önceki adıma dönmek için bkz: [3. adım: bilgisayarınızı Form özelliklerini ayarla](../ide/step-3-set-your-form-properties.md).
