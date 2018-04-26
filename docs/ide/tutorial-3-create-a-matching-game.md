---
title: 'Öğretici 3: eşleşen bir oyun oluşturma'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 525815c8-2845-45e8-be96-100d1f144725
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd560c6a3675617741f35f40d1fe23a70b482349
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="tutorial-3-create-a-matching-game"></a>Öğretici 3: eşleşen bir oyun oluşturma
Bu öğreticide, oyuncunun gizli simge çiftlerini eşleştirmesi gereken bir eşleştirme oyunu oluşturuyorsunuz. Aşağıdakilerin nasıl yapıldığını öğreneceksiniz:  

-   Deposunda simgeler gibi nesneleri bir `List` nesnesi.  

-   Kullanım bir `foreach` döngü Visual C# veya `For Each` listesini öğelerinde yinelemek için Visual Basic'te döngü.  

-   Başvuru değişkenlerini kullanarak bir formun durumunu takip edin.  

-   Birden fazla nesneyle kullanabileceğiniz olaylara yanıt vermek için bir olay işleyicisi oluşturun.  

-   Geriye doğru sayan ve başlatılmasının ardından bir olayı kesin olarak tetikleyen bir zamanlayıcı hazırlayın.  

 Bu öğreticiyi bitirdiğinizde, programınız aşağıdaki resim gibi görünecektir.  

 ![Bu öğreticide oluşturduğunuz oyun](../ide/media/express_finishedgame.png "Express_FinishedGame")  
Bu öğreticide oluşturduğunuz oyun  

 Tamamlanmış bir örnek sürümünü indirmek için bkz: [tam eşleşen oyun öğretici örnek](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).  

> [!NOTE]
>  Bu öğreticide, hem Visual C# hem de Visual Basic ele alınmaktadır; bu nedenle kullandığınız programlama diline özgü bilgilere odaklanın.  

 Bir yerde tıkanıp kalırsanız veya programlamayla ilgili sorularınız olursa, MSDN forumlarından birinde sorunuzu göndermeyi deneyin. Bkz: [Visual Basic Forumu](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) ve [Visual C# Forumu](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral). Ayrıca, yararlanabileceğiniz harika ve ücretsiz video öğrenme kaynakları vardır. Visual Basic'te programlama hakkında daha fazla bilgi için bkz: [Visual Basic temelleri: yeni başlayanlar için geliştirme](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Visual C# programlama hakkında daha fazla bilgi için bkz: [C# temelleri: yeni başlayanlar için geliştirme](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).  

## <a name="related-topics"></a>İlgili Konular  

|Başlık|Açıklama|  
|-----------|-----------------|  
|[1. Adım: Proje Oluşturma ve Formunuza Tablo Ekleme](../ide/step-1-create-a-project-and-add-a-table-to-your-form.md)|Proje oluşturma ve ekleme başlamak bir `TableLayoutPanel` denetimleri tutmak üzere Denetim hizalı düzgün.|  
|[2. Adım: Rasgele Nesne ve Simge Listesi Ekleme](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)|Ekleme bir `Random` nesne ve `List` simgeleri listesini oluşturmak için nesne.|  
|[3. Adım: Her Etikete Rasgele Simge Atama](../ide/step-3-assign-a-random-icon-to-each-label.md)|Simgeler rastgele çok Ata `Label` denetimleri her oyun farklı olmasını sağlayın.|  
|[4. Adım: Her Etikete Click Olay İşleyicisi Ekleme](../ide/step-4-add-a-click-event-handler-to-each-label.md)|Tıklanan etiketin rengini değiştiren bir Click olayı işleyicisi ekleyin.|  
|[5. Adım: Etiket Başvuruları Ekleme](../ide/step-5-add-label-references.md)|Hangi etiketlere tıklandığını takip etmek için başvuru değişkenleri ekleyin.|  
|[6. Adım: Zamanlayıcı Ekleme](../ide/step-6-add-a-timer.md)|Oyunda geçen süreyi takip etmek için forma bir zamanlayıcı ekleyin.|  
|[7. Adım: Çiftleri Görünür Kılma](../ide/step-7-keep-pairs-visible.md)|Eşleşen bir çift seçilirse, simge çiftlerini görünür durumda tutun.|  
|[8. Adım: Oyuncunun Kazandığını Doğrulamak için Yöntem Ekleme](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md)|Ekleme bir `CheckForWinner()` oyuncunun kazandığını doğrulamak için yöntem.|  
|[9. Adım: Diğer Özellikleri Deneme](../ide/step-9-try-other-features.md)|Simgeleri ve renkleri değiştirme, kılavuz ekleme ve ses ekleme gibi diğer özellikleri deneyin. Tahtayı büyütmeyi ve zamanlayıcıyı ayarlamayı deneyin.|
