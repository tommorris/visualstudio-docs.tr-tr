---
title: 'Eğitmen 3: eşleşen bir oluşturma oyun'
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
ms.openlocfilehash: f64de3b95d21fdae87dd6b14754956381d60e9a3
ms.sourcegitcommit: 96a6d1f16d06ca28d309d05b6e9fbd52f628cdbc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40008248"
---
# <a name="tutorial-3-create-a-matching-game"></a>Eğitmen 3: eşleşen bir oluşturma oyun

Bu öğreticide, oyuncunun gizli simge çiftlerini eşleştirmesi gereken bir eşleştirme oyunu oluşturuyorsunuz. Aşağıdakilerin nasıl yapıldığını öğreneceksiniz:

-   Store simgeler gibi nesneleri bir <xref:System.Collections.Generic.List%601> nesne.

-   Kullanım bir `foreach` döngü Visual C# veya `For Each` bir listedeki öğeler arasında yineleme yapmak için Visual Basic'te döngü.

-   Başvuru değişkenlerini kullanarak bir formun durumunu takip edin.

-   Birden fazla nesneyle kullanabileceğiniz olaylara yanıt vermek için bir olay işleyicisi oluşturun.

-   Geriye doğru sayan ve başlatılmasının ardından bir olayı kesin olarak tetikleyen bir zamanlayıcı hazırlayın.

Bu öğreticiyi tamamladığınızda, programınız aşağıdaki resim gibi görünecektir:

![Bu öğreticide oluşturduğunuz oyun](../ide/media/express_finishedgame.png)

## <a name="tutorial-links"></a>Öğretici bağlantıları

Örnek tamamlanmış bir sürümünü indirmek için bkz [eksiksiz eşleştirme oyunu Öğreticisi örneği](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).

> [!NOTE]
> Bu öğreticide, hem Visual C# hem de Visual Basic ele alınmaktadır; bu nedenle kullandığınız programlama diline özgü bilgilere odaklanın.

Bir yerde tıkanıp kalırsanız veya programlamayla ilgili sorularınız olursa, MSDN forumlarından birinde sorunuzu göndermeyi deneyin. Bkz: [Visual Basic Forumu](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) ve [Visual C# Forumu](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral). Ayrıca, yararlanabileceğiniz harika ve ücretsiz video öğrenme kaynakları vardır. Visual Basic'te programlama hakkında daha fazla bilgi için bkz. [Visual Basic fundamentals: Development yeni başlayanlar için](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Visual C# programlama hakkında daha fazla bilgi için bkz [C# fundamentals: Development yeni başlayanlar için](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[1. adım: Proje oluşturma ve formunuza tablo ekleme](../ide/step-1-create-a-project-and-add-a-table-to-your-form.md)|Proje oluşturma ve ekleyerek başlayın bir `TableLayoutPanel` düzgün hizalanmasını denetimleri korumak için denetimi.|
|[2. adım: rasgele nesne ve simge listesi ekleme](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)|Ekleme bir `Random` nesnesi ve bir `List` simge listesini oluşturmak için nesne.|
|[3. adım: her etikete rasgele simge atama](../ide/step-3-assign-a-random-icon-to-each-label.md)|Rasgele simgeleri atayın `Label` her oyunun farklı olması denetler.|
|[4. adım: her etikete click olay işleyicisi ekleme](../ide/step-4-add-a-click-event-handler-to-each-label.md)|Ekleme bir `Click` tıklanan etiketin rengini değiştiren olay işleyicisi.|
|[5. adım: etiket başvuruları ekleme](../ide/step-5-add-label-references.md)|Hangi etiketlere tıklandığını takip etmek için başvuru değişkenleri ekleyin.|
|[6. adım: Zamanlayıcı ekleme](../ide/step-6-add-a-timer.md)|Oyunda geçen süreyi takip etmek için forma bir zamanlayıcı ekleyin.|
|[7. adım: çiftleri görünür kılma](../ide/step-7-keep-pairs-visible.md)|Eşleşen bir çift seçilirse, simge çiftlerini görünür durumda tutun.|
|[8. adım: oyuncunun kazandığını doğrulamak için yöntem ekleme](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md)|Ekleme bir `CheckForWinner()` oyuncunun kazanıp kazanmadığını doğrulamak için yöntem.|
|[9. adım: diğer özellikleri deneme](../ide/step-9-try-other-features.md)|Simgeleri ve renkleri değiştirme, kılavuz ekleme ve ses ekleme gibi diğer özellikleri deneyin. Tahtayı büyütmeyi ve zamanlayıcıyı ayarlamayı deneyin.|
