---
title: '1. adım: Proje oluşturma ve formunuza tablo ekleme'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 1cac4ba4-f3cd-43bd-ad5d-50fc599234e8
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c9f8d42122f5efca57687677b5d10884ec08066
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="step-1-create-a-project-and-add-a-table-to-your-form"></a>1. adım: Proje oluşturma ve formunuza tablo ekleme
Eşleştirme oyunu hazırlarken ilk adım projeyi oluşturmak ve formunuza bir tablo eklemektir. Tablo, simgeleri 4x4'lük muntazam bir kılavuza hizalamaya yardımcı olur. Ayrıca, oyun tahtasının görünüşünü iyileştirmek için çeşitli özellikleri ayarlarsınız.  

## <a name="to-create-a-project-and-add-a-table-to-your-form"></a>Bir proje oluşturmak ve formunuza bir tablo eklemek için  
  
1.  Menü çubuğunda seçin **dosya** > **yeni** > **proje**.  
  
2.  Visual Studio Express kullanmıyorsanız, ilk bir programlama dili seçmeniz gerekir. Gelen **yüklü şablonlar** listesinde, ya da seçin **Visual C#** veya **Visual Basic**.  

3.  Proje şablonları listesinden seçip **Windows Forms uygulaması**, proje adı **MatchingGame**ve ardından **Tamam** düğmesi.  

4.  İçinde **özellikleri** penceresinde, aşağıdaki form özelliklerini ayarlayın.  

    1.  Formun değiştirme **metin** özelliğinden **Form1** için **eşleşen oyun**. Bu metin oyun penceresinin en üstünde görünür.  

    2.  Formun boyutunu 550 piksel genişliğe ve 550 piksel uzunluğa ayarlayın. Bunu aşağıdakilerden ayarlayarak yapabilirsiniz **boyutu** özelliğine **550, 550**, veya tümleşik geliştirme ortamı (sağ alt köşesindeki doğru boyutta görene kadar formun köşesindeki sürükleyerek IDE).  

5.  Araç kutusunu seçerek görüntülemek **araç** IDE sol tarafındaki sekmesinde.  

6.  Sürükleme bir <xref:System.Windows.Forms.TableLayoutPanel> gelen denetim **kapsayıcıları** araç, kategori ve bunun için aşağıdaki özellikleri ayarlayın.  

    1.  Ayarlama **BackColor** özelliğine **CornflowerBlue**. Bunu yapmak için açın **BackColor** yanında aşağı açılan okunu seçerek iletişim kutusu **BackColor** özelliğinde **özellikleri** penceresi.  Ardından, **Web** sekmesinde **BackColor** kullanılabilir renk adlarının bir listesini görüntülemek için iletişim kutusu.  

        > [!NOTE]
        >  Renkler alfabetik sırada değildir ve **CornflowerBlue** listenin altına değil.  
  
    2.  Ayarlama **yerleştirme** özelliğine **doldurun** özelliği yanında aşağı açılan düğmesini seçerek ve büyük Orta düğmesini seçerek. Böylece tablo formun tamamını kaplayacak şekilde yayılır.  

    3.  Ayarlama **CellBorderStyle** özelliğine **dışarı**. Böylece, tahta üzerindeki her bir hücre arasında görsel kenarlıklar olur.  

    4.  TableLayoutPanel denetiminin sağ üst köşesindeki üçgen düğmesini seçerek ilgili görev menüsünü görüntüleyin.  

    5.  Görev menüsünde seçin **Satır Ekle** iki kez iki daha fazla satır eklemek ve ardından **Sütun Ekle** iki kez iki daha fazla sütun eklemek için.  

    6.  Görev menüsünde seçin **Düzenle satırları ve sütunları** açmak için **sütun ve satır stilleri** penceresi. Her sütun seçme, seçin **yüzde** seçeneği düğmesine ve ardından her sütunun genişliği toplam genişliği % 25 oranında ayarlayın. Ardından **satırları** açılan gelen kutusu penceresinin en üstünde ve her satırın yüksekliği için yüzde 25'i ayarlayın. İşiniz bittiğinde seçin **Tamam** düğmesi.  

     TableLayoutPanel denetiminiz şu anda, eşit boyutlu on altı kare hücre içeren 4x4'lük bir kılavuz halinde olmalıdır. Bu satırlar ve sütunlar, sonradan simge resimlerinin görüneceği yerlerdir.  

7.  Form düzenleyicisinde TableLayoutPanel seçildiğinden emin olun. Bunu doğrulamak için görmelisiniz **tableLayoutPanel1** en üstündeki **özellikleri** penceresi. Seçilmezse, formdaki TableLayoutPanel seçin veya en üstündeki açılır denetimindeki seçin **özellikleri** penceresi.  
  
     TableLayoutPanel seçiliyken, araç kutusunu açın ve eklemek bir <xref:System.Windows.Forms.Label> denetimi (bulunan **ortak denetimler** kategori) TableLayoutPanel sol üst hücreye. Etiket denetimi IDE içinde artık seçili olmalıdır. Bu öğe için aşağıdaki özellikleri ayarlayın.  
  
    1.  Etiketin olduğundan emin olun **BackColor** özelliği ayarlanmış **CornflowerBlue**.  

    2.  Ayarlama **AutoSize** özelliğine **False**.  

    3.  Ayarlama **yerleştirme** özelliğine **doldurun**.  

    4.  Ayarlama **TextAlign** özelliğine **MiddleCenter** özelliği yanında aşağı açılan düğmesini seçerek ve ardından Orta düğmesini seçerek. Böylece, simgenin hücrenin ortasında görünmesi sağlanır.  
  
    5.  Seçin **yazı tipi** özelliği. Üç nokta (**...** ) düğmesini görünmelidir.  
  
    6.  Üç nokta düğmesini seçin ve ayarlayın **yazı tipi** değeri **Webdings**, **yazı tipi stilini** için **kalın**ve **boyutu** için **72**.  

    7.  Ayarlama **metin** harfine etiketin özelliğini **c**.  
  
         TableLayoutPanel öğesinin sol üst hücresinde şimdi, mavi arka plan üzerinde ortalanmış bir siyah kutu yer alıyor olmalıdır.  
  
        > [!NOTE]
        >  Webdings yazı tipi, simgelerden oluşan bir yazı tipi olup Windows işletim sistemiyle birlikte gelir. Eşleştirme oyununuzda oyuncunun simge çiftlerini eşleştirmesi gerektiğinden, eşleştirilecek simgeleri göstermek için bu yazı tipini kullanıyorsunuz. Koyma yerine **c** içinde **metin** özelliği, hangi simgeleri görüntülenir görmek için farklı harf girmeyi deneyin. Ünlem işareti bir örümcek, büyük N harfi bir göz ve virgül ise kırmızı biberdir.  
  
8.  Etiket denetimi seçin ve İleri TableLayoutPanel hücreye kopyalayın. (Seçin **Ctrl**+**C** anahtarları veya menü çubuğunda seçin **Düzenle** > **kopya**.) Sonra da yapıştırın. (Seçin **Ctrl**+**V** anahtarları veya menü çubuğunda seçin **Düzenle** > **Yapıştır**.) İlk etiketi bir kopyasını TableLayoutPanel ikinci hücrede görünür. Yeniden yapıştırın ve başka bir etiket üçüncü hücrede görünür. Hücrelerin tümünü doldurulur kadar etiket denetimleri yapıştırma tutun.  
  
    > [!NOTE]
    >  Çok fazla kez yapıştırırsanız, IDE yeni etiket denetimi eklemek için bir yer sahip olması için TableLayoutPanel yeni bir satır ekler. Bunu geri alabilirsiniz. Yeni hücreye kaldırmak için tercih **Ctrl**+**Z** anahtarları veya menü çubuğunda seçin **Düzenle** > **geri**.  
  
     Artık formunuz hazırdır. Aşağıdaki resimde olduğu gibi görünmesi gerekir.  

     ![İlk oyun form eşleşen](../ide/media/express_tut4step1.png "Express_Tut4Step1")  
İlk eşleştirme oyunu formu  

## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [2. adım: rasgele nesne ve simge listesi ekleme](../ide/step-2-add-a-random-object-and-a-list-of-icons.md).  
  
-   Genel Bakış konuya geri dönmek için bkz: [öğretici 3: eşleşen bir oluşturma oyun](../ide/tutorial-3-create-a-matching-game.md).
