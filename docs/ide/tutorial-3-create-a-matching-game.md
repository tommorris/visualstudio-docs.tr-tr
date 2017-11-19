---
title: "Öğretici 3: eşleşen bir oyun oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 525815c8-2845-45e8-be96-100d1f144725
caps.latest.revision: "13"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: e4e09e0957ab9aa412d8bd8fc1ea2494c9fb5553
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
|[1. adım: Proje oluşturma ve formunuza tablo ekleme](../ide/step-1-create-a-project-and-add-a-table-to-your-form.md)|Proje oluşturma ve ekleme başlamak bir `TableLayoutPanel` denetimleri tutmak üzere Denetim hizalı düzgün.|  
|[2. adım: rasgele nesne ve simge listesi ekleme](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)|Ekleme bir `Random` nesne ve `List` simgeleri listesini oluşturmak için nesne.|  
|[3. adım: her etikete rasgele simge atama](../ide/step-3-assign-a-random-icon-to-each-label.md)|Simgeler rastgele çok Ata `Label` denetimleri her oyun farklı olmasını sağlayın.|  
|[4. adım: her etikete Click olay işleyicisi ekleme](../ide/step-4-add-a-click-event-handler-to-each-label.md)|Tıklanan etiketin rengini değiştiren bir Click olayı işleyicisi ekleyin.|  
|[5. adım: Etiket başvuruları ekleme](../ide/step-5-add-label-references.md)|Hangi etiketlere tıklandığını takip etmek için başvuru değişkenleri ekleyin.|  
|[6. adım: Zamanlayıcı ekleme](../ide/step-6-add-a-timer.md)|Oyunda geçen süreyi takip etmek için forma bir zamanlayıcı ekleyin.|  
|[7. adım: Çiftleri görünür kılma](../ide/step-7-keep-pairs-visible.md)|Eşleşen bir çift seçilirse, simge çiftlerini görünür durumda tutun.|  
|[8. adım: oyuncunun kazandığını doğrulamak için yöntem ekleme](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md)|Ekleme bir `CheckForWinner()` oyuncunun kazandığını doğrulamak için yöntem.|  
|[9. adım: Diğer özellikleri deneme](../ide/step-9-try-other-features.md)|Simgeleri ve renkleri değiştirme, kılavuz ekleme ve ses ekleme gibi diğer özellikleri deneyin. Tahtayı büyütmeyi ve zamanlayıcıyı ayarlamayı deneyin.|