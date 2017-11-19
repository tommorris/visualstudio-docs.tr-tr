---
title: "6. adım: Zamanlayıcı ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09e7930b-cab6-4a22-9a6f-72e23f489585
caps.latest.revision: "21"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: d4a31cd461f470c7b510be02c33dd1744f7ed616
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="step-6-add-a-timer"></a>6. Adım: Zamanlayıcı Ekleme
Ardından, eklediğiniz bir **Zamanlayıcı** eşleşen oyun denetimine. Süreölçer belirtilen bir milisaniye sayısını bekler ve ardından olarak adlandırılan bir olay tetikler. bir *onay*. Bu olay, bir eylemi başlatmak veya eylemi düzenli aralıklarla yinelemek için kullanışlıdır. Bu durumda, oyuncuların iki simge seçmesini sağlamak ve simgeler eşleşmez ise, kısa bir süre sonra bu iki simgeyi yeniden gizlemek için bir zamanlayıcı kullanacaksınız.  
  
### <a name="to-add-a-timer"></a>Zamanlayıcı eklemek için  
  
1.  Araç Kutusu'ndan Windows Formları tasarımcısında seçin **Zamanlayıcı** (içinde **bileşenleri** kategori) ve ENTER tuşuna seçin veya Zamanlayıcı forma bir zamanlayıcı denetim eklemek için çift tıklayın. Adlı Zamanlayıcı'nın simgesi **Süreölçer1**, formun altındaki bir alanında aşağıdaki resimde gösterildiği gibi görünmesi gerekir.  
  
     ![Zamanlayıcı](../ide/media/express_timer.png "Express_Timer")  
Zamanlayıcı  
  
    > [!NOTE]
    >  Araç kutusu boş ise, araç kutusunu açmadan önce formun arkasındaki kodu değil de, form tasarımcısını seçtiğinizden emin olun.  
  
2.  Seçin **Süreölçer1** Zamanlayıcı seçmek için simge. İçinde **özellikleri** penceresinde, özelliklerini görüntüleyerek olayları görüntülemesine anahtar. Sonra Zamanlayıcı 's ayarlayın **aralığı** özelliğine **750**, ancak bırakın kendi **etkin** özelliğini **False**. **Aralığı** özelliği bildirir arasında beklenecek süreyi Zamanlayıcı *çizgilerine*, veya kendi onay olay zaman tetikler. 750 değeri zamanlayıcıya, Tick olayını tetiklemeden önce saniyenin dörtte üçü kadar (750 milisaniye) beklemesini bildirir. Çağrı `Start()` yalnızca player ikinci etiketi seçtikten sonra süreölçeri başlatmak için yöntem.  
  
3.  Zamanlayıcı seçin kontrol Windows Form Tasarımcısı'ndaki simgesini ve ENTER tuşuna seçin veya boş bir eklemek için Zamanlayıcı, çift **onay** olay işleyicisi. Kodu aşağıdaki kodla değiştirin ya da aşağıdaki kodu olay işleyicisine el ile girin.  
  
     [!code-csharp[VbExpressTutorial4Step6#7](../ide/codesnippet/CSharp/step-6-add-a-timer_1.cs)]
     [!code-vb[VbExpressTutorial4Step6#7](../ide/codesnippet/VisualBasic/step-6-add-a-timer_1.vb)]  
  
     Değer çizgilerinin olay işleyicisi üç şey yapar: ilk olarak, Zamanlayıcı çağırarak çalışmadığından emin olur `Stop()` yöntemi. İki başvuru değişkenleri kullanıyorsa `firstClicked` ve `secondClicked`, player seçtiğiniz iki etiket simgeleri yeniden görünmez yapmak için. Son olarak, sıfırlar `firstClicked` ve `secondClicked` başvuru değişkenleri `null` Visual C# ve `Nothing` Visual Basic'te. Programın kendini sıfırlama şekli olması nedeniyle bu adım önemlidir. Bunu herhangi izleyen artık değil `Label` denetimleri ve onu bir etiket seçmek yeniden player için hazır.  
  
    > [!NOTE]
    >  A `Timer` nesnesi bir `Start()` süreölçer başlatır yöntemi ve `Stop()` durdurduğu yöntemi. Zamanlayıcı 's ayarlandığında **etkin** özelliğine **True** içinde **özellikleri** penceresinde başlar program başlar başlamaz ticking. Ancak çıktığınızda, kümesine **False**, şekilde ilerleyen kadar başlamıyor kendi `Start()` yöntemi çağrılır. Normalde, bir süreölçer onay olay tekrar tekrar, kullanarak harekete **aralığı** çizgilerine arasında beklenecek kaç milisaniye belirlemek için özellik. Fark etmiş olabilirsiniz nasıl Zamanlayıcı 's `Stop()` yöntemi onay olayı içinde çağrılır. Zamanlayıcı içine yerleştirir *bir çekim modu*, olduğunda anlamına `Start()` yöntemi çağrıldığında, belirtilen aralık için bekler, tek bir değer çizgisi olay tetikler ve durur.  
  
4.  Eylem yeni süreölçeri görmek için Kod Düzenleyici'ye gidin ve üst ve alt aşağıdaki kodu ekleyin `label_Click()` olay işleyicisi yöntemi. (Eklediğiniz bir `if` deyimi üstüne ve altına; üç deyimleri yöntem kalan aynı kalır.)  
  
     [!code-csharp[VbExpressTutorial4Step6#8](../ide/codesnippet/CSharp/step-6-add-a-timer_2.cs)]
     [!code-vb[VbExpressTutorial4Step6#8](../ide/codesnippet/VisualBasic/step-6-add-a-timer_2.vb)]  
  
     Kod yöntemi üstündeki Zamanlayıcı değerini denetleyerek başlatıldığından olup olmadığını denetler **etkin** özelliği. İlk player seçerse, böylece ve ikinci `Label` denetimleri ve üçüncü bir etiket seçme süreölçer başlatır olmaz yapmak herhangi bir şey.  
  
     Kod yöntemi kümelerinin altındaki `secondClicked` ikinci izlemek için başvuru değişkenini `Label` player seçin ve ardından bu etiketin simgenin rengi siyah görünür hale getirmek için ayarlar denetimi. Daha sonra, 750 milisaniye bekler ve tek bir Tick olayı tetiklemesi için zamanlayıcıyı tek sefer modunda başlatır. Zamanlayıcı'nın onay olay işleyicisi iki simgeleri gizler ve sıfırlar `firstClicked` ve `secondClicked` formun player simgeleri başka bir çift seçmek hazır olması için değişkenleri başvuru.  
  
5.  Programınızı kaydedin ve çalıştırın. Bir simge seçin; bu simge görünür duruma gelir.  
  
6.  Başka bir simge seçin. Kısa bir süre görünür ve sonra iki simge birden kaybolur. Bunu birçok kez tekrar edin. Form artık, seçtiğiniz birinci ve ikinci simgeleri takip ediyor ve simgelerin kaybolmasını sağlamadan önce duraklamak için zamanlayıcıyı kullanıyor.  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [adım 7: çiftleri görünür](../ide/step-7-keep-pairs-visible.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [5. adım: etiket başvuruları ekleme](../ide/step-5-add-label-references.md).