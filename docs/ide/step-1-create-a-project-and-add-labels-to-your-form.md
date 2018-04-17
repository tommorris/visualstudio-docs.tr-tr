---
title: '1. adım: Proje oluşturma ve formunuza etiketler ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-acquisition
ms.topic: conceptual
ms.assetid: f44e50be-a5f5-4d77-9cff-dd52374c3f74
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 992541fe80067a6255ae0909edba0bf8f239c004
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="step-1-create-a-project-and-add-labels-to-your-form"></a>1. Adım: Proje Oluşturma ve Formunuza Etiketler Ekleme
Bu test geliştirme ilk adımlar, olarak projesi oluşturun ve etiketler, bir düğmeyi ve diğer denetimlerin bir forma ekleyin. Ayrıca, eklediğiniz her denetim için özellikler de ayarlayın. Proje formu denetimlerini içerir ve (sonraki öğreticide) kodu. Test sorunları etiketlerini göster düğmesini test başlatır ve diğer denetimlerin test yanıtlar ve test tamamlamak için kalan süreyi gösterir.  
  
> [!NOTE]
>  Bu konuda bir öğretici serisi kodlama temel kavramları hakkında bir parçasıdır. Öğretici genel bakış için bkz: [Eğitmen 2: bir zaman aşımına matematik test oluşturma](../ide/tutorial-2-create-a-timed-math-quiz.md).  
  
### <a name="to-create-a-project-and-and-set-properties-for-a-form"></a>Bir proje oluşturmak için ve ve bir form özelliklerini ayarlama  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  İçinde **yüklü şablonlar** listesinde, ya da seçin **C#** veya **Visual Basic**.  
  
3.  Şablonları listesinden seçip **Windows Forms uygulaması** şablon adlandırın **matematik test**ve ardından **Tamam** düğmesi.  
  
     Adlı bir form **Form1.cs** veya **Form1.vb** , seçtiğiniz programlama dili bağlı olarak görünür.  
  
4.  Form seçin ve sonra değiştirmek kendi **metin** özelliğine **matematik test**.  
  
     **Özellikleri** penceresi formun özelliklerini içerir.  
  
5.  Formun boyutunu 500 piksel genişliğinde 400 piksel uzunluğunda değiştirin.  
  
     Tümleşik geliştirme ortamı (IDE) sol alt köşesindeki doğru boyutta görünene kadar kendi kenarları sürükleyerek formu yeniden boyutlandırabilirsiniz. Alternatif olarak, değerlerini değiştirebilirsiniz **boyutu** özelliği.  
  
6.  Değerini değiştirme **FormBorderStyle** özelliğine **Fixed3D**ve **MaximizeBox** özelliğine **False**.  
  
     Bu değerler, formu yeniden boyutlandırma test tutmayı engeller.  
  
### <a name="to-create-the-time-remaining-box"></a>Zaman kalan kutusu oluşturmak için  
  
1.  Ekleme bir **etiket** Denetim Araç Kutusu'ndan ve değerini ayarlama kendi **(ad)** özelliğine `timeLabel`.  
  
     Bu etiket test kalan saniye sayısını gösterir sağ üst köşesinde kutusunda olur.  
  
2.  Değişiklik **AutoSize** özelliğine **False** böylece kutusunu yeniden boyutlandırabilirsiniz.  
  
3.  Değişiklik **kenarlık stili** özelliğine **FixedSingle** kutunun etrafında bir çizgi çizmek için.  
  
4.  Ayarlama **boyutu** özelliğine **200, 30**.  
  
5.  Etiket mavi ayırıcı satırları nerede görüneceğini formun sağ üst köşesinde taşıyın.  
  
     Bu satırlar form üzerinde denetimleri hizalama yardımcı olur.  
  
6.  İçinde **özellikleri** penceresinde, seçin **metin** özelliği ve değerini temizlemek için Geri tuşu'i seçin.  
  
7.  Artı işareti (+) seçin **yazı tipi** özelliği ve değerini değiştirme **boyutu** özelliğine **15.75**.  
  
     Aşağıdaki resimde gösterildiği gibi birkaç yazı tipi özelliklerini değiştirebilirsiniz.  
  
     ![Yazı tipi boyutunu gösteren Özellikler penceresi](../ide/media/express_setfontsize.png "Express_setFontSize")  
Yazı tipi boyutunu gösteren Özellikler penceresi  
  
8.  Başka bir tane eklemek **etiket** Denetim Araç Kutusu'ndan ve yazı tipi boyutunu ayarlamak **15.75**.  
  
9. Ayarlama **metin** özelliğine **zaman sol**.  
  
10. Böylece yalnızca solunda hizalanacak etiketi taşımak **timeLabel** etiketi.  
  
### <a name="to-add-controls-for-the-addition-problems"></a>Denetimler ek sorunlar için eklemek için  
  
1.  Ekleme bir **etiket** Denetim Araç Kutusu'ndan ve ardından kendi **metin** özelliğine **?** (soru işareti).  
  
2.  Ayarlama **AutoSize** özelliğine **False**.  
  
3.  Ayarlama **boyutu** özelliğine **60, 50**.  
  
4.  Yazı tipi boyutunu ayarlamak **18**.  
  
5.  Ayarlama **TextAlign** özelliğine **MiddleCenter**.  
  
6.  Ayarlama **konumu** özelliğine **50, 75** formdaki denetim konumlandırmak için.  
  
7.  Ayarlama **(ad)** özelliğine **plusLeftLabel**.  
  
8.  Seçin **plusLeftLabel** etiket ve Ctrl + C tuşlarını seçin veya **kopya** üzerinde **Düzenle** menüsü.  
  
9. Ctrl + V tuşlarını seçerek üç kez etiketi Yapıştır veya **Yapıştır** üzerinde **Düzenle** menüsü.  
  
10. Böylece bir satır kutusunun sağ tarafında bulunan üç yeni etiket düzenleme **plusLeftLabel** etiketi.  
  
     Boşluk ve bunları satır ayırıcı satırları kullanabilirsiniz.  
  
11. İkinci etiketin değerini **metin** özelliğine **+** (artı işareti).  
  
12. Üçüncü etiketin değerini **(ad)** özelliğine **plusRightLabel**.  
  
13. Dördüncü etiketin değerini **metin** özelliğine **=** (eşittir işareti).  
  
14. Ekleme bir **NumericUpDown** Denetim Araç Kutusu'ndan, yazı tipi boyutunu ayarlamak **18**ve genişliğini ayarlamak **100**.  
  
     Bu tür daha sonra denetimi hakkında daha fazla bilgi edineceksiniz.  
  
15. Satır yukarı **NumericUpDown** Denetim toplama problemi etiket denetimleri ile.  
  
16. Değerini değiştirme **(ad)** özelliği için **NumericUpDown** denetimini **toplam**.  
  
     Aşağıdaki resimde gösterildiği gibi ilk satırı oluşturduğunuzu düşünün.  
  
     ![Matematik testi ilk satırının](../ide/media/express_firstrow.png "Express_firstRow")  
Matematik testi ilk satırının  
  
### <a name="to-add-controls-for-the-subtraction-multiplication-and-division-problems"></a>Çıkarma, çarpma ve bölme sorunları için denetimleri eklemek için  
  
1.  Toplama problemi (dört etiket denetimleri ve NumericUpDown denetimi) için tüm beş denetimleri kopyalayın ve ardından bunları yapıştırın.  
  
     Form hala seçili beş yeni denetimler içerir.  
  
2.  Ek denetimleri hizaya gelecek şekilde tüm denetimler yerine taşıyın.  
  
     Ayırıcı satırları iki satır arasındaki yeterli uzaklığı vermek için kullanabilirsiniz.  
  
3.  Değerini değiştirme **metin** ikinci label özelliği **-** (eksi).  
  
4.  İlk soru işareti etiketi adı **minusLeftLabel**.  
  
5.  Ad ikinci soru işareti etiketi **minusRightLabel**.  
  
6.  Ad **NumericUpDown** denetim **fark**.  
  
7.  Beş denetimleri iki kez daha yapıştırın.  
  
8.  Üçüncü satır için ilk etiket adı **timesLeftLabel**, İkinci etiketin değiştirme **metin** özelliğine **×** (çarpma oturum) ad üçüncü label **timesRightLabel**ve NumericUpDown denetimi adı **ürün**.  
  
9. Dördüncü satır için ilk etiket adı **dividedLeftLabel**, İkinci etiketin değiştirme **metin** özelliğine **÷** (bölme işareti) üçüncü etiket adı  **dividedRightLabel**ve NumericUpDown denetimi adı **sayının**.  
  
    > [!NOTE]
    >  Bu öğretici çarpma oturum × ve bölme oturum ÷ kopyalayın ve forma yapıştırın.  
  
### <a name="to-add-a-start-button-and-set-the-tab-index-order"></a>Başlat düğmesi ekleme ve sekme dizin sırasını ayarlamak için  
  
1.  Ekleme bir **düğmesini** Denetim Araç Kutusu'ndan ve ardından kendi **(ad)** özelliğine **startButton**.  
  
2.  Ayarlama **metin** özelliğine **test Başlat**.  
  
3.  Yazı tipi boyutunu ayarlamak **14**.  
  
4.  Ayarlama **AutoSize** özelliğine **doğru**, metnin sığması için otomatik olarak yeniden boyutlandırmak için düğmesini neden olur.  
  
5.  Orta düğme formun alt kısmındaki yakın.  
  
6.  Değerini **TabIndex** özelliği için **startButton** denetimini **1**.  
  
    > [!NOTE]
    >  **TabIndex** özelliği test alanın SEKME tuşuna seçtiğinde denetimlerini sırasını ayarlar. Nasıl çalıştığını görmek için herhangi bir iletişim kutusunu açın (örneğin, menü çubuğunda, tercih **dosya**, **açmak**) ve ardından SEKME tuşuna birkaç kez seçin. Nasıl imlecinizi denetimi denetimi her zaman için SEKME tuşunu seçin taşınır izleyin. Bu form oluştururken Programcı sırasını karar.  
  
7.  Değerini **TabIndex** özelliği NumericUpDown toplam denetimi için **2**, fark denetimi için **3**, ürün denetimi için **4**ve sayının denetimi için **5**.  
  
     Form aşağıdaki gibi görünmelidir.  
  
     ![İlk matematik testi form](../ide/media/express_formlaidout.png "Express_FormLaidOut")  
İlk matematik testi formu  
  
8.  Doğrulamak için olup olmadığını **TabIndex** özelliği çalışır beklediğiniz, kaydetme ve F5 tuşuna seçerek veya seçerek programınızı çalıştırma gibi **hata ayıklama**, **hata ayıklamayı Başlat** menü çubuğunda, ve ardından SEKME tuşuna birkaç kez seçin.  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [2. adım: rasgele bir toplama problemi oluşturma](../ide/step-2-create-a-random-addition-problem.md).  
  
-   Genel Bakış konuya geri dönmek için bkz: [Eğitmen 2: bir zaman aşımına matematik test oluşturma](../ide/tutorial-2-create-a-timed-math-quiz.md).