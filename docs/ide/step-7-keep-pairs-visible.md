---
title: '7. Adım: Çiftleri Görünür Kılma'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 42e1d08c-7b2e-4efd-9f47-85d6206afe35
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0373a4d51c6da6685d3fc837b569607daa059854
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="step-7-keep-pairs-visible"></a>7. Adım: Çiftleri Görünür Kılma
Oyuncu yalnızca eşleşmeyen simge çiftlerini seçtiği sürece oyun düzgün çalışır. Ancak oyuncu eşleşen bir çift seçtiğinde ne olması gerektiğini bir düşünün. Süreölçer kapatarak simgeleri yerine yapma kayboluyor (kullanarak `Start()` yöntemi), böylece, artık kullanarak etiketleri izleyen oyun kendisini sıfırlamalıdır `firstClicked` ve `secondClicked` başvuru değişkenleri sıfırlamadan Seçilen iki etiket renklerini.  

### <a name="to-keep-pairs-visible"></a>Çiftleri görünür durumda tutmak için  

1.  Aşağıdakileri ekleyin `if` ifadesine `label_Click()` yalnızca Zamanlayıcı başladığınız deyimi yukarıdaki kodu sona olay işleyicisi yöntemi. Kodu programa eklerken yakından inceleyin. Kodun nasıl çalıştığını bir düşünün.  

     [!code-csharp[VbExpressTutorial4Step7#9](../ide/codesnippet/CSharp/step-7-keep-pairs-visible_1.cs)]
     [!code-vb[VbExpressTutorial4Step7#9](../ide/codesnippet/VisualBasic/step-7-keep-pairs-visible_1.vb)]  

     İlk satırı `if` eklediğiniz deyimi player seçer ilk etiketi simgesinde İkinci etiketin simgesinde aynı olup denetler. Simgeler aynıysa, C# veya üç deyimleri içinde süslü ayraçlar arasında üç deyimleri programı yürütür `if` Visual Basic'de deyimini. İlk iki deyimleri sıfırlama `firstClicked` ve `secondClicked` böylece bunlar artık herhangi bir etiket izlemek değişkenleri başvuru. (Bu iki deyim, zamanlayıcının Tick olay işleyicisinden size tanıdık gelebilir.) Üçüncü deyimi bir `return` program yürütme olmadan yöntemi deyimlerinde kalanını atlayın söyler deyimi.  

     Visual C# ile programlama, bazı kodları kullandığını tek bir eşittir işareti fark etmiş (`=`), diğer deyimler iki eşittir işareti kullanırken (`==`). Neden göz önünde bulundurun `=` bazı yerlerde kullanılır ancak `==` farklı konumlarda kullanılır.  

     Bu örnek, aradaki farkı gösteren güzel bir örnektir. Parantez içine arasında yer alan kodunu dikkatli bir göz atalım `if` deyimi.  

    ```vb  
    firstClicked.Text = secondClicked.Text  
    ```  

    ```csharp  
    firstClicked.Text == secondClicked.Text  
    ```  

     İlk ifade sonra kod bloğunu, en yakın Ara `if` deyimi.  

    ```vb  
    firstClicked = Nothing  
    ```  

    ```csharp  
    firstClicked = null;  
    ```  

     Bu deyimlerden birincisi iki simgenin aynı olup olmadığını denetler. Visual C# programı kullanır, iki değer karşılaştırıldığında çünkü `==` eşitlik işleci. İkinci ifade gerçekten değeri değişir (adlı *atama*), ayar `firstClicked` başvuru değişkeni eşit `null` sıfırlama. İşte bu nedenle kullandığı `=` atama işleci yerine. Visual C# kullanan `=` değerlerini ayarlamak için ve `==` bunları karşılaştırmak için. Visual Basic kullanan `=` değişkeni ataması ve karşılaştırma için.  

2.  Programı kaydedip çalıştırın ve sonra formdaki simgeleri seçmeye başlayın. Eşleşmeyen bir çift seçerseniz, zamanlayıcının Tick olayı tetiklenir ve iki simge de kaybolur. Eşleşen bir çift seçerseniz yeni `if` deyimini yürütür ve return deyiminin simgeler aşağıdaki resimde gösterildiği gibi görünür, kalır, böylece süreölçer başlatır kod atlamak yönteminin neden olur.  

     ![Bu öğreticide oluşturduğunuz oyun](../ide/media/express_finishedgame.png "Express_FinishedGame")  
Eşleştirme oyunu ve görünür simge çiftleri  

### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  

-   Öğretici bir sonraki adıma dönmek için bkz: [adım 8: doğrulayın olup olmadığını Player Won için bir yöntem ekleyin](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).  

-   Eğitmen önceki adıma dönmek için bkz: [6. adım: Zamanlayıcı ekleme](../ide/step-6-add-a-timer.md).
